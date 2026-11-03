
# Data type: String — URI reference (Model)

`data-types.data-type.string-uri-reference` *v1.0*

A string representing a URI reference as defined by RFC 3986.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A string representing a URI reference as defined by RFC 3986.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-reference` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "uri-reference" }
```

Valid values: `/processes/buffer`, `../a.json`.

May be relative to a base URI.

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: uri-reference)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
- [RFC 3986](https://datatracker.ietf.org/doc/html/rfc3986)

## Examples

### URI reference string
Canonical concept, version and addition action for this string format.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-reference> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "URI reference string"@en ; skos:definition "A string representing a URI reference as defined by RFC 3986."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/string> ; dct:source [ dct:title "EOAP schemas: string_format.yaml (JSON Schema format: uri-reference)"@en ; dct:references <https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml> ], [ dct:title "RFC 3986"@en ; dct:references <https://datatracker.ietf.org/doc/html/rfc3986> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-reference/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-reference> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-reference/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-reference"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-reference/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-uri-reference/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-01T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [EOAP schemas: string_format.yaml (JSON Schema format: uri-reference)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
* [RFC 3986](https://datatracker.ietf.org/doc/html/rfc3986)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/string-uri-reference`

