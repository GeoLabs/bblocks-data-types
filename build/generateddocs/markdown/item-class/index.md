
# Data type item class (Schema)

`data-types.item-class` *v0.1*

The item class shared by the data type items of this register, in JSON: a profile of the Registered Item Model register item class.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The item class of the data type items, as a Registered Item Model **register item class**, in JSON.

## Definition

A profile of the RIM `register-item-class` schema: the abstraction every data type item of the
register shares (`dt:dataTypeItemClass`), defined in the register (`definedIn`) and validated by the
`dt:DataTypeItemShape` of the [shared vocabulary](../vocabulary/) (`validatedBy`).

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register-item-class`; `id` is fixed to the item
  class IRI, and `definedIn` and `validatedBy` are required.
- `examples.yaml`: the item class in JSON, validated against the schema, uplifted to RDF and checked
  against the shapes of the vocabulary.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)

## Examples

### The data type item class (JSON)
The abstraction every data type item shares. `validatedBy` names the executable rule set (the SHACL shape of the vocabulary) that expresses its data requirements.
#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "type": "RegisterItemClass",
  "title": "Data type",
  "definedIn": "https://geolabs.github.io/bblocks-data-types/def/register",
  "validatedBy": "https://geolabs.github.io/bblocks-data-types/def/DataTypeItemShape"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/item-class/context.jsonld",
  "id": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "type": "RegisterItemClass",
  "title": "Data type",
  "definedIn": "https://geolabs.github.io/bblocks-data-types/def/register",
  "validatedBy": "https://geolabs.github.io/bblocks-data-types/def/DataTypeItemShape"
}
```

#### ttl
```ttl
@prefix dct: <http://purl.org/dc/terms/> .
@prefix rim: <https://w3id.org/ogc/rim/> .

<https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass> a rim:RegisterItemClass ;
    dct:title "Data type" ;
    rim:definedIn <https://geolabs.github.io/bblocks-data-types/def/register> ;
    rim:validatedBy <https://geolabs.github.io/bblocks-data-types/def/DataTypeItemShape> .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data type item class
description: The item class every data type item of the register shares, in JSON.
  It is defined in the data-types register and validated by the vocabulary's `DataTypeItemShape`.
allOf:
- $ref: https://ogcincubator.github.io/registered-item-model/build/annotated/rim/schemas/register-item-class/schema.yaml
required:
- definedIn
- validatedBy
properties:
  id:
    const: https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass
x-bblocks-metadata:
  itemIdentifier: data-types.item-class
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-03'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/item-class/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/item-class/schema.yaml)


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
    "itemClass": {
      "@id": "rim:itemClass",
      "@type": "@id"
    },
    "inRegister": {
      "@id": "rim:inRegister",
      "@type": "@id"
    },
    "realizes": {
      "@id": "rim:realizes",
      "@type": "@id"
    },
    "versionOf": {
      "@id": "rim:versionOf",
      "@type": "@id"
    },
    "version": "rim:version",
    "validityStatus": {
      "@id": "rim:validityStatus",
      "@type": "@vocab"
    },
    "publicationStatus": {
      "@id": "rim:publicationStatus",
      "@type": "@vocab"
    },
    "valid": "rim:valid",
    "invalid": "rim:invalid",
    "published": "rim:published",
    "unpublished": "rim:unpublished",
    "isRedacted": {
      "@id": "rim:isRedacted",
      "@type": "xsd:boolean"
    },
    "isDeleted": {
      "@id": "rim:isDeleted",
      "@type": "xsd:boolean"
    },
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
    "title": "dct:title",
    "description": "dct:description",
    "definedIn": {
      "@id": "rim:definedIn",
      "@type": "@id"
    },
    "validatedBy": {
      "@id": "rim:validatedBy",
      "@type": "@id"
    },
    "rim": "https://w3id.org/ogc/rim/",
    "prov": "http://www.w3.org/ns/prov#",
    "dct": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/item-class/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/item-class`

