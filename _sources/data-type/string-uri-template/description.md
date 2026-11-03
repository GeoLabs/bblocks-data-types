A string representing a URI template as defined by RFC 6570.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-template` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "uri-template" }
```

Valid values: `https://example.org/collections/{collectionId}/items{?limit}`.

A template to be expanded with variables, not yet a usable URI.

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: uri-template)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
- [RFC 6570](https://datatracker.ietf.org/doc/html/rfc6570)
