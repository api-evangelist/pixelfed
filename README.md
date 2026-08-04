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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Pixelfed is a decentralized, federated photo-sharing platform and open-source alternative to Instagram. Built on the ActivityPub protocol, it connects with the broader Fediverse — including Mastodon, PeerTube, and other federated networks — while giving users full ownership of their content and data.

## API

Pixelfed exposes a REST API broadly compatible with the Mastodon v1/v2 API. Because Pixelfed is self-hosted software, every instance operates its own independent API endpoint at its own domain. Developers build against a specific instance (e.g., `https://pixelfed.social`) or target the instance their users belong to.

Key capability areas:

- **Accounts** — verify credentials, manage profiles, follow/unfollow, block/mute
- **Statuses** — create, retrieve, delete posts; favourite and reblog
- **Timelines** — home, public, hashtag, and list feeds
- **Media** — upload and manage photos and videos
- **Notifications** — retrieve and dismiss notification events
- **Search** — full-text and account/hashtag search (v2)
- **Collections** — curated photo sets
- **Stories** — ephemeral content (Pixelfed extension)
- **Direct Messages** — private conversations (v1.1 extension)
- **ActivityPub / Federation** — inbox/outbox, WebFinger, NodeInfo

## Authentication

OAuth2 with authorization_code flow. Register an application at `https://{instance}/settings/applications` to obtain `client_id` and `client_secret`, then exchange for a Bearer token. Personal Access Tokens are also supported for scripting.

## Resources

- **Documentation**: https://docs.pixelfed.org/
- **GitHub**: https://github.com/pixelfed/pixelfed
- **Flagship instance**: https://pixelfed.social
- **Mobile apps**: iOS and Android (launched January 2025)

## License

Pixelfed is licensed under the [AGPL-3.0](https://github.com/pixelfed/pixelfed/blob/dev/LICENSE).
