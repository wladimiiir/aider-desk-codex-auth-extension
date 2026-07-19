# ⚠️ Deprecated — Codex Auth Provider

> **This repository is deprecated.** The extension is now part of the officially supported AiderDesk extensions and is maintained in-repo at [hotovo/aider-desk — `packages/extensions/extensions/openai-codex`](https://github.com/hotovo/aider-desk/tree/main/packages/extensions/extensions/openai-codex).

Install it directly from the AiderDesk extension registry:

```bash
npx -y @aiderdesk/extensions install openai-codex --global
```

No further updates will be published to this standalone repository. Existing installs will continue to work until OpenAI or AiderDesk introduces breaking changes — please migrate to the official in-repo version to receive updates.

---

Codex Auth Provider is an extension for [AiderDesk](https://aiderdesk.hotovo.com) ([GitHub](https://github.com/hotovo/aider-desk)).

It provides an OpenAI Codex provider using **ChatGPT Plus/Pro OAuth authentication**. No API key required — authenticate with your ChatGPT subscription directly through the browser.

## Installation

You can install the extension either with the AiderDesk extensions CLI or manually.

### Option 1: Install with the extensions CLI globally for all projects

```bash
npx -y @aiderdesk/extensions install https://github.com/wladimiiir/aider-desk-codex-auth-extension --global
```

### Option 2: Manual installation

Clone the repository into your `~/.aider-desk/extensions/` folder and install dependencies:

```bash
cd ~/.aider-desk/extensions/
git clone https://github.com/wladimiiir/aider-desk-codex-auth-extension
cd aider-desk-codex-auth-extension
npm install
```

After installation, AiderDesk will pick up the extension automatically via hot reload.

## Usage

1. In AiderDesk, open the model selector.
2. Find **Codex Auth Provider** and choose one of its models (e.g., `gpt-5.4`, `gpt-5.3-codex`, `gpt-5.2`).
3. Start a task — on first use, your browser will open for OpenAI login.
4. Complete the login with your ChatGPT Plus/Pro account.
5. After authentication, you'll see a success page and can return to AiderDesk.

The access token is stored locally in `.aider-desk/extensions/openai-auth/auth-token.json` and will be automatically refreshed when it expires. You will not need to re-authenticate unless the refresh token becomes invalid.

## Available Models

Since Codex OAuth tokens cannot access the `/v1/models` API, the available models are hardcoded in the extension based on the [official Codex models page](https://developers.openai.com/codex/models):

| Model               | Description                                  |
| ------------------- | -------------------------------------------- |
| `gpt-5.6-sol`       | Flagship GPT-5.6 model for complex coding, computer use, research, and cybersecurity |
| `gpt-5.6-terra`     | Balanced GPT-5.6 model for everyday work |
| `gpt-5.6-luna`      | Fast and affordable GPT-5.6 model for cost-sensitive, high-volume tasks |
| `gpt-5.4`           | Flagship frontier model for professional work |
| `gpt-5.4-mini`      | Fast, efficient mini model for responsive tasks |
| `gpt-5.3-codex`     | Industry-leading coding model                |
| `gpt-5.2-codex`     | Advanced coding model                        |
| `gpt-5.2`           | Previous general-purpose model               |
| `gpt-5.1-codex-max` | Optimized for long-horizon agentic coding    |
| `gpt-5.1-codex-mini`| Cost-effective coding model                  |

## Troubleshooting

- **Browser doesn't open** — Check that AiderDesk has permission to open external URLs.
- **Authentication keeps failing** — Delete `.aider-desk/extensions/openai-auth/auth-token.json` and try again.

## Requirements

- [AiderDesk](https://aiderdesk.hotovo.com) with extension support
- ChatGPT Plus or Pro subscription
- Node.js ≥ 22

## ⚠️ Usage Notice

This plugin is for personal development use with your own ChatGPT Plus/Pro subscription. For production or multi-user applications, use the OpenAI Platform API.
