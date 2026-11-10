A dataset delivered as one unit by a data provider, typically one acquisition over one area, made of several assets such as spectral bands, masks and metadata, and described by metadata.

## Definition

`https://geolabs.github.io/bblocks-data-types/def/data-type/eo-product` is a `dt:DataType` in the `dt:dataTypes` concept system. It names a kind of data, not its encoding.

A product is the data and its description together. The record that describes it, or the package that delivers it, is a representation of the product, not part of the type.

## Requested by

Added on 2026-11-10 for a role of a new Generic Profile of `bblocks-generic-profiles` (branch
`planes/new-profiles`), one of the six profiles proposed so that unattached OSPD CWL processes can
attach at tier 4. No standard source is given: none was read for this definition.

- [`generic-profile/band-retrieval/inputs/product`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/band-retrieval/inputs/product): the product from which a band is retrieved
- [`generic-profile/product-selection/outputs/products`](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/product-selection/outputs/products): the products selected

## Hierarchy

- Broader: none (top-level data type).
- Narrower: none

## Content of this block

- `ontology.ttl`: the concept, its governed `dt:DataTypeVersion`, the proposed addition action and the register item that realizes the version (canonical source).
- `schema.yaml`: a profile of the vocabulary's data type item schema (itself a profile of the RIM register item), with `id` fixed to this item.
- `examples.yaml`: the register item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same graph in Turtle.

## Sources

- [Generic Profile band-retrieval (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/band-retrieval/inputs/product)
- [Generic Profile product-selection (bblocks-generic-profiles), the role that requests this type](https://geolabs.github.io/bblocks-generic-profiles/def/generic-profile/product-selection/outputs/products)
