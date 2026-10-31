# Deploy and Host SillyTavern on Railway

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/new/template/sillytavern-server?referralCode=sLjDXb&utm_medium=integration&utm_source=button&utm_campaign=sillytavern-server)

[SillyTavern](https://github.com/SillyTavern/SillyTavern) is the power-user chat front end for large language models: character cards, group chats, lorebooks (world info), personas, prompt presets and a big extension ecosystem, on top of whatever API you bring: OpenAI, Claude, Gemini, OpenRouter, DeepSeek, KoboldCpp, Ollama and dozens more. This template runs a pinned SillyTavern release that is password-protected from the first boot, with your chats and characters on a volume.

## About Hosting SillyTavern

One service, the official SillyTavern image, with a volume over its data directory: characters, chats, settings, presets, backgrounds and uploads all survive redeploys.

SillyTavern opened to the internet without protection is an open door to your API keys, so this template turns on SillyTavern's password login before anyone can reach it. The username is `admin` and the password is generated when you deploy. Every page and API call needs it.

## Common Use Cases

- Roleplay and character chat from any device, phone included, with one shared library
- A private front end for OpenRouter, Claude, OpenAI or a local model on another server
- Group chats where several characters talk to each other and to you
- Long-running stories with lorebooks and memory that stay put between sessions

## Dependencies for SillyTavern Hosting

- An API key for at least one model provider (OpenRouter, OpenAI, Anthropic, Google, DeepSeek, ...), or the URL of your own model server.

### Deployment Dependencies

- [SillyTavern on GitHub](https://github.com/SillyTavern/SillyTavern)
- [SillyTavern docs](https://docs.sillytavern.app)
- [OpenRouter](https://openrouter.ai) for one key to many models (optional)

### Implementation Details

**First use:**

1. Open the SillyTavern service's domain once it's green.
2. Log in as `admin` with `SILLYTAVERN_BASICAUTHUSER_PASSWORD` from the service's Variables tab.
3. Click the plug icon (API Connections), pick your provider and paste your API key.

**Change the login:** edit `SILLYTAVERN_BASICAUTHUSER_USERNAME` or `SILLYTAVERN_BASICAUTHUSER_PASSWORD` and redeploy.

**Any setting in config.yaml** can be set the same way: the variable name is `SILLYTAVERN_` plus the key path in capitals with dots as underscores. For example, `SILLYTAVERN_ENABLEUSERACCOUNTS=true` turns on separate user accounts.

**Local models on Railway:** a model server in the same project (Ollama, KoboldCpp) is reachable on its private domain, e.g. `http://ollama.railway.internal:11434`.

Notes and limits:

- Five wrong passwords in a minute lock that visitor out for the rest of the minute.
- Extensions installed from the UI live on the volume and survive redeploys. A new SillyTavern release may need updated extensions.
- Each template update pins a newer SillyTavern release. Back up the volume (Railway backups) before updating.

## Why Deploy SillyTavern on Railway?

Railway is a singular platform to deploy your infrastructure stack. Railway will host your infrastructure so you don't have to deal with configuration, while allowing you to vertically and horizontally scale it.

By deploying SillyTavern on Railway, you are one step closer to supporting a complete full-stack application with minimal burden. Host your servers, databases, AI agents, and more on Railway.
