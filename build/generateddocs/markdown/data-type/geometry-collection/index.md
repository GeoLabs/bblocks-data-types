
# Data type: GeometryCollection (Model)

`data-types.data-type.geometry-collection` *v1.0*

A geometry that is a collection of geometry objects, which may be of different types.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A geometry that is a collection of geometry objects, which may be of different types.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A geometry collection is a set of geometry objects that may be of different types. MultiPoint, MultiCurve and MultiSurface are collections restricted by dimension and element type; MultiLineString and MultiPolygon restrict them further to line strings and polygons.

## Illustration

Illustration only: the data type does not depend on any encoding. Here is one possible encoding, GeoJSON, in which positions are `[longitude, latitude]`.

```json
{ "type": "GeometryCollection", "geometries": [{ "type": "Point", "coordinates": [0, 0] }, { "type": "LineString", "coordinates": [[0, 0], [1, 1]] }] }
```

## Hierarchy

- Broader: [Geometry](../geometry/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: [MultiCurve](../multi-curve/), [MultiPoint](../multi-point/), [MultiSurface](../multi-surface/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)

## Examples

### GeometryCollection
Canonical concept, version and addition action for this geometry type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "GeometryCollection"@en ; skos:definition "A geometry that is a collection of geometry objects, which may be of different types."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry> ; dct:source [ dct:title "OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture"@en ; dct:references <https://www.ogc.org/standards/sfa/> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-01T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/geometry-collection`

