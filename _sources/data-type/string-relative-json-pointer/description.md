A string representing a relative JSON Pointer as defined by the JSON Pointer specification.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-relative-json-pointer` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "relative-json-pointer" }
```

Valid values: `1/name`, `0#`.

Relative to a location in a JSON document; it extends the RFC 6901 syntax with a leading number of levels to go up.

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: relative-json-pointer)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
- [RFC 6901](https://datatracker.ietf.org/doc/html/rfc6901)
