# Zendrive

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

Zendrive Inc. was a San Francisco mobility risk intelligence company that measured driving
behavior from ordinary smartphone sensors. Its integration surface was a **mobile SDK, not an
HTTP API**: an application embedded the Zendrive SDK, which detected the start and end of every
drive, collected accelerometer/gyroscope/GPS data with minimal battery impact, raised in-process
callbacks for trip and collision events, and uploaded the drive to Zendrive for scoring. Fleets,
rideshare operators and auto insurers consumed the analytics through a dashboard and a
server-side Analytics REST API.

Intuit announced on 2024-06-13 that it would acquire Zendrive's technology for Credit Karma's
usage-based auto insurance product, Karma Drive, taking on CEO Dennis Ellis and co-founder/CTO
Pankaj Risbood. The developer program was shut down afterwards.

## Status as probed 2026-09-05

- `zendrive.com` and `www.zendrive.com` have **no DNS A record**. Nothing answers on HTTP.
- `developers.zendrive.com`, `app.zendrive.com`, `api.zendrive.com`, `iql.zendrive.com` and
  `status.zendrive.com` are NXDOMAIN.
- `docs.zendrive.com` is a **dangling Cloudflare CNAME** — every path returns HTTP 403 with the
  body `error code: 1014`. That is an edge error, not documentation.
- No OpenAPI, Swagger, GraphQL SDL, AsyncAPI, agent card, `llms.txt`, MCP server or
  `/.well-known/` document is served on any reachable Zendrive host. The full negative probe is
  in [`well-known/zendrive-well-known.yml`](well-known/zendrive-well-known.yml).
- The zone itself is still **actively held**: a Google Trust Services certificate for
  `zendrive.com` and `*.zendrive.com` was issued 2026-08-26, DMARC is `p=reject` with strict
  alignment, and CAA carries an `iodef` security contact. See
  [`security/zendrive-domain-security.yml`](security/zendrive-domain-security.yml).

## What is still online (all first-party, all read-only)

| Surface | URL |
|---|---|
| iOS SDK reference (ZendriveSDK 10.1.0) | https://zendrive-root.bitbucket.io/ios/docs/latest/index.html |
| Android SDK javadoc (v10.1.0) | https://zendrive-root.bitbucket.io/android/docs/latest/index.html |
| React Native SDK guide | https://react-native-zendrive-guide-v2.netlify.app/readme |
| React Native SDK API reference | https://react-native-zendrive-api-v2.netlify.app/ |
| React Native release notes | https://master--react-native-zendrive-guide-v2.netlify.app/releases |
| GitHub organization (two sample apps) | https://github.com/zendrive |
| Maven Central `com.zendrive.sdk.android:ZendriveSDK` 10.1.0 | https://central.sonatype.com/artifact/com.zendrive.sdk.android/ZendriveSDK |
| npm `react-native-zendrive` 7.0.5 | https://www.npmjs.com/package/react-native-zendrive |

Every first-party publication stops in the same fortnight as the acquisition — Maven 2024-06-24,
the iOS reference 2024-06-25, npm 2024-07-03 — and nothing has shipped since. The binaries remain
downloadable but **no integration can be completed**: SDK setup validates an application key
against Zendrive's servers, and no new key can be issued.

Harvest source: https://forgeglobal.com/zendrive_stock/ (a secondary-market listing, not a
company website — deliberately not wired as a `Website` pointer).
