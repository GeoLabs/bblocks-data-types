
# Data type: STAC Collection (Model)

`data-types.data-type.stac-collection` *v1.0*

A STAC Collection: a Catalog specialization that describes a collection of related spatiotemporal assets with spatial and temporal extents.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A STAC Collection: a Catalog specialization that describes a collection of related spatiotemporal assets with spatial and temporal extents.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A STAC Collection describes a set of related STAC Items. In the STAC 1.1.0 JSON Schema it must have `stac_version`, `type: "Collection"`, `id`, `description`, `license`, `links` and an `extent` (a spatial `bbox` and a temporal `interval`). `assets`, `item_assets` and `summaries` are optional.

It is a metadata object and does not contain the Items. To obtain the Items themselves use STAC Item Collection.

## Hierarchy

- Broader: [STAC Catalog](../stac-catalog/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [STAC Collection JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/collection-spec/json-schema/collection.json)
- [STAC Catalog JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/catalog-spec/json-schema/catalog.json)

## Examples

### STAC Collection
Canonical concept, version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "STAC Collection"@en ; skos:definition "A STAC Collection: a Catalog specialization that describes a collection of related spatiotemporal assets with spatial and temporal extents."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog> ; dct:source [ dct:title "STAC Collection JSON Schema"@en ; dct:references <https://github.com/radiantearth/stac-spec/blob/master/collection-spec/json-schema/collection.json> ], [ dct:title "STAC Catalog JSON Schema"@en ; dct:references <https://github.com/radiantearth/stac-spec/blob/master/catalog-spec/json-schema/catalog.json> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-02T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [STAC Collection JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/collection-spec/json-schema/collection.json)
* [STAC Catalog JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/catalog-spec/json-schema/catalog.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/stac-collection`

