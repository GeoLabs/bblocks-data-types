
# Data type: MultiCurve (Model)

`data-types.data-type.multi-curve` *v1.0*

A 1-dimensional geometry collection whose elements are curves.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A 1-dimensional geometry collection whose elements are curves.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/multi-curve` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A multi-curve is a 1-dimensional geometry collection whose elements are curves. Line strings are the only curves defined by Simple Feature Access, so MultiLineString is its specialization here.

## Hierarchy

- Broader: [GeometryCollection](../geometry-collection/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: [MultiLineString](../multi-line-string/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
- [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)

## Examples

### MultiCurve
Canonical concept, version and addition action for this geometry type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/multi-curve> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "MultiCurve"@en ; skos:definition "A 1-dimensional geometry collection whose elements are curves."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection> ; dct:source [ dct:title "OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture"@en ; dct:references <https://www.ogc.org/standards/sfa/> ], [ dct:title "OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry"@en ; dct:references <https://docs.ogc.org/is/23-034/23-034.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/multi-curve/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/multi-curve> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/multi-curve/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/multi-curve"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/multi-curve/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/multi-curve/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-03T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
* [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/multi-curve`

