
# Data type: String — UUID (Model)

`data-types.data-type.string-uuid` *v1.0*

A string representation of a universally unique identifier (UUID).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

## Examples

### UUID string
Canonical concept, version and addition action for this string format.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "UUID string"@en ; skos:definition "A string representation of a universally unique identifier (UUID)."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/string> ; dct:source [ dct:title "EOAP schemas: string_format.yaml (JSON Schema format: uuid)"@en ; dct:references <https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml> ], [ dct:title "UUID specification references"@en ; dct:references <https://www.rfc-editor.org/rfc/rfc9562.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-01T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [EOAP schemas: string_format.yaml (JSON Schema format: uuid)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
* [UUID specification references](https://www.rfc-editor.org/rfc/rfc9562.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/string-uuid`

