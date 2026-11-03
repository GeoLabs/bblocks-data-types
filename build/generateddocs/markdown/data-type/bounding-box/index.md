
# Data type: Bounding box (Model)

`data-types.data-type.bounding-box` *v1.0*

An axis-aligned extent given by its corners, with its CRS.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

An axis-aligned extent given by its corners, with its CRS.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [ogc.api.processes.v1.schemas.bbox, after OGC 17-069r4 §7.15.3 bbox](https://docs.ogc.org/is/17-069r4/17-069r4.html)

## Examples

### Bounding box
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Bounding box"@en ; skos:definition "An axis-aligned extent given by its corners, with its CRS."@en ; dct:source [ dct:title "ogc.api.processes.v1.schemas.bbox, after OGC 17-069r4 §7.15.3 bbox"@en ; dct:references <https://docs.ogc.org/is/17-069r4/17-069r4.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [ogc.api.processes.v1.schemas.bbox, after OGC 17-069r4 §7.15.3 bbox](https://docs.ogc.org/is/17-069r4/17-069r4.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/bounding-box`

