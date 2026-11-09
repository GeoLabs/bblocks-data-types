A string representing a time of day in the hh:mm:ss.sTZD format.

## Withdrawn

This type was a proposal and is withdrawn (2026-11-09): it is a format, not a kind of data. Its item and its version are `rim:unpublished` and stay `rim:invalid`; nothing is deleted and no IRI changes.

- Replacement: the format [`https://w3id.org/geolabs-ospd/data-formats/format/string-time`](https://w3id.org/geolabs-ospd/data-formats/format/string-time) of the data-formats register (`dct:isReplacedBy` on the item). The Registered Item Model link, `rim:supersedes`, is carried by that format, because this register does not depend on data-formats.
- Action: `https://geolabs.github.io/bblocks-data-types/def/data-type/string-time/actions/unpublication`, of type `rim:unpublishAction`, classified `rim:substantiveChange` (the retirement of a type), next to the addition, which is unchanged.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-time` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "time" }
```

Valid values: `12:30:00Z`, `13:30:00.25+01:00`.

A time of day without a date; the offset is required (RFC 3339 `full-time`).

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition and the unpublication actions and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: time)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
