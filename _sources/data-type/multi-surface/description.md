A 2-dimensional geometry collection whose elements are surfaces. The interiors of any two of its surfaces do not intersect.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/multi-surface` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A multi-surface is a 2-dimensional geometry collection whose elements are surfaces. The interiors of any two of its surfaces do not intersect. Polygon is the surface type of Simple Feature Access, so MultiPolygon is its specialization here.

## Hierarchy

- Broader: [GeometryCollection](../geometry-collection/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: [MultiPolygon](../multi-polygon/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
- [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)
