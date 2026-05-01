# Previo Pilot

Previo helps engineering teams stop shipping blind.

It surfaces relevant prior incidents, constraints, and deployment context inside CI/CD before releases go live.

Previo runs in **advisory mode by default** — no blocking, no disruption, no additional process.

---

## What this repo is

This repository contains pilot integration examples, setup guides, and security information for teams evaluating Previo.

It does **not** contain Previo source code.

---

## How Previo works

Previo runs as a CLI inside your existing deployment pipeline.

```bash
previo check
```

During a deployment, Previo evaluates available context and surfaces relevant advisories only when signal exists.

When no relevant context is found, Previo stays silent.

CI Compatibility

Previo is CI-agnostic.

It works in any system that can run shell commands, including:

* GitHub Actions
* GitLab CI
* Jenkins
* CircleCI
* Azure DevOps

GitHub Actions is provided as an example integration in this repo.

For other systems, simply run:

```bash
previo check
```

inside your pipeline.


## Quick Start

1. Add Previo to your pipeline using one of the examples in examples/
2. Configure environment variables:

PREVIO_API_KEY=your_key
PREVIO_CUSTOMER_ID=your_customer_id
PREVIO_EVENTS_URL=https://api.previoops.com/pilot/events

3. Run your pipeline
4. Review Previo advisories in CI logs

## Optional Context (Not Required)

Previo works without any additional data.

Teams can optionally provide lightweight context to improve signal quality over time.

Examples include:

* Prior incidents
* Deployment constraints
* Known service risks

See examples/config/ for sample formats.

=====================================================
Example Output: 

⚠️ Previo found relevant operational context

Service: payments-api
Severity: high
Prior Incident: Latency spike after deployment
Recommendation: Use canary deploy and monitor latency
========================================================

## Security

Previo is designed with a privacy-first architecture.

* Runs inside your CI environment
* Does not require access to your systems
* Does not require source code access
* Does not require incident log ingestion

Optional telemetry is limited to non-sensitive metadata such as:

* customer id
* service name
* environment
* advisory result type
* timestamp

See SECURITY.md for details.

⸻

## Privacy

Previo does not require:

* incident logs
* postmortems
* production data
* credentials

All operational context remains in your environment.

See PRIVACY.md for details.

⸻

## Pilot Scope

Previo pilots are intentionally lightweight:

* Advisory-only (no blocking)
* Single service or limited scope
* No infrastructure changes required
* No vendor lock-in

⸻

## Product Site

https://previoops.com

## Pilot Access

This repository is shared with teams currently evaluating Previo.

If you were directed here, follow the setup instructions above to get started.

