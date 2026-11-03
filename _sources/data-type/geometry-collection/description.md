A geometry that is a collection of geometry objects, which may be of different types.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/geometry-collection` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A geometry collection is a set of geometry objects that may be of different types. MultiPoint, MultiCurve and MultiSurface are collections restricted by dimension and element type; MultiLineString and MultiPolygon restrict them further to line strings and polygons.

## Illustration

Illustration only: the data type does not depend on any encoding. Here is one possible encoding, GeoJSON, in which positions are `[longitude, latitude]`.

```json
{ "type": "GeometryCollection", "geometries": [{ "type": "Point", "coordinates": [0, 0] }, { "type": "LineString", "coordinates": [[0, 0], [1, 1]] }] }
```

## Hierarchy

- Broader: [Geometry](../geometry/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: [MultiCurve](../multi-curve/), [MultiPoint](../multi-point/), [MultiSurface](../multi-surface/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
