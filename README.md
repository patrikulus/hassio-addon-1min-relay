# Home Assistant Add-on Repository: 1min Relay

A [Home Assistant](https://www.home-assistant.io/) add-on repository that packages
[`kokofixcomputers/1min-relay`](https://github.com/kokofixcomputers/1min-relay) —
an OpenAI-compatible API relay for the [1min.ai](https://1min.ai) API.

## Add this repository to Home Assistant

1. Go to **Settings → Add-ons → Add-on Store**.
2. Open the top-right menu (⋮) → **Repositories**.
3. Add the URL:

   ```text
   https://github.com/patrikulus/hassio-addon-1min-relay
   ```

4. **1min Relay** will now appear in the Add-on Store. Install and start it.

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fpatrikulus%2Fhassio-addon-1min-relay)

## Add-ons in this repository

| Add-on | Description |
| ------ | ----------- |
| [1min Relay](./onemin_relay) | OpenAI-compatible API relay for the 1min.ai API. |

## Usage

After starting the add-on, point any OpenAI-compatible client at:

- **Base URL:** `http://<home-assistant-host>:5001/v1`
- **API key:** your 1min.ai API key (from <https://app.1min.ai/api>)

See the [add-on documentation](./onemin_relay/DOCS.md) for details.

## License

This packaging is provided as-is. The relay itself is distributed under the
[MIT license](https://github.com/kokofixcomputers/1min-relay/blob/main/LICENSE) by
its authors.
