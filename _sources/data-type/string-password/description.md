A string designated to carry a password value; the source schema does not define a password-strength constraint.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-password` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "password" }
```

The source schema puts no constraint on the value; the format marks it as a secret. Such values should not be echoed in results or logs.

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: password)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
