A string representing an absolute JSON Pointer as defined by RFC 6901.

## Withdrawn

This type was a proposal and is withdrawn (2026-11-09): it is a format, not a kind of data. Its item and its version are `rim:unpublished` and stay `rim:invalid`; nothing is deleted and no IRI changes.

- Replacement: the format [`https://w3id.org/geolabs/ospd/data-formats/format/string-json-pointer`](https://w3id.org/geolabs/ospd/data-formats/format/string-json-pointer) of the data-formats register (`dct:isReplacedBy` on the item). The Registered Item Model link, `rim:supersedes`, is carried by that format, because this register does not depend on data-formats.
- Action: `https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer/actions/unpublication`, of type `rim:unpublishAction`, classified `rim:substantiveChange` (the retirement of a type), next to the addition, which is unchanged.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "json-pointer" }
```

Valid values: `/inputs/0/name`.

An absolute pointer into a JSON document (starts with `/`, or is empty).

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition and the unpublication actions and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: json-pointer)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
- [RFC 6901](https://datatracker.ietf.org/doc/html/rfc6901)
