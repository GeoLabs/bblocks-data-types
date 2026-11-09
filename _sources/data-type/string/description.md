A literal character string, e.g. an expression, a CRS identifier or a format name.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

Use this type for a character string. A recognised syntax for the string (date-time, URI, email, ...) is a format, not a narrower data type: the 20 formats of the EOAP `string_format.yaml`, `Pattern` included, are `df:Format` items of the data-formats register (`https://w3id.org/geolabs-ospd/data-formats/format/string-*`).

The 19 narrower types below were registered here as proposals and are withdrawn (2026-11-09): their items and versions are unpublished, each item is replaced (`dct:isReplacedBy`) by the matching format, and nothing is deleted. Their `skos:broader` link to this type is kept as recorded.

## Hierarchy

- Broader: none (top-level data type)
- Narrower (withdrawn): [Date string](../string-date/), [Date-time string](../string-date-time/), [Duration string](../string-duration/), [Email address string](../string-email/), [Hostname string](../string-hostname/), [Internationalized email address string](../string-idn-email/), [Internationalized hostname string](../string-idn-hostname/), [IPv4 address string](../string-ipv4/), [IPv6 address string](../string-ipv6/), [IRI string](../string-iri/), [IRI reference string](../string-iri-reference/), [JSON Pointer string](../string-json-pointer/), [Password string](../string-password/), [Relative JSON Pointer string](../string-relative-json-pointer/), [Time string](../string-time/), [URI string](../string-uri/), [URI reference string](../string-uri-reference/), [URI template string](../string-uri-template/), [UUID string](../string-uuid/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 18-062r2 OGC API - Processes - Part 1: Core (inputs/outputs schema, JSON Schema)](https://docs.ogc.org/is/18-062r2/18-062r2.html)
