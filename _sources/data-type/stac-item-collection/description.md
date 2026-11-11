A feature collection whose features are STAC Items, such as a STAC API Item Search response; distinct from a STAC Collection object.

## Withdrawn

This type was a proposal and is withdrawn (2026-11-11, decision Q4, option b): it describes an encoding, a STAC JSON object, not a kind of data, and no role uses it. Its item and its version are `rim:unpublished` and stay `rim:invalid`; nothing is deleted and no IRI changes.

- Replacement: the format [`https://w3id.org/geolabs-ospd/data-formats/format/stac-item-collection`](https://w3id.org/geolabs-ospd/data-formats/format/stac-item-collection) of the data-formats register (`dct:isReplacedBy` on the item). The Registered Item Model link, `rim:supersedes`, is carried by that format, because this register does not depend on data-formats.
- Action: `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/actions/unpublication`, of type `rim:unpublishAction`, classified `rim:substantiveChange` (the retirement of a type), next to the addition, which is unchanged.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A feature collection (see Feature collection) whose features are STAC Items. It is typically what a STAC API returns when searching Items.

Not to be confused with STAC Collection: that one is a metadata object that describes a set of Items, whereas this one is an array of Items.

## Hierarchy

- Broader: [Feature collection](../feature-collection/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition and the unpublication actions and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [EOAP schemas: stac.yaml (STAC Item)](https://raw.githubusercontent.com/eoap/schemas/main/stac.yaml)
- [STAC API Item Search](https://api.stacspec.org/v1.0.0/item-search/)
- [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html)
