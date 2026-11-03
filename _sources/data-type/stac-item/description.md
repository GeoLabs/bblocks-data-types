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

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [STAC Item JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/item-spec/json-schema/item.json)
