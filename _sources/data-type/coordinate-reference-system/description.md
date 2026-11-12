A coordinate system that is related to an object by a datum.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/coordinate-reference-system` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

The definition is the term definition of OGC 18-005r5, 3.1.9. A value of this type identifies or describes one coordinate reference system; how it is written (a code, a URI, a WKT string) is a representation, not part of the type.

## Requested by

Added because existing roles of `bblocks-generic-profiles` need it. They declare the data type
`string` today (branch `planes/phase-1-docs`, `b0da6aa`); pointing them to this type is a change of
that register, not made here.

- [`generic-profile/raster-reprojection/inputs/targetCRS`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-reprojection/inputs/targetCRS): the target coordinate reference system identifier
- [`implementation-profile/raster-reprojection/inputs/targetCRS`](https://geolabs.github.io/bblocks-generic-profiles/def/implementation-profile/raster-reprojection/inputs/targetCRS)

## Hierarchy

- Broader: none (top-level data type). It is not a narrower type of String: what it names is not a
  character string, even if a string can represent it.
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 18-005r5 Topic 2 - Referencing by coordinates (ISO 19111:2019), 3.1.9 coordinate reference system](https://docs.ogc.org/as/18-005r5/18-005r5.html)
- [Generic Profile raster-reprojection (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-reprojection/inputs/targetCRS)
