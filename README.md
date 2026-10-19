# ABT AI Assistant

A Windows desktop assistant that uses **Siemens ABT Openness** to inspect and engineer the project open in ABT Site. Ask questions in plain language, prepare project changes, import physical-I/O schedules, compare Excel workbooks with ABT and generate native editable graphics for separate import into ABT.

[Download the latest installer](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest) · [Release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases) · [Disclaimer](DISCLAIMER.md)

Version **0.18.3** adds complete CFC graph authoring and **Create CFC snippet**, an editable conversation starter for control logic and custom-library saving. Read the [0.18.3 release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.18.3). Supported plans include typed datapoints, block settings, layout and wiring; effective device binding, native acceptance and complete portable-library reuse remain separate checks.

The installer includes the bounded cASA answer client. Original cASA documents, excerpts, diagrams and source references remain inside the private service; users and their selected connection receive derived answers. The private service, corpus, extraction tools and credentials are excluded from installers and updates. The reviewed 184-file graphics library remains included and accessible under its existing entitlement notices.

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
| **CFC programming** | Inspect programs, charts, function blocks, pins and interconnections; compose new programs from reviewed block/datapoint profiles, check complete graphs, and prepare approved point, setting, layout, wiring and supported library-export work. |
| **CFC references and static checks** | Search/read/trace prepared local CFC libraries, capture a selected attached program into a bounded read-only snapshot, and review connection traces and static requirements scenarios. These checks do not compile, download or simulate a controller. |
| **Bulk project changes** | Select exact objects across controllers and prepare approved naming, description or allowed configuration-value changes, including text replacements and numeric transforms. |
| **Excel physical-I/O import** | Review supported points schedules, resolve controller/module/library mappings, and prepare controller, structure, point and physical-I/O assignments for an approved import. |
| **Workbook-only schedule review** | Check supported schedules without an ABT connection, retaining worksheet/cell evidence for duplicate names or addresses, missing values and explicitly configured rules. |
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
- “Help me create a reusable CFC snippet for a fan with fault inhibition and a delayed run-proof alarm. Ask for the sequence and controller, then show the complete design and explain what can be saved to my custom library.”

## Create CFC snippets

Choose **Create CFC snippet** under **Start a workflow** to draft an editable message. Send it when ready, then specify the control sequence, intended controller and library item name. The Assistant asks for decisions that affect behavior, including input/output roles, units, settings, priorities, interlocks, timing, resets and alarms. Review the complete design before approving any project change.

Version **0.18.3** composes supported sequences using 21 reviewed block profiles and nine typed datapoint profiles. Prepared plans include the required datapoints, blocks, effective parameter sources, layout and directed connections, with physical channels left unassigned. Complete-graph checks reject unknown types or pins, missing required signals, incompatible values, duplicate drivers and unsupported structures before preparation. Target preparation verifies actual supported types and reviewed help evidence; execution uses native approval, fresh state checks, verified locks and complete engineering readback. Requests outside the qualified profiles need clarification or further capability qualification. The requirement-to-signal preview still needs engineering review; a static graph check does not execute Siemens function blocks or prove the interpretation of a user's sequence.

Request library export in the plan, then inspect the reported saved contents and remaining manual steps. The observed installed Openness service exports CFC graph data and metadata without the associated BACnet datapoints. Its object-reference metadata does not establish effective device binding, and device placement and detached-program persistence remain unverified. A saved CFC artifact is therefore not proof of a complete reusable equipment package. Native custom-library placement/import, ABT Check, execution order, device binding, persistence, download and commissioning require separate acceptance in the intended environment. Alarm-condition logic does not configure BACnet notification classes, recipients or acknowledgment behavior.

## Generate graphics

Version **0.17.3** includes a graphics builder inside the Assistant. Choose **Generate graphics** in **Start a workflow**, select a sample prompt or describe your plant, equipment, connections and required readings in chat. The Assistant can assemble a complete native page from supported equipment symbols, pipe/duct connections, labels and grouped readout panels. Its 61 plant and PAC-meter examples provide layouts and reusable components; new scenes can have their own equipment counts and arrangement.

Review **Preview graphic**, then choose **Save .f5p…** and **Save supporting files…** to save the native graphic, preview, mapping schedules and validation report. Import the `.f5p` into ABT separately. Graphics generation uses your selected AI provider and the bundled graphics library; no ABT Openness connection is required.

For a graphic based on engineering data, connect to ABT and select **Graphic from ABT plant**. Name the controller and plant, for example: “Build a graphic for plant AHU1234 in controller AS5668. Inspect its points, suggest the equipment and readings, and identify any missing information.” The Assistant inspects the exact selection through existing read-only tools and can retain selected engineering-object identities in the mapping schedule. Ambiguous, incomplete or stale evidence requires resolution; point names alone do not prove physical topology.

Choose **Controller overview** to inspect plants under one exact controller. The Assistant can suggest and generate equipment dashboards, air-side or hydronic equipment overviews, room temperature tables and general point tables from captured points and their hierarchy. Relevant exact ABT naming-catalog entries help classify the evidence; an optional strict naming profile leaves unqualified names unresolved. Larger inspections and layouts continue in pages, with incomplete coverage reported. Automatic overviews use unbound placeholders, preserve each point's plant identity and keep commands, feedback, run proof, measurements and setpoints distinct. They do not infer physical connections or read current temperatures.

For the AHU21x Detailed template, qualified animation choices include numeric 0–100% fan-speed input and valve-linked heating/cooling coil colour. The result reports which choices changed the template and which existing behaviour was preserved. Renaming equipment or adding a speed caption alone does not configure animation; final animation inputs need mapping and checking in the target ABT environment.

The normal Assistant installer and update package include the reviewed library of 61 native examples, reusable components and required readout/animation metadata. Connect your AI provider to start generating graphics; there is no separate graphics installation, asset download or file-copy step. The included native assets retain their original ownership and applicable terms; notices are under `legal/` in the installation.

Generated files remain unbound. Static previews, structural validation and offline animation checks do not establish target ABT import or native animation compatibility. Live ABT acceptance remains deferred. Import, save and re-export the graphic in the intended ABT version, check native editing and animations, and verify point mappings, units, command/feedback, flow proof and quality behaviour before commissioning. Photorealistic generation and arbitrary existing `.f5p` intake are outside this release's supported scope.

Read the [0.17.3 release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.17.3).

## Local reference knowledge

Read-only lookup covers prepared local PDF, values-only XLSX and Programming Library Help reference packages. Results retain document editions, PDF page numbers or workbook worksheet/cell ranges, source hashes and linked topics so answers can cite their reference evidence. English, German and French can be selected explicitly.

Version **0.17.3** can consult the locally prepared NGA System One BACnet object/property workbook for **PXC4, PXC5, PXC7 and DXR3 only**, citing its revision, source hash, worksheet and cells. Documented data types, limits, enum choices and access notes must be checked against the actual target version, supported operations and live project evidence. This reference does not qualify other or legacy controller families or grant additional write permissions.

Documentation import, extraction and package writing belong to the owner's separate development utility. The installed Assistant has no import controls, and the utility is excluded from installers and updates. Existing knowledge packages remain in the local ABTAgent store. Siemens reference workbooks, manuals, programming archives and customer documents are not included in public downloads. Workbook formulas and macros are not executed.

Private cASA answers use the shared bounded `abt_ask_casa` tool across configured Codex, Claude API, Gemini API, OpenClaw and qualified Siemens SDC connections, plus authenticated MCP clients. A separately owner-provisioned local private service must authorize the installation and enable derived answers; no company sign-in is required. Raw-evidence generation stays on its separately approved Siemens SDC connection, with no generation fallback. Other selected connections receive derived answers without original excerpts or source references. cASA describes historical, unverified and incomplete design intent; CFC references are candidates that require independent checking against the actual target implementation.

PDF and HTML text provide reference evidence; inspect the original documents for diagrams, images and scanned content. Documentation does not establish live controller state or make additional ABT operations available. Engineering approval, locks and readback remain enforced.

Read the [0.17.3 release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.17.3).

## Requirements

- Windows x64 with permission to install a per-user application.
- For live engineering and plant inspection: a separately installed, licensed Siemens ABT Site with its hosted ABT Openness service configured and running.
- The account or gateway required by your chosen AI provider, listed below.
- For graphics generation: a connected AI provider. The installer supplies the native graphics library; generated files are imported into licensed ABT separately.
- For cASA answers: a separately owner-provisioned local private cASA service with prepared knowledge, background installation authorization and explicit answer approval. The installer supplies only its client; a new installation has no automatic cASA access.

The installer includes .NET 10, the graphics builder and its runtime graphics library. Licensed Siemens ABT software and reference documentation are supplied separately.

## AI providers

| Provider | What you need |
|---|---|
| ChatGPT / Codex | ChatGPT sign-in and a separately installed, qualified Codex runtime; uses your plan's Codex allowance. |
| Claude API | An Anthropic API key with separate API usage and billing. |
| Gemini API | A Google API key with separate API quota or billing. |
| Siemens SDC | A company-issued LLM Gateway API key and access to the selected model in the global/European region; subject to company allocation and policy. |
| OpenClaw | A separately configured local Gateway and its token or password; model access is configured in OpenClaw. |
| Claude Code (separate app) | The official installed client, using its own sign-in and conversation. |

Assistant **0.17.5** additionally accepts the exact separately installed Codex version `0.162.0-alpha.17.2`, qualified with an isolated offline runtime probe. The earlier qualified versions `0.160.1`, `0.160.0`, `0.154.0-alpha.6.2` and `0.153.4` remain supported. Earlier Assistant releases do not qualify the new version. Offline runtime qualification does not establish live account access. Direct API providers do not require Codex or Claude Code.

Use **Provider setup & billing** in the application for detailed instructions. Provider credentials, settings and conversations stay separate, with no automatic account, endpoint or model fallback.

**Siemens SDC setup.** One **Siemens SDC** connection supports qualified Claude, Gemini and OpenAI models. Choose **Model provider**, then **Model** from its filtered list. The public catalogue loads automatically without an API key; **Test & connect** verifies access to that exact model and saves the connection only after success. Other gateway models remain unavailable until their ABT tool support is verified.

**Test & connect** can consume company quota. When Siemens SDC is the saved provider and its key is remembered, reopening the desktop also checks access to the exact saved model through its saved gateway, model provider and protocol. This isolated check can consume company quota and sends only “Reply OK.” without conversation, attachments or ABT tools. **Connecting…** becomes **Connected** after success; a failed check preserves the saved connection and shows a reconnect notice. Opening Siemens SDC settings does not itself run a paid access test. Changing region, model provider or model requires explicit selection and verification. Keys stay within the selected gateway and model family, and switching families starts a fresh conversation.

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

Version **0.17.4** checks the qualified ABT Site locking startup prerequisite before engineering writes. The startup qualification currently covers ProjectServices build **62.0.2172.1**; other builds block engineering writes until qualified. If the setting is missing or was restored after ABT Site started, save the project, close ABT Site normally and reopen it as directed before preparing a new plan. The Assistant does not change that setting or restart ABT Site automatically; it still verifies actual lock ownership before device-scoped writes.

Version **0.17.5** recognizes qualified binary-contact evidence, including explicit normally-open/normally-closed signals and supported current-switch, leak-contact terminal and actuator end-switch mappings. Recognized contacts without explicit polarity use the disclosed normally-open default; explicit normally-closed signals are preserved. Conflicting wiring and unqualified signals remain for review. Remote island-bus rail connections, including IBE expansion placement, are preserved in topology readback. Application placement uses the logical Plant/Folder path, while assignment verification checks the physical module and channel.

Independent assignment batches can continue after a failed batch while the approved session remains usable. Results identify failed or unconfirmed rows and created-but-unassigned points; failed batches are never replayed automatically. An owner-approved repair and complete live readback matched all **1,030 active physical points across 21 controllers** for assignments, I/O classes, current source names and application paths. That validates the repaired existing project; it does not establish cold-project import acceptance or compatibility with every ABT build.

For a failed physical-I/O import, inspect the current project before retrying. Reconnect explicitly and prepare a fresh plan that reuses any controller already created and includes only work confirmed to be missing. Version 0.17.4 retains the original failure, displays confirmed partial work and stops scheduling further controllers after losing a usable session. Updating does not undo existing project changes or replay the original plan.

A timeout or lost reply may leave a partially completed change. Inspect the current ABT state before preparing further work; controller creation is never retried automatically after an uncertain result. Live account access, gateway compatibility and engineering changes require verification in your authorised environment.

## Updates

Open **About & updates** to check for and download updates. **Later** keeps a downloaded update staged.

Before choosing **Restart and Update**, disconnect the assistant from ABT, wait for all tasks, readback and cleanup to finish, and close other assistant sessions and companions normally. The updater rechecks readiness, blocks new ABT work during installation and waits for existing sessions to exit naturally. Active assistant/ABT work must finish; only an empty process blocked before startup may be stopped by the guarded updater.

If readiness is unconfirmed or guards/helpers are unavailable, use **Download installer ↗** after finishing work and closing sessions normally. Settings and credentials are retained across updates; updates do not undo ABT project changes.

## Help

- **Interface size (0.17.4):** use **Ctrl + mouse wheel** or the bottom **− / +** controls to scale text, buttons and panels from 70% to 150%. **Ctrl+0** or the percentage button resets to 100%. Zoom lasts for the current window session.
- **Connection problems:** check that ABT Site's hosted Openness service is configured and running. The assistant does not start Siemens services or restart ABT Site automatically.
- **Provider setup:** open **Provider setup & billing** in the application.
- **Graphics library unavailable:** finish Assistant/ABT work and close Assistant sessions and companion windows normally, then repair or update using the normal Setup installer. The graphics library is included; no separate asset pack is required.
- **Windows trust warnings:** follow [CODE_SIGNING.md](CODE_SIGNING.md). SmartScreen or company policy may still block a self-signed application; keep Windows protections enabled.
- **Download problems:** continue using the installed version and retry later, or download Setup from the latest release. Finish active work before repair or reinstall.
- **Issues:** [report a problem](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/issues) without customer projects, credentials, private logs or Siemens reference material. Third-party notices are included under `legal/` in the installed application.
