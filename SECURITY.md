# Security

Previo is designed with a privacy-first architecture.

## Customer data stays local

Previo can read local configuration/context files inside your CI environment.

Examples:

- incidents
- deployment constraints
- service metadata

Sensitive operational data does not need to be sent to Previo.

## Metadata only

Optional telemetry can include:

- customer id
- service name
- environment
- advisory result type
- timestamp