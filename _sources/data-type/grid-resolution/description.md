The spacing of the cells of a regular grid along each of its axes, in the units of its coordinate reference system.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/grid-resolution` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

A value of this type gives one spacing per axis of the grid.

## Requested by

Added on 2026-11-10 for a role of a new Generic Profile of `bblocks-generic-profiles` (branch
`planes/new-profiles`), one of the six profiles proposed so that unattached OSPD CWL processes can
attach at tier 4. No standard source is given: none was read for this definition.

- [`generic-profile/raster-resampling/inputs/resolution`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-resampling/inputs/resolution): the cell size of the resampled raster

## Hierarchy

- Broader: none (top-level data type).
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile raster-resampling (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-resampling/inputs/resolution)
