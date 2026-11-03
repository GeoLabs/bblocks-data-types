
# Data type: STAC Catalog (Model)

`data-types.data-type.stac-catalog` *v1.0*

A STAC Catalog: a linked metadata object organizing STAC Items, Collections or child Catalogs.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A STAC Catalog: a linked metadata object organizing STAC Items, Collections or child Catalogs.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

## Usage

A STAC Catalog organises other STAC objects through its `links`. In the STAC 1.1.0 JSON Schema it must have `stac_version`, `type: "Catalog"`, `id`, `description` and `links`; `title` and `stac_extensions` are optional.

It carries no assets and no extent: those are added by STAC Collection.

## Hierarchy

- Broader: none (top-level data type)
- Narrower: [STAC Collection](../stac-collection/)

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion` and the proposed addition action (canonical source).
- `examples.yaml`: the same graph shown as a Turtle example.

## Sources

- [STAC Catalog JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/catalog-spec/json-schema/catalog.json)

## Examples

### STAC Catalog
Canonical concept, version and addition action for this data type.
#### turtle
```turtle
@prefix dt: <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim: <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog> a dt:DataType, rim:Concept, skos:Concept ; skos:inScheme dt:dataTypes ; skos:prefLabel "STAC Catalog"@en ; skos:definition "A STAC Catalog: a linked metadata object organizing STAC Items, Collections or child Catalogs."@en ; dct:source [ dct:title "STAC Catalog JSON Schema"@en ; dct:references <https://github.com/radiantearth/stac-spec/blob/master/catalog-spec/json-schema/catalog.json> ] .
<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/v1> a dt:DataTypeVersion, rim:ConceptVersion ; rim:versionOf <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog> ; rim:version "1.0" ; rim:objectIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/v1"^^xsd:anyURI ; rim:functionalIdentifier "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog"^^xsd:anyURI ; rim:validityStatus rim:invalid ; rim:publicationStatus rim:published ; dt:hasVersionAction <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/actions/addition> .
<https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/actions/addition> a rim:RegisterAction ; rim:actionType rim:additionAction ; rim:proposer dt:geolabs ; prov:startedAtTime "2026-11-02T00:00:00Z"^^xsd:dateTime .

```

## Sources

* [STAC Catalog JSON Schema](https://github.com/radiantearth/stac-spec/blob/master/catalog-spec/json-schema/catalog.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types)
* Path: `_sources/data-type/stac-catalog`

