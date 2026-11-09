# Work summary: bblocks-data-types

State as of 2026-11-04. Last verified build: 55/55 tests passing, locally and on CI.

## Purpose

An OGC Building Blocks register (identifier prefix `data-types.`) of the kinds of data that process
inputs and outputs carry. It is modelled on the
[Registered Item Model](https://ogcincubator.github.io/registered-item-model/) (RIM, ISO 19135:2026).

A data type names the **kind** of data, not its **encoding**. The encoding a concrete process uses is
declared where that process is profiled. Descriptions may show GeoJSON or JSON Schema as an
illustration only.

The vocabulary was first drafted inline in `bblocks-generic-profiles`; this register extracts it so it
can be reused and governed on its own. `bblocks-generic-profiles` is not changed by this register.

## Content: 55 Building Blocks

| Group | Blocks |
|---|---|
| Geometry (17) | `geometry`, `point`, `curve`, `surface`, `line-string`, `line`, `linear-ring`, `polygon`, `triangle`, `polyhedral-surface`, `tin`, `geometry-collection`, `multi-point`, `multi-curve`, `multi-surface`, `multi-line-string`, `multi-polygon` |
| Features (2) and STAC (4) | `feature`, `feature-collection`, `stac-item`, `stac-collection`, `stac-catalog`, `stac-item-collection` |
| Literals (22) | `string`, 19 `string-*` formats from the EOAP schemas, `number`, `boolean` |
| Raster (4) | `raster`, `raster-single-band`, `raster-multi-band`, `elevation-model` |
| Other (3) | `point-cloud`, `table`, `bounding-box` |
| Support (3) | `vocabulary`, `register`, `item-class` |

## Model

**Concept plane.** Each data type is a `dt:DataType` (a sub-class of `rim:Concept`) in the
`dt:dataTypes` concept system, with a governed `dt:DataTypeVersion` (`/v1`) and a recorded
`rim:RegisterAction` of type addition, proposed by GeoLabs. Versions are `rim:invalid` (not in force)
and `rim:published`: a proposed addition awaiting a decision.

**Content plane.** Each data type also has a `dt:DataTypeItem` (a sub-class of `rim:RegisterItem`) of
the `dt:dataTypeItemClass` item class, in `dt:register`, that `rim:realizes` its version.
`dt:DataTypeItemShape` checks this and is the item class's `rim:validatedBy`.

**Hierarchy.** It is expressed twice, and both must be kept in sync:

- `skos:broader` in the block's `ontology.ttl` (canonical);
- `isProfileOf` in `bblock.json`, which the register publishes as `prof:isProfileOf`.

A check that compares the two currently finds 41 relations and no gap.

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

`register` and `item-class` take `../vocabulary/data.ttl` as SHACL closure rather than depending on
`vocabulary`, which would make a cycle.

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
  JSON Schema formats for `string-*`) are cited as sources, not asserted as encodings.
- **Concept version, not concept, carries the status.** The embedded concept in JSON has `type: Concept`
  because the RIM schema fixes it; its `dt:DataType` class comes from the ontologies in the closure.

## Working on the register

```bash
./build.sh   # process and validate (requires Docker); output in build-local/
./view.sh    # preview in the bblocks viewer
```

To add a type, create a block under `_sources/data-type/<slug>/` with the five files above, then:

1. add `../data-type/<slug>/ontology.ttl` to `shaclClosures` in `_sources/vocabulary/bblock.json`;
2. add its row to the README table;
3. update the `Hierarchy` lines of its parent and children (broader, narrower);
4. run the build and the `isProfileOf` against `skos:broader` check.

Check `git status` before pushing: an untracked `_sources/vocabulary/data.ttl` once made every test fail on CI.
`description.md` files are not covered by the tests; check them by hand after bulk edits.

## Known gaps

- Simple Feature Access was read only through excerpts; `06-103r3` and `06-103r4` were not compared.
- The `Surface` definition (`A 2-dimensional geometry, e.g. a Polygon.`) was not compared to the SFA text.
- Type blocks have `itemClass: model` although they carry a schema; the RIM uses `schema` for its
  schema blocks. The effect on the published register was not checked.
- `dt:RegisterShape` no longer applies to `register` and `item-class`; only the RIM core shapes do.
  It is still checked in `vocabulary`.
- `bblocks-generic-profiles` still points to its own inline vocabulary; redirecting it to this register
  is an open decision.
