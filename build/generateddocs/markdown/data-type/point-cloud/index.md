
# Data type: Point cloud (Model)

`data-types.data-type.point-cloud` *v1.0*

A set of three-dimensional points, each with its own attributes (intensity, classification, ...), typically from LiDAR.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A set of three-dimensional points, each with its own attributes (intensity, classification, ...), typically from LiDAR.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 17-030r1 LAS Specification 1.4 OGC Community Standard](https://www.ogc.org/standards/las/)

## Examples

### Point cloud
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Point cloud"@en ; skos:definition "A set of three-dimensional points, each with its own attributes (intensity, classification, ...), typically from LiDAR."@en ; dct:source [ dct:title "OGC 17-030r1 LAS Specification 1.4 OGC Community Standard"@en ; dct:references <https://www.ogc.org/standards/las/> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/point-cloud/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 17-030r1 LAS Specification 1.4 OGC Community Standard](https://www.ogc.org/standards/las/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/point-cloud`

