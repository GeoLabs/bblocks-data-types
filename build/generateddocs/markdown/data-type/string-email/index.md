
# Data type: String — email (Model)

`data-types.data-type.string-email` *v1.0*

A string representing a valid e-mail address as defined by RFC 5322.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A string representing a valid e-mail address as defined by RFC 5322.

## Withdrawn

This type was a proposal and is withdrawn (2026-11-09): it is a format, not a kind of data. Its item and its version are `rim:unpublished` and stay `rim:invalid`; nothing is deleted and no IRI changes.

- Replacement: the format [`https://w3id.org/geolabs/ospd/data-formats/format/string-email`](https://w3id.org/geolabs/ospd/data-formats/format/string-email) of the data-formats register (`dct:isReplacedBy` on the item). The Registered Item Model link, `rim:supersedes`, is carried by that format, because this register does not depend on data-formats.
- Action: `https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/actions/unpublication`, of type `rim:unpublishAction`, classified `rim:substantiveChange` (the retirement of a type), next to the addition, which is unchanged.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/string-email` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

An Implementation Profile can express this type as:

```json
{ "type": "string", "format": "email" }
```

Valid values: `user@example.org`.

As with any JSON Schema `format`, whether a value is actually checked depends on the validator.

## Hierarchy

- Broader: [String](../string/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition and the unpublication actions and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [EOAP schemas: string_format.yaml (JSON Schema format: email)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
- [RFC 5322](https://www.rfc-editor.org/rfc/rfc5322.html#page-16)

## Examples

### Email address string
The register item of the Email address string data type: it realizes the governed version of the concept and belongs to the register's data type item class. The type is withdrawn: item and version are unpublished, and the item is replaced by a format of the data-formats register.
#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email",
      "type": "Concept",
      "prefLabel": "Email address string",
      "definition": "A string representing a valid e-mail address as defined by RFC 5322.",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/v1",
    "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email",
    "validityStatus": "invalid",
    "publicationStatus": "unpublished",
    "hasAction": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
      "startedAtTime": "2026-11-01T00:00:00Z"
    }
  },
  "validityStatus": "invalid",
  "publicationStatus": "unpublished",
  "isReplacedBy": "https://w3id.org/geolabs/ospd/data-formats/format/string-email"
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

<https://geolabs.github.io/bblocks-data-types/def/data-type/string-email> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Email address string"@en ; skos:definition "A string representing a valid e-mail address as defined by RFC 5322."@en ; skos:broader <https://geolabs.github.io/bblocks-data-types/def/data-type/string> ; dct:source [ dct:title "EOAP schemas: string_format.yaml (JSON Schema format: email)"@en ; dct:references <https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml> ], [ dct:title "RFC 5322"@en ; dct:references <https://www.rfc-editor.org/rfc/rfc5322.html#page-16> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/string-email> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:unpublished ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/actions/addition>, <https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/actions/unpublication> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-01T00:00:00Z"^^xsd:dateTime .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/item> a dt:DataTypeItem, rim:RegisterItem ; dct:title "Email address string"@en ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/item"^^xsd:anyURI ; rim:itemClass dt:dataTypeItemClass ; rim:inRegister dt:register ; rim:realizes <https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/v1> ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:unpublished ; dct:isReplacedBy <https://w3id.org/geolabs/ospd/data-formats/format/string-email> ; rim:hasAction <https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/actions/unpublication> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/actions/unpublication> a rim:RegisterAction ; rim:actionType rim:unpublishAction ; rim:changeClassification rim:substantiveChange ; rim:proposer dt:geolabs ; rim:appliesTo <https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/item> ; prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime ; dct:description "Withdrawal of the proposal: this is a format, not a kind of data. It is replaced by the format https://w3id.org/geolabs/ospd/data-formats/format/string-email of the data-formats register, which carries rim:supersedes towards this item. Classified substantive: the retirement of a type."@en .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/string-email/context.jsonld",
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email",
      "type": "Concept",
      "prefLabel": "Email address string",
      "definition": "A string representing a valid e-mail address as defined by RFC 5322.",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/v1",
    "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email",
    "validityStatus": "invalid",
    "publicationStatus": "unpublished",
    "hasAction": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
      "startedAtTime": "2026-11-01T00:00:00Z"
    }
  },
  "validityStatus": "invalid",
  "publicationStatus": "unpublished",
  "isReplacedBy": "https://w3id.org/geolabs/ospd/data-formats/format/string-email"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data type item - Email address string
description: The register item of the Email address string data type, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.yaml
properties:
  id:
    const: https://geolabs.github.io/bblocks-data-types/def/data-type/string-email/item
x-bblocks-metadata:
  itemIdentifier: data-types.data-type.string-email
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '1.0'
  dateOfLastChange: '2026-11-01'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/string-email/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/string-email/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/string-email/context.jsonld)

## Sources

* [EOAP schemas: string_format.yaml (JSON Schema format: email)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)
* [RFC 5322](https://www.rfc-editor.org/rfc/rfc5322.html#page-16)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/string-email`

