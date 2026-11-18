A calendar day, without a time of day.

## Definition

`https://w3id.org/geolabs/ospd/data-types/data-type/date` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

How the day is written (for instance `YYYY-MM-DD`, the JSON Schema `date` format) is a representation, not part of the type: the data-formats register binds this type to the format `string-date`.

## Requested by

Added on 2026-11-18 for an input of a deployed process, not for a Generic Profile role: the input
`DATE_MIN` of the process type `terrain/hillshading` of `bblocks-process-profiles` declares
`"type": "string", "format": "date"`. No standard source is given: none was read for this definition.

- [`process-type/terrain/hillshading`](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/hillshading): `DATE_MIN`, the first day of the period

It is not the withdrawn proposal `string-date`, which was a format registered as a data type.

## Hierarchy

- Broader: none (top-level data type).
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Process type terrain/hillshading (bblocks-process-profiles), input DATE_MIN, the deployed process input that requests this type](https://w3id.org/geolabs/ospd/process-profiles/process-type/terrain/hillshading)
