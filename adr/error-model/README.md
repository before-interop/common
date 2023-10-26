# ADR - Error model

This ADR must determine if we must use the standard TMF way for error model
or use the universal way: [RFC 7807](https://tools.ietf.org/html/rfc7807).

## Considered Options

1. TMF way
2. RFC 7807 - Problem Details for HTTP APIs

## Pros and Cons of the Options

### TMF way

* Good, because it is the TMF way.
* Bad, because it is not the universal way.
* Bad, because it is not natively supported by frameworks.
* Bad, because it can not be used for array of errors.

example:

```json
{
  "code": "42",
  "reason": "The answer to life, the universe and everything.",
  "message": "The answer to life, the universe and everything.",
  "status": "500",
  "referenceError": "https://en.wikipedia.org/wiki/The_Hitchhiker%27s_Guide_to_the_Galaxy"
}
```

validation example:

```json
{
  "code": "400-1",
  "reason": "Your request parameters didn't validate.",
  "message": "Name is required.",
  "status": "400",
  "referenceError": "https://example.net/validation-error/name",
}
```

### RFC 7807 - Problem Details for HTTP APIs

* Good, because it is the universal way.
* Good, because it is natively supported by lots of frameworks.
* Good, because it can be used for array of errors.
* Good, because the error use a specific type (`application/problem+json`)
  which can be used for content negotiation.
* Bad, because it is not the TMF way.

example:

```json
{
  "type": "https://en.wikipedia.org/wiki/The_Hitchhiker%27s_Guide_to_the_Galaxy",
  "title": "The answer to life, the universe and everything.",
  "detail": "42"
}
```

validation example:

```json
{
  "type": "https://example.net/validation-error",
  "title": "Your request parameters didn't validate.",
  "errors": [
    {
      "path": "name",
      "message": "Name is required."
    },
    {
      "path": "address.street",
      "message": "Street must be at least 5 characters long."
    }
  ]
}
```

## Decision Outcome

The solution must be used for all INTEROP protocols.

## Positive Consequences

TODO

## Negative Consequences

TODO
