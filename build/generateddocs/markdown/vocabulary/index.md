
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
register specification, register system, owner and `rim:ConceptSystem`. The individual ontologies carry each concept,
version and proposed-addition action. The JSON example below illustrates one item and the version it realizes; the Turtle
example references the support block's register metadata.

The initial types are `raster`, `raster-single-band`, `raster-multi-band`, `elevation-model`,
`geometry`, `point`, `curve`, `surface`, `feature-collection`, `point-cloud`, `tin`, `table`,
`bounding-box`, `number`, `string` and `boolean`. `coordinate-reference-system`, `expression`,
`format-identifier` and `radiometric-index` were added for four Generic Profile roles of
`bblocks-generic-profiles` that declare `string` for something that is not a character string
(`raster-reprojection/targetCRS`, `raster-band-math/expression`,
`raster-format-conversion/targetFormat`, `radiometric-index/index`); each names the role that
requests it and has no broader type. `band-identifier`, `eo-product`, `grid-resolution`, `binary-mask`,
`colour-map`, `rendered-image`, `time-interval` and `collection-identifier` were added on 2026-11-10
for the roles of six new Generic Profiles of `bblocks-generic-profiles` (band retrieval, product
selection, raster resampling, thresholding and rendering); each names the role that requests it, and
only `binary-mask` has a broader type, `raster-single-band`.

The 19 fixed string formats in
[`eoap/schemas/string_format.yaml`](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
were registered as individual specializations of `string`, as proposals: date, date-time,
duration, email, hostname, idn-email, idn-hostname, ipv4, ipv6, iri, iri-reference, password,
json-pointer, relative-json-pointer, uuid, uri, uri-reference, uri-template and time. They are
formats, not kinds of data: the data-formats register holds them, with `Pattern`, as `df:Format`
items (`df:format/string-*`), and the 19 types are withdrawn: see "Content plane".

The geometry types of OGC Simple Feature Access are represented individually: besides `point`,
`curve` and `surface`, the `line-string` (under `curve`), `polygon` (under `surface`) and
`geometry-collection` entries are narrower geometry concepts, and `multi-point`, `multi-curve` and
`multi-surface` are collections, hence narrower than `geometry-collection`; `multi-line-string` is
a `multi-curve` and `multi-polygon` a `multi-surface` (OGC CDB 2.0 Core, 23-034, 7.6). `line` and
`linear-ring` are narrower than `line-string`, `triangle` than `polygon`, and `polyhedral-surface`
than `surface`; `tin` is a `polyhedral-surface` (geometry model of 23-034, 7.6.1). A `feature`, which
wraps a geometry with properties, is a type of its own. Four STAC types were registered from
[`radiantearth/stac-spec`](https://github.com/radiantearth/stac-spec), as proposals: `stac-item`
under `feature`, `stac-item-collection` under `feature-collection`, `stac-collection` under
`stac-catalog`, and `stac-catalog`. No role uses them, and their definitions describe STAC JSON
objects, which are encodings. They are withdrawn (2026-11-11, decision Q4, option b) like the
`string-*` types: each item and its version are unpublished, with an unpublication action classified
substantive, and the item carries `dct:isReplacedBy` towards the format `df:format/stac-*` of the same
name, which carries `rim:supersedes`. Their `skos:broader` links are kept as recorded.

## Content plane and JSON binding

Each data type is also a register item in the Registered Item Model's content plane. Its
`dt:DataTypeItem` (a sub-class of `rim:RegisterItem`) is of the `dt:dataTypeItemClass` item class,
is in `dt:register`, and `rim:realizes` the data type's `dt:DataTypeVersion`; `dt:DataTypeItemShape`
checks this and is the class's `rim:validatedBy`. This item is the record of the type in this
register; it says nothing about an encoding.

Encodings are held by the data-formats register
([`GeoLabs/bblocks-data-formats`](https://github.com/GeoLabs/bblocks-data-formats), prefix `df:`).
A `df:Format` is an encoding and realizes no version; a `df:Representation` realizes
(`rim:realizes`) at most one `dt:DataTypeVersion` of this register and points to one format, e.g.
`df:representation/raster-geotiff` realizes `raster/v1`. A version of this register may therefore be
realized by its own `dt:DataTypeItem` and by representations of data-formats (the Registered Item
Model limits `rim:realizes` per item, not per version). data-formats depends on this register; this
register never depends on data-formats.

The 19 `string-*` types (2026-11-09) and the four `stac-*` types (2026-11-11) are withdrawn: each item and its version are `rim:unpublished` and stay `rim:invalid`, with
an action of type `rim:unpublishAction` classified `rim:substantiveChange` next to the addition, and
the item carries `dct:isReplacedBy` towards the matching `df:format/string-*` or `df:format/stac-*`. The Registered Item
Model link, `rim:supersedes`, is carried by the format in data-formats, because `rim:RegisterItemShape`
rejects a `rim:supersededBy` towards an item this register does not type, and this register does not
depend on data-formats. Nothing is deleted and no IRI changes.

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

The register and item class blocks load the register metadata of this block's `data.ttl` as a data
resource, so their JSON examples do not repeat it.

The data resources of a block (`resources` with role `data` in `bblock.json`) are part of the SHACL
closure of that block and of every block that depends on it, in this register or in a register that
imports it; their references are published as absolute URLs. This block lists `data.ttl` and the
`ontology.ttl` of every data type there, and declares no `shaclClosures`: a relative closure path is
published as is, and fails to load in an importing register.

The item class and register nodes that `data.ttl` and each `ontology.ttl` already declare are not
repeated in the JSON examples: the SHACL closure supplies them, and a second value for a
single-valued property such as `dct:title` would be a violation.

## Meaning, not encoding

A data type names the **kind** of data, not its **encoding**. The byte format a concrete process
uses is a `df:Format` of the data-formats register, bound to a data type by a `df:Representation`;
an Implementation Profile still declares it in its own `schema` until it points to a
representation. This is the same meaning / representation split the concept plane exists for.

That boundary is an intent, not an absolute: a few types are grounded in a standard that happens to
be a format -- `point-cloud` cites the OGC LAS community standard, and the `string-*` types are named
after JSON Schema formats. Those are the concept's **source**, not an encoding asserted on it.
Definitions otherwise avoid naming a format: the geometry types, for example, are defined from
Simple Feature Access, not from any encoding of them. Descriptions may still show an encoding
(GeoJSON, JSON Schema `format`) as an illustration only.

## Governance: a proposed addition, not a status

The rules are those of the register specification, `dt:specification` in [`data.ttl`](data.ttl): a
concept register, GeoLabs as owner, manager and, for now, control body, with the intention to
delegate that role; the definition of a substantive change and the table of substantive and
clarifying changes; the rule for proposals, which are amended in place with a classified action of
type `dt:amendmentAction`. No eligibility criteria and no commitments are set.

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
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

# Register-level metadata only. Each data-type concept, version and addition action is canonical
# in the ontology.ttl of its own data-type Building Block.

dt:register a rim:Register ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/register"^^xsd:anyURI ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/"^^xsd:anyURI ;
    dct:title "Data Types"@en ;
    dct:description "A concept-plane register of the kinds of data that process profile inputs and outputs carry."@en ;
    rim:registerOwner dt:geolabs ;
    rim:registerManager dt:geolabs ;
    rim:controlBody dt:geolabs ;
    rim:hasSpecification dt:specification ;
    rim:runsOn dt:registerSystem ;
    dt:conceptSystem dt:dataTypes .

# The register specification. rim:definesSubstantiveChange, the rule for proposals and the table of
# substantive and clarifying changes are the texts validated by GeoLabs on 2026-11-05, word for word;
# the table was validated in French and is given verbatim, followed by an English rendering.
# vocabulary/tests/specification-without-title-fail.ttl proves that rim:RegisterSpecificationShape
# runs on this register.
dt:specification a rim:RegisterSpecification ;
    dct:title "Data Types register specification"@en ;
    dct:description
        "Scope. This register holds the data types of process profile inputs and outputs: the kinds of data they carry, named independently of any encoding. Formats and representations are not items of this register; they are held by the data-formats register (https://w3id.org/geolabs/ospd/data-formats/)."@en ,
        "Register type. A concept register, as the Registered Item Model uses the term. Each data type is a dt:DataType, a rim:Concept of the dt:dataTypes concept system, and its governed state is a dt:DataTypeVersion. Each version is realized (rim:realizes) by one dt:DataTypeItem of this register."@en ,
        "Relation with the data-formats register. A df:Representation item of the data-formats register realizes (rim:realizes) at most one dt:DataTypeVersion of this register and points to a df:Format. The Registered Item Model allows a version of this register to be realized by items of both registers: it limits rim:realizes to one version per item (rim:RegisterItemShape), not to one item per version. The data-formats register depends on this register; this register never depends on the data-formats register."@en ,
        "Roles. GeoLabs SARL is the register owner, the register manager and, for now, the control body. GeoLabs intends to delegate the control body role to the OGC or to an OSPD working group."@en ,
        "Identifiers. The object identifier of a data type is its IRI, https://geolabs.github.io/bblocks-data-types/def/data-type/<name>; its version is <name>/v1 and its register item <name>/item. The functional identifier of a version is the IRI of its data type. An object identifier never redirects; only a functional identifier may. The identifier of a published item changes only by an explicit decision."@en ,
        "Versions. An addition is an action of type addition, with no classification. A substantive change creates a new item or a new version, linked by rim:supersededBy, with an action classified substantive. A clarifying change keeps the item and its version, with an action classified clarifying. This version rule is specific to the registers of this project and does not come from ISO 19135. The classification correctional is not available. An item is retired by unpublishing it, not by deleting it."@en ,
        "Ce qui est substantiel ici (tableau validé le 2026-11-05, repris tel quel). Substantiel : Définition qui change ce que le type recouvre, `skos:broader` modifié, retrait d'un type. Clarification : Coquille, reformulation de même sens, source ajoutée."@fr ,
        "What is substantive here (English rendering of the validated table above). Substantive: a definition that changes what the type covers, a modified skos:broader, the retirement of a type. Clarifying: a typo, a rewording with the same meaning, an added source."@en ,
        "Withdrawal of a type. A type is withdrawn by unpublishing its item and its version, with an action of type rim:unpublishAction classified substantive; nothing is deleted. When the item is replaced by an item of the data-formats register, the item of this register carries dct:isReplacedBy towards it, and the Registered Item Model link rim:supersedes is carried by the data-formats item, because this register does not depend on data-formats."@en ,
        "Proposals. While an item is a proposal, with no control-body decision recorded, it is amended in place, with a classified `rim:RegisterAction`. The substantive rule applies once it has been accepted."@en ,
        "Amendment. dt:amendmentAction is the action type of an in-place change to a proposal, an item with no control-body decision recorded. Such an action is always classified, clarifying or substantive: it is the classified rim:RegisterAction of the rule for proposals. This type is specific to this register and will be replaced if the Registered Item Model defines one."@en ,
        "Eligibility. No eligibility criteria for proposers have been set. GeoLabs is the only proposer recorded so far."@en ,
        "Commitments. No commitment to register users has been set."@en ;
    rim:definesSubstantiveChange "A change is substantive when a register user may have to change their data, profiles or processes because of it, or when it changes what an item means. Any other change to an existing item is clarifying." .

# rim:actionType is required and the Registered Item Model has no type for an in-place change of a
# proposal; it lets a register specification define further action types. Defined by
# dt:specification, specific to this register.
dt:amendmentAction a rim:RegisterActionType , skos:Concept ;
    rdfs:isDefinedBy dt: ;
    skos:prefLabel "amendment"@en ;
    skos:definition "An in-place change to a proposal, an item with no control-body decision recorded. Always classified, clarifying or substantive."@en .

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
  isReplacedBy:
    x-jsonld-id: http://purl.org/dc/terms/isReplacedBy
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
  dateOfLastChange: '2026-11-12'

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
    "isReplacedBy": {
      "@id": "dct:isReplacedBy",
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

