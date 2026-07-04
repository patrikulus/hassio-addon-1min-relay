# Home Assistant Add-on: 1min Relay

## About

This add-on packages [`kokofixcomputers/1min-relay`](https://github.com/kokofixcomputers/1min-relay),
an OpenAI-compatible relay for the [1min.ai](https://1min.ai) API. It lets any
client that supports a custom OpenAI endpoint talk to 1min.ai models.

## Installation

1. In Home Assistant, go to **Settings → Add-ons → Add-on Store**.
2. Open the top-right menu (⋮) → **Repositories** and add:
   `https://github.com/patrikulus/hassio-addon-1min-relay`
3. Find **1min Relay** in the store and click **Install**.
4. Click **Start**.

## Configuration

This add-on has no configurable options. It runs with the upstream defaults:

- Listens on port `5001` (mapped to the Home Assistant host).
- Exposes **all** models supported by 1min.ai.
- Uses in-memory rate limiting (no Memcached).

You can change the host port under the add-on's **Network** section if `5001` is
already in use.

## Usage

The relay does not hold any 1min.ai credentials. Each request must include your
1min.ai API key as a Bearer token. Configure your OpenAI-compatible client like
this:

- **Base URL / Endpoint:** `http://<home-assistant-host>:5001/v1`
- **API key:** your 1min.ai API key (from <https://app.1min.ai/api>)

### Verify it is running

```bash
curl http://<home-assistant-host>:5001/v1/models \
  -H "Authorization: Bearer <YOUR_1MIN_AI_API_KEY>"
```

### Example chat completion

```bash
curl http://<home-assistant-host>:5001/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <YOUR_1MIN_AI_API_KEY>" \
  -d '{
    "model": "gpt-4o-mini",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

Supported endpoints:

- `GET  /v1/models`
- `POST /v1/chat/completions` (streaming and non-streaming)
- `POST /v1/images/generations`

## Notes

- The add-on is pinned to a specific upstream image build that correctly serves
  on port `5001`. (The upstream `latest` tag currently has a regression that
  binds the server to the wrong port.)
- The upstream image is multi-architecture and supports `aarch64` and `amd64`.

## Support

For issues with this add-on packaging, open an issue in this repository. For
issues with the relay itself, see the
[upstream project](https://github.com/kokofixcomputers/1min-relay).
