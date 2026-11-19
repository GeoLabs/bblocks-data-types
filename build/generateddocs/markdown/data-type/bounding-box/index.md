
# Data type: Bounding box (Model)

`data-types.data-type.bounding-box` *v1.0*

An axis-aligned extent given by its corners, with its CRS.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

An axis-aligned extent given by its corners, with its CRS.

## Definition

`https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [ogc.api.processes.part1.v1.schemas.bbox, after OGC 17-069r4 §7.15.3 bbox](https://docs.ogc.org/is/17-069r4/17-069r4.html)

## Examples

### Bounding box
The register item of the Bounding box data type: it realizes the governed version of the concept and belongs to the register's data type item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item",
  "itemClass": "https://w3id.org/geolabs/ospd/data-types/dataTypeItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-types/register",
  "realizes": {
    "id": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box",
      "type": "Concept",
      "prefLabel": "Bounding box",
      "definition": "An axis-aligned extent given by its corners, with its CRS.",
      "inScheme": "https://w3id.org/geolabs/ospd/data-types/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/v1",
    "functionalIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-types/geolabs",
      "startedAtTime": "2026-10-08T00:00:00Z"
    }
  },
  "validityStatus": "invalid",
  "publicationStatus": "published"
}

```

#### turtle
```turtle
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix dt: <https://w3id.org/geolabs/ospd/data-types/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Bounding box"@en ; skos:definition "An axis-aligned extent given by its corners, with its CRS."@en ; dct:source [ dct:title "ogc.api.processes.part1.v1.schemas.bbox, after OGC 17-069r4 §7.15.3 bbox"@en ; dct:references <https://docs.ogc.org/is/17-069r4/17-069r4.html> ] .
<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box> ; rim:version "1.0" ; rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/addition> .
<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-10-08T00:00:00Z"^^xsd:dateTime .
<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item> a dt:DataTypeItem, rim:RegisterItem ; dct:title "Bounding box"@en ; rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item"^^xsd:anyURI ; rim:itemClass dt:dataTypeItemClass ; rim:inRegister dt:register ; rim:realizes <https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/v1> ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; rim:hasAction <https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/amendment-source-title> .
<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/amendment-source-title> a rim:RegisterAction ; rim:actionType dt:amendmentAction ; rim:changeClassification rim:clarifyingChange ; rim:proposer dt:geolabs ; rim:appliesTo <https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item> ; rim:affectedProperty dct:source ; prov:startedAtTime "2026-11-10T00:00:00Z"^^xsd:dateTime ; dct:description "In-place amendment of a proposal: the title of the source that names the OGC API - Processes bbox building block follows its renaming by GeoLabs on 2026-11-10, from ogc.api.processes.v1.schemas.bbox to ogc.api.processes.part1.v1.schemas.bbox (Part 1, edition 1.0). The source, the definition and skos:broader are unchanged. Classified clarifying: the type covers the same data."@en .

<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box> .
<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/v1> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/v1> .
<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/item> ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/identifier-2026-11-17> .

<https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/identifier-2026-11-17> a rim:RegisterAction ;
    rim:actionType dt:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty rim:objectIdentifier ;
    dct:description "The object identifier of this item moves from https://geolabs.github.io/bblocks-data-types/def/data-type/bounding-box/item to https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item, which resolves through w3id.org (decision of 2026-11-17); the register actions of the item move with it, under https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/. The old IRI is kept as owl:sameAs. The content of the item is unchanged. Classified clarifying: the item is the same, only its identifier changes. The data type and its version keep their old IRIs as owl:sameAs too."@en ;
    rim:proposer dt:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item> ;
    prov:startedAtTime "2026-11-17T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/bounding-box/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item",
  "itemClass": "https://w3id.org/geolabs/ospd/data-types/dataTypeItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-types/register",
  "realizes": {
    "id": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box",
      "type": "Concept",
      "prefLabel": "Bounding box",
      "definition": "An axis-aligned extent given by its corners, with its CRS.",
      "inScheme": "https://w3id.org/geolabs/ospd/data-types/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/v1",
    "functionalIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-types/geolabs",
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
title: Data type item - Bounding box
description: The register item of the Bounding box data type, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-types/data-type/bounding-box/item
x-bblocks-metadata:
  itemIdentifier: data-types.data-type.bounding-box
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '1.0'
  dateOfLastChange: '2026-11-19'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/bounding-box/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/bounding-box/schema.yaml)


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
    "dt": "https://w3id.org/geolabs/ospd/data-types/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/bounding-box/context.jsonld)

## Sources

* [ogc.api.processes.part1.v1.schemas.bbox, after OGC 17-069r4 §7.15.3 bbox](https://docs.ogc.org/is/17-069r4/17-069r4.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/bounding-box`

