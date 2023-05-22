# ADR - Selecting a documentation format

**Status**: Proposed

We need to select a format for documenting:

* the APIs
* the data models
* the workflows

The documentation format must be:

* human readable for non technical people
* clear for technical people
* versionable
* diffable
* mergeable

## Considered Options

1. [Json Schema](https://json-schema.org/)
2. [Swagger 2](https://swagger.io/specification/v2/)
3. [OpenAPI 3.0.3](https://spec.openapis.org/oas/v3.0.3)
4. [OpenAPI 3.1.0](https://spec.openapis.org/oas/v3.1.0)

## Pros and Cons of the Options

### Json Schema

* Good, because it is a standard.
* Good, because it is simple.
* Good, because it is well supported by tooling.
* Good, because it is used by the TMF.
* Good, because it is the most advanced format for Json validation.
* Bad, because it is not a documentation format.
* Bad, because it is not a human readable format.
* Bad, because it is difficult to write by hand multiline descriptions.
* Bad, because it can be used only for data models.

### Swagger 2

* Good, because it is a standard.
* Good, because it is well supported by tooling.
* Good, because it is used by the TMF.
* Good, because it is used by lots of ARCEP projects.
* Bad, because it is difficult to write by hand multiline descriptions.
* Bad, because it is deprecated in favor of OpenAPI 3.

### OpenAPI 3.0.3

* Good, because it is a standard.
* Good, because it is simple.
* Good, because it is well supported by tooling.
* Good, because it is a human readable format.
* Good, because conversion from Swagger 2 is easy.
* Good, because it is used by lots of ARCEP projects.
* Bad, because it is not the latest version.

### OpenAPI 3.1.0

* Good, because it is a standard.
* Good, because it is simple.
* Good, because it is a human readable format.
* Good, because it is the latest version.
* Good, because it can reference external Json Schema files.
* Bad, because it is well supported by tooling.

## Decision Outcome

* Chosen Option: **OpenAPI 3.0.3**, because it is human readable and well supported by tooling.

The main reason for not choosing **OpenAPI 3.1.0** is that it is not well supported by tooling.
For example, the [Swagger UI](https://swagger.io/tools/swagger-ui/) does not support it yet.

The best technical option would be to use **Json Schema** for the data model
and **OpenAPI 3.1.0** for APIs with references to the Json Schema files.

## Positive Consequences

* We can add documentation to the API.
* We can insert examples in the documentation.
* We can insert images and diagrams in the documentation.

## Negative Consequences

* Will need to be upgraded to **OpenAPI 3.1.0** when tooling catches up.
* We should duplicate the data model in **Json Schema** and **OpenAPI 3.0.3**.
