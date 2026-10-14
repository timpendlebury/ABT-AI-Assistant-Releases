# ABT AI Assistant

A Windows desktop assistant that uses **Siemens ABT Openness** to inspect and engineer the project open in ABT Site. Ask questions in plain language, prepare project changes, import physical-I/O schedules, compare Excel workbooks with ABT and generate native editable graphics for separate import into ABT.

[Download the latest installer](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest) · [Release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases) · [Disclaimer](DISCLAIMER.md)

The latest published installer is **0.17.1**. **0.17.2 is in preparation** with an included graphics library and a redesigned Siemens SDC connection. The upcoming features described below are not yet in the public download.

> ABT AI Assistant is an independent, unofficial third-party tool developed in a personal capacity. It is not an official Siemens product and is not affiliated with, sponsored, endorsed or supported by Siemens AG or any other vendor or manufacturer. To the extent permitted by applicable law, the software is provided "as is", without warranty of any kind, express or implied. No ongoing support, updates or maintenance are promised. Use of the tool is at the user's own risk. Users should maintain appropriate project backups and independently review and validate all outputs and changes before applying them.

## ABT Openness capabilities

The assistant connects to your open project through the **local ABT Openness service**. It reads actual engineering data and turns natural-language requests into reviewable plans for supported ABT operations.

| Area | Capabilities |
|---|---|
| **Project exploration** | List controllers, inspect models and application structures, and search datapoints, domain parameters and building-automation (BA) properties by name, hierarchy, type or current value. |
| **Controllers and templates** | Discover supported controller types and existing device templates; prepare controller creation, batch creation, renaming, template-based instances, supported SVS upgrades and explicit deletion where enabled. |
| **Hierarchy and application structure** | Explore buildings, floors and rooms; prepare supported hierarchy changes and create or organise Plants, Coordination, Equipment and Folders. |
| **TX-I/O engineering** | Inspect rails, modules and point assignments; discover compatible modules and library points; prepare rails, modules, datapoints and channel assignment changes. |
| **Modbus engineering** | Inspect available libraries and serial ports; prepare supported TCP/RTU networks, devices, library-device instances and datapoints using explicit communication and register settings. |
| **Application libraries** | Find controller-compatible applications, inspect configurations, and prepare application-configuration creation, option/variant selections and user-designation assignments. |
| **CFC programming** | Inspect programs, charts, function blocks, pins and interconnections; prepare supported chart, block, pin-value and connection edits. |
| **Bulk project changes** | Select exact objects across controllers and prepare approved naming, description or allowed configuration-value changes, including text replacements and numeric transforms. |
| **Excel physical-I/O import** | Review supported points schedules, resolve controller/module/library mappings, and prepare controller, structure, point and physical-I/O assignments for an approved import. |
| **Excel and ABT reconciliation** | Compare an existing workbook with ABT, review mismatches and choose the source for supported name, description and I/O assignment updates. Excel output is a revised copy. |
| **ABT help and engineering guidance** | Search locally installed ABT and Programming Library Help, plus prepared local reference packages; explain documented functions and relate application recommendations to live controller-compatible libraries. |

**You review the action before it changes the project.** Preparation is read-only; applying a plan requires explicit approval and state checks, followed by verification of the result. Available actions depend on your ABT version, enabled services and local configuration; implemented tools do not establish live compatibility with every installation.

Project creation remains in ABT Site. Hardware commissioning, controller downloads and runtime commands are outside the assistant's supported tools. Use the desktop chat or connect a compatible AI client through the local MCP integration.

### Example requests

- “Show the controllers in this project and their I/O module layouts.”
- “Prepare a consistent naming update for the points I select, and show the plan before applying it.”
- “Review this points schedule and show the proposed controllers, modules and point assignments before making changes.”
- “Compare this workbook with ABT and show which names, descriptions or I/O assignments differ.”
- “Show compatible library applications for this controller and explain which match my AHU requirements.”

## Generate graphics

Version **0.17.1** adds a graphics builder inside the Assistant. Choose **Generate graphics** in **Start a workflow**, select a sample prompt or describe your plant, equipment, connections and required readings in chat. The Assistant can assemble a complete native page from supported equipment symbols, pipe/duct connections, labels and grouped readout panels. Its 61 plant and PAC-meter examples provide layouts and reusable components; new scenes can have their own equipment counts and arrangement.

Review **Preview graphic**, then choose **Save .f5p…** and **Save supporting files…** to save the native graphic, preview, mapping schedules and validation report. Import the `.f5p` into ABT separately. Graphics generation needs the selected AI provider and local graphics library, with no ABT Openness connection required.

For a graphic based on engineering data, connect to ABT and select **Graphic from ABT plant**. Name the controller and plant, for example: “Build a graphic for plant AHU1234 in controller AS5668. Inspect its points, suggest the equipment and readings, and identify any missing information.” The Assistant inspects the exact selection through existing read-only tools and can retain selected engineering-object identities in the mapping schedule. Ambiguous, incomplete or stale evidence requires resolution; point names alone do not prove physical topology.

**Upcoming 0.17.2:** the normal Assistant installer and update package will include the reviewed library of 61 native examples, reusable components and required metadata. Graphics generation will be available after connecting an AI provider, with no separate graphics installation or file-copy step.

**Current public 0.17.1:** the graphics builder is included, but its required library is not. Graphics generation needs a separately provisioned library in the local ABTAgent graphics store. The upcoming package corrects this installation gap.

Generated files remain unbound. Static previews and structural validation do not establish target ABT import or native animation compatibility. Import, save and re-export the graphic in the intended ABT version, check native editing and animations, and verify point mappings, units, command/feedback, flow proof and quality behaviour before commissioning. Photorealistic generation and arbitrary existing `.f5p` intake are outside this release's supported scope.

Read the [0.17.1 release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.17.1).

## Local reference knowledge

Version **0.16.10** expands read-only lookup across the prepared local PDF and Programming Library Help collection. Results retain document editions, PDF page numbers and linked topics so answers can cite their reference evidence. English, German and French can be selected explicitly.

Documentation import, extraction and package writing belong to the owner's separate development utility. The installed Assistant has no import controls, and the utility is excluded from installers and updates. Existing knowledge packages remain in the local ABTAgent store. Siemens manuals, programming archives and customer documents are not included in public downloads.

PDF and HTML text provide reference evidence; inspect the original documents for diagrams, images and scanned content. Documentation does not establish live controller state or make additional ABT operations available. Engineering approval, locks and readback remain enforced.

Read the [0.16.10 release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.16.10).

## Requirements

- Windows x64 with permission to install a per-user application.
- For live engineering and plant inspection: a separately installed, licensed Siemens ABT Site with its hosted ABT Openness service configured and running.
- The account or gateway required by your chosen AI provider, listed below.
- For graphics generation: a connected AI provider and the graphics library described above. Generated files are imported into licensed ABT separately.

The installer includes .NET 10 and the graphics builder code; upcoming 0.17.2 also includes its runtime graphics library. Licensed Siemens ABT software and reference documentation are supplied separately.

## AI providers

| Provider | What you need |
|---|---|
| ChatGPT / Codex | ChatGPT sign-in and a separately installed, qualified Codex runtime; uses your plan's Codex allowance. |
| Claude API | An Anthropic API key with separate API usage and billing. |
| Gemini API | A Google API key with separate API quota or billing. |
| Siemens SDC | A company-issued LLM Gateway API key and access to the selected model in the global/European region; subject to company allocation and policy. |
| OpenClaw | A separately configured local Gateway and its token or password; model access is configured in OpenClaw. |
| Claude Code (separate app) | The official installed client, using its own sign-in and conversation. |

Assistant **0.16.8 and later** supports Codex `0.160.1`, `0.160.0`, `0.154.0-alpha.6.2` and `0.153.4`. Older assistant builds reject `0.160.1`. Direct API providers do not require Codex or Claude Code.

Use **Provider setup & billing** in the application for detailed instructions. Provider credentials, settings and conversations stay separate, with no automatic account, endpoint or model fallback.

**Upcoming 0.17.2: simpler Siemens SDC setup.** One **Siemens SDC** connection supports qualified Claude, Gemini and OpenAI models. Choose **Model provider**, then **Model** from its filtered list. The public catalogue loads automatically without an API key; **Test & connect** verifies access to that exact model and saves the connection only after success. Other gateway models remain unavailable until their ABT tool support is verified.

Opening settings or starting the upcoming version does not make a paid model-access request. **Test & connect** consumes company quota and sends a small test message without conversation, attachments or ABT tools. Changing region, model provider or model requires explicit selection and verification. Keys stay within the selected gateway and model family, and switching families starts a fresh conversation.

**Current public 0.17.1:** Siemens SDC supports Claude only. Its saved-model startup access check can consume company quota. The catalogue fixes and redesigned connection above will arrive in the next publication.

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

Engineering changes require explicit approval and readback checks, with verified device locks for device-scoped operations. Cancellation, expiry and closing the assistant never approve an action. **Disconnect** releases the assistant's connection while leaving the project open in ABT Site.

A timeout or lost reply may leave a partially completed change. Inspect the current ABT state before preparing further work; controller creation is never retried automatically after an uncertain result. Live account access, gateway compatibility and engineering changes require verification in your authorised environment.

## Updates

Open **About & updates** to check for and download updates. **Later** keeps a downloaded update staged.

Before choosing **Restart and Update**, disconnect the assistant from ABT, wait for all tasks, readback and cleanup to finish, and close other assistant sessions and companions normally. The updater rechecks readiness, blocks new ABT work during installation and waits for existing sessions to exit naturally. Active assistant/ABT work must finish; only an empty process blocked before startup may be stopped by the guarded updater.

If readiness is unconfirmed or guards/helpers are unavailable, use **Download installer ↗** after finishing work and closing sessions normally. Settings and credentials are retained across updates; updates do not undo ABT project changes.

## Help

- **Connection problems:** check that ABT Site's hosted Openness service is configured and running. The assistant does not start Siemens services or restart ABT Site automatically.
- **Provider setup:** open **Provider setup & billing** in the application.
- **Graphics library unavailable in 0.17.1:** this version requires a separately provisioned local library. Upcoming 0.17.2 will include the library in the normal installer and update package.
- **Windows trust warnings:** follow [CODE_SIGNING.md](CODE_SIGNING.md). SmartScreen or company policy may still block a self-signed application; keep Windows protections enabled.
- **Download problems:** continue using the installed version and retry later, or download Setup from the latest release. Finish active work before repair or reinstall.
- **Issues:** [report a problem](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/issues) without customer projects, credentials, private logs or Siemens reference material. Third-party notices are included under `legal/` in the installed application.
