# Awesome Visio [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of Microsoft Visio and `.vsdx` resources: file format specs, libraries, converters, viewers, stencils, diagram-as-code routes and AI tools.

**English** | [简体中文](README.zh-CN.md)

Microsoft Visio is the long-standing standard for business and technical diagrams: flowcharts, swimlanes, network and architecture diagrams, org charts and floor plans. Since Visio 2013 the default file format is **`.vsdx`**, an [Open Packaging Convention](https://ecma-international.org/publications-and-standards/standards/ecma-376/) ZIP archive of XML parts (pages, masters, ShapeSheet cells, themes). Related extensions are `.vssx` (stencil), `.vstx` (template) and the macro-enabled `.vsdm`. Older versions used the binary **`.vsd`** format and the Visio 2003–2010 XML format **`.vdx`**.

Because `.vsdx` is plain XML in a ZIP, you can read, generate and convert Visio files without Visio itself. This list collects the tools that make that practical.

Legend: 💲 commercial or paid product · 🆓 free / open source where not obvious

## Contents

- [Featured tools](#featured-tools)
  - [Comparison](#comparison)
  - [VSDX.ai](#vsdxai)
  - [LayerBack](#layerback)
  - [vsdx.app](#vsdxapp)
- [Official Microsoft resources](#official-microsoft-resources)
  - [Product and documentation](#product-and-documentation)
  - [File format](#file-format)
  - [Programming and automation](#programming-and-automation)
- [Libraries](#libraries)
  - [Python](#python)
  - [.NET / PowerShell](#net--powershell)
  - [Java](#java)
  - [JavaScript / TypeScript](#javascript--typescript)
  - [C++ / Rust / Go](#c--rust--go)
- [Converters](#converters)
- [Viewers and editors](#viewers-and-editors)
- [Stencils and shape libraries](#stencils-and-shape-libraries)
- [Diagram-as-code to Visio](#diagram-as-code-to-visio)
- [AI tools for diagrams](#ai-tools-for-diagrams)
- [Blogs, tutorials and community](#blogs-tutorials-and-community)
- [Related lists](#related-lists)
- [Contributing](#contributing)

---

## Featured tools

All three tools produce **real Visio content**: native shapes, connectors glued to those shapes, and editable text. They do not wrap a flat picture in a `.vsdx` container. You do not need a Visio license to create or view files with them.

### Comparison

| | [VSDX.ai](https://vsdx.ai) | [LayerBack](https://layerback.com) | [vsdx.app](https://vsdx.app) |
|---|---|---|---|
| **Start from** | Text, documents, spreadsheets, data, Mermaid/PlantUML code | A picture or PDF of an existing diagram | An existing `.vsdx` / `.vsd` file |
| **What you get** | A new native Visio diagram, plus format conversions | The same diagram rebuilt as an editable file | Open, edit and save Visio files natively on Mac |
| **Output formats** | `.vsdx`, `.drawio`, PNG, SVG | VSDX, PPTX, draw.io XML, SVG | `.vsdx`, `.vsd` (opens both) |
| **Runs in** | Browser (web app) | Browser (web app) | macOS app (Swift/AppKit) |
| **Free option** | Free browser tools (Visio→draw.io, Visio→PNG/SVG); 20 welcome credits | Convert and preview free without sign-in; free online VSDX viewer | Open, view, print and Quick Look any `.vsdx`/`.vsd` |
| **Paid from** | Pro $20/mo | Pro $20/mo | Pro or Lifetime license |
| **Agent / developer access** | REST API, OpenAPI spec, remote MCP server | REST API, open-source MCP server and Agent Skill | — |
| **Languages** | 7 (EN, ZH, DE, FR, ES, JA, KO) | 7, recognizes CJK and other non-Latin text | — |

**Which one?** Use LayerBack when you have a *picture* of a diagram and want it editable. Use VSDX.ai when you have *content* (text, documents, data or diagram code) and want a new Visio diagram, or when an AI agent needs to produce `.vsdx` files. Use vsdx.app when you need to *open and edit Visio files on a Mac*.

### VSDX.ai

**[VSDX.ai](https://vsdx.ai)** is an AI Visio diagram generator. It turns text, documents and data into native `.vsdx` files.

- **Many input types.** Reads spreadsheets (Excel, CSV), PDF, Word, plain text, Markdown, JSON, YAML, images, audio and short video. You can combine several sources in one project, and they are stored privately.
- **Real Visio output.** It turns meaning into a structured diagram and exports a native `.vsdx` with editable shapes and glued connectors, not a flat image or a PNG renamed to `.vsdx`. Files are verified to open in Microsoft Visio on Windows. It also exports `.drawio`, and you can import existing `.vsdx` / `.drawio` files back.
- **Diagram types.** Flowchart, swimlane, BPMN, org chart, architecture, network, ER and UML.
- **Edit after generation.** Every diagram opens in an embedded draw.io editor. You can also edit by chatting, and saved versions can be restored.
- **Clean layouts.** An automatic layout engine based on ELK. The *Tidy up a diagram* tool re-lays out messy draw.io or Visio diagrams.
- **Conversion tools** ([all tools](https://vsdx.ai/tools)): image → Visio, Excel → org chart, outline → org chart, [Mermaid → Visio](https://vsdx.ai/tools/mermaid-to-visio), PlantUML → Visio, draw.io → Visio, [Visio → draw.io](https://vsdx.ai/tools/visio-to-drawio), Visio → PNG/SVG and tidy diagram. Also see [Excel → org chart](https://vsdx.ai/tools/excel-to-org-chart).
- **Free, no account, runs entirely in your browser:** Visio → draw.io and Visio → PNG/SVG, for modern `.vsdx` files (legacy `.vsd` is not supported).
- **For developers and agents.** Public REST API with an [OpenAPI spec](https://vsdx.ai/api/v1/openapi.json) ([developer page](https://vsdx.ai/developers), [docs](https://vsdx.ai/docs)). A remote MCP server at `https://vsdx.ai/api/mcp` provides `generate_diagram`, `convert_diagram` and `get_credits`. [Setup guides](https://vsdx.ai/mcp) cover Claude Code, Cursor and Codex, and OAuth is supported for ChatGPT and Claude on the web. PNG, SVG and draw.io output work on every account. `.vsdx` output via API/MCP needs a paid plan or a credit pack.
- **Interface languages:** English, Chinese, German, French, Spanish, Japanese and Korean.

**Pricing** ([details](https://vsdx.ai/pricing)): each generation or edit costs 10 credits, and each tool run costs 10 credits (the free tools cost nothing). New accounts get 20 welcome credits.

| Plan | Monthly | Yearly | Credits / month |
|---|---|---|---|
| Free | $0 | — | 20 welcome credits |
| Pro | $20 | $120 | 300 |
| Business | $50 | $300 | 1,000 |
| Team | $100 | $600 | 3,000 |

Top-ups: 300 credits for $20, 1,000 for $50 or 3,000 for $100, each valid for 90 days.

### LayerBack

**[LayerBack](https://layerback.com)** turns a diagram image or PDF into editable Visio, PowerPoint, draw.io or SVG files.

- **Rebuilds the diagram instead of tracing it.** Converts screenshots, PNG, JPG, WebP and PDF pages into fully editable files. Vector tracers produce outlines, and some tools just embed the picture in a file container. LayerBack makes every box a native shape, every arrow a live connector glued to its shapes, and every label real editable text. Output is verified in Visio and PowerPoint.
- **Four formats per diagram.** About 30 seconds per conversion. Converting and previewing are free with no sign-in. The first download or edit of a diagram uses 10 credits and unlocks all four formats: VSDX, PPTX, draw.io XML and SVG. Failed conversions are never charged.
- **Built-in online editor** to fix anything and re-export.
- **Privacy.** Uploads are deleted automatically after 72 hours.
- **Multilingual.** Recognizes non-Latin text such as Chinese and Japanese. The interface is available in 7 languages.
- **Free [online VSDX viewer](https://layerback.com/vsdx-viewer).** Open `.vsdx` files in the browser without Visio.
- **Landing pages:** [Image to Visio](https://layerback.com/image-to-visio) · [PDF to Visio](https://layerback.com/pdf-to-visio) · [Image to PPTX](https://layerback.com/image-to-pptx) · [Image to draw.io](https://layerback.com/image-to-drawio) · [All tools](https://layerback.com/tools)
- **For developers and agents:**
  - [Public API](https://layerback.com/docs/api) (authenticated with an `x-api-key` header).
  - [layerback-mcp](https://github.com/TopLocalAI/layerback-mcp): open-source MCP server with `convert_diagram_image`, `get_conversion_status` and `download_converted_diagram`. Works in Claude Desktop, Claude Code and Cursor.
  - [layerback-image-to-vsdx-skill](https://github.com/TopLocalAI/layerback-image-to-vsdx-skill): open-source Agent Skill. Install with:

    ```sh
    npx -y skills@latest add TopLocalAI/layerback-image-to-vsdx-skill --skill layerback-image-to-vsdx --agent codex --global
    ```

**Pricing** ([details](https://layerback.com/pricing)): Pro $20/mo (1,000 credits), Plus $40/mo (3,000 credits), Max $80/mo (10,000 credits). Credit packs start at $10 and never expire.

### vsdx.app

**[vsdx.app](https://vsdx.app)** is an independent native macOS app that opens, edits and saves Visio `.vsdx` and `.vsd` files.

- **Native Mac app.** Built with Swift and AppKit, not a web wrapper. It has a familiar ribbon interface.
- **File fidelity.** When it writes a file back, it preserves the original XML.
- **Finder integration.** Quick Look previews and thumbnails for Visio files.
- **Works offline** after you sign in once. Sign-in happens in the browser, and the app stores no passwords or API keys.
- **AI drafting.** Describe a diagram in one sentence and get a first draft (powered by VSDX.ai).
- **Free:** open, view and print any `.vsdx` or `.vsd`, and preview them in Finder. Editing, saving and AI need **Pro** or **Lifetime**. Lifetime is a forever license that includes 100 AI credits per month, and credit packs are available.

---

## Official Microsoft resources

### Product and documentation

- [Microsoft Visio](https://www.microsoft.com/en-us/microsoft-365/visio) - Product home: Visio Plan 1, Plan 2 and the desktop app. 💲
- [Visio in Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/visio/visio-in-microsoft-365) - The lightweight web version of Visio included with many Microsoft 365 subscriptions.
- [Visio support](https://support.microsoft.com/en-us/visio) - Official help, how-to articles and training.
- [Create a Data Visualizer diagram](https://support.microsoft.com/en-us/office/create-a-data-visualizer-diagram-17211b46-d144-4ca2-9ea7-b0f48f0ae0a6) - Generate flowcharts, org charts and swimlanes from Excel tables in Visio.
- [Visio Viewer (legacy)](https://www.microsoft.com/en-us/download/details.aspx?id=35811) - Free viewer for Visio drawings. Old, Internet Explorer-based, and unlikely to work well on current Windows. ([background](https://learn.microsoft.com/en-us/archive/blogs/office_resource_kit/download-the-new-microsoft-visio-viewer))

### File format

- [Introduction to the Visio file format (.vsdx)](https://learn.microsoft.com/en-us/office/client-developer/visio/introduction-to-the-visio-file-formatvsdx) - Package structure, parts and relationships.
- [Manipulate the Visio file format programmatically](https://learn.microsoft.com/en-us/office/client-developer/visio/how-to-manipulate-the-visio-file-format-programmatically) - Step-by-step walkthrough of reading and editing a `.vsdx` package with System.IO.Packaging.
- [Visio file format reference](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-file-format-reference) - Reference for the XML elements in a `.vsdx` package.
- [[MS-VSDX]: Visio Graphics Service VSDX File Format](https://learn.microsoft.com/en-us/openspecs/sharepoint_protocols/ms-vsdx/50c23601-c943-4ff2-b4a1-02445f52daf0) - The formal open specification of the `.vsdx` format.
- [Visio ShapeSheet reference](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-shapesheet-reference) - Cells, functions, rows and sections. These map directly onto the XML inside `.vsdx`.
- [ECMA-376 (Office Open XML)](https://ecma-international.org/publications-and-standards/standards/ecma-376/) - The Open Packaging Conventions standard that `.vsdx` is built on.

### Programming and automation

- [Visio JavaScript API overview](https://learn.microsoft.com/en-us/office/dev/add-ins/visio/visio-overview) - Office Add-ins API for Visio diagrams embedded in SharePoint Online.
- [Visio JavaScript API reference](https://learn.microsoft.com/en-us/javascript/api/visio) - Full reference for the `Visio` namespace.
- [Office Add-ins platform](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins) - General documentation for building web-based Office add-ins.
- [Office Add-in samples](https://github.com/OfficeDev/Office-Add-in-samples) - Official code samples for the Office Add-ins platform.
- [Visio VBA reference](https://learn.microsoft.com/en-us/office/vba/api/overview/visio) - The Visio object model for VBA and COM automation.
- [Visio Application object](https://learn.microsoft.com/en-us/office/vba/api/visio.application) - Entry point of the COM object model, used by VBA, C#, PowerShell and Python (pywin32).
- [Visio solutions in Visual Studio (VSTO)](https://learn.microsoft.com/en-us/visualstudio/vsto/visio-solutions) - Build VSTO add-ins for desktop Visio.
- [Open XML SDK](https://learn.microsoft.com/en-us/office/open-xml/open-xml-sdk) - Microsoft's .NET SDK for Office Open XML packages. Handy for low-level work on the `.vsdx` package (parts, relationships, XML). ([GitHub](https://github.com/dotnet/Open-XML-SDK), [NuGet](https://www.nuget.org/packages/DocumentFormat.OpenXml))

## Libraries

### Python

- [vsdx](https://github.com/dave-howard/vsdx) - Read and edit `.vsdx` files (shapes, text, connectors) and generate new files from Jinja templates. Works without Visio. ([PyPI](https://pypi.org/project/vsdx/), [docs](https://vsdx.readthedocs.io/))
- [libvisio-ng](https://github.com/yeager/libvisio-ng) - Parse `.vsdx` and `.vsd` files and convert them to SVG. Extracted from the vsdview viewer. ([PyPI](https://pypi.org/project/libvisio-ng/))
- [pywin32](https://github.com/mhammond/pywin32) - Python for Windows extensions. The usual way to drive desktop Visio through COM from Python. Requires Windows and Visio.
- [Aspose.Diagram for Python via .NET](https://products.aspose.com/diagram/python-net/) - Create, edit and convert Visio formats. 💲 ([PyPI](https://pypi.org/project/aspose-diagram-python/))

### .NET / PowerShell

- [VisioAutomation](https://github.com/saveenr/VisioAutomation) - Long-running .NET libraries and PowerShell cmdlets for automating desktop Visio.
- [VisioBot3000](https://github.com/MikeShepard/VisioBot3000) - PowerShell DSL for building Visio diagrams through automation.
- [Aspose.Diagram for .NET](https://products.aspose.com/diagram/net/) - Read, write, render and convert VSD, VSDX, VDX and related formats without Visio. 💲 ([NuGet](https://www.nuget.org/packages/Aspose.Diagram))

### Java

- [Apache POI – XDGF](https://poi.apache.org/components/diagram/) - Apache POI's component for `.vsdx` (XDGF) and legacy `.vsd` (HDGF). Read-focused. ([API docs](https://poi.apache.org/apidocs/dev/org/apache/poi/xdgf/usermodel/package-summary.html), [GitHub mirror](https://github.com/apache/poi))
- [Aspose.Diagram for Java](https://products.aspose.com/diagram/java/) - Commercial Java API for Visio files. 💲

### JavaScript / TypeScript

- [ooxml (visio-core and viewers)](https://github.com/ChristopherVR/ooxml) - Local-first OOXML engine with Visio document APIs and drop-in viewers for React, Vue, Angular, Svelte, Solid and vanilla JS. ([demo/docs](https://christophervr.github.io/ooxml/))
- [ts-visio](https://github.com/zimmermanw84/ts-visio) - Create `.vsdx` files from TypeScript.
- [vsdx-js](https://github.com/jgreywolf/vsdx-js) - Parse a `.vsdx` file into a JavaScript object.
- [cytoscape-vsdx](https://github.com/ShanteshSindgi/cytoscape-vsdx) - Export Cytoscape.js graphs (nodes, edges, groups, styles) to `.vsdx` in the browser.
- [Aspose.Diagram for Node.js via Java](https://products.aspose.com/diagram/nodejs-java/) - Commercial Node.js API for Visio files. 💲

### C++ / Rust / Go

- [libvisio](https://github.com/LibreOffice/libvisio) - The LibreOffice/Document Liberation Project C++ library that imports `.vsd`, `.vdx` and `.vsdx`. It powers Visio import in LibreOffice and Inkscape. ([project page](https://wiki.documentfoundation.org/DLP/Libraries/libvisio))
- [MisterDiagram](https://github.com/MisterDiagram/MisterDiagram) - Clean-room, headless Rust implementation of `.vsdx` and the ShapeSheet. Reads and writes drawings, stencils and templates, renders to PNG/SVG/PDF, and ships a CLI and an MCP server. Beta.
- [libvisio-rs](https://github.com/yeager/libvisio-rs) - Rust library for parsing `.vsdx` / `.vsd` and converting to SVG.
- [vsdx-go](https://github.com/wijnberg-net/vsdx-go) - Go library for reading, editing and writing `.vsdx` files.

## Converters

- [draw.io import formats](https://www.drawio.com/docs/manual/import/import-formats/) - draw.io imports `.vsdx`, `.vsd`, `.vssx` stencils and more, and exports to VSDX (*File > Export as > VSDX*, labeled beta). ([VSDX import notes](https://drawio-app.com/blog/import-vsdx-files/))
- [LibreOffice Draw](https://www.libreoffice.org/) - Opens `.vsd`, `.vdx` and `.vsdx` through libvisio. It can export to PDF, SVG and ODG, but cannot save back to Visio formats. ([import/export limitations](https://help.libreoffice.org/latest/en-US/text/shared/guide/ms_import_export_limitations.html))
- [Inkscape](https://inkscape.org/) - Vector editor that imports Visio files through libvisio and can export them to SVG/PDF. ([source](https://gitlab.com/inkscape/inkscape))
- [weasyvsdx](https://github.com/grigoriev/weasyvsdx) - WeasyPrint plugin that renders VSDX/VSD drawings as vector SVG (via libvisio) in HTML-to-PDF output.
- [visio2img](https://github.com/visio2img/visio2img) - Python CLI that exports `.vsd` / `.vsdx` pages to images. Requires Windows, pywin32 and Visio. Inactive.
- [VSDtoVSDX-Converter](https://github.com/jprtf/VSDtoVSDX-Converter) - PowerShell GUI that batch-converts legacy `.vsd` files to `.vsdx` through Visio.
- [bpmn-to-visio](https://github.com/Mgabr90/bpmn-to-visio) - Converts BPMN 2.0 XML into `.vsdx`. Pure Python with no dependencies.
- [GroupDocs Viewer – VSDX](https://products.groupdocs.app/viewer/vsdx) - Free online VSDX viewer and renderer from GroupDocs.
- [Convertio](https://convertio.co/vsdx-converter/) - General online converter for VSDX to PDF and image formats. Free tier with limits.
- [Zamzar](https://www.zamzar.com/convert/vsdx-to-pdf/) - Online VSDX to PDF conversion. Free tier with limits.

## Viewers and editors

- [draw.io / diagrams.net](https://www.drawio.com/) - Free, open-source diagram editor in the browser and on the desktop. Imports and exports Visio files. ([web app](https://app.diagrams.net/), [desktop](https://github.com/jgraph/drawio-desktop), [source](https://github.com/jgraph/drawio))
- [vsdview](https://github.com/yeager/vsdview) - GTK4/Adwaita viewer for `.vsdx` / `.vsd` on Linux.
- [Lucidchart](https://www.lucidchart.com/) - Web diagramming tool that imports Visio files. 💲 ([import guide](https://help.lucid.co/hc/en-us/articles/16389149809428))
- [SmartDraw](https://www.smartdraw.com/) - Web diagramming tool with Visio import and export. 💲
- [EdrawMax](https://www.edrawsoft.com/edraw-max/) - Cross-platform diagram editor (Windows, Mac, Linux, web) with Visio import and export. 💲
- [ConceptDraw DIAGRAM](https://www.conceptdraw.com/) - Mac and Windows diagram editor that opens and saves Visio formats. 💲
- [OmniGraffle](https://www.omnigroup.com/omnigraffle) - Mac and iPad diagramming app that can import and export Visio files. 💲
- [Visual Paradigm Online](https://online.visual-paradigm.com/) - Web diagramming suite with Visio import. Free tier available. 💲
- [yEd](https://www.yworks.com/products/yed) - Free desktop graph editor with strong automatic layout. Useful for laying out graphs before moving them to Visio.

## Stencils and shape libraries

- [VisioCafe](https://www.visiocafe.com/) - Long-standing free index of official vendor Visio stencils (HPE, Dell, NetApp, IBM, Lenovo, Fujitsu and more).
- [Cisco network topology icons](https://www.cisco.com/c/en/us/about/brand-center/network-topology-icons.html) - Official Cisco icon and Visio stencil downloads.
- [Azure architecture icons](https://learn.microsoft.com/en-us/azure/architecture/icons/) - Official Azure icons. Provided as SVG, not Visio stencils, but they drag straight into Visio.
- [Microsoft 365 architecture icons and templates](https://learn.microsoft.com/en-us/previous-versions/microsoft-365/solutions/architecture-icons-templates) - Microsoft 365 icon sets and Visio templates (archived page).
- [Microsoft Integration & Azure Stencils Pack](https://github.com/sandroasp/Microsoft-Integration-and-Azure-Stencils-Pack-for-Visio) - Large community Visio pack for Azure, BizTalk, Power Platform and Microsoft 365.
- [visioStencils](https://github.com/bhdicaire/visioStencils) - Collection of 4,000+ IT infrastructure shapes, stencils and icons.
- [Visio-Azure](https://github.com/xeeva/Visio-Azure) - Searchable Azure stencil set (1,259 icons) with connection points and shape data.
- [Visio-Cisco](https://github.com/xeeva/Visio-Cisco) - Community-built searchable Cisco stencil set with Metric and US builds. Unofficial.
- [C4 model Visio stencil](https://github.com/pihalve/c4model-visio-stencil) - Shapes for C4 software architecture diagrams.
- [ntwrk-clean-and-flat](https://github.com/DukeNuke3D/ntwrk-clean-and-flat) - Clean, flat 2D network symbols with Visio stencils.
- [Unifi Visio Stencils](https://github.com/brightmethods/Unifi-Visio-Stencils) - Stencils for common Ubiquiti UniFi hardware.
- [Visio Stencil Factory](https://github.com/rezanid/visiostencilfactory) - Build your own Visio stencils from a folder of SVG files.
- [ShapeSource](https://www.shapesource.com/) - Vendor Visio shapes produced by Visimation (many manufacturers). Some are paid. 💲
- [draw.io libraries](https://github.com/jgraph/drawio-libs) - Community shape libraries for draw.io. Combined with draw.io's VSDX export, they are a route to Visio.

## Diagram-as-code to Visio

Visio has no native text syntax. These are the practical routes from code to `.vsdx`.

- [Mermaid](https://mermaid.js.org/) - Popular Markdown-like diagram syntax. Common route to Visio: Mermaid → draw.io ([insert Mermaid](https://www.drawio.com/docs/manual/mermaid/)) → export VSDX, or a direct converter below.
- [PlantUML](https://plantuml.com/) - Text-based UML and more. draw.io can [insert PlantUML](https://www.drawio.com/docs/manual/insert/insert_plantuml/) and then export to VSDX.
- [Graphviz](https://graphviz.org/) - The classic graph layout engine (DOT language). Export SVG, then import it into Visio or draw.io. ([output formats](https://graphviz.org/docs/outputs/))
- [md2visio](https://github.com/Megre/md2visio) - Converts Mermaid in Markdown into `.vsdx`.
- [mermaid-to-visio](https://github.com/FBklyra/mermaid-to-visio) - Converts rendered Mermaid into native `.vsdx` shapes and connectors, client-side. Includes a library, CLI and web editor.
- [draw.io: diagrams from code](https://www.drawio.com/docs/tutorials/diagrams-from-code/) - Overview of draw.io's Mermaid, PlantUML and CSV import options.
- [D2](https://d2lang.com/) - Modern diagram scripting language. Export SVG for use in Visio-based workflows.
- [Diagrams](https://diagrams.mingrammer.com/) - Python "diagram as code" for cloud architecture. Renders images, which you can recreate in Visio.
- [Kroki](https://kroki.io/) - One HTTP API that renders many text diagram languages (Mermaid, PlantUML, Graphviz, D2…) to SVG/PNG. ([source](https://github.com/yuzutech/kroki))

## AI tools for diagrams

- [Visiomaster](https://github.com/Rss3208/Visiomaster) - Windows toolkit and Codex skill that rebuilds flowcharts and paper figures from images as editable `.vsdx` through Visio COM (Chinese docs).
- [visio-com-skill](https://github.com/WUXU-Tech/visio-com-skill) - Codex skill that generates editable `.vsdx` diagrams through local Visio COM automation on Windows.
- [MisterDiagram](https://github.com/MisterDiagram/MisterDiagram) - MCP server that drafts `.vsdx` files from plain-English prompts without Visio (also listed under libraries).
- [Eraser DiagramGPT](https://www.eraser.io/diagramgpt) - Generates technical diagrams from natural language or code. 💲
- [Mermaid Chart](https://www.mermaidchart.com/) - Commercial Mermaid editor from the Mermaid team, with AI-assisted diagramming. 💲
- [Napkin AI](https://www.napkin.ai/) - Turns text into visuals and simple diagrams. 💲
- [Excalidraw](https://excalidraw.com/) - Open-source hand-drawn-style whiteboard with text-to-diagram features. ([source](https://github.com/excalidraw/excalidraw))

## Blogs, tutorials and community

- [bVisual](https://bvisual.net/) - Blog by David Parker, a long-time Visio MVP, with deep dives on ShapeSheet, data linking and the file format.
- [Visio Guy](https://www.visguy.com/) - Classic Visio tips, free shapes and ShapeSheet techniques.
- [VisGuy forum](https://visguy.com/vgforum/) - Active community forum for Visio development and ShapeSheet questions.
- [Microsoft Visio blog](https://techcommunity.microsoft.com/category/microsoft-visio/blog/visioblog) - Official product announcements on Microsoft Tech Community.
- [Open the ShapeSheet](https://learn.microsoft.com/en-us/office/client-developer/visio/open-the-shapesheet-for-a-shape-page-or-document) - Starting point for learning the ShapeSheet, the formula engine behind every Visio shape.
- [visiowings](https://github.com/twobeass/visiowings) - Edit Visio VBA modules in VS Code with live sync.
- [VisioImportExportVba](https://github.com/nbelyh/VisioImportExportVba) - Import and export Visio VBA code for version control.

## Related lists

- [awesome-visio (bhdicaire)](https://github.com/bhdicaire/awesome-visio) - An earlier community list of Visio resources, focused on shapes and stencils.
- [awesome-diagramming](https://github.com/shubhamgrg04/awesome-diagramming) - Tools for software diagramming in general.
- [awesome](https://github.com/sindresorhus/awesome) - The list of awesome lists.

## Contributing

Contributions are welcome. Read the [contribution guidelines](CONTRIBUTING.md) first.

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this list. See [LICENSE](LICENSE).

*Microsoft, Visio and Microsoft 365 are trademarks of the Microsoft group of companies. This list is not affiliated with, endorsed by or sponsored by Microsoft. VSDX.ai, LayerBack and vsdx.app are independent products and are not made by Microsoft. All other product names are trademarks of their respective owners.*
