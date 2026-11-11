A STAC Collection: a Catalog specialization that describes a collection of related spatiotemporal assets with spatial and temporal extents.

## Withdrawn

This type was a proposal and is withdrawn (2026-11-11, decision Q4, option b): it describes an encoding, a STAC JSON object, not a kind of data, and no role uses it. Its item and its version are `rim:unpublished` and stay `rim:invalid`; nothing is deleted and no IRI changes.

- Replacement: the format [`https://w3id.org/geolabs-ospd/data-formats/format/stac-collection`](https://w3id.org/geolabs-ospd/data-formats/format/stac-collection) of the data-formats register (`dct:isReplacedBy` on the item). The Registered Item Model link, `rim:supersedes`, is carried by that format, because this register does not depend on data-formats.
- Action: `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection/actions/unpublication`, of type `rim:unpublishAction`, classified `rim:substantiveChange` (the retirement of a type), next to the addition, which is unchanged.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/stac-collection` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A STAC Collection describes a set of related STAC Items. In the STAC 1.1.0 JSON Schema it must have `stac_version`, `type: "Collection"`, `id`, `description`, `license`, `links` and an `extent` (a spatial `bbox` and a temporal `interval`). `assets`, `item_assets` and `summaries` are optional.

It is a metadata object and does not contain the Items. To obtain the Items themselves use STAC Item Collection.

## Hierarchy

- Broader: [STAC Catalog](../stac-catalog/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition and the unpublication actions and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [STAC Collection JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/collection-spec/json-schema/collection.json)
- [STAC Catalog JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/catalog-spec/json-schema/catalog.json)
