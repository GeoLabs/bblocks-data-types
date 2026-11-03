A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM).

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: [Raster (single band)](../raster-single-band/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 09-146r8 CIS 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)
- [SAGA 7.3.0 Terrain Analysis tools, Elevation grid inputs](https://saga-gis.sourceforge.io/saga_tool_doc/7.3.0/ta_morphometry.html)
