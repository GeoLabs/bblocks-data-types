
# Data type: STAC Item Collection (Model)

`data-types.data-type.stac-item-collection` *v1.0*

A feature collection whose features are STAC Items, such as a STAC API Item Search response; distinct from a STAC Collection object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A feature collection whose features are STAC Items, such as a STAC API Item Search response; distinct from a STAC Collection object.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A feature collection (see Feature collection) whose features are STAC Items. It is typically what a STAC API returns when searching Items.

Not to be confused with STAC Collection: that one is a metadata object that describes a set of Items, whereas this one is an array of Items.

## Hierarchy

- Broader: [Feature collection](../feature-collection/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: stac.yaml (STAC Item)](https://raw.githubusercontent.com/eoap/schemas/main/stac.yaml)
- [STAC API Item Search](https://api.stacspec.org/v1.0.0/item-search/)
- [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html)

## Examples

### STAC Item Collection
A feature collection of STAC Items, such as a STAC API Item Search response; distinct from a STAC Collection object.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "STAC Item Collection"@en ; skos:definition "A feature collection whose features are STAC Items, such as a STAC API Item Search response; distinct from a STAC Collection object."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/feature-collection> ; dct:source [ dct:title "EOAP schemas: stac.yaml (STAC Item)"@en ; dct:references <https://raw.githubusercontent.com/eoap/schemas/main/stac.yaml> ], [ dct:title "STAC API Item Search"@en ; dct:references <https://api.stacspec.org/v1.0.0/item-search/> ], [ dct:title "OGC 17-069r4 OGC API - Features - Part 1: Core"@en ; dct:references <https://docs.ogc.org/is/17-069r4/17-069r4.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-01T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [EOAP schemas: stac.yaml (STAC Item)](https://raw.githubusercontent.com/eoap/schemas/main/stac.yaml)
* [STAC API Item Search](https://api.stacspec.org/v1.0.0/item-search/)
* [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/stac-item-collection`

