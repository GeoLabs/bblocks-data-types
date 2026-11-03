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

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 18-062r2 OGC API - Processes - Part 1: Core (inputs/outputs schema, JSON Schema)](https://docs.ogc.org/is/18-062r2/18-062r2.html)
