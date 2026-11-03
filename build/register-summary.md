# Data Types

A concept-plane register (ISO 19135:2026, via the Registered Item Model) of the kinds of data
that process profile inputs and outputs carry -- raster (by band count), elevation model,
geometry (by type), feature collection, point cloud, TIN, table, bounding box and the literals.
Each data type is a rim:Concept in a rim:ConceptSystem, with a governed rim:ConceptVersion.
A data type names the *kind* of data, not its encoding: the encoding a concrete process uses is
declared where that process is profiled (an Implementation Profile's schema).


This register holds, as a Registered Item Model **concept plane**, the vocabulary first drafted
inline in [GeoLabs/bblocks-generic-profiles](https://github.com/GeoLabs/bblocks-generic-profiles)
as its generic-profiles.data-type block. Extracting it makes the vocabulary reusable beyond that
one register and gives it its own governance and lifecycle.

Modelled on the concept plane of the
[Registered Item Model](https://ogcincubator.github.io/registered-item-model/): dt:DataType is a
sub-class of rim:Concept (a unit of meaning), dt:dataTypes is the rim:ConceptSystem that holds
them, and each type's governed state lives on a rim:ConceptVersion. A data type names the kind of
data (its meaning); the encoding a concrete process uses is declared at the Implementation Profile
tier, not here. Some types are nonetheless grounded in a standard that happens to be a format
(e.g. point cloud in the OGC LAS community standard) -- that is their source, not their encoding.

Identifiers: this register mints its own IRIs
(https://geolabs.github.io/bblocks-data-types/def/data-type/...). The original inline block in
bblocks-generic-profiles keeps its own until a permanent, register-independent namespace is agreed
and that register is pointed here. Nothing in bblocks-generic-profiles is changed by this register.


## Building Blocks

### `data-types.vocabulary` — Data Types shared concept model

**Type:** model

Shared RIM concept-plane model, register metadata, and SHACL rules for the individual data-type Building Blocks in this register.

### `data-types.data-type.boolean` — Data type: Boolean

**Type:** model

A literal truth value.

### `data-types.data-type.bounding-box` — Data type: Bounding box

**Type:** model

An axis-aligned extent given by its corners, with its CRS.

### `data-types.data-type.curve` — Data type: Curve

**Type:** model

A 1-dimensional geometry, e.g. a LineString.

### `data-types.data-type.elevation-model` — Data type: Elevation model

**Type:** model

A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM).

### `data-types.data-type.feature` — Data type: Feature

**Type:** model

A representation of a real-world phenomenon, with a geometry and properties, optionally identified by an identifier.

### `data-types.data-type.feature-collection` — Data type: Feature collection

**Type:** model

A set of features, each with a geometry and attributes; e.g. an OGC API - Features feature collection.

### `data-types.data-type.geometry` — Data type: Geometry

**Type:** model

A geometric object of the Simple Feature Access geometry model.

### `data-types.data-type.geometry-collection` — Data type: GeometryCollection

**Type:** model

A geometry that is a collection of geometry objects, which may be of different types.

### `data-types.data-type.line-string` — Data type: LineString

**Type:** model

A connected sequence of two or more points joined by straight line segments, forming a one-dimensional geometry.

### `data-types.data-type.multi-curve` — Data type: MultiCurve

**Type:** model

A 1-dimensional geometry collection whose elements are curves.

### `data-types.data-type.multi-line-string` — Data type: MultiLineString

**Type:** model

A multi-curve whose elements are line strings.

### `data-types.data-type.multi-point` — Data type: MultiPoint

**Type:** model

A 0-dimensional geometry collection whose elements are points.

### `data-types.data-type.multi-polygon` — Data type: MultiPolygon

**Type:** model

A multi-surface whose elements are polygons.

### `data-types.data-type.multi-surface` — Data type: MultiSurface

**Type:** model

A 2-dimensional geometry collection whose elements are surfaces. The interiors of any two of its surfaces do not intersect.

### `data-types.data-type.number` — Data type: Number

**Type:** model

A literal number.

### `data-types.data-type.point` — Data type: Point

**Type:** model

A 0-dimensional geometry, a single location.

### `data-types.data-type.point-cloud` — Data type: Point cloud

**Type:** model

A set of three-dimensional points, each with its own attributes (intensity, classification, ...), typically from LiDAR.

### `data-types.data-type.polygon` — Data type: Polygon

**Type:** model

A planar surface geometry bounded by one exterior ring and, optionally, interior rings that form holes.

### `data-types.data-type.raster` — Data type: Raster

**Type:** model

A coverage on a regular grid of cells, each cell carrying one value per band; its band structure is its range type.

### `data-types.data-type.raster-multi-band` — Data type: Raster (multiple bands)

**Type:** model

A raster with more than one band: a range type of several fields.

### `data-types.data-type.raster-single-band` — Data type: Raster (single band)

**Type:** model

A raster with exactly one band: a range type of one field.

### `data-types.data-type.stac-catalog` — Data type: STAC Catalog

**Type:** model

A STAC Catalog: a linked metadata object organizing STAC Items, Collections or child Catalogs.

### `data-types.data-type.stac-collection` — Data type: STAC Collection

**Type:** model

A STAC Collection: a Catalog specialization that describes a collection of related spatiotemporal assets with spatial and temporal extents.

### `data-types.data-type.stac-item` — Data type: STAC Item

**Type:** model

A STAC Item: a feature with STAC identity, links, assets, version and spatiotemporal metadata.

### `data-types.data-type.stac-item-collection` — Data type: STAC Item Collection

**Type:** model

A feature collection whose features are STAC Items, such as a STAC API Item Search response; distinct from a STAC Collection object.

### `data-types.data-type.string` — Data type: String

**Type:** model

A literal character string, e.g. an expression, a CRS identifier or a format name.

### `data-types.data-type.string-date` — Data type: String — date

**Type:** model

A string representing a calendar date in the YYYY-MM-DD format.

### `data-types.data-type.string-date-time` — Data type: String — date-time

**Type:** model

A string representing a date and time in the YYYY-MM-DDThh:mm:ss.sTZD format.

### `data-types.data-type.string-duration` — Data type: String — duration

**Type:** model

A string representing a duration as specified by ISO 8601.

### `data-types.data-type.string-email` — Data type: String — email

**Type:** model

A string representing a valid e-mail address as defined by RFC 5322.

### `data-types.data-type.string-hostname` — Data type: String — hostname

**Type:** model

A string representing a valid hostname as defined by RFC 1123.

### `data-types.data-type.string-idn-email` — Data type: String — internationalized email

**Type:** model

A string representing a valid internationalized e-mail address.

### `data-types.data-type.string-idn-hostname` — Data type: String — internationalized hostname

**Type:** model

A string representing a valid internationalized domain name hostname.

### `data-types.data-type.string-ipv4` — Data type: String — IPv4 address

**Type:** model

A string representing an IPv4 address.

### `data-types.data-type.string-ipv6` — Data type: String — IPv6 address

**Type:** model

A string representing an IPv6 address.

### `data-types.data-type.string-iri` — Data type: String — IRI

**Type:** model

A string representing an Internationalized Resource Identifier (IRI) as defined by RFC 3987.

### `data-types.data-type.string-iri-reference` — Data type: String — IRI reference

**Type:** model

A string representing an IRI reference as defined by RFC 3987.

### `data-types.data-type.string-json-pointer` — Data type: String — JSON Pointer

**Type:** model

A string representing an absolute JSON Pointer as defined by RFC 6901.

### `data-types.data-type.string-password` — Data type: String — password

**Type:** model

A string designated to carry a password value; the source schema does not define a password-strength constraint.

### `data-types.data-type.string-relative-json-pointer` — Data type: String — relative JSON Pointer

**Type:** model

A string representing a relative JSON Pointer as defined by the JSON Pointer specification.

### `data-types.data-type.string-time` — Data type: String — time

**Type:** model

A string representing a time of day in the hh:mm:ss.sTZD format.

### `data-types.data-type.string-uri` — Data type: String — URI

**Type:** model

A string representing a Uniform Resource Identifier (URI) as defined by RFC 3986.

### `data-types.data-type.string-uri-reference` — Data type: String — URI reference

**Type:** model

A string representing a URI reference as defined by RFC 3986.

### `data-types.data-type.string-uri-template` — Data type: String — URI template

**Type:** model

A string representing a URI template as defined by RFC 6570.

### `data-types.data-type.string-uuid` — Data type: String — UUID

**Type:** model

A string representation of a universally unique identifier (UUID).

### `data-types.data-type.surface` — Data type: Surface

**Type:** model

A 2-dimensional geometry, e.g. a Polygon.

### `data-types.data-type.table` — Data type: Table

**Type:** model

Records of attribute values, without geometry.

### `data-types.data-type.tin` — Data type: Triangulated irregular network

**Type:** model

A surface represented by a network of triangles over irregularly spaced points.

