# ABT AI Assistant

[Download the latest Windows installer](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest)

This repository distributes Windows installers and application updates for ABT
AI Assistant. The source repository is private. Download the Setup EXE from the
latest stable release below.

> ABT AI Assistant is an independent, unofficial third-party tool developed in a personal capacity. It is not an official Siemens product and is not affiliated with, sponsored, endorsed or supported by Siemens AG or any other vendor or manufacturer. To the extent permitted by applicable law, the software is provided "as is", without warranty of any kind, express or implied. No ongoing support, updates or maintenance are promised. Use of the tool is at the user's own risk. Users should maintain appropriate project backups and independently review and validate all outputs and changes before applying them.

## Requirements

Version **0.16.9** brings action approvals into a blocking review panel inside
the desktop window, verifies saved Siemens SDC model access at startup, and
shares the independent third-party disclaimer across the application and release
materials. The qualified signed **0.16.9** release is published as the latest
public stable version.

Connection confirmations, prepared engineering changes, physical-I/O imports
and Excel/ABT reconciliation appear inside the assistant window. Review the
complete details, tick the review checkbox when required, then choose
**Accept action** or **Decline**. The window draws attention to pending approval
and blocks its other controls until the decision finishes. Cancellation, expiry,
closing the assistant or a missing approval interface never grant approval.
Exact-plan validation, device locks and readback remain enforced. Standalone
MCP clients retain their native confirmation dialogs.

When Siemens SDC is your saved provider, startup restores its remembered key
and tests the exact saved model at the saved gateway. **Connecting…** changes
to **Connected** only after a valid response. This isolated eight-token access
test can consume company quota; it sends no conversation, attachments or ABT
tools. Failed checks never switch providers, gateways or models. Missing
credentials or an unavailable saved model require an explicit connection or
model choice.

Version **0.16.8** added support for the separately installed **Codex CLI 0.160.1**,
restoring ChatGPT/Codex connection after that runtime update. Previous qualified
versions remain supported. An unsupported-version message now identifies the
recognized installed runtime; failure to check its version has a separate safe
message. ChatGPT sign-in and credential storage remain unchanged.

Controller creation retains its own 120-second default
timeout, allowing ABT Site more time to create each controller in an approved
workflow. A larger configured timeout is respected. After a controller is
confirmed and checked, the workflow automatically proceeds to the next
controller covered by the same approval. Device locks, approval and readback
checks remain enforced.

If creation or verification fails, the workflow stops. A timeout or lost reply
can leave a controller created in ABT Site without confirmed completion in the
assistant. It never retries that creation automatically: inspect the current
controllers and prepare a new plan for only those still missing before retrying.

Failed **Connect** attempts show a persistent explanation,
including when the hosted Openness endpoint is unavailable. Hosted discovery
distinguishes missing startup discovery files from endpoint validation failures.
The hosted Openness service still needs to be configured and running in ABT Site;
the assistant does not start Siemens services or restart ABT Site automatically.

Claude API, Siemens SDC Claude, Gemini API and OpenClaw setup restore the masked
saved credential and **Remember** choice when reopened. An unchanged credential
keeps its chosen storage mode. Providers and connection settings keep separate
credentials; a different endpoint or OpenClaw agent/authentication method loads
only its own matching credential.

The assistant keeps the ABT project status and connected project
name visible in the main conversation header, including with the sidebar hidden.
**Connect** changes to **Disconnect** after a confirmed attachment; **Refresh**
checks its status. These actions use the existing native session controls without
an AI prompt. Disconnect leaves the project open in ABT Site. Native events and
idle checks every 15 seconds update the display; unconfirmed or lost connections
never reconnect automatically.

**Start a workflow** now sits above the conversation, separate from provider
settings and updates. Its six suggestions fill an editable draft, preserve any
existing draft and wait for you to send. They collapse after the first message
and can be reopened; short windows keep the composer visible.

**Siemens SDC** remains Claude-only, retaining the global/European gateway choice
and existing Claude keys. Direct Google **Gemini API** remains available separately.
An old SDC Gemini selection opens disconnected and requires an explicit supported
connection; its saved keys and preferences are preserved without reuse.

Signed Windows distribution uses T. Pendlebury's existing
self-signed code-signing certificate, introduced in 0.16.3. Read [certificate verification and opt-in
trust](CODE_SIGNING.md); independently confirm its SHA-256 fingerprint before
choosing to import the public .cer. Signing does not guarantee Windows policy
acceptance. The guarded automatic updates added in 0.16.2 remain: **Restart and Update** becomes
available when this assistant has disconnected its ABT project and confirmed
that its tasks and cleanup have completed. The startup barrier prevents new
assistant/companion ABT work during installation. See the
[release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.16.9).
Siemens SDC model discovery remains separate from API-key verification, and
provider settings can collapse while keeping their provider, model and status
visible.
Controller deadlines, five-controller workflows and recovery after a lost reply
are covered by offline tests, alongside connection controls, workflow suggestions
and Gemini client behavior. Offline regression also covers approval rendering
and control bindings, explicit decisions, cancellation and expiry, exact
request identity, provider/model isolation, saved credential scopes and malformed
startup-verification replies. The local regression run passed 1,555 tests, with
three existing opt-in skips. Codex **0.160.1** passed the unchanged offline
runtime qualification using a fake model, without a real account or OpenAI/ABT
request.
Live controller creation, account access, gateway compatibility, live ABT
connection validation and ABT engineering acceptance require separate
verification with authorized accounts.

- Windows x64 supported by .NET 10, with permission to install a per-user application.
- A separately installed and licensed Siemens ABT Site installation with its
  local ABT Openness service available. Siemens software and documentation are
  not included.
- The prerequisites for the model provider you select. Codex mode requires a
  separately installed qualified Codex runtime (`0.160.1`, `0.160.0`,
  `0.154.0-alpha.6.2` or `0.153.4` in **0.16.8** and later) and ChatGPT sign-in.
  Builds **0.16.7** and earlier retain their previous exact runtime allow-lists
  and reject **0.160.1**; update the assistant to **0.16.8** or later to use it.
  Direct Claude/Gemini APIs and Siemens SDC Claude use
  separate API credentials and do not require Codex or Claude Code. Native
  Claude Code and OpenClaw are optional external clients installed and configured
  by the user. Siemens SDC offers global/European endpoint choices; model access remains subject to company allocation and policy.

The installer includes the .NET 10 runtime. You do not need a GitHub account,
Git, the .NET SDK or Visual Studio to download and use it.

Use **Provider setup & billing** in the application for its packaged guide to
all six account routes, required installations, sign-in, model refresh,
credential storage and common failures. ChatGPT uses the selected plan's Codex
allowance; direct Claude/Gemini APIs use separate API accounts; Siemens SDC uses
company access and allocation. OpenClaw's model account is configured upstream.
**Open Claude Code (separate app)** opens the official client's own conversation.
The application does not display a verified monetary balance or switch accounts
automatically when access or quota fails.

## Install and update

1. Open the latest release and download `ABTAIAssistant-stable-Setup.exe` and the
   public `T-Pendlebury-code-signing.cer`. Follow [signature verification](CODE_SIGNING.md)
   and make your own trust choice before running the signed installer.
2. Finish any ABT work and close existing assistant sessions and companion
   windows normally, then run the installer and start ABT AI Assistant.
3. Configure the local ABT connection and selected provider in the application.

**Upgrading from unsigned 0.16.2 or earlier:** use the signed Setup EXE once.
The unsigned native updater cannot pass its original byte-equality check against
a newly signed native updater. Earlier installations also need the startup
barrier and dedicated helper. Unsupported transitions offer the installer.

For subsequent guarded installations, open **About & updates** and choose
**Download update**. **Later** keeps the package staged. Disconnect this
assistant from its ABT project, let all tasks and readback/cleanup finish, then
choose **Restart and Update** when its readiness message allows it. The action
rechecks readiness, blocks new work, waits for normal application exit and
applies the verified update. Other assistant windows and ABT companions,
including those used by external Claude Code or OpenClaw, must close normally.
Readiness concerns the assistant's connection; it does not require every project
in ABT Site to close. Detaching leaves ABT Site's project open.

The native updater still has
[force-stop behavior](https://github.com/velopack/velopack/blob/1.2.161/src/bins/src/shared/util_windows.rs#L81).
On 6 October 2026 the owner approved guarded updates with possible termination
only of an empty process blocked before startup; active assistant/ABT work must
finish and exit naturally. If guards/helpers are unavailable, use **Download
installer ↗** or the Setup EXE from **Release notes ↗**, after finishing work and
closing all assistant sessions and companions normally. Unconfirmed cleanup or
an update failure blocks automatic installation. Keep project backups and
review proposed engineering changes before approving them.

Settings and credentials remain in their established per-user storage across
application updates. Updates do not roll back ABT project changes.

## Troubleshooting

If a network check or download fails, continue using the installed version and
retry later. You can also download the latest installer from this repository.
Do not run a repair or reinstall while ABT operations or companion processes
are active; close them cleanly first. Preserve project backups and user data
before any recovery work.

Historical installers are unsigned. Current signed installers use the exact
public identity in [CODE_SIGNING.md](CODE_SIGNING.md). Only the public .cer and
fingerprint are distributed; users never need a PFX, private key or password.
SmartScreen may still warn, and Smart App Control or enterprise policy may block
self-signed applications. Respect your organization's policy and do not disable
Windows protections.

Third-party package metadata and available license texts are included under
`legal/` in the installed application. Report issues through this repository
without attaching customer projects, credentials, private logs or Siemens
reference material.
