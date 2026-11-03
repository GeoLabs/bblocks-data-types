The item class of the data type items, as a Registered Item Model **register item class**, in JSON.

## Definition

A profile of the RIM `register-item-class` schema: the abstraction every data type item of the
register shares (`dt:dataTypeItemClass`), defined in the register (`definedIn`) and validated by the
`dt:DataTypeItemShape` of the [shared vocabulary](../vocabulary/) (`validatedBy`).

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register-item-class`; `id` is fixed to the item
  class IRI, and `definedIn` and `validatedBy` are required.
- `examples.yaml`: the item class in JSON, validated against the schema, uplifted to RDF and checked
  against the shapes of the vocabulary.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)
