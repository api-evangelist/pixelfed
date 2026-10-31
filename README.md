# Pixelfed

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

Pixelfed is a decentralized, federated photo-sharing platform and open-source alternative to Instagram. Built on the ActivityPub protocol, it connects with the broader Fediverse — including Mastodon, PeerTube, and other federated networks — while giving users full ownership of their content. Pixelfed exposes a REST API that is broadly compatible with the Mastodon v1/v2 API, covering media uploads, status management, timelines, notifications, follower graphs, direct messages, stories, collections, and administrative functions. Developers can register OAuth2 applications against any public Pixelfed instance and build clients using the same patterns used for Mastodon- compatible apps.

**Areas:** Fediverse · ActivityPub · Photo Sharing · Social Media · Open Source · Decentralized · Mastodon Compatible · Federation

## Pixelfed on APIs.io

Everything profiled for Pixelfed is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/pixelfed/](https://apis.io/providers/pixelfed/)** — or go straight to one of the APIs or properties below.

### APIs (17)

- [Pixelfed Accounts API](https://apis.io/apis/pixelfed/pixelfed-accounts-api/) — Account management, follow/block/mute operations
- [Pixelfed Blocks and Mutes API](https://apis.io/apis/pixelfed/pixelfed-blocks-and-mutes-api/) — Blocked accounts and muted accounts
- [Pixelfed Bookmarks API](https://apis.io/apis/pixelfed/pixelfed-bookmarks-api/) — Bookmarked statuses
- [Pixelfed Collections API](https://apis.io/apis/pixelfed/pixelfed-collections-api/) — Pixelfed-specific photo collections (v1.1)
- [Pixelfed Direct Messages API](https://apis.io/apis/pixelfed/pixelfed-direct-messages-api/) — Pixelfed-specific direct messaging (v1.1)
- [Pixelfed Discovery API](https://apis.io/apis/pixelfed/pixelfed-discovery-api/) — Trending content, suggestions, and directory
- [Pixelfed Favourites API](https://apis.io/apis/pixelfed/pixelfed-favourites-api/) — Favourited statuses
- [Pixelfed Follow Requests API](https://apis.io/apis/pixelfed/pixelfed-follow-requests-api/) — Pending follow requests
- [Pixelfed Instance API](https://apis.io/apis/pixelfed/pixelfed-instance-api/) — Instance and federation metadata
- [Pixelfed Lists API](https://apis.io/apis/pixelfed/pixelfed-lists-api/) — List management and membership
- [Pixelfed Media API](https://apis.io/apis/pixelfed/pixelfed-media-api/) — Media upload and management
- [Pixelfed Notifications API](https://apis.io/apis/pixelfed/pixelfed-notifications-api/) — Notification retrieval and management
- [Pixelfed Push Notifications API](https://apis.io/apis/pixelfed/pixelfed-push-notifications-api/) — Web push subscription management (v1.1)
- [Pixelfed Search API](https://apis.io/apis/pixelfed/pixelfed-search-api/) — Full-text and entity search
- [Pixelfed Statuses API](https://apis.io/apis/pixelfed/pixelfed-statuses-api/) — Creating, reading, and interacting with statuses (posts)
- [Pixelfed Stories API](https://apis.io/apis/pixelfed/pixelfed-stories-api/) — Pixelfed-specific ephemeral stories (v1.1)
- [Pixelfed Timelines API](https://apis.io/apis/pixelfed/pixelfed-timelines-api/) — Home, public, tag, and list timelines

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Pixelfed Agentic Access](https://apis.io/agentic-access/pixelfed/pixelfed-agentic-access/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Pixelfed Context](https://apis.io/jsonld/pixelfed/pixelfed/)

#### Collections (17)

Postman and Open Collection request collections.

- [Pixelfed REST Accounts API](https://apis.io/collections/pixelfed/open-pixelfed-accounts-api/)
- [Pixelfed REST Accounts Blocks and Mutes API](https://apis.io/collections/pixelfed/open-pixelfed-blocks-and-mutes-api/)
- [Pixelfed REST Accounts Bookmarks API](https://apis.io/collections/pixelfed/open-pixelfed-bookmarks-api/)
- [Pixelfed REST Accounts Collections API](https://apis.io/collections/pixelfed/open-pixelfed-collections-api/)
- [Pixelfed REST Accounts Direct Messages API](https://apis.io/collections/pixelfed/open-pixelfed-direct-messages-api/)
- [Pixelfed REST Accounts Discovery API](https://apis.io/collections/pixelfed/open-pixelfed-discovery-api/)
- [Pixelfed REST Accounts Favourites API](https://apis.io/collections/pixelfed/open-pixelfed-favourites-api/)
- [Pixelfed REST Accounts Follow Requests API](https://apis.io/collections/pixelfed/open-pixelfed-follow-requests-api/)
- [Pixelfed REST Accounts Instance API](https://apis.io/collections/pixelfed/open-pixelfed-instance-api/)
- [Pixelfed REST Accounts Lists API](https://apis.io/collections/pixelfed/open-pixelfed-lists-api/)
- [Pixelfed REST Accounts Media API](https://apis.io/collections/pixelfed/open-pixelfed-media-api/)
- [Pixelfed REST Accounts Notifications API](https://apis.io/collections/pixelfed/open-pixelfed-notifications-api/)
- [Pixelfed REST Accounts Push Notifications API](https://apis.io/collections/pixelfed/open-pixelfed-push-notifications-api/)
- [Pixelfed REST Accounts Search API](https://apis.io/collections/pixelfed/open-pixelfed-search-api/)
- [Pixelfed REST Accounts Statuses API](https://apis.io/collections/pixelfed/open-pixelfed-statuses-api/)
- [Pixelfed REST Accounts Stories API](https://apis.io/collections/pixelfed/open-pixelfed-stories-api/)
- [Pixelfed REST Accounts Timelines API](https://apis.io/collections/pixelfed/open-pixelfed-timelines-api/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Pixelfed Authentication](https://apis.io/security/pixelfed/pixelfed-authentication/)
- [Pixelfed Domain Security](https://apis.io/security/pixelfed/pixelfed-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Pixelfed Scopes](https://apis.io/scopes/pixelfed/pixelfed-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Plans](https://apis.io/plans/pixelfed/plans/)

#### Rate limits (1)

Published request limits.

- [Rate Limits](https://apis.io/rate-limits/pixelfed/rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Finops](https://apis.io/finops/pixelfed/finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://pixelfed.org)
- [Blog](https://pixelfed.org/blog/)

## API Evangelist rating

**Kin Score 37.2** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 53.6 |
| Contract governance | 0.0 |
| Operational transparency | 39.5 |
| Developer ergonomics | 11.9 |
| Access clarity | 7.9 |

**Agent readiness 26.5** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | documented (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 26.5** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/pixelfed/](https://apis.io/providers/pixelfed/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Pixelfed: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/pixelfed/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
