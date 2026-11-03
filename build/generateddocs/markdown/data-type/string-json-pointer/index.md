
# Data type: String — JSON Pointer (Model)

`data-types.data-type.string-json-pointer` *v1.0*

A string representing an absolute JSON Pointer as defined by RFC 6901.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A string representing an absolute JSON Pointer as defined by RFC 6901.

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

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: json-pointer)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
- [RFC 6901](https://datatracker.ietf.org/doc/html/rfc6901)

## Examples

### JSON Pointer string
Canonical concept, version and addition action for this string format.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "JSON Pointer string"@en ; skos:definition "A string representing an absolute JSON Pointer as defined by RFC 6901."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/string> ; dct:source [ dct:title "EOAP schemas: string_format.yaml (JSON Schema format: json-pointer)"@en ; dct:references <https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml> ], [ dct:title "RFC 6901"@en ; dct:references <https://datatracker.ietf.org/doc/html/rfc6901> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-json-pointer/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-01T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [EOAP schemas: string_format.yaml (JSON Schema format: json-pointer)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
* [RFC 6901](https://datatracker.ietf.org/doc/html/rfc6901)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/string-json-pointer`

