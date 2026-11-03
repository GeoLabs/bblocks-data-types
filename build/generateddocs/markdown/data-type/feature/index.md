
# Data type: Feature (Model)

`data-types.data-type.feature` *v1.0*

A representation of a real-world phenomenon, with a geometry and properties, optionally identified by an identifier.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A representation of a real-world phenomenon, with a geometry and properties, optionally identified by an identifier.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/feature` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A feature has a geometry and a set of properties, and may have an identifier.

A feature is not a geometry: it wraps one. This is why it is not under Geometry. Features are gathered in a Feature collection.

## Illustration

Illustration only: the data type does not depend on any encoding. Here is one possible encoding, GeoJSON, in which positions are `[longitude, latitude]`.

```json
{ "type": "Feature", "id": "a1", "geometry": { "type": "Point", "coordinates": [2.35, 48.85] }, "properties": { "name": "Paris" } }
```

## Hierarchy

- Broader: none (top-level data type)
- Narrower: [STAC Item](../stac-item/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- ISO 19109:2015 Geographic information -- Rules for application schema
- [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html)

## Examples

### Feature
Canonical concept, version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/feature> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Feature"@en ; skos:definition "A representation of a real-world phenomenon, with a geometry and properties, optionally identified by an identifier."@en ; dct:source [ dct:title "ISO 19109:2015 Geographic information -- Rules for application schema"@en ], [ dct:title "OGC 17-069r4 OGC API - Features - Part 1: Core"@en ; dct:references <https://docs.ogc.org/is/17-069r4/17-069r4.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/feature/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/feature> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/feature/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/feature"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/feature/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/feature/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-02T00:00:00Z"^^xsd:dateTime .

```

## Sources

* ISO 19109:2015 Geographic information -- Rules for application schema
* [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/feature`

