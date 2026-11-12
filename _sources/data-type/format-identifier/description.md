An identifier that designates a data format, used to tell a process which format to read or produce.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/format-identifier` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

The formats themselves are items of the data-formats register; this type is the identification of one of them passed as a value.

## Requested by

Added because existing roles of `bblocks-generic-profiles` need it. They declare the data type
`string` today (branch `planes/phase-1-docs`, `b0da6aa`); pointing them to this type is a change of
that register, not made here.

- [`generic-profile/raster-format-conversion/inputs/targetFormat`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-format-conversion/inputs/targetFormat): the target raster encoding
- [`implementation-profile/raster-format-conversion/inputs/targetFormat`](https://geolabs.github.io/bblocks-generic-profiles/def/implementation-profile/raster-format-conversion/inputs/targetFormat)

## Hierarchy

- Broader: none (top-level data type). It is not a narrower type of String: what it names is not a
  character string, even if a string can represent it.
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile raster-format-conversion (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-format-conversion/inputs/targetFormat)
