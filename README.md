# Awesome Visio [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of Microsoft Visio and `.vsdx` resources: file format specs, libraries, converters, viewers, stencils, diagram-as-code routes and AI tools.

**English** | [简体中文](README.zh-CN.md)

Microsoft Visio is the long-standing standard for business and technical diagrams: flowcharts, swimlanes, network and architecture diagrams, org charts and floor plans. Since Visio 2013 the default file format is **`.vsdx`**, an Open Packaging Conventions ZIP archive of XML parts (pages, masters, ShapeSheet cells, themes). Related extensions are `.vssx` (stencil), `.vstx` (template) and the macro-enabled `.vsdm`. Older versions used the binary **`.vsd`** format and the Visio 2003–2010 XML format **`.vdx`**.

Because `.vsdx` is plain XML in a ZIP, you can read, generate and convert Visio files without Visio itself. This list collects the tools, specs and shapes that make that practical.

Maintained by the team behind VSDX.ai and LayerBack. Our own tools are marked ⭐ and listed alongside the alternatives, with the same format and criteria as every other entry.

Legend: 💲 paid or commercial (may have a free tier) · ⭐ made by the maintainers of this list

## Contents

- [Official Microsoft resources](#official-microsoft-resources)
  - [Product and documentation](#product-and-documentation)
  - [File format](#file-format)
  - [Programming and automation](#programming-and-automation)
- [Libraries](#libraries)
  - [Python](#python)
  - [.NET and PowerShell](#net-and-powershell)
  - [Java](#java)
  - [JavaScript and TypeScript](#javascript-and-typescript)
  - [C, C++, Rust, Go and PHP](#c-c-rust-go-and-php)
- [Converters](#converters)
  - [Desktop and command line](#desktop-and-command-line)
  - [Online converters](#online-converters)
- [Viewers and editors](#viewers-and-editors)
- [Stencils, templates and icons](#stencils-templates-and-icons)
  - [Official vendor stencils](#official-vendor-stencils)
  - [Community stencils](#community-stencils)
  - [Icon sets without Visio stencils](#icon-sets-without-visio-stencils)
  - [Stencil tools](#stencil-tools)
- [Diagram-as-code to Visio](#diagram-as-code-to-visio)
- [AI tools that output Visio](#ai-tools-that-output-visio)
- [Add-ins and developer tools](#add-ins-and-developer-tools)
- [Integrations](#integrations)
- [Books, blogs and community](#books-blogs-and-community)
- [Related lists](#related-lists)

## Official Microsoft resources

### Product and documentation

- [Microsoft Visio](https://www.microsoft.com/en-us/microsoft-365/visio) - Product home for Visio Plan 1, Plan 2 and the desktop app. 💲
- [Visio in Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/visio/visio-in-microsoft-365) - Lightweight web version of Visio included with many Microsoft 365 subscriptions.
- [Visio support](https://support.microsoft.com/en-us/visio) - Official help, how-to articles and training.
- [Create a Data Visualizer diagram](https://support.microsoft.com/en-us/office/create-a-data-visualizer-diagram-17211b46-d144-4ca2-9ea7-b0f48f0ae0a6) - Generate flowcharts, org charts and swimlanes from Excel tables in Visio.
- [Create Azure diagrams in Visio](https://support.microsoft.com/office/efbb25e7-c80e-42e1-b1ad-7ef630ff01b7) - The built-in Azure Diagrams template with more than twenty stencils.
- [Microsoft Visio 2013 Viewer](https://www.microsoft.com/en-us/download/details.aspx?id=35811) - Free ActiveX viewer for `.vsdx`, `.vsd` and `.vdx` that runs inside Internet Explorer, so it is of limited use on current Windows.

### File format

- [Introduction to the Visio file format (.vsdx)](https://learn.microsoft.com/en-us/office/client-developer/visio/introduction-to-the-visio-file-formatvsdx) - Package structure, parts and relationships.
- [Manipulate the Visio file format programmatically](https://learn.microsoft.com/en-us/office/client-developer/visio/how-to-manipulate-the-visio-file-format-programmatically) - Walkthrough of reading and editing a `.vsdx` package with System.IO.Packaging.
- [Visio file format reference](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-file-format-reference) - Reference for the XML elements in a `.vsdx` package.
- [Schema map (Visio XML)](https://learn.microsoft.com/en-us/office/client-developer/visio/schema-mapvisio-xml) - The XSD schema definition of the Visio 2013 file format.
- [MS-VSDX: Visio Graphics Service VSDX File Format](https://learn.microsoft.com/en-us/openspecs/sharepoint_protocols/ms-vsdx/50c23601-c943-4ff2-b4a1-02445f52daf0) - Formal open specification of the `.vsdx` format.
- [Visio ShapeSheet reference](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-shapesheet-reference) - Cells, functions, rows and sections, which map directly onto the XML inside `.vsdx`.
- [Open the ShapeSheet](https://learn.microsoft.com/en-us/office/client-developer/visio/open-the-shapesheet-for-a-shape-page-or-document) - Starting point for learning the ShapeSheet, the formula engine behind every Visio shape.
- [ECMA-376 (Office Open XML)](https://ecma-international.org/publications-and-standards/standards/ecma-376/) - The Open Packaging Conventions standard that `.vsdx` is built on.

### Programming and automation

- [Visio developer documentation](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-home) - Hub for Visio client development, file format and ShapeSheet docs.
- [Visio JavaScript API overview](https://learn.microsoft.com/en-us/office/dev/add-ins/visio/visio-overview) - Office Add-ins API for Visio diagrams embedded in SharePoint Online.
- [Visio JavaScript API reference](https://learn.microsoft.com/en-us/javascript/api/visio) - Full reference for the `Visio` namespace.
- [Office Add-ins platform](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins) - General documentation for building web-based Office add-ins.
- [Office Add-in samples](https://github.com/OfficeDev/Office-Add-in-samples) - Official code samples for the Office Add-ins platform.
- [Visio VBA reference](https://learn.microsoft.com/en-us/office/vba/api/overview/visio) - The Visio object model for VBA and COM automation. Needs desktop Visio.
- [Visio Application object](https://learn.microsoft.com/en-us/office/vba/api/visio.application) - Entry point of the COM object model used by VBA, C#, PowerShell and Python.
- [Visio solutions in Visual Studio (VSTO)](https://learn.microsoft.com/en-us/visualstudio/vsto/visio-solutions) - Build VSTO add-ins for desktop Visio.
- [Visio 2013 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=36825) - Documentation, samples, headers and tools such as Event Monitor for Visio 2013 solutions.
- [Open XML SDK](https://github.com/dotnet/Open-XML-SDK) - Microsoft's .NET SDK for Office Open XML packages, handy for low-level part and relationship work on `.vsdx`.

## Libraries

### Python

- [vsdx](https://github.com/dave-howard/vsdx) - Read and edit `.vsdx` shapes, text and connectors, and generate files from Jinja templates. Works without Visio.
- [libvisio-ng](https://github.com/yeager/libvisio-ng) - Parse `.vsdx` and `.vsd` files and convert them to SVG. Extracted from the vsdview viewer.
- [pywin32](https://github.com/mhammond/pywin32) - Python for Windows extensions, the usual way to drive desktop Visio through COM. Needs Windows and Visio.
- [visioplot](https://github.com/jchliao/visioplot) - Export Matplotlib figures as Office-friendly SVG and convert them to `.vsdx`. VSDX export needs Windows and Visio (Chinese docs).
- [Aspose.Diagram for Python via .NET](https://products.aspose.com/diagram/python-net/) - Create, edit and convert Visio formats without Visio. 💲

### .NET and PowerShell

- [VisioAutomation](https://github.com/saveenr/VisioAutomation) - Long-running .NET libraries and PowerShell cmdlets for automating desktop Visio.
- [VisioBot3000](https://github.com/MikeShepard/VisioBot3000) - PowerShell DSL for building Visio diagrams through automation. Needs Visio.
- [NetOffice](https://github.com/netoffice/NetOffice) - Version-independent .NET wrappers for Office automation, including Visio. Unmaintained since 2020.
- [Aspose.Diagram for .NET](https://products.aspose.com/diagram/net/) - Read, write, render and convert VSD, VSDX, VDX and related formats without Visio. 💲

### Java

- [Apache POI](https://poi.apache.org/components/diagram/) - XDGF component for `.vsdx` and HDGF for legacy `.vsd`. Read-focused.
- [Aspose.Diagram for Java](https://products.aspose.com/diagram/java/) - Java API to create, edit and convert Visio files. 💲

### JavaScript and TypeScript

- [ooxml](https://github.com/ChristopherVR/ooxml) - Local-first OOXML engine with Visio document APIs and drop-in viewers for React, Vue, Angular, Svelte, Solid and vanilla JS.
- [ts-visio](https://github.com/zimmermanw84/ts-visio) - Create `.vsdx` files from TypeScript.
- [vsdx-js](https://github.com/jgreywolf/vsdx-js) - Parse a `.vsdx` file into a JavaScript object.
- [cytoscape-vsdx](https://github.com/ShanteshSindgi/cytoscape-vsdx) - Export Cytoscape.js graphs with nodes, edges, groups and styles to `.vsdx` in the browser.
- [JointJS+ Visio plugin](https://docs.jointjs.com/learn/features/export-import/visio) - Import `.vsdx` into JointJS diagrams and export a JointJS paper as `.vsdx`. 💲
- [Syncfusion Diagram Visio import and export](https://ej2.syncfusion.com/documentation/diagram/visio) - Experimental VSDX import and export for the Syncfusion diagram component. 💲
- [Aspose.Diagram for Node.js via Java](https://products.aspose.com/diagram/nodejs-java/) - Node.js API for Visio files. 💲

### C, C++, Rust, Go and PHP

- [libvisio](https://github.com/LibreOffice/libvisio) - The Document Liberation Project C++ library that imports `.vsd`, `.vdx` and `.vsdx`, used by LibreOffice and Inkscape.
- [MisterDiagram](https://github.com/MisterDiagram/MisterDiagram) - Clean-room Rust core for `.vsdx` and the ShapeSheet that reads, writes and renders drawings, with a CLI and an MCP server. Beta.
- [libvisio-rs](https://github.com/yeager/libvisio-rs) - Rust library for parsing `.vsdx` and `.vsd` and converting to SVG.
- [vsdx-go](https://github.com/wijnberg-net/vsdx-go) - Go library for reading, editing and writing `.vsdx` files.
- [PhpDiagram](https://github.com/PHPOffice/PhpDiagram) - Pure PHP library from PHPOffice for reading and writing diagram files. Unmaintained since 2019.

## Converters

### Desktop and command line

- [LibreOffice headless conversion](https://help.libreoffice.org/latest/en-US/text/shared/guide/start_parameters.html) - `soffice --headless --convert-to pdf` turns `.vsd` and `.vsdx` into PDF, SVG or PNG on any OS without Visio.
- [libvisio2svg](https://github.com/kakwa/libvisio2svg) - Library and CLI tools that convert Visio drawings and stencils (VSD, VSS) to SVG, including embedded EMF shapes.
- [weasyvsdx](https://github.com/grigoriev/weasyvsdx) - WeasyPrint plugin that renders VSDX and VSD drawings as vector SVG in HTML-to-PDF output.
- [bpmn-to-visio](https://github.com/Mgabr90/bpmn-to-visio) - Convert BPMN 2.0 XML into `.vsdx` with pure Python and no dependencies.
- [svg2vsdx_gui](https://github.com/kinglonh/svg2vsdx_gui) - Windows GUI that converts SVG files to `.vsdx` (Chinese docs). Inactive.
- [Visio-Export-Pages-To-Docs](https://github.com/saveenr/Visio-Export-Pages-To-Docs) - CLI that splits a multi-page Visio document into one file per page. Needs Visio.
- [VSDtoVSDX-Converter](https://github.com/jprtf/VSDtoVSDX-Converter) - PowerShell GUI that batch-converts legacy `.vsd` files to `.vsdx` through Visio.
- [visio2img](https://github.com/visio2img/visio2img) - Python CLI that exports `.vsd` and `.vsdx` pages to images through Visio. Unmaintained since 2018.

### Online converters

- [VSDX.ai free tools](https://vsdx.ai/tools?utm_source=awesome-visio) - ⭐ Free in-browser Visio to draw.io and Visio to PNG/SVG for `.vsdx`, no account, plus paid Mermaid, PlantUML and Excel to Visio tools.
- [draw.io import formats](https://www.drawio.com/docs/manual/import/import-formats/) - draw.io imports `.vsdx`, `.vsd` and `.vssx` stencils, and exports VSDX (labeled beta).
- [SVG to Visio](https://mcmarius11.github.io/svgtovisio/) - Client-side converter from SVG or draw.io files to `.vsdx` with glued connectors, `.drawio` and `.fodg`. ([source](https://github.com/McMarius11/svgtovisio))
- [Aspose Visio Converter](https://products.aspose.app/diagram/conversion) - Free web app that converts Visio files to PDF, images, HTML, SVG, PPTX, DRAWIO and more.
- [GroupDocs Viewer for VSDX](https://products.groupdocs.app/viewer/vsdx) - Free online VSDX viewer and renderer.
- [AnyConv](https://anyconv.com/vsdx-converter/) - Free online VSDX converter to PDF and image formats.
- [Convertio](https://convertio.co/vsdx-converter/) - General online converter for VSDX to PDF and image formats. Free tier with limits.
- [Zamzar](https://www.zamzar.com/convert/vsdx-to-pdf/) - Online VSDX to PDF conversion. Free tier with limits.

## Viewers and editors

- [vsdx.app](https://vsdx.app?utm_source=awesome-visio) - ⭐ Native macOS app that opens, edits and saves `.vsdx` and `.vsd`, with Finder Quick Look previews. Viewing is free. 💲
- [LayerBack VSDX Viewer](https://layerback.com/vsdx-viewer?utm_source=awesome-visio) - ⭐ Free online viewer that opens `.vsdx` files in the browser without Visio.
- [draw.io](https://www.drawio.com/) - Free, open-source diagram editor for web and desktop that imports and exports Visio files. ([desktop](https://github.com/jgraph/drawio-desktop))
- [LibreOffice Draw](https://www.libreoffice.org/) - Opens `.vsd`, `.vdx` and `.vsdx` through libvisio, but cannot save back to Visio formats. ([limitations](https://help.libreoffice.org/latest/en-US/text/shared/guide/ms_import_export_limitations.html))
- [Inkscape](https://inkscape.org/) - Vector editor that imports Visio files through libvisio.
- [vsdview](https://github.com/yeager/vsdview) - GTK4/Adwaita viewer for `.vsdx` and `.vsd` on Linux.
- [VSD Viewer](https://nektony.com/products/visio-viewer-mac) - Mac viewer for VSD, VDX and VSDX drawings with layers and shape data. Free download with paid Pro version. 💲
- [Aspose Visio Viewer](https://products.aspose.app/diagram/viewer) - Free web app that renders VSD, VSDX, VDX and stencil files as images.
- [Lucidchart](https://www.lucidchart.com/) - Web diagramming tool that imports Visio files. 💲 ([import guide](https://help.lucid.co/hc/en-us/articles/16389149809428))
- [Miro](https://help.miro.com/hc/en-us/articles/11842818558738) - Online whiteboard that imports `.vsdx` diagrams as boards. 💲
- [SmartDraw](https://www.smartdraw.com/) - Web diagramming tool with Visio import and export. 💲
- [EdrawMax](https://www.edrawsoft.com/edraw-max/) - Cross-platform diagram editor with Visio import and export. 💲
- [ConceptDraw DIAGRAM](https://www.conceptdraw.com/) - Mac and Windows diagram editor that opens and saves Visio formats. 💲
- [OmniGraffle](https://www.omnigroup.com/omnigraffle) - Mac and iPad diagramming app that imports and exports Visio files. 💲
- [Visual Paradigm Online](https://online.visual-paradigm.com/) - Web diagramming suite with Visio import and a free tier. 💲

## Stencils, templates and icons

### Official vendor stencils

- [VisioCafe](https://www.visiocafe.com/) - Long-standing free index of official vendor Visio stencils from HPE, Dell, NetApp, IBM, Lenovo, Fujitsu and others.
- [Cisco network topology icons](https://www.cisco.com/c/en/us/about/brand-center/network-topology-icons.html) - Official Cisco icons and Visio stencil downloads.
- [Fortinet icon library](https://www.fortinet.com/resources/icon-library) - Official Fortinet product and cybersecurity icons with Visio stencils.
- [Microsoft 365 architecture icons and templates](https://learn.microsoft.com/en-us/previous-versions/microsoft-365/solutions/architecture-icons-templates) - Microsoft 365 icon sets and Visio templates (archived page).
- [ShapeSource](https://www.shapesource.com/) - Visimation's library of manufacturer Visio stencils, many free, such as Palo Alto Networks and Juniper. 💲
- [Paul Herber Software](https://www.paulherber.co.uk/) - Visio shape sets for electrical, electronics, UML, HVAC and more, with some free shapes. 💲

### Community stencils

- [Microsoft Integration and Azure Stencils Pack](https://github.com/sandroasp/Microsoft-Integration-and-Azure-Stencils-Pack-for-Visio) - Large Visio pack for Azure, BizTalk, Power Platform and Microsoft 365.
- [visioStencils](https://github.com/bhdicaire/visioStencils) - Collection of 4,000+ IT infrastructure shapes, stencils and icons.
- [VisioStencils](https://github.com/girlpunk/VisioStencils) - Collection of more than 600 `.vss` and `.vssx` stencil files.
- [Visio-Azure](https://github.com/xeeva/Visio-Azure) - Searchable Azure stencil set with 1,259 icons, connection points and shape data.
- [Visio-Cisco](https://github.com/xeeva/Visio-Cisco) - Searchable, unofficial Cisco stencil set with Metric and US builds.
- [C4 model Visio stencil](https://github.com/pihalve/c4model-visio-stencil) - Shapes for C4 software architecture diagrams.
- [ntwrk-clean-and-flat](https://github.com/DukeNuke3D/ntwrk-clean-and-flat) - Clean, flat 2D network symbols with Visio stencils.
- [VMware Visio stencils](https://github.com/uldyssian-sh/vmware-visio-stencils) - More than 100 VMware product icons and templates for infrastructure diagrams.
- [Microsoft Fabric Visio stencils](https://github.com/PatrickGallucci/fabric-stencils) - Over 90 shapes for Microsoft Fabric architecture diagrams.
- [Unifi Visio Stencils](https://github.com/brightmethods/Unifi-Visio-Stencils) - Stencils for common Ubiquiti UniFi hardware.
- [Ubiquiti Visio stencils](https://github.com/digiservnet/ubiquiti-visio-stencils) - Ubiquiti devices with a connection point for every port.
- [Domotic Visio stencils](https://github.com/rrobinet/Visio-Stencils) - Home automation and electrical stencils.
- [IEC 61131-3 Visio stencils](https://github.com/avafab/IEC-61131-3-Visio-stencils) - Sequential Function Chart shapes for PLC software design.
- [DMN Visio stencils](https://github.com/debasishdalui/dmn-visio-stencils) - Decision Model and Notation (DMN 1.0) shapes.
- [bootstrap-visio-templates](https://github.com/henck/bootstrap-visio-templates) - Configurable stencils for Bootstrap web UI mockups. Inactive.
- [Shapes-n-stencils](https://github.com/Visio-Resources/Shapes-n-stencils) - Categorized link list of third-party Visio stencils and add-ons.

### Icon sets without Visio stencils

- [Azure architecture icons](https://learn.microsoft.com/en-us/azure/architecture/icons/) - Official Azure icons as SVG. Microsoft has no plans to ship them as Visio stencils, but they drag straight into Visio.
- [AWS architecture icons](https://aws.amazon.com/architecture/icons/) - Official AWS icon package and PowerPoint toolkit. No Visio stencils.
- [Google Cloud icons](https://cloud.google.com/icons) - Official Google Cloud product icons as SVG and PNG.
- [Microsoft Power Platform icons](https://learn.microsoft.com/en-us/power-platform/guidance/icons) - Official Power Platform icons as SVG.
- [Microsoft Fabric icons](https://learn.microsoft.com/en-us/fabric/fundamentals/icons) - Official Fabric product and item icons as SVG.

### Stencil tools

- [Visio Stencil Factory](https://github.com/rezanid/visiostencilfactory) - Build your own Visio stencils from a folder of SVG files.
- [visio-stencil-creator](https://github.com/hoveytechllc/visio-stencil-creator) - Create a `.vssx` stencil from PNG images without Visio, also as a Docker image. Inactive.

## Diagram-as-code to Visio

Visio has no native text syntax. These are the practical routes between code and `.vsdx`.

- [md2visio](https://github.com/Megre/md2visio) - Convert Mermaid in Markdown into `.vsdx`.
- [mermaid-to-visio](https://github.com/FBklyra/mermaid-to-visio) - Convert rendered Mermaid into native `.vsdx` shapes and connectors client-side, with a library, CLI and web editor.
- [convert2mermaid](https://github.com/jgreywolf/convert2mermaid) - CLI and npm package that converts `.vsdx`, draw.io, Excalidraw and PlantUML diagrams into Mermaid.
- [draw.io diagrams from code](https://www.drawio.com/docs/tutorials/diagrams-from-code/) - Overview of draw.io's Mermaid, PlantUML and CSV import, after which you can export VSDX.
- [Mermaid](https://mermaid.js.org/) - Popular Markdown-like diagram syntax, usually taken to Visio through draw.io or a converter above.
- [PlantUML](https://plantuml.com/) - Text-based UML that draw.io can insert and then export to VSDX.
- [Graphviz](https://graphviz.org/) - Classic graph layout engine (DOT language) whose SVG output can be imported into Visio.
- [D2](https://d2lang.com/) - Modern diagram scripting language with SVG export.
- [Diagrams](https://diagrams.mingrammer.com/) - Python diagram-as-code for cloud architecture that renders images.
- [Kroki](https://kroki.io/) - HTTP API that renders Mermaid, PlantUML, Graphviz, D2 and more to SVG or PNG. ([source](https://github.com/yuzutech/kroki))

## AI tools that output Visio

- [VSDX.ai](https://vsdx.ai?utm_source=awesome-visio) - ⭐ AI Visio generator from text, documents, data, diagram code or images that exports native `.vsdx` with glued connectors. REST API and remote MCP server at `https://vsdx.ai/api/mcp`. 💲
- [LayerBack](https://layerback.com?utm_source=awesome-visio) - ⭐ Rebuilds a picture or PDF of a diagram as editable VSDX, PPTX, draw.io or SVG, with an API and an [MCP server](https://github.com/TopLocalAI/layerback-mcp). 💲
- [Visiomaster](https://github.com/Rss3208/Visiomaster) - Codex toolkit that rebuilds flowcharts and paper figures from images as editable `.vsdx`. Needs Windows and Visio (Chinese docs).
- [codex-visio-paper-figure-skill](https://github.com/pengjunchi0/codex-visio-paper-figure-skill) - Codex skill that rebuilds research paper figures from images as native Visio shapes through COM. Needs Visio (Chinese docs).
- [visio-com-skill](https://github.com/WUXU-Tech/visio-com-skill) - Codex skill that generates editable `.vsdx` through local Visio COM automation. Needs Windows and Visio.
- [Visio Scientific Figures](https://github.com/ywq177995212697-droid/visio-scientific-figures) - Agent skill that renders research figures from YAML specs as `.vsdx` with layout quality checks. Needs Visio.
- [VSDX Trace](https://github.com/ZJUZhiyuCai/vsdx-trace) - Agent skill and Python toolchain that traces screenshots and scientific figures into editable `.vsdx`.
- [CVPR-Figure](https://github.com/ChizkiyahuOhayon/CVPR-Figure) - Generates AI conference paper figures from a spec or model code, editable in Visio and PowerPoint.

## Add-ins and developer tools

- [SvgPublish](https://unmanagedvisio.com/products/svg-publish/) - Visio add-in that publishes diagrams as interactive HTML/SVG pages. 💲 ([releases](https://github.com/nbelyh/svgpublish-releases))
- [Extended Visio Addin Project](https://github.com/nbelyh/VisioPanelAddinVSTO) - Visual Studio template for VSTO or COM Visio add-ins with a task pane, ribbon and installer.
- [visiowings](https://github.com/twobeass/visiowings) - Edit Visio VBA modules in VS Code with live sync.
- [VisioImportExportVba](https://github.com/nbelyh/VisioImportExportVba) - Import and export Visio VBA code for version control. Inactive.
- [ShapeSheetWatch](https://github.com/nbelyh/ShapeSheetWatch) - ShapeSheet watch window with extra features for shape developers. Inactive.

## Integrations

- [FlowToVisio](https://github.com/LinkeD365/FlowToVisio) - XrmToolBox tool that documents Power Automate cloud flows and Logic Apps as Visio diagrams.
- [StartLeft](https://github.com/iriusrisk/startleft) - Generates Open Threat Model files from sources including Visio diagrams.

## Books, blogs and community

- [Visualize Complex Processes with Microsoft Visio](https://www.packtpub.com/product/visualize-complex-processes-with-microsoft-visio/9781837631926) - Book by David Parker and Senaj Lelic on process diagrams and BPMN in Visio (Packt, 2023). 💲
- [bVisual](https://bvisual.net/) - Blog by David Parker, a long-time Visio MVP, with deep dives on ShapeSheet, data linking and the file format.
- [Visio Guy](https://www.visguy.com/) - Classic Visio tips, free shapes and ShapeSheet techniques.
- [VisGuy forum](https://visguy.com/vgforum/) - Active forum for Visio development and ShapeSheet questions.
- [Unmanaged Visio](https://unmanagedvisio.com/) - Nikolay Belyh's Visio add-ins, web tools and articles.
- [Microsoft Visio blog](https://techcommunity.microsoft.com/category/microsoft-visio/blog/visioblog) - Official product announcements on Microsoft Tech Community.
- [Stack Overflow visio tag](https://stackoverflow.com/questions/tagged/visio) - Programming questions about Visio automation and file formats.
- [r/visio](https://www.reddit.com/r/visio/) - Reddit community for Visio users.

## Related lists

- [awesome-visio by bhdicaire](https://github.com/bhdicaire/awesome-visio) - Earlier community list of Visio resources, focused on shapes and stencils.
- [awesome-diagramming](https://github.com/shubhamgrg04/awesome-diagramming) - Tools for software diagramming in general.

## Contributing

Contributions are welcome. Read the [contribution guidelines](CONTRIBUTING.md) first. This list is released under [CC0](LICENSE).

*Microsoft, Visio and Microsoft 365 are trademarks of the Microsoft group of companies. This list is not affiliated with, endorsed by or sponsored by Microsoft. All other product names are trademarks of their respective owners.*
