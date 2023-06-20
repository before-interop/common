# ADR - TMF Eager Loading vs Lazy Loading

**Status**: Accepted

This ADR must determine if we must use the standard TMF way (eager loading)
or lazy loading for nested resources.

## Considered Options

1. Eager loading
2. Lazy loading

## Pros and Cons of the Options

### Eager loading

* Good, because it is the TMF way.
* Good, because it is simple.
* Bad, because it is not the best way for performance.
* Bad, because it is not the best way for scalability.

### Lazy loading

* Good, because it is the best way for performance.
* Good, because it is the best way for scalability.
* Good, because it can be used for non TMF applications.
* Good, because it allow the reuse.
* Bad, because it is not the TMF way for API.
* Bad, because it does not respect the TMF data models.

## Decision Outcome

TODO

## Positive Consequences

TODO

## Negative Consequences

TODO
