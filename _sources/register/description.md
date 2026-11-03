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
