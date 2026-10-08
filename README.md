# ABT AI Assistant

A Windows desktop assistant for Siemens ABT engineering. Explore project data, prepare reviewed changes, import physical-I/O schedules and compare Excel workbooks with ABT.

[Download the latest installer](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest) · [Release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases) · [Disclaimer](DISCLAIMER.md)

## Features

- Inspect controllers, application structures, parameters and properties, and search local ABT reference material.
- Prepare engineering changes with explicit approval, device locking and readback verification.
- Review supported Excel physical-I/O imports and reconcile workbook data with an existing ABT project.
- Chat in the desktop or use the local MCP integration with a compatible AI client.

## Requirements

- Windows x64 with permission to install a per-user application.
- A separately installed, licensed Siemens ABT Site with its hosted ABT Openness service configured and running.
- The account or gateway required by your chosen AI provider, listed below.

The installer includes .NET 10. Siemens software and documentation are supplied separately.

## AI providers

| Provider | What you need |
|---|---|
| ChatGPT / Codex | ChatGPT sign-in and a separately installed, qualified Codex runtime; uses your plan's Codex allowance. |
| Claude API | An Anthropic API key with separate API usage and billing. |
| Gemini API | A Google API key with separate API quota or billing. |
| Siemens SDC | Company-issued Claude access for the selected global/European gateway; subject to company allocation and policy. |
| OpenClaw | A separately configured local Gateway and its token or password; model access is configured in OpenClaw. |
| Claude Code (separate app) | The official installed client, using its own sign-in and conversation. |

Assistant **0.16.8 and later** supports Codex `0.160.1`, `0.160.0`, `0.154.0-alpha.6.2` and `0.153.4`. Older assistant builds reject `0.160.1`. Direct API providers do not require Codex or Claude Code.

Use **Provider setup & billing** in the application for detailed instructions. Provider credentials, settings and conversations stay separate, with no automatic account, endpoint or model fallback. Siemens SDC is Claude-only; its saved-model startup access check can consume company quota without sending conversation, attachments or ABT tools.

## Install

1. Open the [latest release](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest) and download `ABTAIAssistant-stable-Setup.exe` and `T-Pendlebury-code-signing.cer`.
2. Follow [signature verification and optional certificate trust](CODE_SIGNING.md). Installers use a self-signed certificate; independently confirm its fingerprint and follow your organisation's policy.
3. Finish existing ABT work and close assistant sessions and companion windows normally, then run Setup.
4. Start ABT AI Assistant and connect your chosen AI provider.

**Upgrading from unsigned 0.16.2 or earlier:** run the signed Setup installer once before using in-app updates.

## Use with ABT

1. Open the intended project in ABT Site and keep a single ABT Site instance running.
2. Choose **Connect** in the assistant, confirm the project and enter ABT credentials in the local sign-in dialog.
3. Use a workflow suggestion or type a request. Review the proposed action, tick the review checkbox when required, then choose **Accept action** or **Decline**.

Engineering changes require explicit approval, verified device locks and readback. Cancellation, expiry and closing the assistant never approve an action. **Disconnect** releases the assistant's connection while leaving the project open in ABT Site.

A timeout or lost reply may leave a partially completed change. Inspect the current ABT state before preparing further work; controller creation is never retried automatically after an uncertain result. Live account access, gateway compatibility and engineering changes require verification in your authorised environment.

## Updates

Open **About & updates** to check for and download updates. **Later** keeps a downloaded update staged.

Before choosing **Restart and Update**, disconnect the assistant from ABT, wait for all tasks, readback and cleanup to finish, and close other assistant sessions and companions normally. The updater rechecks readiness, blocks new ABT work during installation and waits for existing sessions to exit naturally. Active assistant/ABT work must finish; only an empty process blocked before startup may be stopped by the guarded updater.

If readiness is unconfirmed or guards/helpers are unavailable, use **Download installer ↗** after finishing work and closing sessions normally. Settings and credentials are retained across updates; updates do not undo ABT project changes.

## Help

- **Connection problems:** check that ABT Site's hosted Openness service is configured and running. The assistant does not start Siemens services or restart ABT Site automatically.
- **Provider setup:** open **Provider setup & billing** in the application.
- **Windows trust warnings:** follow [CODE_SIGNING.md](CODE_SIGNING.md). SmartScreen or company policy may still block a self-signed application; keep Windows protections enabled.
- **Download problems:** continue using the installed version and retry later, or download Setup from the latest release. Finish active work before repair or reinstall.
- **Issues:** [report a problem](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/issues) without customer projects, credentials, private logs or Siemens reference material. Third-party notices are included under `legal/` in the installed application.

## Disclaimer

ABT AI Assistant is an independent, unofficial third-party tool developed in a personal capacity. Read the full [disclaimer](DISCLAIMER.md) before use, keep project backups and independently validate proposed changes.
