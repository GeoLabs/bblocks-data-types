A string representation of a universally unique identifier (UUID).

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "uuid" }
```

Valid values: `123e4567-e89b-12d3-a456-426614174000`.

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: uuid)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
- [UUID specification references](https://www.rfc-editor.org/rfc/rfc9562.html)
