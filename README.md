# bblocks-data-types

OGC Building Blocks register holding the **data types** of process profile inputs and outputs, as a
[Registered Item Model](https://ogcincubator.github.io/registered-item-model/) (ISO 19135:2026)
**concept plane**. Identifier prefix: `data-types.`

`dt:dataTypes` is a `rim:ConceptSystem`; each data type is a `dt:DataType` (sub-class of
`rim:Concept`) with a governed `dt:DataTypeVersion` (sub-class of `rim:ConceptVersion`). A data type
names the *kind* of data, not its encoding -- the encoding a concrete process uses is declared at the
Implementation Profile tier, not here. See
[`_sources/vocabulary/description.md`](_sources/vocabulary/description.md).

This vocabulary was first drafted inline in
[`GeoLabs/bblocks-generic-profiles`](https://github.com/GeoLabs/bblocks-generic-profiles) as its
`generic-profiles.data-type` block; this register extracts it so it can be reused and governed on
its own. It mints its own IRIs; `bblocks-generic-profiles` is **not** changed by this register
existing (reconciliation of the two IRI namespaces is a later, separate decision).

## Building blocks

| Identifier | Tier |
|---|---|
| `data-types.vocabulary` | Shared concept model, shapes, and register metadata (support block) |
| `data-types.data-type.raster` | Data type: Raster |
| `data-types.data-type.raster-single-band` | Data type: Raster (single band) |
| `data-types.data-type.raster-multi-band` | Data type: Raster (multiple bands) |
| `data-types.data-type.elevation-model` | Data type: Elevation model |
| `data-types.data-type.geometry` | Data type: Geometry |
| `data-types.data-type.feature` | Data type: Feature |
| `data-types.data-type.line-string` | Data type: LineString |
| `data-types.data-type.polygon` | Data type: Polygon |
| `data-types.data-type.multi-point` | Data type: MultiPoint |
| `data-types.data-type.multi-curve` | Data type: MultiCurve |
| `data-types.data-type.multi-line-string` | Data type: MultiLineString |
| `data-types.data-type.multi-surface` | Data type: MultiSurface |
| `data-types.data-type.multi-polygon` | Data type: MultiPolygon |
| `data-types.data-type.geometry-collection` | Data type: GeometryCollection |
| `data-types.data-type.point` | Data type: Point |
| `data-types.data-type.curve` | Data type: Curve |
| `data-types.data-type.surface` | Data type: Surface |
| `data-types.data-type.feature-collection` | Data type: Feature collection |
| `data-types.data-type.stac-item-collection` | Data type: STAC Item Collection |
| `data-types.data-type.stac-item` | Data type: STAC Item |
| `data-types.data-type.stac-catalog` | Data type: STAC Catalog |
| `data-types.data-type.stac-collection` | Data type: STAC Collection |
| `data-types.data-type.point-cloud` | Data type: Point cloud |
| `data-types.data-type.tin` | Data type: Triangulated irregular network |
| `data-types.data-type.table` | Data type: Table |
| `data-types.data-type.bounding-box` | Data type: Bounding box |
| `data-types.data-type.number` | Data type: Number |
| `data-types.data-type.string` | Data type: String |
| `data-types.data-type.string-date` | Data type: String — date |
| `data-types.data-type.string-date-time` | Data type: String — date-time |
| `data-types.data-type.string-duration` | Data type: String — duration |
| `data-types.data-type.string-email` | Data type: String — email |
| `data-types.data-type.string-hostname` | Data type: String — hostname |
| `data-types.data-type.string-idn-email` | Data type: String — internationalized email |
| `data-types.data-type.string-idn-hostname` | Data type: String — internationalized hostname |
| `data-types.data-type.string-ipv4` | Data type: String — IPv4 address |
| `data-types.data-type.string-ipv6` | Data type: String — IPv6 address |
| `data-types.data-type.string-iri` | Data type: String — IRI |
| `data-types.data-type.string-iri-reference` | Data type: String — IRI reference |
| `data-types.data-type.string-json-pointer` | Data type: String — JSON Pointer |
| `data-types.data-type.string-password` | Data type: String — password |
| `data-types.data-type.string-relative-json-pointer` | Data type: String — relative JSON Pointer |
| `data-types.data-type.string-time` | Data type: String — time |
| `data-types.data-type.string-uri` | Data type: String — URI |
| `data-types.data-type.string-uri-reference` | Data type: String — URI reference |
| `data-types.data-type.string-uri-template` | Data type: String — URI template |
| `data-types.data-type.string-uuid` | Data type: String — UUID |
| `data-types.data-type.boolean` | Data type: Boolean |

Each vocabulary concept has its own `model` Building Block, linked to the corresponding
`dt:DataType` IRI. Each block contains its own `ontology.ttl`, which is autodetected and published
as that entry's ontology in the Building Blocks UI. The 19 EOAP string formats are specialized
types of `string`; `Pattern` is omitted because it is a parameterized validation constraint rather
than a fixed data type. `Feature` is distinct from `Geometry`: a feature contains a geometry and
properties. `LineString`, `Polygon`, `MultiPoint`, `MultiLineString`, `MultiPolygon` and
`GeometryCollection` are geometry types of OGC Simple Feature Access: `LineString` specializes
`curve` and `Polygon` specializes `surface`, while `MultiPoint`, `MultiCurve` and `MultiSurface`
are collections and specialize `GeometryCollection`; `MultiLineString` specializes `MultiCurve` and
`MultiPolygon` specializes `MultiSurface`, as in OGC CDB 2.0 Core (23-034, 7.6) and Simple Feature
Access. `STAC
Item` specializes `Feature`; `STAC Collection` specializes `STAC Catalog`; and
`STAC Item Collection` specializes `feature-collection`. The latter is a collection of items, not a
STAC `Collection` metadata object.

The hierarchy between types is expressed twice: as `skos:broader` in each block's `ontology.ttl`
(the canonical source), and as `isProfileOf` towards the parent block in its `bblock.json`, so that
the register itself publishes it (`prof:isProfileOf`). Both must be changed together.
`data-types.vocabulary` remains the shared model/SHACL block.

## Registered data

The registered concepts, their broader links, governed versions and proposed-addition actions are
canonical in the `ontology.ttl` of their respective Building Blocks under
[`_sources/data-type/`](_sources/data-type/). Each ontology is published with its own entry.
[`_sources/vocabulary/data.ttl`](_sources/vocabulary/data.ttl) contains only shared register
metadata: the `rim:Register`, register system, owner and concept system. Concept versions link to
their addition actions with the register-specific `dt:hasVersionAction`: the RIM's
`rim:hasAction` / `rim:appliesTo` pair currently applies only to content-plane `rim:RegisterItem`s,
not concept-plane `rim:ConceptVersion`s.

## Building locally

Imports the published Registered Item Model
([Geonovum-labs/registered-item-model](https://github.com/Geonovum-labs/registered-item-model)); no
local mapping is needed.

```bash
./build.sh   # process and validate (Docker)
./view.sh    # preview at http://localhost:9090
```

## License

Apache-2.0.
