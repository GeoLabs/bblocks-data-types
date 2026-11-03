
# Data type: STAC Item (Model)

`data-types.data-type.stac-item` *v1.0*

A STAC Item: a feature with STAC identity, links, assets, version and spatiotemporal metadata.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A STAC Item: a feature with STAC identity, links, assets, version and spatiotemporal metadata.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A STAC Item is a Feature (see Feature). In the STAC 1.1.0 JSON Schema it must have:

- `stac_version`, `id`, `links`, `assets` and `properties`;
- a `geometry`, and a `bbox` when the geometry is not `null`;
- `properties.datetime`, which may be `null` only if `start_datetime` and `end_datetime` are given;
- a `collection` identifier if, and only if, its `links` contain a `collection` relation.

It describes one spatiotemporal asset (for example a satellite scene) and points to its files through `assets`.

## Hierarchy

- Broader: [Feature](../feature/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [STAC Item JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/item-spec/json-schema/item.json)

## Examples

### STAC Item
Canonical concept, version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "STAC Item"@en ; skos:definition "A STAC Item: a feature with STAC identity, links, assets, version and spatiotemporal metadata."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/feature> ; dct:source [ dct:title "STAC Item JSON Schema"@en ; dct:references <https://github.com/radiantearth/stac-spec/blob/master/item-spec/json-schema/item.json> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-02T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [STAC Item JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/item-spec/json-schema/item.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/stac-item`

