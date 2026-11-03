A representation of a real-world phenomenon, with a geometry and properties, optionally identified by an identifier.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/feature` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A feature has a geometry and a set of properties, and may have an identifier.

A feature is not a geometry: it wraps one. This is why it is not under Geometry. Features are gathered in a Feature collection.

## Illustration

Illustration only: the data type does not depend on any encoding. Here is one possible encoding, GeoJSON, in which positions are `[longitude, latitude]`.

```json
{ "type": "Feature", "id": "a1", "geometry": { "type": "Point", "coordinates": [2.35, 48.85] }, "properties": { "name": "Paris" } }
```

## Hierarchy

- Broader: none (top-level data type)
- Narrower: [STAC Item](../stac-item/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- ISO 19109:2015 Geographic information -- Rules for application schema
- [OGC 17-069r4 OGC API - Features - Part 1: Core](https://docs.ogc.org/is/17-069r4/17-069r4.html)
