A polygon with three distinct, non-collinear vertices and no interior boundary.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/triangle` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A triangle is the polygon of three vertices; the patches of a triangulated irregular network are triangles.

## Hierarchy

- Broader: [Polygon](../polygon/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
- [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)
