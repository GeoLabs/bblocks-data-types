
# Data type: Number (Model)

`data-types.data-type.number` *v1.0*

A literal number.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A literal number.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/number` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 18-062r2 OGC API - Processes - Part 1: Core (inputs/outputs schema, JSON Schema)](https://docs.ogc.org/is/18-062r2/18-062r2.html)

## Examples

### Number
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/number> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Number"@en ; skos:definition "A literal number."@en ; dct:source [ dct:title "OGC 18-062r2 OGC API - Processes - Part 1: Core (inputs/outputs schema, JSON Schema)"@en ; dct:references <https://docs.ogc.org/is/18-062r2/18-062r2.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/number/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/number> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/number/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/number"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/number/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/number/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 18-062r2 OGC API - Processes - Part 1: Core (inputs/outputs schema, JSON Schema)](https://docs.ogc.org/is/18-062r2/18-062r2.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/number`

