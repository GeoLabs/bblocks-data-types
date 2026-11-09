The data-types register as a Registered Item Model **register**, in JSON.

## Definition

A profile of the RIM `register` schema: the governed collection of data types, distinct from the
register system it runs on (`runsOn`) and from the roles that govern it (`registerOwner`,
`registerManager`, `controlBody`). Its title, description, concept system (`dt:conceptSystem`) and
register specification (`hasSpecification`, `dt:specification`) are declared in the `data.ttl` of the
[shared vocabulary](../vocabulary/), which the SHACL closure of this block includes.

## Register specification

`dt:specification` is a `rim:RegisterSpecification`. It records:

- the register type: a concept register, as the Registered Item Model uses the term;
- the roles: GeoLabs SARL is owner, manager and, for now, control body, with the written intention
  to delegate the control body role to the OGC or to an OSPD working group;
- the `rim:realizes` link with the data-formats register: a `df:Representation` realizes at most one
  `dt:DataTypeVersion`, and data-formats depends on this register, never the reverse;
- the definition of a substantive change (`rim:definesSubstantiveChange`), the table of substantive
  and clarifying changes for data types, the version rule and the rule for proposals;
- `dt:amendmentAction`, the action type of an in-place change to a proposal;
- that no eligibility criteria and no commitments have been set.

## Content of this block

- `schema.yaml`: a profile of `ogc.rim.schemas.register`; `id` is fixed to the register's IRI and
  its identifier, system and owner are required.
- `examples.yaml`: the register in JSON, validated against the schema, uplifted to RDF and checked
  against the shapes of the vocabulary.

## Sources

- [ISO 19135:2026, Geographic information — Registration and register governance](https://www.iso.org/standard/86261.html)
- [Registered Item Model](https://ogcincubator.github.io/registered-item-model/)
