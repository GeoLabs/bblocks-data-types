
# Data type: Radiometric index (Model)

`data-types.data-type.radiometric-index` *v1.0*

A quantity derived by combining the radiometric values of several spectral bands, designed to highlight a property of the observed surface such as vegetation or water.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A quantity derived by combining the radiometric values of several spectral bands, designed to highlight a property of the observed surface such as vegetation or water.

## Definition

`https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

A value of this type designates one such index (for example NDVI); how it is named is a representation, not part of the type.

## Requested by

Added because existing roles of `bblocks-generic-profiles` need it. They declare the data type
`string` today (branch `planes/phase-1-docs`, `b0da6aa`); pointing them to this type is a change of
that register, not made here.

- [`generic-profile/radiometric-index/inputs/index`](https://w3id.org/geolabs/ospd/generic-profiles/generic-profile/radiometric-index/inputs/index): the name of the radiometric index (or indices) to compute
- [`implementation-profile/radiometric-index/inputs/index`](https://w3id.org/geolabs/ospd/generic-profiles/implementation-profile/radiometric-index/inputs/index)

## Hierarchy

- Broader: none (top-level data type). It is not a narrower type of String: what it names is not a
  character string, even if a string can represent it.
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile radiometric-index (bblocks-generic-profiles), the role that requests this type](https://w3id.org/geolabs/ospd/generic-profiles/generic-profile/radiometric-index/inputs/index)

## Examples

### Radiometric index
The register item of the Radiometric index data type: it realizes the governed version of the concept and belongs to the register's data type item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item",
  "itemClass": "https://w3id.org/geolabs/ospd/data-types/dataTypeItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-types/register",
  "realizes": {
    "id": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index",
      "type": "Concept",
      "prefLabel": "Radiometric index",
      "definition": "A quantity derived by combining the radiometric values of several spectral bands, designed to highlight a property of the observed surface such as vegetation or water.",
      "inScheme": "https://w3id.org/geolabs/ospd/data-types/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/v1",
    "functionalIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-types/geolabs",
      "startedAtTime": "2026-11-09T00:00:00Z"
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

<https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Radiometric index"@en ; skos:definition "A quantity derived by combining the radiometric values of several spectral bands, designed to highlight a property of the observed surface such as vegetation or water."@en ; dct:source [ dct:title "Generic Profile radiometric-index (bblocks-generic-profiles), the role that requests this type"@en ; dct:references <https://w3id.org/geolabs/ospd/generic-profiles/generic-profile/radiometric-index/inputs/index> ] .
<https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index> ; rim:version "1.0" ; rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/actions/addition> .
<https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime .
<https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item> a dt:DataTypeItem, rim:RegisterItem ; dct:title "Radiometric index"@en ; rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item"^^xsd:anyURI ; rim:itemClass dt:dataTypeItemClass ; rim:inRegister dt:register ; rim:realizes <https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/v1> ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published .

<https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/radiometric-index> .
<https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/v1> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/radiometric-index/v1> .
<https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/radiometric-index/item> ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/actions/identifier-2026-11-17> .

<https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/actions/identifier-2026-11-17> a rim:RegisterAction ;
    rim:actionType dt:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty rim:objectIdentifier ;
    dct:description "The object identifier of this item moves from https://geolabs.github.io/bblocks-data-types/def/data-type/radiometric-index/item to https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item, which resolves through w3id.org (decision of 2026-11-17); the register actions of the item move with it, under https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/actions/. The old IRI is kept as owl:sameAs. The content of the item is unchanged. Classified clarifying: the item is the same, only its identifier changes. The data type and its version keep their old IRIs as owl:sameAs too."@en ;
    rim:proposer dt:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item> ;
    prov:startedAtTime "2026-11-17T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/radiometric-index/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item",
  "itemClass": "https://w3id.org/geolabs/ospd/data-types/dataTypeItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-types/register",
  "realizes": {
    "id": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index",
      "type": "Concept",
      "prefLabel": "Radiometric index",
      "definition": "A quantity derived by combining the radiometric values of several spectral bands, designed to highlight a property of the observed surface such as vegetation or water.",
      "inScheme": "https://w3id.org/geolabs/ospd/data-types/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/v1",
    "functionalIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-types/geolabs",
      "startedAtTime": "2026-11-09T00:00:00Z"
    }
  },
  "validityStatus": "invalid",
  "publicationStatus": "published"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data type item - Radiometric index
description: The register item of the Radiometric index data type, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-types/data-type/radiometric-index/item
x-bblocks-metadata:
  itemIdentifier: data-types.data-type.radiometric-index
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '1.0'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/radiometric-index/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/radiometric-index/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/radiometric-index/context.jsonld)

## Sources

* [Generic Profile radiometric-index (bblocks-generic-profiles), the role that requests this type](https://w3id.org/geolabs/ospd/generic-profiles/generic-profile/radiometric-index/inputs/index)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/radiometric-index`

