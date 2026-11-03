
# Data type: MultiPoint (Model)

`data-types.data-type.multi-point` *v1.0*

A 0-dimensional geometry collection whose elements are points.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A 0-dimensional geometry collection whose elements are points.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/multi-point` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A multi-point is a 0-dimensional geometry collection whose elements are points.

## Illustration

Illustration only: the data type does not depend on any encoding. Here is one possible encoding, GeoJSON, in which positions are `[longitude, latitude]`.

```json
{ "type": "MultiPoint", "coordinates": [[2.35, 48.85], [2.37, 48.86]] }
```

## Hierarchy

- Broader: [GeometryCollection](../geometry-collection/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
- [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)

## Examples

### MultiPoint
Canonical concept, version and addition action for this geometry type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/multi-point> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "MultiPoint"@en ; skos:definition "A 0-dimensional geometry collection whose elements are points."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection> ; dct:source [ dct:title "OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture"@en ; dct:references <https://www.ogc.org/standards/sfa/> ], [ dct:title "OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry"@en ; dct:references <https://docs.ogc.org/is/23-034/23-034.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/multi-point/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/multi-point> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/multi-point/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/multi-point"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/multi-point/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/multi-point/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-01T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
* [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/multi-point`

