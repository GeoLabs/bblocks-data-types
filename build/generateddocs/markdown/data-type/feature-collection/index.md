
# Data type: Feature collection (Model)

`data-types.data-type.feature-collection` *v1.0*

A set of features, each with a geometry and attributes; e.g. an OGC API - Features feature collection.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A set of features, each with a geometry and attributes -- e.g. a SAGA shapes layer or an OGC API - Features feature collection.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: [STAC Item Collection](../stac-item-collection/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html)

## Examples

### Feature collection
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Feature collection"@en ; skos:definition "A set of features, each with a geometry and attributes -- e.g. a SAGA shapes layer or an OGC API - Features feature collection."@en ; dct:source [ dct:title "OGC 17-069r4 OGC API - Features - Part 1: Core"@en ; dct:references <https://docs.ogc.org/is/17-069r4/17-069r4.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/feature-collection`

