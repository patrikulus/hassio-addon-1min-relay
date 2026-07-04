# Changelog

## 79968daa373b961e223e5abfe1628ecb7ff2d43a

- Initial release of the 1min Relay Home Assistant add-on.
- Runs the upstream `kokofixcomputers/1min-relay` OpenAI-compatible relay.
- Pinned to a known-good upstream image build that serves correctly on port 5001.
- Exposes port 5001 with in-memory rate limiting; no Memcached required.
