# ABT AI Assistant

A Windows desktop assistant for **Siemens ABT Site**, using the local **ABT Openness** service. Ask questions in plain language, inspect engineering data, prepare project changes, work with Excel points schedules and generate editable native graphics.

[Download installer](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases/latest) · [Release notes](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/releases) · [Signature guidance](CODE_SIGNING.md) · [Disclaimer](DISCLAIMER.md)

## Features and capabilities

| Area | What you can do |
|---|---|
| **Project exploration** | Inspect controllers, datapoints, properties, I/O layouts and application structures. |
| **Controllers and templates** | Prepare supported controller creation, template instances, renaming and upgrades. |
| **Project structure** | Organise buildings, floors, rooms, plants, equipment and folders. |
| **TX-I/O and Modbus** | Inspect and prepare supported modules, point assignments, networks and devices. |
| **Application libraries** | Find compatible applications and prepare configurations, options and variants. |
| **CFC programming** | Inspect and trace logic, compose supported snippets, run static checks and prepare supported library exports. |
| **Bulk changes** | Prepare naming, description and supported configuration updates across selected objects. |
| **Excel workflows** | Review points schedules offline, prepare physical-I/O imports and compare workbooks with ABT to resolve supported differences. |
| **Generate graphics** | Generate plant graphics, Room Automation and controller overviews; preview and export editable `.f5p` files with mapping schedules. |
| **Engineering guidance** | Search available local ABT and Programming Library Help for documented guidance. |

**Project changes require your explicit approval**, state checks and verification of the result. Available operations depend on your ABT version and configuration. Project creation, controller downloads and commissioning remain in ABT Site.

CFC static checks do not simulate controller operation. Generated graphics are unbound and require separate ABT import, point mapping and validation. Graphics generation uses the included library and can run without an ABT connection.

## AI connections

Choose **ChatGPT / Codex**, **GitHub Copilot**, **Claude API**, **Gemini API**, **Siemens SDC** or **OpenClaw**, using your authorised account or gateway. Codex requires a separately installed supported runtime. **Claude Code** is available as a separate app.

See **Provider setup & billing** in the application for setup and access requirements. You can also connect a compatible AI client through the local MCP integration.

## Get started

Requires **Windows x64** and access to your chosen AI provider. Live project work also requires separately installed, licensed **ABT Site** with its hosted **ABT Openness** service running. The installer includes .NET and the graphics library.

1. Download Setup, follow the [signature guidance](CODE_SIGNING.md), then install after finishing ABT work and closing assistant sessions normally.
2. Start the assistant, read and acknowledge the disclaimer, then configure your AI connection.
3. Open your project in ABT Site, choose **Connect**, and describe the task or select a workflow.

Check for updates under **About & updates**; finish work, disconnect and close other assistant sessions before installing.

Usage reporting is enabled after first-launch acknowledgement unless disabled by your saved preference or policy. You can turn it off under **Privacy & usage**.

[Report an issue](https://github.com/timpendlebury/ABT-AI-Assistant-Releases/issues) without including credentials or customer/project data.

<details>
<summary>Disclaimer and usage reporting</summary>

> ABT AI Assistant is an independent, unofficial third-party tool developed in a personal capacity. It is not an official Siemens product and is not affiliated with, sponsored, endorsed or supported by Siemens AG or any other vendor or manufacturer. To the extent permitted by applicable law, the software is provided "as is", without warranty of any kind, express or implied. No ongoing support, updates or maintenance are promised. Use of the tool is at the user's own risk. Users should maintain appropriate project backups and independently review and validate all outputs and changes before applying them.
>
> Usage statistics apply only to releases that include usage reporting. On first launch of such a release, acknowledging this disclaimer enables reporting unless an existing reporting preference or administrator policy disables it. You can disable reporting at any time under Privacy & usage without losing access to the tool.
>
> The publisher uses a private PostHog Cloud project hosted in the European Union to measure installation activity, feature use and update adoption. Reports contain a random installation identifier that persists across updates, session and conversation identifiers, conversation and assistant-turn counts, turn outcomes, AI connection/provider and reviewed public model identifiers, the running app version, timestamps and the Windows configured country/region. The country/region is a computer setting, not a verified physical location. The installation identifier represents a Windows user profile, not a named person or guaranteed distinct PC; activity from that installation can be linked over time.
>
> Usage reports exclude conversation text, prompts, replies, attachments, customer and project content, usernames, email addresses, computer names, hardware identifiers and credentials. IP-based location enrichment is disabled; the analytics service still receives the network source IP when a connection is made. Reporting is independent of your AI provider and does not train AI models. Private knowledge access and requests sent to your selected AI provider follow their separate configurations and terms.
>
> Unsent statistics expire after seven days and are removed when the application next processes its reporting queue. Disabling reporting cancels pending delivery and removes unsent statistics; it does not delete information already received by PostHog, which remains subject to the project's retention and deletion settings. Statistics and installation identifiers are not published to the public releases repository. Questions about usage reporting can be raised with the publisher through the public repository's issue tracker; do not post installation identifiers, credentials or project data publicly.

</details>

