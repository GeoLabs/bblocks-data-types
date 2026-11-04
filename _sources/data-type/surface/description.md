A 2-dimensional geometry, e.g. a Polygon.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/surface` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

The only instantiable kinds of surface in Simple Feature Access are the polygon and the polyhedral surface.

## Hierarchy

- Broader: [Geometry](../geometry/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: [Polygon](../polygon/), [PolyhedralSurface](../polyhedral-surface/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
- [OGC 06-103r3 Simple Feature Access - Part 1: Common Architecture](https://docs.ogc.org/is/06-103r3/06-103r3.pdf)
