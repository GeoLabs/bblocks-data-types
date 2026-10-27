# bblocks-data-types

OGC Building Blocks register holding the **data types** of process profile inputs and outputs, as a
[Registered Item Model](https://nielshoffmann.github.io/registered-item-model/) (ISO 19135:2026)
**concept plane**. Identifier prefix: `data-types.`

`dt:dataTypes` is a `rim:ConceptSystem`; each data type is a `dt:DataType` (sub-class of
`rim:Concept`) with a governed `dt:DataTypeVersion` (sub-class of `rim:ConceptVersion`). A data type
names the *kind* of data, not its encoding -- the encoding a concrete process uses is declared at the
Implementation Profile tier, not here. See
[`_sources/vocabulary/description.md`](_sources/vocabulary/description.md).

This vocabulary was first drafted inline in
[`GeoLabs/bblocks-generic-profiles`](https://github.com/GeoLabs/bblocks-generic-profiles) as its
`generic-profiles.data-type` block; this register extracts it so it can be reused and governed on
its own. It mints its own IRIs; `bblocks-generic-profiles` is **not** changed by this register
existing (reconciliation of the two IRI namespaces is a later, separate decision).

## Building blocks

| Identifier | Tier |
|---|---|
| `data-types.vocabulary` | The `rim:ConceptSystem` and the sixteen `dt:DataType` concepts with their governed versions |

## Building locally

This register imports the Registered Item Model's **JSON binding**, which currently lives on the
`rim-consolidation` branch of the GeoLabs fork (proposed upstream). Until upstream publishes it,
build with a local URL mapping to a checkout of that branch, built with
`--base-url https://nielshoffmann.github.io/registered-item-model/`:

```yaml
# bblocks-config-local.yml (gitignored; the file name must end in .yml)
url-mappings:
  'https://nielshoffmann.github.io/registered-item-model/build/': '/imports/registered-item-model/build-local/'
  'https://nielshoffmann.github.io/registered-item-model/': '/imports/registered-item-model/'
```
```
# .volumes (gitignored)
../registered-item-model:/imports/registered-item-model
```

```bash
./build.sh   # process and validate (Docker)
./view.sh    # preview at http://localhost:9090
```

## License

Apache-2.0.
