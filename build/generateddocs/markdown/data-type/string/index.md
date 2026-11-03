
# Data type: String (Model)

`data-types.data-type.string` *v1.0*

A literal character string, e.g. an expression, a CRS identifier or a format name.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A literal character string, e.g. an expression, a CRS identifier or a format name.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

Use this type for a character string that has no more specific recognised format. When one applies, prefer the narrower type: the 19 formats of the EOAP `string_format.yaml` (date, date-time, time, duration, email, idn-email, hostname, idn-hostname, ipv4, ipv6, uri, uri-reference, uri-template, iri, iri-reference, uuid, json-pointer, relative-json-pointer, password) are registered as its narrower types.

A string constrained by a caller-supplied regular expression (`Pattern` in `string_format.yaml`) is not a data type of its own: the expression is a parameter of the profile, so it is not registered.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: [Date string](../string-date/), [Date-time string](../string-date-time/), [Duration string](../string-duration/), [Email address string](../string-email/), [Hostname string](../string-hostname/), [Internationalized email address string](../string-idn-email/), [Internationalized hostname string](../string-idn-hostname/), [IPv4 address string](../string-ipv4/), [IPv6 address string](../string-ipv6/), [IRI string](../string-iri/), [IRI reference string](../string-iri-reference/), [JSON Pointer string](../string-json-pointer/), [Password string](../string-password/), [Relative JSON Pointer string](../string-relative-json-pointer/), [Time string](../string-time/), [URI string](../string-uri/), [URI reference string](../string-uri-reference/), [URI template string](../string-uri-template/), [UUID string](../string-uuid/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 18-062r2 OGC API - Processes - Part 1: Core (inputs/outputs schema, JSON Schema)](https://docs.ogc.org/is/18-062r2/18-062r2.html)

## Examples

### String
The canonical concept, governed version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/string> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "String"@en ; skos:definition "A literal character string, e.g. an expression, a CRS identifier or a format name."@en ; dct:source [ dct:title "OGC 18-062r2 OGC API - Processes - Part 1: Core (inputs/outputs schema, JSON Schema)"@en ; dct:references <https://docs.ogc.org/is/18-062r2/18-062r2.html> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/string> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/string/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [OGC 18-062r2 OGC API - Processes - Part 1: Core (inputs/outputs schema, JSON Schema)](https://docs.ogc.org/is/18-062r2/18-062r2.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/string`

