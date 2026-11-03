A string representing a date and time in the YYYY-MM-DDThh:mm:ss.sTZD format.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-date-time` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "date-time" }
```

Valid values: `2026-11-03T12:30:00Z`, `2026-11-03T13:30:00.5+01:00`.

A time zone offset or `Z` is required (RFC 3339 `date-time`).

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: date-time)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
