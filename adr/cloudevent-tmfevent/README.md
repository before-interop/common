# ADR - CloudEvent or TMF Event

**Status**: Accepted

This ADR must determine if we must use CloudEvent or TMF Event
to send business events between operators.

## Considered Options

1. [CloudEvent]

2. TMF Event [TMF688_Event_Management_API_User_Guide_v4.0.0.pdf](TMF688_Event_Management_API_User_Guide_v4.0.0.pdf)

## Pros and Cons of the Options

### CloudEvent

* Good, because it is a standard.
* Good, because it is a [CNCF] project.
* Good, because the data model is compatible with other [CNCF projects].
* Good, because it is simpler than TMF Event.
* Bad, because it is not a TMF standard.

### TMF Event

* Good, because it is a TMF standard.
* Bad, because we cannot use it with other [CNCF projects].
* Bad, because it is more complex than [CloudEvent] (an endpoint/listener per event type).
* Bad, because it is optimized for the Trouble Ticket Management domain.

## Decision Outcome

* Chosen option: [CloudEvent], because it is a standard and it is compatible with other [CNCF projects].

## Positive Consequences

* We can use CloudEvent with protocols like Kafka, NATS, AMQP, MQTT, S3, etc.

## Negative Consequences

* We are not using a TMF standard.

[CloudEvent]: https://cloudevents.io/
[CNCF]: https://www.cncf.io/
[CNCF projects]: https://landscape.cncf.io/card-mode?project=graduated,incubating
