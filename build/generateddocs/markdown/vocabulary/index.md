
# Data Types shared concept model (Model)

`data-types.vocabulary` *v0.1*

Shared RIM concept-plane model, register metadata, and SHACL rules for the individual data-type Building Blocks in this register.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

Data types as a Registered Item Model **concept plane**.

## What this block is

A vocabulary of the kinds of data that process profile inputs and outputs carry, modelled on the
concept plane of the [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)
(ISO 19135:2026):

- `dt:dataTypes` is a `rim:ConceptSystem`;
- each data type is a `dt:DataType` (a sub-class of `rim:Concept`) `skos:inScheme` it, carrying
  `skos:prefLabel`, `skos:definition` and, where one type specialises another,
  `skos:broader` (e.g. `raster-single-band` -> `raster`, `elevation-model` -> `raster-single-band`);
- each data type's governed state is a `dt:DataTypeVersion` (a sub-class of `rim:ConceptVersion`):
  object identifier, `validityStatus`, `publicationStatus`, and the `rim:RegisterAction` that
  proposed it.

The `skos:broader` link is canonical in each block's `ontology.ttl`. The register's own graph does
not carry it, so each block also declares its parent as `isProfileOf` in `bblock.json`; the register
then publishes it as `prof:isProfileOf`.

Each concept has its own `model` Building Block, with metadata linking the entry to its
`dt:DataType` IRI. These entries are the individually browsable vocabulary items in the published
Building Blocks UI. This `data-types.vocabulary` block is their shared model and SHACL profile, not
a substitute for the individual entries.

## Authoritative register content

The concepts, their `skos:broader` links, versions and addition actions are **registered data**, not
merely examples. Each individual data-type Building Block contains its canonical RDF
graph in `ontology.ttl`, autodetected and published as that block's ontology. The shared
[`data.ttl`](data.ttl) in this support block contains only register metadata: the `rim:Register`,
register system, owner and `rim:ConceptSystem`. The individual ontologies carry each concept,
version and proposed-addition action. The JSON example below illustrates one version; the Turtle
example references the support block's register metadata.

The initial types are `raster`, `raster-single-band`, `raster-multi-band`, `elevation-model`,
`geometry`, `point`, `curve`, `surface`, `feature-collection`, `point-cloud`, `tin`, `table`,
`bounding-box`, `number`, `string` and `boolean`. The 19 fixed string formats in
[`eoap/schemas/string_format.yaml`](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
are also registered as individual specializations of `string`: date, date-time, duration, email,
hostname, idn-email, idn-hostname, ipv4, ipv6, iri, iri-reference, password, json-pointer,
relative-json-pointer, uuid, uri, uri-reference, uri-template and time. The schema's `Pattern`
record is not a fixed datatype; it carries a caller-supplied regular expression and is therefore a
parameterized validation constraint.

The geometry types of OGC Simple Feature Access are represented individually: besides `point`,
`curve` and `surface`, the `line-string` (under `curve`), `polygon` (under `surface`) and
`geometry-collection` entries are narrower geometry concepts, and `multi-point`, `multi-curve` and
`multi-surface` are collections, hence narrower than `geometry-collection`; `multi-line-string` is
a `multi-curve` and `multi-polygon` a `multi-surface` (OGC CDB 2.0 Core, 23-034, 7.6). A `feature`, which
wraps a geometry with properties, is a type of its own. Three distinct STAC data types are
represented from [`radiantearth/stac-spec`](https://github.com/radiantearth/stac-spec): `stac-item`
specializes `feature`, `stac-collection` specializes `stac-catalog`, and `stac-item-collection`
specializes `feature-collection` for responses containing arrays of STAC Items (such as Item
Search). A STAC Collection is metadata for a set of related assets, not an array of STAC Items.

## Meaning, not encoding

A data type names the **kind** of data, not its **encoding**. The byte format a concrete process
uses (GML, GeoTIFF, the OGC API - Processes `bbox` schema, ...) is declared where that process is
profiled -- an Implementation Profile's own `schema` -- not here. This is the same meaning /
representation split the concept plane exists for.

That boundary is an intent, not an absolute: a few types are grounded in a standard that happens to
be a format -- `point-cloud` cites the OGC LAS community standard, and the `string-*` types are named
after JSON Schema formats. Those are the concept's **source**, not an encoding asserted on it.
Definitions otherwise avoid naming a format: the geometry types, for example, are defined from
Simple Feature Access, not from any encoding of them. Descriptions may still show an encoding
(GeoJSON, JSON Schema `format`) as an illustration only.

## Governance: a proposed addition, not a status

There is no single lifecycle `status`. Each version records a `rim:RegisterAction` of type
`addition`, proposed by GeoLabs, at the date the vocabulary was first drafted (2026-10-08, inline in
`bblocks-generic-profiles`). Pending a control-body decision, versions are `invalid` (not in force)
and `published` (visible). `dt:DataTypeVersionShape` requires that addition and its proposer; a
later decision is a further action, not an edit of this one.

The action is linked from its version with the register-specific `dt:hasVersionAction`. The RIM's
`rim:hasAction` / `rim:appliesTo` pair is typed for `rim:RegisterItem` in the content plane, not
`rim:ConceptVersion`; using it here would incorrectly make a concept version look like a content
item. `dt:hasVersionAction` is the small, explicit extension this concept-plane register needs;
the addition action itself remains a `rim:RegisterAction`.

## Relationship to bblocks-generic-profiles

This vocabulary was first drafted inline in `bblocks-generic-profiles` as its
`generic-profiles.data-type` block. This register extracts it so it can be reused and governed on
its own. It mints its **own** IRIs (`.../bblocks-data-types/def/data-type/...`); the original inline
block keeps its own until a permanent, register-independent namespace is agreed and
`bblocks-generic-profiles` is pointed here. Nothing in `bblocks-generic-profiles` is changed by this
register existing (see that register's `docs/data-types-register.md`).

## Examples

### One data type as a concept and its governed version (JSON)
The single-band raster data type: the concept (its meaning, label, definition and broader
type) and its governed version (object identifier, validity/publication status and the
recorded addition proposed by GeoLabs). It names a kind of data, not an encoding.

#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1",
  "type": "DataTypeVersion",
  "versionOf": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band",
    "type": "DataType",
    "prefLabel": "Raster (single band)",
    "definition": "A raster with exactly one band: a range type of one field.",
    "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types",
    "broader": [
      "https://geolabs.github.io/bblocks-data-types/def/data-type/raster"
    ]
  },
  "version": "1.0",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1",
  "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
    "startedAtTime": "2026-10-08T00:00:00Z"
  }
}

```


### Shared register metadata
This Turtle graph contains the shared register, register system, owner and concept system.
Each data-type Building Block publishes its own canonical concept, version and addition
action in its `ontology.ttl`.

#### turtle
```turtle
@prefix dt:   <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim:  <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct:  <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd:  <http://www.w3.org/2001/XMLSchema#> .

# Register-level metadata only. Each data-type concept, version and addition action is canonical
# in the ontology.ttl of its own data-type Building Block.

dt:register a rim:Register ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/register"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/"^^xsd:anyURI ;
    dct:title "Data Types"@en ;
    dct:description "A concept-plane register of the kinds of data that process profile inputs and outputs carry."@en ;
    rim:registerOwner dt:geolabs ;
    rim:registerManager dt:geolabs ;
    rim:runsOn dt:registerSystem ;
    dt:conceptSystem dt:dataTypes .

dt:geolabs a prov:Organization ;
    dct:title "GeoLabs SARL"@en .

dt:registerSystem a rim:RegisterSystem ;
    dct:title "OGC Building Blocks register (bblocks-postprocess, GitHub Pages)"@en .

dt:dataTypes a rim:ConceptSystem, skos:ConceptScheme ;
    dct:title "Data types"@en ;
    skos:prefLabel "Data types"@en ;
    dct:description "The kinds of data a process profile's inputs and outputs carry, independent of encoding."@en .

```


# JSON-LD Context

```jsonld
None
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-data-types/_sources/vocabulary/context.jsonld)

## Sources

* [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
* [OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)
* [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
* [OGC 17-030r1 LAS Specification 1.4 OGC Community Standard](https://www.ogc.org/standards/las/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/vocabulary`

