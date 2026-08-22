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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
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

Beacon Health publishes **no public developer API**. As of 2026-08-15 there is no developer portal, API documentation, API reference, OpenAPI or AsyncAPI definition, GraphQL endpoint, MCP server, A2A agent card, SDK in any public registry, CLI, changelog, status page, or pricing page. The product is delivered as a managed agent workforce through a sales/demo motion.

Notably, Beacon Health's integration model is deliberately *not* API-based: its agents drive EHR user interfaces directly rather than exchanging data over FHIR or HL7v2. That is the company's core thesis — reaching systems that do not offer usable APIs.

The application backend at `api.beaconhealth.ai` is a Convex deployment (CNAME to `convex.domains`) that routes exactly two paths — `/.well-known/openid-configuration` and `/.well-known/jwks.json` — for first-party application session auth. Its advertised `authorization_endpoint` returns 404 and there is no client registration, so it is not a third-party developer authorization server. Everything else returns 404 `No matching routes found`.

**Crawler caution.** `trust.beaconhealth.ai` answers HTTP 200 to *every* path with an identical 604-byte single-page-app HTML shell — including `/.well-known/agent-card.json`, `/openapi.json`, `/llms.txt` and `/.well-known/security.txt`. None of those is a document. Beacon Health serves no agent card and no security.txt.

## Artifacts in this repo

| Artifact | Path | Method |
|---|---|---|
| Well-Known index | `well-known/beacon-health-well-known.yml` | searched (55 paths, 3 hosts) |
| OIDC discovery | `well-known/beacon-health-openid-configuration.json` | searched (verbatim, 200) |
| JWKS | `well-known/beacon-health-jwks.json` | searched (verbatim, 200) |
| Authentication | `authentication/beacon-health-authentication.yml` | searched |
| Conformance / Compliance | `conformance/beacon-health-conformance.yml` | searched |
| Trust center | `security/beacon-health-trust-center.yml` | searched |
| Vulnerability disclosure | `security/beacon-health-vulnerability-disclosure.yml` | searched |
| Domain security | `security/beacon-health-domain-security.yml` | probed |
| Lifecycle | `lifecycle/beacon-health-lifecycle.yml` | searched (absence recorded) |
| Packages | `packages/beacon-health-packages.yml` | searched (zero found) |
| Plans / pricing | `plans/beacon-health-plans-pricing.yml` | searched (`plan_count: 0`) |
| Rate limits | `rate-limits/beacon-health-rate-limits.yml` | searched (`limit_count: 0`) |
| llms.txt | `llms/beacon-health-llms.txt` | generated |

## Compliance posture

HIPAA Business Associate operating under a BAA with each covered entity; commits to HIPAA Security Rule safeguards.

Since the previous pass Beacon Health has stood up a public **trust center** at <https://trust.beaconhealth.ai/> (its own subdomain, Oneleet-hosted — the live counterpart of the `oneleet-domain-verification` TXT record noted before). It publishes:

- **SOC 2** — `IN_PROGRESS`, no Type I/II report, auditor, or attestation letter.
- **HIPAA (Business Associate)** — `IN_PROGRESS`.
- **56 monitored controls**, 55 `PASSING` and 1 `NEEDS_CHANGES` (*Adequate audit log storage maintained*, mapped to the HIPAA framework).
- **8 named subprocessors**, 2 declared to process PII: AWS (Patient Documents) and Convex (Application Data, Patient Data, Audit Logs).
- **No downloadable documents** — nothing to request or retrieve.

There is still **no completed third-party attestation** of any kind. The trust center is client-side rendered, so none of the above is machine-readable from the served HTML.

The site's own `/security` route 307-redirects to a *second* trust center at `https://trust.delve.co/beacon-health`, which sits behind a Vercel bot challenge (429) and could not be read. Two trust surfaces exist; only the Oneleet one is legible.

A security contact (`security@beaconhealth.ai`) and a report-a-security-issue form are now published on the trust center — but there is no `security.txt`, no disclosure policy, and no bug bounty. A channel, not a policy.

## A note on the GitHub organization

<https://github.com/beaconhealthai> displays the name "Beacon Health" and was created April 2025, but **ownership is unconfirmed**: the YC profile and beaconhealth.ai link to no GitHub org, it has no public members, and its single repository is an unmodified fork of `cyberdesk-hq/cyberdriver` with no first-party commits. It is recorded as a candidate in `packages/` and deliberately **not** wired as a `GitHubOrganization` pointer.

## Disambiguation

Not to be confused with **Beacon Health System** (hospital network, South Bend, Indiana) or **Beacon Health Options** (behavioral health managed care). This profile covers only beaconhealth.ai, the Y Combinator W26 AI company.
