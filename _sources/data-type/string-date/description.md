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

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: date)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
