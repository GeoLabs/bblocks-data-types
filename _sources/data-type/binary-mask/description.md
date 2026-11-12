A single-band raster whose cells each state whether the location belongs to a class or not.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/binary-mask` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

How the two states are coded (for example 1 and 0, or 1 and no data) is a property of the data, not part of the type.

## Requested by

Added on 2026-11-10 for a role of a new Generic Profile of `bblocks-generic-profiles` (branch
`planes/new-profiles`), one of the six profiles proposed so that unattached OSPD CWL processes can
attach at tier 4. No standard source is given: none was read for this definition.

- [`generic-profile/raster-thresholding/outputs/mask`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-thresholding/outputs/mask): the cells above the threshold

## Hierarchy

- Broader: [Raster (single band)](../raster-single-band/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile raster-thresholding (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-thresholding/outputs/mask)
