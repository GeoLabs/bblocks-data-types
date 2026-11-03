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
