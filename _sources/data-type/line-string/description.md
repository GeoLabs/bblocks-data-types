A connected sequence of two or more points joined by straight line segments, forming a one-dimensional geometry.

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
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
