A curve with linear interpolation between points: each consecutive pair of points defines a line segment.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/line-string` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A line string has two or more points; consecutive points are joined by straight line segments.

## Illustration

Illustration only: the data type does not depend on any encoding. Here is one possible encoding, GeoJSON, in which positions are `[longitude, latitude]`.

```json
{ "type": "LineString", "coordinates": [[2.35, 48.85], [2.37, 48.86]] }
```

## Hierarchy

- Broader: [Curve](../curve/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: [Line](../line/), [LinearRing](../linear-ring/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
- [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)
