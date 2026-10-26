# ABT AI Assistant

A Windows desktop assistant that uses **Siemens ABT Openness** to inspect and engineer the project open in ABT Site. Ask questions in plain language, prepare project changes, import physical-I/O schedules, compare Excel workbooks with ABT and generate native editable graphics for separate import into ABT.

[Download the latest installer](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest) · [Release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases) · [Disclaimer](DISCLAIMER.md)

> ABT AI Assistant is an independent, unofficial third-party tool developed in a personal capacity. It is not an official Siemens product and is not affiliated with, sponsored, endorsed or supported by Siemens AG or any other vendor or manufacturer. To the extent permitted by applicable law, the software is provided "as is", without warranty of any kind, express or implied. No ongoing support, updates or maintenance are promised. Use of the tool is at the user's own risk. Users should maintain appropriate project backups and independently review and validate all outputs and changes before applying them.
>
> Usage statistics apply only to releases that include usage reporting. On first launch of such a release, acknowledging this disclaimer enables reporting unless an existing reporting preference or administrator policy disables it. You can disable reporting at any time under Privacy & usage without losing access to the tool.
>
> The publisher uses a private PostHog Cloud project hosted in the European Union to measure installation activity, feature use and update adoption. Reports contain a random installation identifier that persists across updates, session and conversation identifiers, conversation and assistant-turn counts, turn outcomes, AI connection/provider and reviewed public model identifiers, the running app version, timestamps and the Windows configured country/region. The country/region is a computer setting, not a verified physical location. The installation identifier represents a Windows user profile, not a named person or guaranteed distinct PC; activity from that installation can be linked over time.
>
> Usage reports exclude conversation text, prompts, replies, attachments, customer and project content, usernames, email addresses, computer names, hardware identifiers and credentials. IP-based location enrichment is disabled; the analytics service still receives the network source IP when a connection is made. Reporting is independent of your AI provider and does not train AI models. Private knowledge access and requests sent to your selected AI provider follow their separate configurations and terms.
>
> Unsent statistics expire after seven days and are removed when the application next processes its reporting queue. Disabling reporting cancels pending delivery and removes unsent statistics; it does not delete information already received by PostHog, which remains subject to the project's retention and deletion settings. Statistics and installation identifiers are not published to the public releases repository. Questions about usage reporting can be raised with the publisher through the public repository's issue tracker; do not post installation identifiers, credentials or project data publicly.

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

Choose **Create CFC snippet** under **Start a workflow** to draft an editable message. Send it when ready, then specify the control sequence, intended controller and library item name. The Assistant asks for decisions that affect behaviour, including input/output roles, units, settings, priorities, interlocks, timing, resets and alarms. Review the complete design before approving any project change.

Version **0.18.3** composes supported sequences using 21 reviewed block profiles and nine typed datapoint profiles. Prepared plans include the required datapoints, blocks, effective parameter sources, layout and directed connections, with physical channels left unassigned. Complete-graph checks reject unknown types or pins, missing required signals, incompatible values, duplicate drivers and unsupported structures before preparation. Target preparation verifies actual supported types and reviewed help evidence; execution uses native approval, fresh state checks, verified locks and complete engineering readback. Requests outside the qualified profiles need clarification or further capability qualification. The requirement-to-signal preview still needs engineering review; a static graph check does not execute Siemens function blocks or prove the interpretation of a user's sequence.

Request library export in the plan, then inspect the reported saved contents and remaining manual steps. The observed installed Openness service exports CFC graph data and metadata without the associated BACnet datapoints. Its object-reference metadata does not establish effective device binding, and device placement and detached-program persistence remain unverified. A saved CFC artifact is therefore not proof of a complete reusable equipment package. Native custom-library placement/import, ABT Check, execution order, device binding, persistence, download and commissioning require separate acceptance in the intended environment. Alarm-condition logic does not configure BACnet notification classes, recipients or acknowledgement behaviour.

## Generate graphics

Version **0.17.3** includes a graphics builder inside the Assistant. Choose **Generate graphics** in **Start a workflow**, select a sample prompt or describe your plant, equipment, connections and required readings in chat. The Assistant can assemble a complete native page from supported equipment symbols, pipe/duct connections, labels and grouped readout panels. Its 61 plant and PAC-meter examples provide layouts and reusable components; new scenes can have their own equipment counts and arrangement.

Request **Room Automation** for FCU, VAV, series FPB, parallel FPB or reversible HPU, with Detailed or Simplified information. Native equipment sits above a grey room scene. Only room measurements and presence appear inside the room; Detailed side panels contain setpoints, occupancy mode, Schedule / Mode and other equipment information. Simplified uses one large white outer frame without information cards. Both include editable return-air artwork by default, with outside-air duct/damper artwork for applicable unit families. All values are unbound, and users must check the illustrated topology against the installation.

Review **Preview graphic** with its zoom control. Technical notes are available under the collapsed **Preview notes** section. Choose **Save all graphics** in the conversation header to export every generated graphic from that conversation into one ZIP, with a named folder for each `.f5p`, previews, CSV/JSON mapping schedules and validation report. The individual **Save .f5p…** and **Save supporting files…** controls remain available. Import the `.f5p` files into ABT separately. Graphics generation uses your selected AI provider and the bundled graphics library; no ABT Openness connection is required.

For a graphic based on engineering data, connect to ABT and select **Graphic from ABT plant**. Name the controller and plant, for example: “Build a graphic for plant AHU1234 in controller AS5668. Inspect its points, suggest the equipment and readings, and identify any missing information.” The Assistant inspects the exact selection through existing read-only tools and can retain selected engineering-object identities in the mapping schedule. Ambiguous, incomplete or stale evidence requires resolution; point names alone do not prove physical topology.

Choose **Controller overview** to inspect plants under one exact controller. The Assistant can suggest and generate equipment dashboards, air-side or hydronic equipment overviews, room temperature tables and general point tables from captured points and their hierarchy. Relevant exact ABT naming-catalog entries help classify the evidence; an optional strict naming profile leaves unqualified names unresolved. Larger inspections and layouts continue in pages, with incomplete coverage reported. Automatic overviews use unbound placeholders, preserve each point's plant identity and keep commands, feedback, run proof, measurements and setpoints distinct. They do not infer physical connections or read current temperatures.

For the AHU21x Detailed template, qualified animation choices include numeric 0–100% fan-speed input and valve-linked heating/cooling coil colour. The result reports which choices changed the template and which existing behaviour was preserved. Renaming equipment or adding a speed caption alone does not configure animation; final animation inputs need mapping and checking in the target ABT environment.

The normal Assistant installer and update package include the reviewed library of 61 native examples, reusable components and required readout/animation metadata. Connect your AI provider to start generating graphics; there is no separate graphics installation, asset download or file-copy step. The included native assets retain their original ownership and applicable terms; notices are under `legal/` in the installation.

Generated files remain unbound. Static previews, structural validation and offline animation checks do not establish target ABT import or native animation compatibility. Live ABT acceptance remains deferred. Import, save and re-export the graphic in the intended ABT version, check native editing and animations, and verify point mappings, units, command/feedback, flow proof and quality behaviour before commissioning. Photorealistic generation and arbitrary existing `.f5p` intake are outside this release's supported scope.

Read the [0.17.3 release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.17.3).

## Local reference knowledge

Read-only lookup covers prepared local PDF, values-only XLSX and Programming Library Help reference packages. Results retain document editions, PDF page numbers or workbook worksheet/cell ranges, source hashes and linked topics so answers can cite their reference evidence. English, German and French can be selected explicitly.

Version **0.17.3** can consult the locally prepared NGA System One BACnet object/property workbook for **PXC4, PXC5, PXC7 and DXR3 only**, citing its revision, source hash, worksheet and cells. Documented data types, limits, enum choices and access notes must be checked against the actual target version, supported operations and live project evidence. This reference does not qualify other or legacy controller families or grant additional write permissions.

Documentation import, extraction and package writing belong to the owner's separate development utility. The installed Assistant has no import controls, and the utility is excluded from installers and updates. Existing knowledge packages remain in the local ABTAIAssistantData store. Siemens reference workbooks, manuals, programming archives and customer documents are not included in public downloads. Workbook formulas and macros are not executed.

PDF and HTML text provide reference evidence; inspect the original documents for diagrams, images and scanned content. Documentation does not establish live controller state or make additional ABT operations available. Engineering approval, locks and readback remain enforced.

Read the [0.17.3 release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/tag/v0.17.3).

## Requirements

- Windows x64 with permission to install a per-user application.
- For live engineering and plant inspection: a separately installed, licensed Siemens ABT Site with its hosted ABT Openness service configured and running.
- The account or gateway required by your chosen AI provider, listed below.
- For graphics generation: a connected AI provider. The installer supplies the native graphics library; generated files are imported into licensed ABT separately.

The installer includes .NET 10, the graphics builder and its runtime graphics library. Licensed Siemens ABT software and reference documentation are supplied separately.

## AI providers

| Provider | What you need |
|---|---|
| ChatGPT / Codex | ChatGPT sign-in and a separately installed, qualified Codex runtime; uses your plan's Codex allowance. |
| GitHub Copilot | A permitted GitHub Copilot account and licence. Siemens users can request access and sign in with their managed work account; the matching runtime is included. |
| Claude API | An Anthropic API key with separate API usage and billing. |
| Gemini API | A Google API key with separate API quota or billing. |
| Siemens SDC | A company-issued LLM Gateway API key and access to the selected model in the global/European region; subject to company allocation and policy. |
| OpenClaw | A separately configured local Gateway and its token or password; model access is configured in OpenClaw. |
| Claude Code (separate app) | The official installed client, using its own sign-in and conversation. |

Assistant **0.19.2** supports Codex `0.163.0-alpha.10.2` and the earlier supported versions `0.162.0-alpha.17.2`, `0.160.1`, `0.160.0`, `0.154.0-alpha.6.2` and `0.153.4`. On first use, install a supported Codex runtime and sign in to ChatGPT. The Assistant retains a compatible runtime for later connections, so Codex app updates do not replace it. A confirmed unreadable encrypted sign-in cache is preserved separately so you can sign in again; other saved connections and settings are retained. Direct API providers do not require Codex or Claude Code.

Use **Provider setup & billing** in the application for detailed instructions. Credentials and settings remain scoped to their selected account and endpoint, with no automatic account, endpoint or model fallback. Conversations stay separate by AI provider. Within a project and provider, earlier chats can be referenced across model, effort, account and endpoint changes; matching documentation and ABT scopes still apply. References include source links and remain historical, untrusted evidence.

**GitHub Copilot setup.** Select **GitHub Copilot** and open its connection settings. Siemens users choose **Sign in with Siemens**, then authorise the displayed device code in their work browser. The Assistant supplies its registered public application ID; no client secret or API key is required for the normal connection. A permitted Copilot account, licence and company approval are still required. **Remember sign-in** optionally protects the saved credential for the current Windows user. Available models and reasoning choices follow that account's advertised capabilities and policies. Changing model or effort keeps the saved chat; the Assistant rebuilds Copilot's native session from bounded recent history where required.

**Siemens SDC setup.** One **Siemens SDC** connection supports qualified Claude, Gemini and OpenAI models. Choose **Model provider**, then **Model** from its filtered list. The public catalogue loads automatically without an API key; **Test & connect** verifies access to that exact model and saves the connection only after success. Other gateway models remain unavailable until their ABT tool support is verified.

**Siemens SDC model controls.** Choose **Reasoning effort** for supported models. Verified profiles are included for qualified Global Claude models and OpenAI `gpt-6.1-sol`; available choices match each model. Other gateway/model/protocol combinations require explicit configuration, and local configuration takes precedence. Models without a native effort setting retain **Default**, which leaves the choice to the gateway or model. Your choice is remembered; higher effort may increase response time and token usage. Open **Model selection & pricing guide** beside the model controls for task suggestions, dated example costs, current pricing links and effort configuration instructions.

**Test & connect** can consume company quota. When Siemens SDC is the saved provider and its key is remembered, reopening the desktop also checks access to the exact saved model through its saved gateway, model provider and protocol. This isolated check can consume company quota and sends only “Reply OK.” without conversation, attachments or ABT tools. **Connecting…** becomes **Connected** after success; a failed check preserves the saved connection and shows a reconnect notice. Opening Siemens SDC settings does not itself run a paid access test. Changing region, model provider or model requires explicit selection and verification. Credentials stay within the selected gateway and model family. The same saved chat continues within Siemens SDC, with a fresh model session when needed and bounded historical context.

## Install

1. Open the [latest release](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest) and download `ABTAIAssistant-stable-Setup.exe` and `T-Pendlebury-code-signing.cer`.
2. Follow [signature verification and optional certificate trust](CODE_SIGNING.md). Installers use a self-signed certificate; independently confirm its fingerprint and follow your organisation's policy.
3. Finish existing ABT work and close assistant sessions and companion windows normally, then run Setup.
4. Start ABT AI Assistant, read the full disclaimer, tick its acknowledgement box and choose **Continue**, then connect your chosen AI provider. The acknowledgement is saved for your Windows profile; revised wording is shown again. Usage reporting is enabled for new reporting installations after acknowledgement and can be disabled under **Privacy & usage** without losing access to the tool. Existing opt-outs are preserved.

**Upgrading from unsigned 0.16.2 or earlier:** run the signed Setup installer once before using in-app updates.

## Use with ABT

1. Open the intended project in ABT Site and keep a single ABT Site instance running.
2. Choose **Connect** in the assistant, confirm the project and enter ABT credentials in the local sign-in dialog.
3. Use a workflow suggestion or type a request. Review the proposed action, tick the review checkbox when required, then choose **Accept action** or **Decline**.

Engineering changes require explicit approval and readback checks, with verified device locks for device-scoped operations. Cancellation, expiry and closing the assistant never approve an action. **Disconnect** releases the assistant's connection while leaving the project open in ABT Site.

Version **0.17.4** checks the qualified ABT Site locking startup prerequisite before engineering writes. The startup qualification currently covers ProjectServices build **62.0.2172.1**; other builds block engineering writes until qualified. If the setting is missing or was restored after ABT Site started, save the project, close ABT Site normally and reopen it as directed before preparing a new plan. The Assistant does not change that setting or restart ABT Site automatically; it still verifies actual lock ownership before device-scoped writes.

Version **0.17.5** recognises qualified binary-contact evidence, including explicit normally-open/normally-closed signals and supported current-switch, leak-contact terminal and actuator end-switch mappings. Recognised contacts without explicit polarity use the disclosed normally-open default; explicit normally-closed signals are preserved. Conflicting wiring and unqualified signals remain for review. Remote island-bus rail connections, including IBE expansion placement, are preserved in topology readback. Application placement uses the logical Plant/Folder path, while assignment verification checks the physical module and channel.

Independent assignment batches can continue after a failed batch while the approved session remains usable. Results identify failed or unconfirmed rows and created-but-unassigned points; failed batches are never replayed automatically. An owner-approved repair and complete live readback matched all **1,030 active physical points across 21 controllers** for assignments, I/O classes, current source names and application paths. That validates the repaired existing project; it does not establish cold-project import acceptance or compatibility with every ABT build.

For a failed physical-I/O import, inspect the current project before retrying. Reconnect explicitly and prepare a fresh plan that reuses any controller already created and includes only work confirmed to be missing. Version 0.17.4 retains the original failure, displays confirmed partial work and stops scheduling further controllers after losing a usable session. Updating does not undo existing project changes or replay the original plan.

A timeout or lost reply may leave a partially completed change. Inspect the current ABT state before preparing further work; controller creation is never retried automatically after an uncertain result. Live account access, gateway compatibility and engineering changes require verification in your authorised environment.

## Updates

Open **About & updates** to check for and download updates. It shows the opening disclaimer above the update controls; the full notice remains in the first-launch dialog and distribution documentation. **Later** keeps a downloaded update staged.

Before choosing **Restart and Update**, disconnect the assistant from ABT, wait for all tasks, readback and cleanup to finish, and close other assistant sessions and companions normally. The updater rechecks readiness, blocks new ABT work during installation and waits for existing sessions to exit naturally. Active assistant/ABT work must finish; only an empty process blocked before startup may be stopped by the guarded updater.

If readiness is unconfirmed or guards/helpers are unavailable, use **Download installer ↗** after finishing work and closing sessions normally. Settings and credentials are retained across updates; updates do not undo ABT project changes.

## Help

- **Interface size (0.17.4):** use **Ctrl + mouse wheel** or the bottom **− / +** controls to scale text, buttons and panels from 70% to 150%. **Ctrl+0** or the percentage button resets to 100%. Your zoom setting is saved and restored on the next launch.
- **Saved-data conflict after updating:** preserve the existing data and follow the startup recovery guidance.
- **Connection problems:** check that ABT Site's hosted Openness service is configured and running. The assistant does not start Siemens services or restart ABT Site automatically.
- **Provider setup:** open **Provider setup & billing** in the application.
- **Graphics library unavailable:** finish Assistant/ABT work and close Assistant sessions and companion windows normally, then repair or update using the normal Setup installer. The graphics library is included; no separate asset pack is required.
- **Windows trust warnings:** follow [CODE_SIGNING.md](CODE_SIGNING.md). SmartScreen or company policy may still block a self-signed application; keep Windows protections enabled.
- **Download problems:** continue using the installed version and retry later, or download Setup from the latest release. Finish active work before repair or reinstall.
- **Issues:** [report a problem](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/issues) without customer projects, credentials, private logs or Siemens reference material. Third-party notices are included under `legal/` in the installed application.

