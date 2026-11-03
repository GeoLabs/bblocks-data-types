
# Data Types shared concept model (Model)

`data-types.vocabulary` *v0.1*

Shared RIM concept-plane model, register metadata, and SHACL rules for the individual data-type Building Blocks in this register.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

Data types as a Registered Item Model **concept plane**, with a content-plane item per data type.

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
version and proposed-addition action. The JSON example below illustrates one item and the version it realizes; the Turtle
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

## Content plane and JSON binding

Each data type is also a register item in the Registered Item Model's content plane. Its
`dt:DataTypeItem` (a sub-class of `rim:RegisterItem`) is of the `dt:dataTypeItemClass` item class,
is in `dt:register`, and `rim:realizes` the data type's `dt:DataTypeVersion`; `dt:DataTypeItemShape`
checks this and is the class's `rim:validatedBy`.

The RIM publishes a JSON binding of its core: one JSON Schema and JSON-LD context per class. This
register conforms to it layer by layer, each block depending on the one below it, as the RIM's own
`register-item` depends on `register`, `register-item-class` and `concept-version`:

- [`data-types.register`](../register/) profiles `ogc.rim.schemas.register`: the register, its
  system and the roles that govern it.
- [`data-types.item-class`](../item-class/) profiles `ogc.rim.schemas.register-item-class`: the item
  class every data type item shares, defined in the register and validated by
  `dt:DataTypeItemShape`.
- `schema.yaml` of this block (it depends on both blocks) profiles `ogc.rim.schemas.register-item`
  (`type` is `DataTypeItem`, `itemClass` and `inRegister` are fixed to that item class and register)
  and its `realizes` profiles `ogc.rim.schemas.concept-version` (`type` is `DataTypeVersion`, with
  the recorded addition required).
- Each data-type block profiles this schema again and fixes the item's `id`.

The register and item class blocks take the register metadata of this block's `data.ttl` as SHACL
closure, so their JSON examples do not repeat it.

The item class and register nodes that `data.ttl` and each `ontology.ttl` already declare are not
repeated in the JSON examples: the SHACL closure supplies them, and a second value for a
single-valued property such as `dct:title` would be a violation.

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

### One data type as a register item realizing its governed version (JSON)
The single-band raster data type: the register item (content plane) of the register's data
type item class, realizing the governed version (object identifier, validity/publication
status and the recorded addition proposed by GeoLabs) of the concept. It names a kind of data,
not an encoding.

#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band",
      "type": "Concept",
      "prefLabel": "Raster (single band)",
      "definition": "A raster with exactly one band: a range type of one field.",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
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
  },
  "validityStatus": "invalid",
  "publicationStatus": "published"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/context.jsonld",
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band",
      "type": "Concept",
      "prefLabel": "Raster (single band)",
      "definition": "A raster with exactly one band: a range type of one field.",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
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
  },
  "validityStatus": "invalid",
  "publicationStatus": "published"
}
```

#### ttl
```ttl
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/item> a dt:DataTypeItem ;
    rim:inRegister dt:register ;
    rim:itemClass dt:dataTypeItemClass ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/item"^^xsd:anyURI ;
    rim:publicationStatus rim:published ;
    rim:realizes <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1> ;
    rim:validityStatus rim:invalid .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band> a rim:Concept ;
    skos:definition "A raster with exactly one band: a range type of one field." ;
    skos:inScheme dt:data-types ;
    skos:prefLabel "Raster (single band)" .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/actions/addition> a rim:RegisterAction ;
    prov:startedAtTime "2026-10-08T00:00:00+00:00"^^xsd:dateTime ;
    rim:actionType rim:additionAction ;
    rim:proposer dt:geolabs .

<https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1> a dt:DataTypeVersion ;
    dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/actions/addition> ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band"^^xsd:anyURI ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band/v1"^^xsd:anyURI ;
    rim:publicationStatus rim:published ;
    rim:validityStatus rim:invalid ;
    rim:version "1.0" ;
    rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band> .


```


### Shared register metadata
This Turtle graph contains the shared register, register system, owner, concept system and
the data type item class. Each data-type Building Block publishes its own canonical concept,
version, addition action and item in its `ontology.ttl`.

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

dt:dataTypeItemClass a rim:RegisterItemClass ;
    dct:title "Data type" ;
    dct:description "The abstraction every data type item of this register shares: one item per data type, realizing its governed concept version."@en ;
    rim:definedIn dt:register ;
    rim:validatedBy dt:DataTypeItemShape .

dt:geolabs a prov:Organization ;
    dct:title "GeoLabs SARL"@en .

dt:registerSystem a rim:RegisterSystem ;
    dct:title "OGC Building Blocks register (bblocks-postprocess, GitHub Pages)"@en .

dt:dataTypes a rim:ConceptSystem, skos:ConceptScheme ;
    dct:title "Data types"@en ;
    skos:prefLabel "Data types"@en ;
    dct:description "The kinds of data a process profile's inputs and outputs carry, independent of encoding."@en .

```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data type item
description: 'The content-plane record of a data type, in JSON: a profile of the Registered
  Item Model register item (`type` pinned to `DataTypeItem`) whose `realizes` is the
  data type''s governed version, a profile of the RIM concept version (`type` pinned
  to `DataTypeVersion`, recorded addition required). The data type is the `versionOf`
  concept; the concept-version schema fixes the type of an embedded concept to `Concept`,
  so its `dt:DataType` class comes from the register''s ontologies.'
allOf:
- $ref: https://ogcincubator.github.io/registered-item-model/build/annotated/rim/schemas/register-item/schema.yaml
type: object
required:
- realizes
properties:
  type:
    const: DataTypeItem
    x-jsonld-id: '@type'
  itemClass:
    const: https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass
    x-jsonld-id: https://w3id.org/ogc/rim/itemClass
    x-jsonld-type: '@id'
  inRegister:
    const: https://geolabs.github.io/bblocks-data-types/def/register
    x-jsonld-id: https://w3id.org/ogc/rim/inRegister
    x-jsonld-type: '@id'
  realizes:
    allOf:
    - $ref: https://ogcincubator.github.io/registered-item-model/build/annotated/rim/schemas/concept-version/schema.yaml
    type: object
    required:
    - hasAction
    properties:
      type:
        const: DataTypeVersion
        x-jsonld-id: '@type'
      hasAction:
        type: object
        required:
        - id
        - actionType
        - proposer
        properties:
          id:
            type: string
            format: uri
            x-jsonld-id: '@id'
          type:
            const: RegisterAction
            x-jsonld-id: '@type'
          actionType:
            const: addition
            x-jsonld-id: https://w3id.org/ogc/rim/actionType
            x-jsonld-type: '@vocab'
          proposer:
            type: string
            format: uri
            x-jsonld-id: https://w3id.org/ogc/rim/proposer
            x-jsonld-type: '@id'
          startedAtTime:
            type: string
            format: date-time
            x-jsonld-id: http://www.w3.org/ns/prov#startedAtTime
            x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
        x-jsonld-id: https://geolabs.github.io/bblocks-data-types/def/hasVersionAction
        x-jsonld-type: '@id'
    x-jsonld-id: https://w3id.org/ogc/rim/realizes
    x-jsonld-type: '@id'
x-jsonld-extra-terms:
  ConceptSystem: https://w3id.org/ogc/rim/ConceptSystem
  Concept: https://w3id.org/ogc/rim/Concept
  RegisterAction: https://w3id.org/ogc/rim/RegisterAction
  Register: https://w3id.org/ogc/rim/Register
  RegisterItem: https://w3id.org/ogc/rim/RegisterItem
  RegisterItemClass: https://w3id.org/ogc/rim/RegisterItemClass
  DataTypeItem: https://geolabs.github.io/bblocks-data-types/def/DataTypeItem
  DataType: https://geolabs.github.io/bblocks-data-types/def/DataType
  DataTypeVersion: https://geolabs.github.io/bblocks-data-types/def/DataTypeVersion
  prefLabel: http://www.w3.org/2004/02/skos/core#prefLabel
  definition: http://www.w3.org/2004/02/skos/core#definition
  inScheme:
    x-jsonld-id: http://www.w3.org/2004/02/skos/core#inScheme
    x-jsonld-type: '@id'
  broader:
    x-jsonld-id: http://www.w3.org/2004/02/skos/core#broader
    x-jsonld-type: '@id'
  concepts:
    x-jsonld-reverse: skos:inScheme
  conceptSystem:
    x-jsonld-id: https://geolabs.github.io/bblocks-data-types/def/conceptSystem
    x-jsonld-type: '@id'
  versionOf:
    x-jsonld-id: https://w3id.org/ogc/rim/versionOf
    x-jsonld-type: '@id'
  version: https://w3id.org/ogc/rim/version
  objectIdentifier:
    x-jsonld-id: https://w3id.org/ogc/rim/objectIdentifier
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#anyURI
  functionalIdentifier:
    x-jsonld-id: https://w3id.org/ogc/rim/functionalIdentifier
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#anyURI
  validityStatus:
    x-jsonld-id: https://w3id.org/ogc/rim/validityStatus
    x-jsonld-type: '@vocab'
  publicationStatus:
    x-jsonld-id: https://w3id.org/ogc/rim/publicationStatus
    x-jsonld-type: '@vocab'
  valid: https://w3id.org/ogc/rim/valid
  invalid: https://w3id.org/ogc/rim/invalid
  published: https://w3id.org/ogc/rim/published
  unpublished: https://w3id.org/ogc/rim/unpublished
  appliesTo:
    x-jsonld-id: https://w3id.org/ogc/rim/appliesTo
    x-jsonld-type: '@id'
  addition: https://w3id.org/ogc/rim/additionAction
  source: http://purl.org/dc/terms/source
  title: http://purl.org/dc/terms/title
  link:
    x-jsonld-id: http://purl.org/dc/terms/references
    x-jsonld-type: '@id'
x-jsonld-prefixes:
  rim: https://w3id.org/ogc/rim/
  dt: https://geolabs.github.io/bblocks-data-types/def/
  skos: http://www.w3.org/2004/02/skos/core#
  xsd: http://www.w3.org/2001/XMLSchema#
  prov: http://www.w3.org/ns/prov#
  dct: http://purl.org/dc/terms/
x-bblocks-metadata:
  itemIdentifier: data-types.vocabulary
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-03'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "Register": "rim:Register",
    "RegisterSystem": "rim:RegisterSystem",
    "RegisterSpecification": "rim:RegisterSpecification",
    "RegisterItemClass": "rim:RegisterItemClass",
    "RegisterItem": "rim:RegisterItem",
    "RegisterAction": "rim:RegisterAction",
    "Concept": "rim:Concept",
    "ConceptVersion": "rim:ConceptVersion",
    "ConceptSystem": "rim:ConceptSystem",
    "Commitment": "rim:Commitment",
    "Agent": "prov:Agent",
    "Organization": "prov:Organization",
    "Person": "prov:Person",
    "label": "rdfs:label",
    "prefLabel": "skos:prefLabel",
    "definition": "skos:definition",
    "inScheme": {
      "@id": "skos:inScheme",
      "@type": "@id"
    },
    "runsOn": {
      "@id": "rim:runsOn",
      "@type": "@id"
    },
    "hasSpecification": {
      "@id": "rim:hasSpecification",
      "@type": "@id"
    },
    "definesSubstantiveChange": "rim:definesSubstantiveChange",
    "registerOwner": {
      "@id": "rim:registerOwner",
      "@type": "@id"
    },
    "registerManager": {
      "@id": "rim:registerManager",
      "@type": "@id"
    },
    "controlBody": {
      "@id": "rim:controlBody",
      "@type": "@id"
    },
    "registerSystemManager": {
      "@id": "rim:registerSystemManager",
      "@type": "@id"
    },
    "registerUser": {
      "@id": "rim:registerUser",
      "@type": "@id"
    },
    "hasCommitment": {
      "@id": "rim:hasCommitment",
      "@type": "@id"
    },
    "commitmentCategory": {
      "@id": "rim:commitmentCategory",
      "@type": "@vocab"
    },
    "access": "rim:accessCommitment",
    "persistence": "rim:persistenceCommitment",
    "transparency": "rim:transparencyCommitment",
    "definedIn": {
      "@id": "rim:definedIn",
      "@type": "@id"
    },
    "validatedBy": {
      "@id": "rim:validatedBy",
      "@type": "@id"
    },
    "versionOf": {
      "@id": "rim:versionOf",
      "@type": "@id"
    },
    "version": "rim:version",
    "valid": "rim:valid",
    "invalid": "rim:invalid",
    "published": "rim:published",
    "unpublished": "rim:unpublished",
    "appliesTo": {
      "@id": "rim:appliesTo",
      "@type": "@id"
    },
    "proposer": {
      "@id": "rim:proposer",
      "@type": "@id"
    },
    "actionType": {
      "@id": "rim:actionType",
      "@type": "@vocab"
    },
    "addition": "rim:additionAction",
    "publish": "rim:publishAction",
    "unpublish": "rim:unpublishAction",
    "invalidation": "rim:invalidationAction",
    "supersession": "rim:supersessionAction",
    "redaction": "rim:redactionAction",
    "deletion": "rim:deletionAction",
    "changeClassification": {
      "@id": "rim:changeClassification",
      "@type": "@vocab"
    },
    "substantive": "rim:substantiveChange",
    "clarifying": "rim:clarifyingChange",
    "correctional": "rim:correctionalChange",
    "startedAtTime": {
      "@id": "prov:startedAtTime",
      "@type": "xsd:dateTime"
    },
    "endedAtTime": {
      "@id": "prov:endedAtTime",
      "@type": "xsd:dateTime"
    },
    "wasAssociatedWith": {
      "@id": "prov:wasAssociatedWith",
      "@type": "@id"
    },
    "id": "@id",
    "type": "@type",
    "objectIdentifier": {
      "@id": "rim:objectIdentifier",
      "@type": "xsd:anyURI"
    },
    "functionalIdentifier": {
      "@id": "rim:functionalIdentifier",
      "@type": "xsd:anyURI"
    },
    "itemClass": {
      "@id": "rim:itemClass",
      "@type": "@id"
    },
    "inRegister": {
      "@id": "rim:inRegister",
      "@type": "@id"
    },
    "realizes": {
      "@context": {
        "hasAction": {
          "@id": "dt:hasVersionAction",
          "@type": "@id"
        }
      },
      "@id": "rim:realizes",
      "@type": "@id"
    },
    "validityStatus": {
      "@id": "rim:validityStatus",
      "@type": "@vocab"
    },
    "publicationStatus": {
      "@id": "rim:publicationStatus",
      "@type": "@vocab"
    },
    "isRedacted": {
      "@id": "rim:isRedacted",
      "@type": "xsd:boolean"
    },
    "isDeleted": {
      "@id": "rim:isDeleted",
      "@type": "xsd:boolean"
    },
    "title": "dct:title",
    "description": "dct:description",
    "relatedItem": {
      "@id": "rim:relatedItem",
      "@type": "@id"
    },
    "supersededBy": {
      "@id": "rim:supersededBy",
      "@type": "@id"
    },
    "supersedes": {
      "@id": "rim:supersedes",
      "@type": "@id"
    },
    "hasAction": {
      "@id": "rim:hasAction",
      "@type": "@id"
    },
    "DataTypeItem": "dt:DataTypeItem",
    "DataType": "dt:DataType",
    "DataTypeVersion": "dt:DataTypeVersion",
    "broader": {
      "@id": "skos:broader",
      "@type": "@id"
    },
    "concepts": {
      "@reverse": "skos:inScheme"
    },
    "conceptSystem": {
      "@id": "dt:conceptSystem",
      "@type": "@id"
    },
    "source": "dct:source",
    "link": {
      "@id": "dct:references",
      "@type": "@id"
    },
    "rim": "https://w3id.org/ogc/rim/",
    "prov": "http://www.w3.org/ns/prov#",
    "dct": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "dt": "https://geolabs.github.io/bblocks-data-types/def/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/context.jsonld)

## Sources

* [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
* [OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)
* [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
* [OGC 17-030r1 LAS Specification 1.4 OGC Community Standard](https://www.ogc.org/standards/las/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/vocabulary`

