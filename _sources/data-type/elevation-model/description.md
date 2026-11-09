A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM).

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

INSPIRE also admits vector and TIN representations of an elevation model; this type covers the grid one.

## Amendment

On 2026-11-09 the source "SAGA 7.3.0 Terrain Analysis tools, Elevation grid inputs", a tool, was replaced by the INSPIRE Data Specification on Elevation, whose executive summary defines the digital elevation, terrain and surface models (DEM, DTM, DSM). The definition is unchanged. The action, `https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/amendment-source`, is of type `dt:amendmentAction` and classified `rim:clarifyingChange`: an in-place change to a proposal.

A second clarifying amendment of the same day, `https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/amendment-inspire-version` (`dt:amendmentAction`, `rim:clarifyingChange`, affected properties `dct:source` and `skos:scopeNote`), gives the version of the INSPIRE specification, D2.8.II.1_v3.3.0, cites its term definitions (§2.4, (6) to (8)) and adds the scope note above. The definition and the broader type are unchanged.

## Hierarchy

- Broader: [Raster (single band)](../raster-single-band/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 09-146r8 CIS 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)
- [INSPIRE D2.8.II.1 Data Specification on Elevation – Technical Guidelines, D2.8.II.1_v3.3.0 (2024-01-31): Executive Summary, and §2.4 Terms and definitions, (6) Digital Elevation Model, (7) Digital Surface Model, (8) Digital Terrain Model](https://inspire.ec.europa.eu/id/document/tg/el)
