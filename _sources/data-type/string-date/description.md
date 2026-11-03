A string representing a calendar date in the YYYY-MM-DD format.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-date` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "date" }
```

Valid values: `2026-11-03`.

This is the RFC 3339 `full-date` (`YYYY-MM-DD`): a date without a time of day. For an instant use String — date-time.

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: date)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
