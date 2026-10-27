
# Data Types vocabulary (Model)

`data-types.vocabulary` *v0.1*

The data types of process profile inputs and outputs, as a Registered Item Model concept plane: a rim:ConceptSystem of dt:DataType concepts (sub-class of rim:Concept), each with a governed rim:ConceptVersion. Encoding is out of scope.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

Data types as a Registered Item Model **concept plane**.

## What this block is

A vocabulary of the kinds of data that process profile inputs and outputs carry, modelled on the
concept plane of the [Registered Item Model](https://nielshoffmann.github.io/registered-item-model/)
(ISO 19135:2026):

- `dt:dataTypes` is a `rim:ConceptSystem`;
- each data type is a `dt:DataType` (a sub-class of `rim:Concept`) `skos:inScheme` it, carrying
  `skos:prefLabel`, `skos:definition` and, where one type specialises another,
  `skos:broader` (e.g. `raster-single-band` -> `raster`, `elevation-model` -> `raster-single-band`);
- each data type's governed state is a `dt:DataTypeVersion` (a sub-class of `rim:ConceptVersion`):
  object identifier, `validityStatus`, `publicationStatus`, and the `rim:RegisterAction` that
  proposed it.

The sixteen current types: `raster`, `raster-single-band`, `raster-multi-band`, `elevation-model`,
`geometry`, `point`, `curve`, `surface`, `feature-collection`, `point-cloud`, `tin`, `table`,
`bounding-box`, `number`, `string`, `boolean`.

## Meaning, not encoding

A data type names the **kind** of data, not its **encoding**. The byte format a concrete process
uses (GML, GeoTIFF, the OGC API - Processes `bbox` schema, ...) is declared where that process is
profiled -- an Implementation Profile's own `schema` -- not here. This is the same meaning /
representation split the concept plane exists for.

That boundary is an intent, not an absolute: a few types are grounded in a standard that happens to
be a format -- `point-cloud` cites the OGC LAS community standard, `feature-collection` and `string`
mention GeoJSON / format names in their definitions. Those are the concept's **source**, not an
encoding asserted on it.

## Governance: a proposed addition, not a status

There is no single lifecycle `status`. Each version records a `rim:RegisterAction` of type
`addition`, proposed by GeoLabs, at the date the vocabulary was first drafted (2026-10-08, inline in
`bblocks-generic-profiles`). Pending a control-body decision, versions are `invalid` (not in force)
and `published` (visible). `dt:DataTypeVersionShape` requires that addition and its proposer; a
later decision is a further action, not an edit of this one.

The action is linked from its version (`rim:hasAction`) but carries no `rim:appliesTo`: in the
Registered Item Model, `rim:appliesTo` is typed to `rim:RegisterItem` (the content plane), so it
cannot point at a `rim:ConceptVersion`. Recording a concept-plane addition via `hasAction` only is a
small gap in the model worth raising with its authors.

## Relationship to bblocks-generic-profiles

This vocabulary was first drafted inline in `bblocks-generic-profiles` as its
`generic-profiles.data-type` block. This register extracts it so it can be reused and governed on
its own. It mints its **own** IRIs (`.../bblocks-data-types/def/data-type/...`); the original inline
block keeps its own until a permanent, register-independent namespace is agreed and
`bblocks-generic-profiles` is pointed here. Nothing in `bblocks-generic-profiles` is changed by this
register existing (see that register's `docs/data-types-register.md`).

## Examples

### One data type as a concept and its governed version (JSON)
The single-band raster data type: the concept (its meaning, label, definition and broader
type) and its governed version (object identifier, validity/publication status and the
recorded addition proposed by GeoLabs). It names a kind of data, not an encoding.

#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1",
  "type": "DataTypeVersion",
  "versionOf": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band",
    "type": "DataType",
    "prefLabel": "Raster (single band)",
    "definition": "A raster with exactly one band: a range type of one field.",
    "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types",
    "broader": [
      "https://geolabs.github.io/bblocks-data-types/def/data-type/raster"
    ]
  },
  "version": "1.0",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1",
  "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
    "startedAtTime": "2026-10-08T00:00:00Z"
  }
}

```


### The data types concept system in full (Turtle)
The sixteen data types as rim:Concepts in the dt:dataTypes concept system, each with a
governed rim:ConceptVersion and the addition that proposed it.

#### turtle
```turtle
@prefix dt:   <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim:  <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd:  <http://www.w3.org/2001/XMLSchema#> .

dt:dataTypes a rim:ConceptSystem , skos:ConceptScheme ;
    skos:prefLabel "Data types"@en .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Raster" ;
    skos:definition "A coverage on a regular grid of cells, each cell carrying one value per band; how many bands it has, and what they mean, is its range type." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/raster> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/raster/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Raster (single band)" ;
    skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/raster> ;
    skos:definition "A raster with exactly one band: a range type of one field." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Raster (multiple bands)" ;
    skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/raster> ;
    skos:definition "A raster with more than one band: a range type of several fields." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Elevation model" ;
    skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band> ;
    skos:definition "A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM)." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/geometry> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Geometry" ;
    skos:definition "A geometric object of the Simple Feature Access geometry model." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/geometry/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/geometry/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/geometry"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/geometry/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/point> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Point" ;
    skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry> ;
    skos:definition "A 0-dimensional geometry, a single location." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/point/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/point> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/point/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/point"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/point/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/point/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/curve> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Curve" ;
    skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry> ;
    skos:definition "A 1-dimensional geometry, e.g. a LineString." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/curve/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/curve> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/curve/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/curve"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/curve/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/curve/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/surface> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Surface" ;
    skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry> ;
    skos:definition "A 2-dimensional geometry, e.g. a Polygon." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/surface/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/surface> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/surface/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/surface"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/surface/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/surface/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Feature collection" ;
    skos:definition "A set of features, each with a geometry and attributes -- e.g. a SAGA shapes layer, a GeoJSON or OGC API - Features feature collection." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Point cloud" ;
    skos:definition "A set of three-dimensional points, each with its own attributes (intensity, classification, ...), typically from LiDAR." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/tin> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Triangulated irregular network" ;
    skos:definition "A surface represented by a network of triangles over irregularly spaced points." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/tin/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/tin> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/tin/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/tin"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/tin/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/tin/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/table> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Table" ;
    skos:definition "Records of attribute values, without geometry." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/table/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/table> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/table/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/table"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/table/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/table/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Bounding box" ;
    skos:definition "An axis-aligned extent given by its corners, with its CRS." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/number> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Number" ;
    skos:definition "A literal number." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/number/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/number> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/number/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/number"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/number/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/number/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/string> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "String" ;
    skos:definition "A literal character string, e.g. an expression, a CRS identifier or a format name." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/string/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/string> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/string/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/string/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

<https://geolabs.github.io/bblocks-data-types/def/data-type/boolean> a dt:DataType ;
    skos:inScheme dt:dataTypes ;
    skos:prefLabel "Boolean" ;
    skos:definition "A literal truth value." .

<https://geolabs.github.io/bblocks-data-types/def/data-type/boolean/v1> a dt:DataTypeVersion ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/boolean> ;
    rim:version "1.0" ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/boolean/v1"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/boolean"^^xsd:anyURI ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/boolean/actions/addition> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/boolean/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs ;
    prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```


# JSON-LD Context

```jsonld
None
```

You can find the full JSON-LD context here:
[context.jsonld](https://raw.githubusercontent.com/GeoLabs/bblocks-data-types/undefined/_sources/vocabulary/context.jsonld)

## Sources

* [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
* [OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)
* [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
* [OGC 17-030r1 LAS Specification 1.4 OGC Community Standard](https://www.ogc.org/standards/las/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/vocabulary`

