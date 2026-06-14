# Pixelfed

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
