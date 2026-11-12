A STAC Catalog: a linked metadata object organizing STAC Items, Collections or child Catalogs.

## Withdrawn

This type was a proposal and is withdrawn (2026-11-11, decision Q4, option b): it describes an encoding, a STAC JSON object, not a kind of data, and no role uses it. Its item and its version are `rim:unpublished` and stay `rim:invalid`; nothing is deleted and no IRI changes.

- Replacement: the format [`https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog`](https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog) of the data-formats register (`dct:isReplacedBy` on the item). The Registered Item Model link, `rim:supersedes`, is carried by that format, because this register does not depend on data-formats.
- Action: `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/actions/unpublication`, of type `rim:unpublishAction`, classified `rim:substantiveChange` (the retirement of a type), next to the addition, which is unchanged.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A STAC Catalog organises other STAC objects through its `links`. In the STAC 1.1.0 JSON Schema it must have `stac_version`, `type: "Catalog"`, `id`, `description` and `links`; `title` and `stac_extensions` are optional.

It carries no assets and no extent: those are added by STAC Collection.

## Hierarchy

- Broader: none (top-level data type)
- Narrower (withdrawn): [STAC Collection](../stac-collection/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition and the unpublication actions and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [STAC Catalog JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/catalog-spec/json-schema/catalog.json)
