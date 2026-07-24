# Beacon Health

Beacon Health (YC W26) builds "AI employees" for primary care — autonomous agents that operate directly inside electronic health record systems the way a human staff member does. A practice records an existing EHR workflow (navigation, clicks, data entry) and Beacon converts that recording into a reusable, deployable agent that runs at scale across the whole patient panel.

The agents automate value-based-care back-office work: preventative and quality gap closure, pre-charting, prior authorizations, referrals, transition-of-care management, and HCC risk-adjustment coding. Advertised EHR coverage includes AthenaHealth, Epic, Cerner, eClinicalWorks, MEDITECH, NextGen, Veradigm Allscripts and MEDENT, plus payer portals and other web applications.

Founded in 2025 in San Francisco by Mark Pothen (CEO) and Obinna Akahara (CTO).

- Website: https://www.beaconhealth.ai/
- Y Combinator: https://www.ycombinator.com/companies/beacon-health (Winter 2026)
- Backed by: y-combinator

## API status

Beacon Health publishes **no public developer API**. There is no developer portal, API documentation, API reference, OpenAPI or AsyncAPI definition, SDK, CLI, MCP server, public GitHub organization, changelog, status page, or pricing page. The product is delivered as a managed agent workforce through a sales/demo motion.

Notably, Beacon Health's integration model is deliberately *not* API-based: its agents drive EHR user interfaces directly rather than exchanging data over FHIR or HL7v2. That is the company's core thesis — reaching systems that do not offer usable APIs.

The application backend at `api.beaconhealth.ai` is a Convex-hosted service that serves a valid OIDC discovery document and JWKS for first-party application session auth. Its advertised `authorization_endpoint` returns 404 and there is no client registration, so it is not a third-party developer authorization server.

## Artifacts in this repo

| Artifact | Path | Method |
|---|---|---|
| Well-Known index | `well-known/beacon-health-well-known.yml` | searched (live probe) |
| OIDC discovery | `well-known/beacon-health-openid-configuration.json` | searched (verbatim, 200) |
| JWKS | `well-known/beacon-health-jwks.json` | searched (verbatim, 200) |
| Authentication | `authentication/beacon-health-authentication.yml` | searched |
| Conformance / Compliance | `conformance/beacon-health-conformance.yml` | searched |
| Domain security | `security/beacon-health-domain-security.yml` | probed |
| llms.txt | `llms/beacon-health-llms.txt` | generated |

## Compliance posture

HIPAA Business Associate operating under a BAA with each covered entity; commits to HIPAA Security Rule safeguards. No published third-party audit attestation (no SOC 2, ISO 27001, or HITRUST report is publicly available), though a `oneleet-domain-verification` DNS TXT record suggests a compliance program in progress. No `security.txt` and no published vulnerability disclosure program.

## Disambiguation

Not to be confused with **Beacon Health System** (hospital network, South Bend, Indiana) or **Beacon Health Options** (behavioral health managed care). This profile covers only beaconhealth.ai, the Y Combinator W26 AI company.
