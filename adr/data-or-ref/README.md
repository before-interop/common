# ADR - Send data or external reference

**Status**: Proposed

This ADR must determine if we must send data or an external reference.

## Considered Options

1. Data

  In this case, the data is sent to the external system.

  ```mermaid
  sequenceDiagram
    participant A as Producer (internal system)
    participant B as Consumer (external system)

    A->>B: POST /{resource}
    B->>A: 201 OK
  ```

2. External reference

  In this case, the data is not sent to the external system.
  The external system must use the external reference to get the data.

  ```mermaid
  sequenceDiagram
    participant A as Producer (internal system)
    participant B as Internal resource (internal + external access)
    participant C as Consumer (external system)

    A->>B: POST /{resource}
    B->>A: 201 OK

    A->>C: POST /{wrapper}
    C->>A: 200 OK
  ```

  The call to the consumer has a body with the external reference.
  For TMF API, you can use the `relatedEntity` attribute:

  ```json
  {
    "relatedEntity": [
      {
        "href": "http://serverA.com/resource/{resourceId}",
        "name": "John Doe",
        "role": "customer",
        "@referredType": "Party"
      }
    ]
  }
  ```

## Pros and Cons of the Options

### Data

* Good, because it can reduce the number of requests.
* Bad, because it can be difficult for large data like big attachments.
* Bad, because it is not the TMF way for API.

### External reference

* Good, because it is the TMF way for API.
* Good, because it is the best way for performance.
* Bad, because it can increase the number of requests.
* Bad; because the workflow is more complex.
* Bad, because it can be difficult to implement a secure way to access the external reference.

## Decision Outcome

TODO

## Positive Consequences

TODO

## Negative Consequences

TODO
