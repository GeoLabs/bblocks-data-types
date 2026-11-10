# Work summary: bblocks-data-types

State as of 2026-11-10 (branch `planes/new-profiles`, from `planes/phase-2`, local commits only). Last verified build: 67/67
blocks passing, locally, in a scratch copy (not on CI: nothing is pushed).

## Purpose

An OGC Building Blocks register (identifier prefix `data-types.`) of the kinds of data that process
inputs and outputs carry. It is modelled on the
[Registered Item Model](https://ogcincubator.github.io/registered-item-model/) (RIM, ISO 19135:2026).

A data type names the **kind** of data, not its **encoding**. Encodings are the content plane of the
data axis and live in a separate register, `bblocks-data-formats` (namespace
`https://w3id.org/geolabs-ospd/data-formats/`, prefix `df:`, not resolved yet), which depends on this
one; this register never depends on it. Descriptions may show GeoJSON or JSON Schema as an
illustration only.

The vocabulary was first drafted inline in `bblocks-generic-profiles`; this register extracts it so it
can be reused and governed on its own. The Generic and Implementation Profiles of
`bblocks-generic-profiles` now use this register's IRIs as `dataType`; it imports this register.

## Content: 67 Building Blocks

| Group | Blocks |
|---|---|
| Geometry (17) | `geometry`, `point`, `curve`, `surface`, `line-string`, `line`, `linear-ring`, `polygon`, `triangle`, `polyhedral-surface`, `tin`, `geometry-collection`, `multi-point`, `multi-curve`, `multi-surface`, `multi-line-string`, `multi-polygon` |
| Features (2) and STAC (4) | `feature`, `feature-collection`, `stac-item`, `stac-collection`, `stac-catalog`, `stac-item-collection` |
| Literals (22) | `string`, 19 `string-*` formats from the EOAP schemas (withdrawn, unpublished), `number`, `boolean` |
| Parameters (9) | `coordinate-reference-system`, `expression`, `format-identifier`, `radiometric-index`, `band-identifier`, `grid-resolution`, `colour-map`, `time-interval`, `collection-identifier` |
| Raster (5) | `raster`, `raster-single-band`, `raster-multi-band`, `elevation-model`, `binary-mask` |
| Other (5) | `point-cloud`, `table`, `bounding-box`, `eo-product`, `rendered-image` |
| Support (3) | `vocabulary`, `register`, `item-class` |

## Model

**Concept plane.** Each data type is a `dt:DataType` (a sub-class of `rim:Concept`) in the
`dt:dataTypes` concept system, with a governed `dt:DataTypeVersion` (`/v1`) and a recorded
`rim:RegisterAction` of type addition, proposed by GeoLabs. Versions are `rim:invalid` (not in force)
and `rim:published`: a proposed addition awaiting a decision.

**Content plane.** Each data type also has a `dt:DataTypeItem` (a sub-class of `rim:RegisterItem`) of
the `dt:dataTypeItemClass` item class, in `dt:register`, that `rim:realizes` its version.
`dt:DataTypeItemShape` checks this and is the item class's `rim:validatedBy`. This item is kept: it
records the type in this register and says nothing about an encoding.

**Formats and representations** are items of `bblocks-data-formats`, not of this register:

| Class | Realizes | Example |
|---|---|---|
| `df:Format` | nothing | `df:format/geotiff`, `df:format/string-date-time` |
| `df:Representation` | one `dt:DataTypeVersion` of this register (`sh:maxCount 1`) | `df:representation/raster-geotiff` realizes `raster/v1` |

A version of this register may thus be realized by its own item and by representations. The
Registered Item Model limits `rim:realizes` per item, not per version; the text of ISO 19135:2026 was
not read on this point.

**Register specification.** `dt:specification` in `data.ttl` (`rim:hasSpecification`): a concept
register; GeoLabs is owner, manager and, for now, control body, with the intention to delegate that
role to the OGC or to an OSPD working group. It carries the validated definition of a substantive
change, the table of substantive and clarifying changes (verbatim in French, with an English
rendering), the version rule, the rule for proposals and `dt:amendmentAction`, the action type of an
in-place change to a proposal. No eligibility criteria and no commitments are set.

**Hierarchy.** It is expressed twice, and both must be kept in sync:

- `skos:broader` in the block's `ontology.ttl` (canonical);
- `isProfileOf` in `bblock.json`, which the register publishes as `prof:isProfileOf`.

A check that compares the two found 41 relations and no gap on 2026-11-09. 19 of them are
`string-*` -> `string`; the four parameter types have no broader type.

**Each type block contains:** `bblock.json`, `ontology.ttl` (concept, version, action and item),
`schema.yaml`, `examples.yaml` (JSON item and Turtle) and `description.md`.

## JSON binding of the RIM

The RIM core is RDF. Its JSON binding is a thin layer: one JSON Schema and JSON-LD context per class.
This register conforms to it, layer by layer, as the RIM's own `register-item` depends on `register`,
`register-item-class` and `concept-version`:

1. `data-types.register` profiles `ogc.rim.schemas.register`.
2. `data-types.item-class` profiles `ogc.rim.schemas.register-item-class`.
3. `data-types.vocabulary` depends on both. Its `schema.yaml` profiles `ogc.rim.schemas.register-item`
   (`type` is `DataTypeItem`; `itemClass` and `inRegister` are fixed) and its `realizes` profiles
   `ogc.rim.schemas.concept-version` (`type` is `DataTypeVersion`, with the recorded addition required).
4. Each data-type block depends on `vocabulary` and fixes the item's `id`.

`register` and `item-class` take `../vocabulary/data.ttl` as a data resource rather than depending
on `vocabulary`, which would make a cycle.

**SHACL closure.** The closure of a block is the data resources (`resources` with role `data`) of the
block and of its dependencies, plus their `shaclClosures`. A register publishes `resources` as
absolute URLs but `shaclClosures` as written, so relative closures cannot be loaded by an importing
register: until 2026-11-09 every block of `bblocks-generic-profiles` reported 53 "Error processing
closure source" warnings (52 data type ontologies and `data.ttl`). The register therefore declares no
`shaclClosures`: `vocabulary` lists `data.ttl` and every data type ontology as data resources, and
`register` and `item-class` list `data.ttl`. The same files were already loaded, as absolute URLs,
through those data resources: the closure was complete, and only the relative duplicates failed.
Measured: same closure sources per block in this register; in `bblocks-generic-profiles`, the 3,551
load errors are gone and the closure sources are the same.

## Geometry hierarchy

```
Geometry
├── Point
├── Curve
│   └── LineString
│       ├── Line
│       └── LinearRing
├── Surface
│   ├── Polygon
│   │   └── Triangle
│   └── PolyhedralSurface
│       └── TIN
└── GeometryCollection
    ├── MultiPoint
    ├── MultiCurve
    │   └── MultiLineString
    └── MultiSurface
        └── MultiPolygon
```

Sources: OGC 06-103r4 and 06-103r3 (Simple Feature Access, Part 1) and OGC 23-034 (CDB 2.0 Core, 7.6).
The definitions of `Line`, `LinearRing`, `Triangle`, `LineString`, `Polygon`, `PolyhedralSurface` and
`TIN` follow text from those documents. The `Multi*` placement follows 23-034 7.6.

## Design decisions

- **`ontology.ttl` plus a JSON schema.** The RIM core is RDF (OWL, SKOS, SHACL), and a sub-register
  profiles its JSON schemas. The data types are concepts in a hierarchy, which JSON Schema cannot
  express, so each block carries both.
- **JSON examples do not repeat nodes already in the RDF.** The SHACL closure is merged into the
  validated graph, so a second plain-string `dct:title` next to a language-tagged one would violate
  `maxCount 1`. The register, item class and item class title in `data.ttl` are the single source.
- **Definitions avoid naming a format.** Sources that are formats (the LAS standard for point clouds,
  JSON Schema formats for `string-*`) are cited as sources, not asserted as encodings. Two `string-*`
  definitions (`string-date`, `string-time`) still quote a syntax. These types are withdrawn and their
  definitions are kept as recorded; the audit invariant "no format in a concept definition" still
  reads them, and what to do about it is a decision for GeoLabs.
- **A new type is requested by a role.** The four parameter types each name the Generic Profile role
  that needs them.
- **Concept version, not concept, carries the status.** The embedded concept in JSON has `type: Concept`
  because the RIM schema fixes it; its `dt:DataType` class comes from the ontologies in the closure.

## Working on the register

```bash
./build.sh   # process and validate (requires Docker); output in build-local/
./view.sh    # preview in the bblocks viewer
```

To add a type, check first that an existing role needs it and that it is a kind of data, not an
encoding (an encoding is a `df:Format` of `bblocks-data-formats`). Then create a block under
`_sources/data-type/<slug>/` with the five files above, as a proposal (addition by GeoLabs,
`rim:invalid`, `rim:published`), and:

1. add `../data-type/<slug>/ontology.ttl` to the `resources` (role `data`) of
   `_sources/vocabulary/bblock.json`; do not add a `shaclClosures` entry;
2. add its row to the README table;
3. update the `Hierarchy` lines of its parent and children (broader, narrower); give no
   `skos:broader string` to a type whose values are not character strings;
4. name the requesting role in its `description.md`;
5. run the build, the `isProfileOf` against `skos:broader` check, and the build of
   `bblocks-generic-profiles` against this one (`url-mappings`).

A change to an existing type is a `rim:RegisterAction` classified against the specification's table;
while the type is a proposal, it is an in-place action of type `dt:amendmentAction`.

Check `git status` before pushing: an untracked `_sources/vocabulary/data.ttl` once made every test fail on CI.
`description.md` files are not covered by the tests; check them by hand after bulk edits.

## Known gaps

- Simple Feature Access was read only through excerpts; `06-103r3` and `06-103r4` were not compared.
- The `Surface` definition (`A 2-dimensional geometry, e.g. a Polygon.`) was not compared to the SFA text.
- Type blocks have `itemClass: model` although they carry a schema; the RIM uses `schema` for its
  schema blocks. The effect on the published register was not checked.
- `dt:RegisterShape` no longer applies to `register` and `item-class`; only the RIM core shapes do.
  It is still checked in `vocabulary`.
- **Withdrawal of the 19 `string-*` (D2, recorded 2026-11-09).** D2 asked for `rim:supersededBy`
  towards the formats; `rim:RegisterItemShape` rejects it towards an item this register does not type
  (observed in a scratch build), and this register must not depend on data-formats. GeoLabs chose
  option c: `dct:isReplacedBy` here, `rim:supersedes` on the data-formats side, unpublication
  classified substantive. Which way `rim:supersedes` points is read from its label only; the question
  is asked to the model maintainers. The bblock `status` of the withdrawn blocks is still
  `under-development`: the Building Blocks register keeps listing them.
- **Proposals:**
  - STAC (`stac-item`, `stac-item-collection`, `stac-catalog`, `stac-collection`): no Generic or
    Implementation Profile role uses them; 6 testbed outputs (kindgrove, water-bodies) serve a STAC
    Catalog JSON schema. Their definitions and usage describe the STAC JSON objects, an encoding.
    Proposal: `stac-item` and `stac-item-collection` become `df:Format` items of data-formats
    (STAC Item, STAC API ItemCollection), bound to `feature` and `feature-collection` by
    representations once a role needs them, and leave this register; `stac-catalog` and
    `stac-collection` are replaced by format-free concepts (a catalogue of metadata records, a
    described collection) only if a role needs them, with STAC Catalog and STAC Collection as
    formats.
    Decision (2026-11-09): nothing until a role needs them.
  - `elevation-model`: its tool source "SAGA 7.3.0 Terrain Analysis tools" was replaced on 2026-11-09
    by the INSPIRE Data Specification on Elevation, in place, by a `dt:amendmentAction` classified
    clarifying. Generalising it to non-gridded elevation models (TIN, point cloud) would change its
    `skos:broader`, a substantive change, and no role needs it today.
- The four parameter types are not used yet: the Generic Profile roles still declare `string`.
