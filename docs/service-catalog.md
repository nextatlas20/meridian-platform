# Meridian Platform — Service Catalog

This catalog is the human-readable index of the deployable services in the
`meridian-platform` monorepo. Rows are derived from the service manifests under
`services/` and the ownership registry in `org/teams.yaml`; the table below is
regenerated whenever a release branch is cut, so do not hand-edit rows.

## 🧭 Active Service Catalog

A service is listed here only while its manifest reports `status: active`. Rows are
ordered by tier and then by service name, so the top of the table is also the on-call
escalation order.

| Service | Team | Tier | Runtime | Owner | On-call |
| --- | --- | --- | --- | --- | --- |
| billing-api | payments | T1 | python3.12 | @rkapoor | #payments-oncall |
| checkout-gateway | commerce | T1 | go1.22 | @jmarino | #commerce-oncall |
| identity-service | platform | T1 | java21 | @nweber | #platform-sre-oncall |
| invoice-worker | payments | T1 | python3.12 | @rkapoor | #payments-oncall |
| catalog-search | commerce | T2 | python3.11 | @jmarino | #commerce-oncall |
| notification-dispatch | platform | T2 | node20 | @nweber | #platform-sre-oncall |
| pricing-engine | commerce | T2 | python3.11 | @jmarino | #commerce-oncall |
| usage-meter | metering | T2 | rust1.79 | @agutierrez | #metering-oncall |
| audit-log | security | T3 | go1.22 | @ssato | #security-oncall |
| report-builder | analytics | T3 | python3.10 | @lchen | #analytics-oncall |

## 🗄️ Retired & Archived Services

- `legacy-sso-bridge` — retired 2026-05, traffic drained after the Okta migration (owner: platform).
- `batch-exporter` — archived 2026-02, superseded by `report-builder`.
- `sandbox-provisioner` — archived 2025-11, kept only for historical incident records.

## 🧾 Change Log

- 2026-08-14: rebuilt the catalog for `release/2026.08`; added `report-builder`.
- 2026-06-02: renamed `payments-core` to `billing-api` across manifests and docs.
- 2026-04-20: moved `audit-log` from the platform team to the security team.
