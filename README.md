# ABT AI Assistant

[Download the latest Windows installer](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest)

This repository distributes Windows installers and application updates for ABT
AI Assistant. The source repository is private. Download the Setup EXE from the
latest stable release below.

> ABT AI Assistant is an independently developed third-party tool. It is not an
> official Siemens product and is not sponsored, endorsed or supported by
> Siemens AG. The software is provided as-is and is used at the user's own
> risk. Users should maintain appropriate project backups and review/validate
> changes before applying them.

## Requirements

Version **0.16.2** adds guarded automatic updates. **Restart and Update** becomes
available when this assistant has disconnected its ABT project and confirmed
that its tasks and cleanup have completed. The startup barrier prevents new
assistant/companion ABT work during installation. See the
[release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.16.2).
Siemens SDC model discovery remains separate from API-key verification, and
provider settings can collapse while keeping their provider, model and status
visible.
Gemini client behavior is covered by offline tests; live account access,
gateway compatibility and ABT engineering acceptance require separate
verification with authorized accounts.

- Windows x64 supported by .NET 10, with permission to install a per-user application.
- A separately installed and licensed Siemens ABT Site installation with its
  local ABT Openness service available. Siemens software and documentation are
  not included.
- The prerequisites for the model provider you select. Codex mode requires a
  separately installed qualified Codex runtime (`0.160.0`, `0.154.0-alpha.6.2` or `0.153.4`)
  and ChatGPT sign-in. Direct Claude/Gemini APIs and Siemens SDC Claude/Gemini use
  separate API credentials and do not require Codex or Claude Code. Native
  Claude Code and OpenClaw are optional external clients installed and configured
  by the user. Siemens SDC offers global/European endpoint choices; model access remains subject to company allocation and policy.

The installer includes the .NET 10 runtime. You do not need a GitHub account,
Git, the .NET SDK or Visual Studio to download and use it.

Use **Provider setup & billing** in the application for its packaged guide to
all seven account routes, required installations, sign-in, model refresh,
credential storage and common failures. ChatGPT uses the selected plan's Codex
allowance; direct Claude/Gemini APIs use separate API accounts; Siemens SDC uses
company access and allocation. OpenClaw's model account is configured upstream.
**Open Claude Code (separate app)** opens the official client's own conversation.
The application does not display a verified monetary balance or switch accounts
automatically when access or quota fails.

## Install and update

1. Open the latest release and download `ABTAIAssistant-stable-Setup.exe`.
2. Finish any ABT work and close existing assistant sessions and companion
   windows normally, then run the installer and start ABT AI Assistant.
3. Configure the local ABT connection and selected provider in the application.

**Upgrading from 0.16.1 or earlier:** use the Setup EXE once to install 0.16.2's
startup barrier and dedicated update helper. Older installations cannot acquire
these safeguards through their disabled restart action.

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

Initial installers may be unsigned. Windows may show a SmartScreen warning;
review the download origin and your organization's policy before running the
installer. Do not disable Windows protection or install an untrusted
certificate to suppress warnings.

Third-party package metadata and available license texts are included under
`legal/` in the installed application. Report issues through this repository
without attaching customer projects, credentials, private logs or Siemens
reference material.
