
# Data Types register (Schema)

`data-types.register` *v0.1*

The data-types register itself, in JSON: a profile of the Registered Item Model register, with its system and the roles that govern it.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

The data-types register as a Registered Item Model **register**, in JSON.

## Definition

A profile of the RIM `register` schema: the governed collection of data types, distinct from the
register system it runs on (`runsOn`) and from the roles that govern it (`registerOwner`,
`registerManager`). Its title, description and concept system (`dt:conceptSystem`) are declared in
the `data.ttl` of the [shared vocabulary](../vocabulary/), which the SHACL closure of this block
includes.

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register`; `id` is fixed to the register's IRI and
  its identifier, system and owner are required.
- `examples.yaml`: the register in JSON, validated against the schema, uplifted to RDF and checked
  against the shapes of the vocabulary.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)

## Examples

### The data-types register (JSON)
The register, the system it runs on and its owner and manager. Its title, description and concept system are in the shared vocabulary's `data.ttl`.
#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/register",
  "type": "Register",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/register",
  "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/",
  "runsOn": "https://geolabs.github.io/bblocks-data-types/def/registerSystem",
  "registerOwner": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
  "registerManager": "https://geolabs.github.io/bblocks-data-types/def/geolabs"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/register/context.jsonld",
  "id": "https://geolabs.github.io/bblocks-data-types/def/register",
  "type": "Register",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/register",
  "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/",
  "runsOn": "https://geolabs.github.io/bblocks-data-types/def/registerSystem",
  "registerOwner": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
  "registerManager": "https://geolabs.github.io/bblocks-data-types/def/geolabs"
}
```

#### ttl
```ttl
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/register> a rim:Register ;
    rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/"^^xsd:anyURI ;
    rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/register"^^xsd:anyURI ;
    rim:registerManager <https://geolabs.github.io/bblocks-data-types/def/geolabs> ;
    rim:registerOwner <https://geolabs.github.io/bblocks-data-types/def/geolabs> ;
    rim:runsOn <https://geolabs.github.io/bblocks-data-types/def/registerSystem> .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data Types register
description: 'The data-types register, in JSON: the governed collection itself, the
  system it runs on and the roles that govern it. Its one concept system (`dt:conceptSystem`)
  is declared in the shared vocabulary''s `data.ttl`.'
allOf:
- $ref: https://ogcincubator.github.io/registered-item-model/build/annotated/rim/schemas/register/schema.yaml
required:
- objectIdentifier
- runsOn
- registerOwner
properties:
  id:
    const: https://geolabs.github.io/bblocks-data-types/def/register
x-bblocks-metadata:
  itemIdentifier: data-types.register
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-03'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/register/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/register/schema.yaml)


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
    "definesSubstantiveChange": "rim:definesSubstantiveChange",
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
    "runsOn": {
      "@id": "rim:runsOn",
      "@type": "@id"
    },
    "hasSpecification": {
      "@id": "rim:hasSpecification",
      "@type": "@id"
    },
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
      "@context": {
        "commitmentCategory": {
          "@id": "rim:commitmentCategory",
          "@type": "@vocab"
        }
      },
      "@id": "rim:hasCommitment",
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
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/register/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/register`

