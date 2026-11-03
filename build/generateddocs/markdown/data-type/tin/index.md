
# Data type: Triangulated irregular network (Model)

`data-types.data-type.tin` *v1.0*

A surface represented by a network of triangles over irregularly spaced points.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A surface represented by a network of triangles over irregularly spaced points.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/tin` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- ISO 19107:2019 Geographic information -- Spatial schema (TIN)
- [SAGA 7.3.0 TIN tools](https://saga-gis.sourceforge.io/saga_tool_doc/7.3.0/tin_tools.html)

## Examples

### Triangulated irregular network
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/tin> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Triangulated irregular network"@en ; skos:definition "A surface represented by a network of triangles over irregularly spaced points."@en ; dct:source [ dct:title "ISO 19107:2019 Geographic information -- Spatial schema (TIN)"@en ], [ dct:title "SAGA 7.3.0 TIN tools"@en ; dct:references <https://saga-gis.sourceforge.io/saga_tool_doc/7.3.0/tin_tools.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/tin/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/tin> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/tin/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/tin"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/tin/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/tin/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* ISO 19107:2019 Geographic information -- Spatial schema (TIN)
* [SAGA 7.3.0 TIN tools](https://saga-gis.sourceforge.io/saga_tool_doc/7.3.0/tin_tools.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/tin`

