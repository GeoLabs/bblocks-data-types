
# Data type: Elevation model (Model)

`data-types.data-type.elevation-model` *v1.0*

A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM).

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: [Raster (single band)](../raster-single-band/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 09-146r8 CIS 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)
- [SAGA 7.3.0 Terrain Analysis tools, Elevation grid inputs](https://saga-gis.sourceforge.io/saga_tool_doc/7.3.0/ta_morphometry.html)

## Examples

### Elevation model
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Elevation model"@en ; skos:definition "A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM)."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band> ; dct:source [ dct:title "OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType"@en ; dct:references <https://docs.ogc.org/is/09-146r8/09-146r8.html> ], [ dct:title "SAGA 7.3.0 Terrain Analysis tools, Elevation grid inputs"@en ; dct:references <https://saga-gis.sourceforge.io/saga_tool_doc/7.3.0/ta_morphometry.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 09-146r8 CIS 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)
* [SAGA 7.3.0 Terrain Analysis tools, Elevation grid inputs](https://saga-gis.sourceforge.io/saga_tool_doc/7.3.0/ta_morphometry.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/elevation-model`

