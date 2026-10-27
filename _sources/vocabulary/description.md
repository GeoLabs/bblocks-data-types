Data types as a Registered Item Model **concept plane**.

## What this block is

A vocabulary of the kinds of data that process profile inputs and outputs carry, modelled on the
concept plane of the [Registered Item Model](https://nielshoffmann.github.io/registered-item-model/)
(ISO 19135:2026):

- `dt:dataTypes` is a `rim:ConceptSystem`;
- each data type is a `dt:DataType` (a sub-class of `rim:Concept`) `skos:inScheme` it, carrying
  `skos:prefLabel`, `skos:definition` and, where one type specialises another,
  `skos:broader` (e.g. `raster-single-band` -> `raster`, `elevation-model` -> `raster-single-band`);
- each data type's governed state is a `dt:DataTypeVersion` (a sub-class of `rim:ConceptVersion`):
  object identifier, `validityStatus`, `publicationStatus`, and the `rim:RegisterAction` that
  proposed it.

The sixteen current types: `raster`, `raster-single-band`, `raster-multi-band`, `elevation-model`,
`geometry`, `point`, `curve`, `surface`, `feature-collection`, `point-cloud`, `tin`, `table`,
`bounding-box`, `number`, `string`, `boolean`.

## Meaning, not encoding

A data type names the **kind** of data, not its **encoding**. The byte format a concrete process
uses (GML, GeoTIFF, the OGC API - Processes `bbox` schema, ...) is declared where that process is
profiled -- an Implementation Profile's own `schema` -- not here. This is the same meaning /
representation split the concept plane exists for.

That boundary is an intent, not an absolute: a few types are grounded in a standard that happens to
be a format -- `point-cloud` cites the OGC LAS community standard, `feature-collection` and `string`
mention GeoJSON / format names in their definitions. Those are the concept's **source**, not an
encoding asserted on it.

## Governance: a proposed addition, not a status

There is no single lifecycle `status`. Each version records a `rim:RegisterAction` of type
`addition`, proposed by GeoLabs, at the date the vocabulary was first drafted (2026-10-08, inline in
`bblocks-generic-profiles`). Pending a control-body decision, versions are `invalid` (not in force)
and `published` (visible). `dt:DataTypeVersionShape` requires that addition and its proposer; a
later decision is a further action, not an edit of this one.

The action is linked from its version (`rim:hasAction`) but carries no `rim:appliesTo`: in the
Registered Item Model, `rim:appliesTo` is typed to `rim:RegisterItem` (the content plane), so it
cannot point at a `rim:ConceptVersion`. Recording a concept-plane addition via `hasAction` only is a
small gap in the model worth raising with its authors.

## Relationship to bblocks-generic-profiles

This vocabulary was first drafted inline in `bblocks-generic-profiles` as its
`generic-profiles.data-type` block. This register extracts it so it can be reused and governed on
its own. It mints its **own** IRIs (`.../bblocks-data-types/def/data-type/...`); the original inline
block keeps its own until a permanent, register-independent namespace is agreed and
`bblocks-generic-profiles` is pointed here. Nothing in `bblocks-generic-profiles` is changed by this
register existing (see that register's `docs/data-types-register.md`).
