
# Data type: Elevation model (Model)

`data-types.data-type.elevation-model` *v1.0*

A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

## Examples

### Elevation model
The register item of the Elevation model data type: it realizes the governed version of the concept and belongs to the register's data type item class.
#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model",
      "type": "Concept",
      "prefLabel": "Elevation model",
      "definition": "A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM).",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1",
    "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/addition",
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

#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Elevation model"@en ; skos:definition "A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM)."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/raster-single-band> ; dct:source [ dct:title "OGC 09-146r8 Coverage Implementation Schema (CIS) 1.1.1, §6.5 RangeType"@en ; dct:references <https://docs.ogc.org/is/09-146r8/09-146r8.html> ], [ dct:title "INSPIRE D2.8.II.1 Data Specification on Elevation – Technical Guidelines, D2.8.II.1_v3.3.0 (2024-01-31): Executive Summary, and §2.4 Terms and definitions, (6) Digital Elevation Model, (7) Digital Surface Model, (8) Digital Terrain Model"@en ; dct:references <https://inspire.ec.europa.eu/id/document/tg/el> ]; skos:scopeNote "INSPIRE also admits vector and TIN representations of an elevation model; this type covers the grid one."@en .
<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/addition>, <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/amendment-source>, <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/amendment-inspire-version> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .
<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item> a dt:DataTypeItem, rim:RegisterItem ; dct:title "Elevation model"@en ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item"^^xsd:anyURI ; rim:itemClass dt:dataTypeItemClass ; rim:inRegister dt:register ; rim:realizes <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1> ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published; rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/amendment-source>, <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/amendment-inspire-version> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/amendment-source> a rim:RegisterAction ; rim:actionType dt:amendmentAction ; rim:changeClassification rim:clarifyingChange ; rim:proposer dt:geolabs ; rim:appliesTo <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item> ; rim:affectedProperty dct:source ; prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime ; dct:description "In-place amendment of a proposal: the source SAGA 7.3.0 Terrain Analysis tools, a tool, is replaced by the INSPIRE Data Specification on Elevation, which defines digital elevation, terrain and surface models. The definition is unchanged. Classified clarifying: a source changes and the type covers the same data."@en .
<https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/amendment-inspire-version> a rim:RegisterAction ; rim:actionType dt:amendmentAction ; rim:changeClassification rim:clarifyingChange ; rim:proposer dt:geolabs ; rim:appliesTo <https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item> ; rim:affectedProperty dct:source, skos:scopeNote ; prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime ; dct:description "In-place amendment of a proposal: the INSPIRE source now gives its version, D2.8.II.1_v3.3.0, and cites the term definitions of its section 2.4, (6) to (8), besides the executive summary; a scope note says that INSPIRE also admits vector and TIN representations and that this type covers the grid one. The definition and skos:broader are unchanged. Classified clarifying: the type covers the same data."@en .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/elevation-model/context.jsonld",
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model",
      "type": "Concept",
      "prefLabel": "Elevation model",
      "definition": "A single-band raster whose values are elevations of the terrain or of a surface (DEM, DTM, DSM).",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/v1",
    "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/actions/addition",
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

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data type item - Elevation model
description: The register item of the Elevation model data type, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.yaml
properties:
  id:
    const: https://geolabs.github.io/bblocks-data-types/def/data-type/elevation-model/item
x-bblocks-metadata:
  itemIdentifier: data-types.data-type.elevation-model
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '1.0'
  dateOfLastChange: '2026-11-12'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/elevation-model/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/elevation-model/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/elevation-model/context.jsonld)

## Sources

* [OGC 09-146r8 CIS 1.1.1, §6.5 RangeType](https://docs.ogc.org/is/09-146r8/09-146r8.html)
* [INSPIRE D2.8.II.1 Data Specification on Elevation – Technical Guidelines, D2.8.II.1_v3.3.0 (2024-01-31): Executive Summary, and §2.4 Terms and definitions, (6) Digital Elevation Model, (7) Digital Surface Model, (8) Digital Terrain Model](https://inspire.ec.europa.eu/id/document/tg/el)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/elevation-model`

