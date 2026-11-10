A period of time between two instants, either of which may be unbounded.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/time-interval` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

How the interval is written (two dates, a date and a duration) is a representation, not part of the type.

## Requested by

Added on 2026-11-10 for a role of a new Generic Profile of `bblocks-generic-profiles` (branch
`planes/new-profiles`), one of the six profiles proposed so that unattached OSPD CWL processes can
attach at tier 4. No standard source is given: none was read for this definition.

- [`generic-profile/product-selection/inputs/timeInterval`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/product-selection/inputs/timeInterval): the acquisition period of the products

## Hierarchy

- Broader: none (top-level data type).
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile product-selection (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/product-selection/inputs/timeInterval)
