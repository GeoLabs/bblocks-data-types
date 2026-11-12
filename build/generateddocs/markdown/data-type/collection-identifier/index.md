
# Data type: Collection identifier (Model)

`data-types.data-type.collection-identifier` *v1.0*

An identifier that designates a collection of data products held in a catalogue.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

An identifier that designates a collection of data products held in a catalogue.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

A value of this type designates one collection; it is not the description of the collection.

## Requested by

Added on 2026-11-10 for a role of a new Generic Profile of `bblocks-generic-profiles` (branch
`planes/new-profiles`), one of the six profiles proposed so that unattached OSPD CWL processes can
attach at tier 4. No standard source is given: none was read for this definition.

- [`generic-profile/product-selection/inputs/collection`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/product-selection/inputs/collection): the collection the products are selected from

## Hierarchy

- Broader: none (top-level data type).
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile product-selection (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/product-selection/inputs/collection)

## Examples

### Collection identifier
The register item of the Collection identifier data type: it realizes the governed version of the concept and belongs to the register's data type item class.
#### json
```json
{
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier",
      "type": "Concept",
      "prefLabel": "Collection identifier",
      "definition": "An identifier that designates a collection of data products held in a catalogue.",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/v1",
    "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
      "startedAtTime": "2026-11-10T00:00:00Z"
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

<https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "Collection identifier"@en ; skos:definition "An identifier that designates a collection of data products held in a catalogue."@en ; dct:source [ dct:title "Generic Profile product-selection (bblocks-generic-profiles), the role that requests this type"@en ; dct:references <https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/product-selection/inputs/collection> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-10T00:00:00Z"^^xsd:dateTime .
<https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/item> a dt:DataTypeItem, rim:RegisterItem ; dct:title "Collection identifier"@en ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/item"^^xsd:anyURI ; rim:itemClass dt:dataTypeItemClass ; rim:inRegister dt:register ; rim:realizes <https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/v1> ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/collection-identifier/context.jsonld",
  "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/item",
  "itemClass": "https://geolabs.github.io/bblocks-data-types/def/dataTypeItemClass",
  "inRegister": "https://geolabs.github.io/bblocks-data-types/def/register",
  "realizes": {
    "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier",
      "type": "Concept",
      "prefLabel": "Collection identifier",
      "definition": "An identifier that designates a collection of data products held in a catalogue.",
      "inScheme": "https://geolabs.github.io/bblocks-data-types/def/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/v1",
    "functionalIdentifier": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://geolabs.github.io/bblocks-data-types/def/geolabs",
      "startedAtTime": "2026-11-10T00:00:00Z"
    }
  },
  "validityStatus": "invalid",
  "publicationStatus": "published"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data type item - Collection identifier
description: The register item of the Collection identifier data type, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.yaml
properties:
  id:
    const: https://geolabs.github.io/bblocks-data-types/def/data-type/collection-identifier/item
x-bblocks-metadata:
  itemIdentifier: data-types.data-type.collection-identifier
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '1.0'
  dateOfLastChange: '2026-11-10'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/collection-identifier/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/collection-identifier/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/collection-identifier/context.jsonld)

## Sources

* [Generic Profile product-selection (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/product-selection/inputs/collection)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/collection-identifier`

