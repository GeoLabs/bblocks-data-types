A string representing a time of day in the hh:mm:ss.sTZD format.

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

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: time)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
