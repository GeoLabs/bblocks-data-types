A formula that combines references to input values, constants, operators and functions, and whose evaluation computes a value.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/expression` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

The syntax of the formula is a representation, not part of the type.

## Requested by

Added because existing roles of `bblocks-generic-profiles` need it. They declare the data type
`string` today (branch `planes/phase-1-docs`, `b0da6aa`); pointing them to this type is a change of
that register, not made here.

- [`generic-profile/raster-band-math/inputs/expression`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-band-math/inputs/expression): the per-pixel mathematical expression
- [`implementation-profile/raster-band-math/inputs/expression`](https://geolabs.github.io/bblocks-generic-profiles/def/implementation-profile/raster-band-math/inputs/expression)
- [`implementation-profile/raster-band-math-multiband/inputs/expression`](https://geolabs.github.io/bblocks-generic-profiles/def/implementation-profile/raster-band-math-multiband/inputs/expression)

## Hierarchy

- Broader: none (top-level data type). It is not a narrower type of String: what it names is not a
  character string, even if a string can represent it.
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile raster-band-math (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-band-math/inputs/expression)
