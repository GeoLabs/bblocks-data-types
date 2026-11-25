
# Data type: PolyhedralSurface (Model)

`data-types.data-type.polyhedral-surface` *v1.0*

A contiguous collection of polygons that share common boundary segments.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A contiguous collection of polygons that share common boundary segments.

## Definition

`https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

For each pair of polygons that touch, the common boundary is a finite collection of line strings, each part of the boundary of at most two polygon patches, and the polygons are consistently oriented. If every such line string bounds exactly two patches, the polyhedral surface is simple and closed, and it bounds a solid; a multi-surface of closed polyhedral surfaces can represent a solid with holes. A triangulated irregular network is the polyhedral surface consisting only of triangle patches.

## Hierarchy

- Broader: [Surface](../surface/) (`skos:broader` in `ontology.ttl`, published as `isProfileOf` in `bblock.json`)
- Narrower: [Triangulated irregular network](../tin/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
- [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)
- [OGC 06-103r3 Simple Feature Access - Part 1: Common Architecture](https://docs.ogc.org/is/06-103r3/06-103r3.pdf)

## Examples

### PolyhedralSurface
The register item of the PolyhedralSurface data type: it realizes the governed version of the concept and belongs to the register's data type item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item",
  "itemClass": "https://w3id.org/geolabs/ospd/data-types/dataTypeItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-types/register",
  "realizes": {
    "id": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface",
      "type": "Concept",
      "prefLabel": "PolyhedralSurface",
      "definition": "A contiguous collection of polygons that share common boundary segments.",
      "inScheme": "https://w3id.org/geolabs/ospd/data-types/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/v1",
    "functionalIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/org/geolabs",
      "startedAtTime": "2026-11-03T00:00:00Z"
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

<https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "PolyhedralSurface"@en ; skos:definition "A contiguous collection of polygons that share common boundary segments."@en ; skos:broader <https://w3id.org/geolabs/ospd/data-types/data-type/surface> ; dct:source [ dct:title "OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture"@en ; dct:references <https://www.ogc.org/standards/sfa/> ], [ dct:title "OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry"@en ; dct:references <https://docs.ogc.org/is/23-034/23-034.html> ], [ dct:title "OGC 06-103r3 Simple Feature Access - Part 1: Common Architecture"@en ; dct:references <https://docs.ogc.org/is/06-103r3/06-103r3.pdf> ] .
<https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface> ; rim:version "1.0" ; rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/actions/addition> .
<https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer <https://w3id.org/geolabs/ospd/org/geolabs> ; prov:startedAtTime "2026-11-03T00:00:00Z"^^xsd:dateTime .
<https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item> a dt:DataTypeItem, rim:RegisterItem ; dct:title "PolyhedralSurface"@en ; rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item"^^xsd:anyURI ; rim:itemClass dt:dataTypeItemClass ; rim:inRegister dt:register ; rim:realizes <https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/v1> ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published .

<https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/polyhedral-surface> .
<https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/v1> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/polyhedral-surface/v1> .
<https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item> owl:sameAs <https://geolabs.github.io/bblocks-data-types/def/data-type/polyhedral-surface/item> ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/actions/identifier-2026-11-17> .

<https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/actions/identifier-2026-11-17> a rim:RegisterAction ;
    rim:actionType dt:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty rim:objectIdentifier ;
    dct:description "The object identifier of this item moves from https://geolabs.github.io/bblocks-data-types/def/data-type/polyhedral-surface/item to https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item, which resolves through w3id.org (decision of 2026-11-17); the register actions of the item move with it, under https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/actions/. The old IRI is kept as owl:sameAs. The content of the item is unchanged. Classified clarifying: the item is the same, only its identifier changes. The data type and its version keep their old IRIs as owl:sameAs too."@en ;
    rim:proposer <https://w3id.org/geolabs/ospd/org/geolabs> ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item> ;
    prov:startedAtTime "2026-11-17T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/polyhedral-surface/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item",
  "type": "DataTypeItem",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item",
  "itemClass": "https://w3id.org/geolabs/ospd/data-types/dataTypeItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-types/register",
  "realizes": {
    "id": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/v1",
    "type": "DataTypeVersion",
    "versionOf": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface",
      "type": "Concept",
      "prefLabel": "PolyhedralSurface",
      "definition": "A contiguous collection of polygons that share common boundary segments.",
      "inScheme": "https://w3id.org/geolabs/ospd/data-types/data-types"
    },
    "version": "1.0",
    "objectIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/v1",
    "functionalIdentifier": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface",
    "validityStatus": "invalid",
    "publicationStatus": "published",
    "hasAction": {
      "id": "https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/org/geolabs",
      "startedAtTime": "2026-11-03T00:00:00Z"
    }
  },
  "validityStatus": "invalid",
  "publicationStatus": "published"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Data type item - PolyhedralSurface
description: The register item of the PolyhedralSurface data type, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-types/build/annotated/vocabulary/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-types/data-type/polyhedral-surface/item
x-bblocks-metadata:
  itemIdentifier: data-types.data-type.polyhedral-surface
  register: https://geolabs.github.io/bblocks-data-types/build/register.json
  version: '1.0'
  dateOfLastChange: '2026-11-03'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/polyhedral-surface/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/polyhedral-surface/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-types/build/annotated/data-type/polyhedral-surface/context.jsonld)

## Sources

* [OGC 06-103r4 Simple Feature Access - Part 1: Common Architecture](https://www.ogc.org/standards/sfa/)
* [OGC 23-034 OGC CDB Version 2 - Part 1: Core Standard, 7.6 Geometry](https://docs.ogc.org/is/23-034/23-034.html)
* [OGC 06-103r3 Simple Feature Access - Part 1: Common Architecture](https://docs.ogc.org/is/06-103r3/06-103r3.pdf)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/polyhedral-surface`

