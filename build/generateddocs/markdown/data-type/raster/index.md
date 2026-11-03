
# Data type: Raster (Model)

`data-types.data-type.raster` *v1.0*

A coverage on a regular grid of cells, each cell carrying one value per band; its band structure is its range type.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A coverage on a regular grid of cells, each cell carrying one value per band; how many bands it has, and what they mean, is its range type.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/raster` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: [Raster (multiple bands)](../raster-multi-band/), [Raster (single band)](../raster-single-band/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)

## Examples

### Raster
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Raster"@en ; skos:definition "A coverage on a regular grid of cells, each cell carrying one value per band; how many bands it has, and what they mean, is its range type."@en ; dct:source [ dct:title "OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType"@en ; dct:references <https://docs.ogc.org/is/09-146r8/09-146r8.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/raster/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/raster> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/raster/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/raster/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/raster`

