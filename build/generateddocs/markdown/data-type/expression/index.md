
# Data type: Expression (Model)

`data-types.data-type.expression` *v1.0*

A formula that combines references to input values, constants, operators and functions, and whose evaluation computes a value.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A formula that combines references to input values, constants, operators and functions, and whose evaluation computes a value.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/expression` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

The syntax of the formula is a representation, not part of the type.

## Requested by

Added because existing roles of `bblocks-generic-profiles` need it. They declare the data type
`string` today (branch `planes/phase-1-docs`, `b0da6aa`); pointing them to this type is a change of
that register, not made here.

- [`generic-profile/raster-band-math/inputs/expression`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-band-math/inputs/expression): the per-pixel mathematical expression
- [`implementation-profile/raster-band-math/inputs/expression`](https://geolabs.github.io/bblocks-generic-profiles/def/implementation-profile/raster-band-math/inputs/expression)
- [`implementation-profile/raster-band-math-multiband/inputs/expression`](https://geolabs.github.io/bblocks-generic-profiles/def/implementation-profile/raster-band-math-multiband/inputs/expression)

## Hierarchy

- Broader: none (top-level data type). It is not a narrower type of String: what it names is not a
  character string, even if a string can represent it.
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile raster-band-math (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-band-math/inputs/expression)

## Examples

### Expression
The register item of the Expression data type: it realizes the governed version of the concept and belongs to the register's data type item class.
#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression",
      "type": "Concept",
      "prefLabel": "Expression",
      "definition": "A formula that combines references to input values, constants, operators and functions, and whose evaluation computes a value.",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/v1",
    "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
      "startedAtTime": "2026-11-09T00:00:00Z"
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

<https://geolabs.github.io/bblocks-data-types/def/data-type/expression> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Expression"@en ; skos:definition "A formula that combines references to input values, constants, operators and functions, and whose evaluation computes a value."@en ; dct:source [ dct:title "Generic Profile raster-band-math (bblocks-generic-profiles), the role that requests this type"@en ; dct:references <https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-band-math/inputs/expression> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/expression/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/expression> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/expression"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/expression/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/expression/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime .
<https://geolabs.github.io/bblocks-data-types/def/data-type/expression/item> a dt:DataTypeItem, rim:RegisterItem ; dct:title "Expression"@en ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/item"^^xsd:anyURI ; rim:itemClass dt:dataTypeItemClass ; rim:inRegister dt:register ; rim:realizes <https://geolabs.github.io/bblocks-data-types/def/data-type/expression/v1> ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/expression/context.jsonld",
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression",
      "type": "Concept",
      "prefLabel": "Expression",
      "definition": "A formula that combines references to input values, constants, operators and functions, and whose evaluation computes a value.",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/v1",
    "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/expression/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
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
title: Data type item - Expression
description: The register item of the Expression data type, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.yaml
properties:
  id:
    const: https://geolabs.github.io/bblocks-data-types/def/data-type/expression/item
x-bblocks-metadata:
  itemIdentifier: data-types.data-type.expression
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '1.0'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/expression/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/expression/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/expression/context.jsonld)

## Sources

* [Generic Profile raster-band-math (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/raster-band-math/inputs/expression)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/expression`

