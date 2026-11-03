
# Data type: Raster (multiple bands) (Model)

`data-types.data-type.raster-multi-band` *v1.0*

A raster with more than one band: a range type of several fields.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A raster with more than one band: a range type of several fields.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: [Raster](../raster/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)

## Examples

### Raster (multiple bands)
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Raster (multiple bands)"@en ; skos:definition "A raster with more than one band: a range type of several fields."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/raster> ; dct:source [ dct:title "OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType"@en ; dct:references <https://docs.ogc.org/is/09-146r8/09-146r8.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-multi-band/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/raster-multi-band`

