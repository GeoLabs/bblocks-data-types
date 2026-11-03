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
