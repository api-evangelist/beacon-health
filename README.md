# Beacon Health

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
