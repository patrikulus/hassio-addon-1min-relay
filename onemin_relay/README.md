# 1min Relay

OpenAI-compatible API relay for the [1min.ai](https://1min.ai) API, packaged as a
Home Assistant add-on.

This add-on runs [`kokofixcomputers/1min-relay`](https://github.com/kokofixcomputers/1min-relay),
which exposes 1min.ai models through an OpenAI-compatible endpoint. Point any tool
that supports a custom OpenAI base URL (for example the OpenAI Conversation
integration, `bolt.diy`, or scripts using the OpenAI SDK) at this add-on.

## How it works

- The relay listens on port **5001** and serves the OpenAI-compatible API under `/v1`.
- Your **1min.ai API key** is supplied by the client on each request as a
  `Bearer` token (the `Authorization` header) — it is **not** stored in the add-on.
- Rate limiting uses in-memory storage (no external Memcached is required).

See [DOCS.md](DOCS.md) for setup and usage details.
