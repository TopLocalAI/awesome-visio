# Awesome Visio [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 精选的 Microsoft Visio 与 `.vsdx` 资源清单：文件格式规范、开发库、格式转换、查看与编辑工具、模具（Stencil）、代码生成图表，以及 AI 绘图工具。

[English](README.md) | **简体中文**

Microsoft Visio 是业务和技术图表领域用了很多年的标准工具，常用来画流程图、泳道图、网络拓扑、架构图、组织架构图和平面图。从 Visio 2013 开始，默认文件格式是 **`.vsdx`**。它本质上是一个遵循 Open Packaging Conventions 的 ZIP 压缩包，里面是一组 XML 文件，分别记录页面、母版、ShapeSheet 单元格和主题。相关扩展名还有 `.vssx`（模具）、`.vstx`（模板）和带宏的 `.vsdm`。更早的版本用二进制格式 **`.vsd`**，Visio 2003–2010 还有一种 XML 格式 **`.vdx`**。

既然 `.vsdx` 就是 ZIP 包里的 XML，那么不装 Visio 也能读取、生成和转换 Visio 文件。这份清单收集的就是让这件事变得可行的工具、规范和图形资源。

本清单由 VSDX.ai 和 LayerBack 的团队维护。我们自己的工具用 ⭐ 标出，和其他同类工具放在一起，格式和收录标准与其他条目完全相同。

图例：💲 付费或商业产品（可能有免费额度）· ⭐ 本清单维护者开发的工具

## 目录

- [微软官方资源](#微软官方资源)
  - [产品与帮助文档](#产品与帮助文档)
  - [文件格式](#文件格式)
  - [编程与自动化](#编程与自动化)
- [开发库](#开发库)
  - [Python](#python)
  - [.NET 与 PowerShell](#net-与-powershell)
  - [Java](#java)
  - [JavaScript 与 TypeScript](#javascript-与-typescript)
  - [C、C++、Rust、Go 与 PHP](#ccrustgo-与-php)
- [格式转换](#格式转换)
  - [桌面与命令行](#桌面与命令行)
  - [在线转换](#在线转换)
- [查看与编辑工具](#查看与编辑工具)
- [模具、模板与图标](#模具模板与图标)
  - [厂商官方模具](#厂商官方模具)
  - [社区模具](#社区模具)
  - [没有 Visio 模具的图标集](#没有-visio-模具的图标集)
  - [模具制作工具](#模具制作工具)
- [用代码生成 Visio 图](#用代码生成-visio-图)
- [能输出 Visio 的 AI 工具](#能输出-visio-的-ai-工具)
- [加载项与开发者工具](#加载项与开发者工具)
- [集成](#集成)
- [书籍、博客与社区](#书籍博客与社区)
- [相关清单](#相关清单)

## 微软官方资源

### 产品与帮助文档

- [Microsoft Visio](https://www.microsoft.com/en-us/microsoft-365/visio) - 产品主页，包括 Visio Plan 1、Plan 2 和桌面版。💲
- [Visio in Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/visio/visio-in-microsoft-365) - 轻量网页版 Visio，很多 Microsoft 365 订阅已包含。
- [Visio 帮助与学习](https://support.microsoft.com/en-us/visio) - 官方帮助、操作指南和培训内容。
- [创建数据可视化工具图表](https://support.microsoft.com/en-us/office/create-a-data-visualizer-diagram-17211b46-d144-4ca2-9ea7-b0f48f0ae0a6) - 在 Visio 中用 Excel 表格直接生成流程图、组织架构图和泳道图。
- [在 Visio 中创建 Azure 图表](https://support.microsoft.com/office/efbb25e7-c80e-42e1-b1ad-7ef630ff01b7) - Visio 内置的 Azure 图表模板，包含二十多个模具。
- [Microsoft Visio 2013 Viewer](https://www.microsoft.com/en-us/download/details.aspx?id=35811) - 免费的 ActiveX 查看器，可查看 `.vsdx`、`.vsd` 和 `.vdx`，但要在 Internet Explorer 里运行，在新版 Windows 上用处有限。

### 文件格式

- [Visio 文件格式（.vsdx）简介](https://learn.microsoft.com/en-us/office/client-developer/visio/introduction-to-the-visio-file-formatvsdx) - 包结构、各个部件和它们之间的关系。
- [以编程方式操作 Visio 文件格式](https://learn.microsoft.com/en-us/office/client-developer/visio/how-to-manipulate-the-visio-file-format-programmatically) - 演示如何用 System.IO.Packaging 读取和修改 `.vsdx` 包。
- [Visio 文件格式参考](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-file-format-reference) - `.vsdx` 包内 XML 元素的参考文档。
- [Visio XML 架构图](https://learn.microsoft.com/en-us/office/client-developer/visio/schema-mapvisio-xml) - Visio 2013 文件格式的 XSD 架构定义。
- [MS-VSDX：Visio Graphics Service VSDX 文件格式](https://learn.microsoft.com/en-us/openspecs/sharepoint_protocols/ms-vsdx/50c23601-c943-4ff2-b4a1-02445f52daf0) - `.vsdx` 格式的正式公开规范。
- [Visio ShapeSheet 参考](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-shapesheet-reference) - 单元格、函数、行和节的说明，与 `.vsdx` 内的 XML 一一对应。
- [打开 ShapeSheet](https://learn.microsoft.com/en-us/office/client-developer/visio/open-the-shapesheet-for-a-shape-page-or-document) - 学习 ShapeSheet 的起点。ShapeSheet 是每个 Visio 形状背后的公式引擎。
- [ECMA-376（Office Open XML）](https://ecma-international.org/publications-and-standards/standards/ecma-376/) - `.vsdx` 所依据的 Open Packaging Conventions 标准。

### 编程与自动化

- [Visio 开发者文档](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-home) - Visio 客户端开发、文件格式和 ShapeSheet 文档的总入口。
- [Visio JavaScript API 概述](https://learn.microsoft.com/en-us/office/dev/add-ins/visio/visio-overview) - 面向嵌入在 SharePoint Online 中的 Visio 图表的 Office 加载项 API。
- [Visio JavaScript API 参考](https://learn.microsoft.com/en-us/javascript/api/visio) - `Visio` 命名空间的完整参考。
- [Office 加载项平台](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins) - 开发基于网页的 Office 加载项的总体文档。
- [Office 加载项示例](https://github.com/OfficeDev/Office-Add-in-samples) - Office 加载项平台的官方示例代码。
- [Visio VBA 参考](https://learn.microsoft.com/en-us/office/vba/api/overview/visio) - 用于 VBA 和 COM 自动化的 Visio 对象模型，需要桌面版 Visio。
- [Visio Application 对象](https://learn.microsoft.com/en-us/office/vba/api/visio.application) - COM 对象模型的入口，VBA、C#、PowerShell 和 Python 都从这里开始。
- [Visual Studio 中的 Visio 解决方案（VSTO）](https://learn.microsoft.com/en-us/visualstudio/vsto/visio-solutions) - 为桌面版 Visio 开发 VSTO 加载项。
- [Visio 2013 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=36825) - Visio 2013 解决方案开发所需的文档、示例、头文件和 Event Monitor 等工具。
- [Open XML SDK](https://github.com/dotnet/Open-XML-SDK) - 微软官方的 Office Open XML 包 .NET SDK，适合在底层直接处理 `.vsdx` 的部件和关系。

## 开发库

### Python

- [vsdx](https://github.com/dave-howard/vsdx) - 读取和修改 `.vsdx` 中的形状、文字和连接线，也能用 Jinja 模板生成文件。无需安装 Visio。
- [libvisio-ng](https://github.com/yeager/libvisio-ng) - 解析 `.vsdx` 和 `.vsd` 并转成 SVG，从 vsdview 查看器中拆分出来。
- [pywin32](https://github.com/mhammond/pywin32) - Python 的 Windows 扩展，用 Python 通过 COM 驱动桌面版 Visio 的常用方式。需要 Windows 和 Visio。
- [visioplot](https://github.com/jchliao/visioplot) - 把 Matplotlib 图导出为便于 Office 编辑的 SVG，并转成 `.vsdx`。导出 VSDX 需要 Windows 和 Visio（中文文档）。
- [Aspose.Diagram for Python via .NET](https://products.aspose.com/diagram/python-net/) - 不依赖 Visio，创建、编辑和转换 Visio 格式。💲

### .NET 与 PowerShell

- [VisioAutomation](https://github.com/saveenr/VisioAutomation) - 维护多年的 .NET 库和 PowerShell cmdlet，用于自动化操作桌面版 Visio。
- [VisioBot3000](https://github.com/MikeShepard/VisioBot3000) - 用 PowerShell DSL 自动生成 Visio 图表，需要 Visio。
- [NetOffice](https://github.com/netoffice/NetOffice) - 不绑定 Office 版本的 .NET 自动化封装，包括 Visio。2020 年起不再维护。
- [Aspose.Diagram for .NET](https://products.aspose.com/diagram/net/) - 不依赖 Visio，读写、渲染和转换 VSD、VSDX、VDX 等格式。💲

### Java

- [Apache POI](https://poi.apache.org/components/diagram/) - 用 XDGF 组件处理 `.vsdx`，用 HDGF 处理旧版 `.vsd`，以读取为主。
- [Aspose.Diagram for Java](https://products.aspose.com/diagram/java/) - 创建、编辑和转换 Visio 文件的 Java API。💲

### JavaScript 与 TypeScript

- [ooxml](https://github.com/ChristopherVR/ooxml) - 本地优先的 OOXML 引擎，提供 Visio 文档 API，以及 React、Vue、Angular、Svelte、Solid 和原生 JS 的现成查看器组件。
- [vsdx-kit](https://github.com/TopLocalAI/vsdx-kit) - ⭐ 不用 Visio、也不用浏览器，从 JSON 或 draw.io 文件生成连线已吸附的原生 `.vsdx`，自带自动排版、命令行和本地 MCP 服务。
- [ts-visio](https://github.com/zimmermanw84/ts-visio) - 用 TypeScript 生成 `.vsdx` 文件。
- [vsdx-js](https://github.com/jgreywolf/vsdx-js) - 把 `.vsdx` 文件解析成 JavaScript 对象。
- [cytoscape-vsdx](https://github.com/ShanteshSindgi/cytoscape-vsdx) - 在浏览器里把 Cytoscape.js 图（节点、边、分组、样式）导出为 `.vsdx`。
- [JointJS+ Visio 插件](https://docs.jointjs.com/learn/features/export-import/visio) - 把 `.vsdx` 导入 JointJS 图表，也能把 JointJS 画布导出为 `.vsdx`。💲
- [Syncfusion Diagram Visio 导入导出](https://ej2.syncfusion.com/documentation/diagram/visio) - Syncfusion 图表组件的 VSDX 导入导出功能，目前为实验性质。💲
- [Aspose.Diagram for Node.js via Java](https://products.aspose.com/diagram/nodejs-java/) - 处理 Visio 文件的 Node.js API。💲

### C、C++、Rust、Go 与 PHP

- [libvisio](https://github.com/LibreOffice/libvisio) - Document Liberation Project 的 C++ 库，可导入 `.vsd`、`.vdx` 和 `.vsdx`，LibreOffice 和 Inkscape 都在用。
- [MisterDiagram](https://github.com/MisterDiagram/MisterDiagram) - 用 Rust 从零实现的 `.vsdx` 与 ShapeSheet 引擎，能读写和渲染图纸，附带命令行工具和 MCP 服务。目前是 Beta。
- [libvisio-rs](https://github.com/yeager/libvisio-rs) - 解析 `.vsdx` 和 `.vsd` 并转成 SVG 的 Rust 库。
- [vsdx-go](https://github.com/wijnberg-net/vsdx-go) - 读取、编辑和写入 `.vsdx` 的 Go 库。
- [PhpDiagram](https://github.com/PHPOffice/PhpDiagram) - PHPOffice 出品的纯 PHP 图表文件读写库。2019 年起不再维护。

## 格式转换

### 桌面与命令行

- [LibreOffice 无界面转换](https://help.libreoffice.org/latest/en-US/text/shared/guide/start_parameters.html) - 用 `soffice --headless --convert-to pdf` 在任何系统上把 `.vsd` 和 `.vsdx` 转成 PDF、SVG 或 PNG，不需要 Visio。
- [libvisio2svg](https://github.com/kakwa/libvisio2svg) - 把 Visio 图纸和模具（VSD、VSS）转成 SVG 的库和命令行工具，能处理内嵌的 EMF 图形。
- [weasyvsdx](https://github.com/grigoriev/weasyvsdx) - WeasyPrint 插件，在 HTML 转 PDF 时把 VSDX/VSD 图纸渲染为矢量 SVG。
- [bpmn-to-visio](https://github.com/Mgabr90/bpmn-to-visio) - 把 BPMN 2.0 XML 转成 `.vsdx`，纯 Python，无依赖。
- [svg2vsdx_gui](https://github.com/kinglonh/svg2vsdx_gui) - 把 SVG 转成 `.vsdx` 的 Windows 图形界面工具（中文文档），已不活跃。
- [Visio-Export-Pages-To-Docs](https://github.com/saveenr/Visio-Export-Pages-To-Docs) - 把多页 Visio 文档拆成每页一个文件的命令行工具，需要 Visio。
- [VSDtoVSDX-Converter](https://github.com/jprtf/VSDtoVSDX-Converter) - 带图形界面的 PowerShell 脚本，借助 Visio 把旧版 `.vsd` 批量转成 `.vsdx`。
- [visio2img](https://github.com/visio2img/visio2img) - 借助 Visio 把 `.vsd` 和 `.vsdx` 页面导出为图片的 Python 命令行工具。2018 年起不再维护。

### 在线转换

- [VSDX.ai 免费工具](https://vsdx.ai/tools?utm_source=awesome-visio) - ⭐ 免注册、在浏览器里运行的 Visio 转 draw.io 和 Visio 转 PNG/SVG（支持 `.vsdx`），另有付费的 Mermaid、PlantUML、Excel 转 Visio 工具。
- [draw.io 支持的导入格式](https://www.drawio.com/docs/manual/import/import-formats/) - draw.io 可导入 `.vsdx`、`.vsd` 和 `.vssx` 模具，也能导出 VSDX（标注为 Beta）。
- [SVG to Visio](https://mcmarius11.github.io/svgtovisio/) - 在浏览器本地把 SVG 或 draw.io 文件转成带粘附连接线的 `.vsdx`，也能导出 `.drawio` 和 `.fodg`。（[源码](https://github.com/McMarius11/svgtovisio)）
- [Aspose Visio Converter](https://products.aspose.app/diagram/conversion) - 免费网页应用，把 Visio 文件转成 PDF、图片、HTML、SVG、PPTX、DRAWIO 等格式。
- [GroupDocs Viewer for VSDX](https://products.groupdocs.app/viewer/vsdx) - 免费在线查看和渲染 VSDX。
- [AnyConv](https://anyconv.com/vsdx-converter/) - 免费在线把 VSDX 转成 PDF 和图片。
- [Convertio](https://convertio.co/vsdx-converter/) - 通用在线转换工具，可把 VSDX 转成 PDF 和图片。免费版有限制。
- [Zamzar](https://www.zamzar.com/convert/vsdx-to-pdf/) - 在线把 VSDX 转成 PDF。免费版有限制。

## 查看与编辑工具

- [vsdx.app](https://vsdx.app?utm_source=awesome-visio) - ⭐ 原生 macOS 应用，打开、编辑和保存 `.vsdx` 与 `.vsd`，支持访达快速查看。查看免费。💲
- [LayerBack VSDX Viewer](https://layerback.com/vsdx-viewer?utm_source=awesome-visio) - ⭐ 免费在线查看器，不装 Visio 也能在浏览器里打开 `.vsdx`。
- [draw.io](https://www.drawio.com/) - 免费开源的图表编辑器，有网页版和桌面版，能导入和导出 Visio 文件。（[桌面版](https://github.com/jgraph/drawio-desktop)）
- [LibreOffice Draw](https://www.libreoffice.org/) - 通过 libvisio 打开 `.vsd`、`.vdx` 和 `.vsdx`，但不能存回 Visio 格式。（[导入导出限制](https://help.libreoffice.org/latest/en-US/text/shared/guide/ms_import_export_limitations.html)）
- [Inkscape](https://inkscape.org/) - 矢量绘图软件，通过 libvisio 导入 Visio 文件。
- [vsdview](https://github.com/yeager/vsdview) - Linux 上基于 GTK4/Adwaita 的 `.vsdx` / `.vsd` 查看器。
- [VSD Viewer](https://nektony.com/products/visio-viewer-mac) - Mac 上的 VSD、VDX、VSDX 查看器，支持图层和形状数据。可免费下载，Pro 版付费。💲
- [Aspose Visio Viewer](https://products.aspose.app/diagram/viewer) - 免费网页应用，把 VSD、VSDX、VDX 和模具文件渲染成图片查看。
- [Lucidchart](https://www.lucidchart.com/) - 在线绘图工具，可导入 Visio 文件。💲（[导入指南](https://help.lucid.co/hc/en-us/articles/16389149809428)）
- [Miro](https://help.miro.com/hc/en-us/articles/11842818558738) - 在线白板，可把 `.vsdx` 图表导入为白板。💲
- [SmartDraw](https://www.smartdraw.com/) - 在线绘图工具，支持 Visio 导入导出。💲
- [EdrawMax（亿图图示）](https://www.edrawsoft.com/edraw-max/) - 跨平台图表软件，支持 Visio 导入导出。💲
- [ConceptDraw DIAGRAM](https://www.conceptdraw.com/) - Mac 和 Windows 图表软件，能打开和保存 Visio 格式。💲
- [OmniGraffle](https://www.omnigroup.com/omnigraffle) - Mac 和 iPad 绘图应用，可导入导出 Visio 文件。💲
- [Visual Paradigm Online](https://online.visual-paradigm.com/) - 在线绘图套件，支持导入 Visio，有免费版。💲

## 模具、模板与图标

### 厂商官方模具

- [VisioCafe](https://www.visiocafe.com/) - 老牌的免费厂商官方 Visio 模具索引，涵盖 HPE、Dell、NetApp、IBM、联想、富士通等。
- [Cisco 网络拓扑图标](https://www.cisco.com/c/en/us/about/brand-center/network-topology-icons.html) - Cisco 官方图标和 Visio 模具下载。
- [Fortinet 图标库](https://www.fortinet.com/resources/icon-library) - Fortinet 官方产品和网络安全图标，提供 Visio 模具。
- [Microsoft 365 架构图标与模板](https://learn.microsoft.com/en-us/previous-versions/microsoft-365/solutions/architecture-icons-templates) - Microsoft 365 图标集和 Visio 模板（已归档页面）。
- [ShapeSource](https://www.shapesource.com/) - Visimation 的厂商 Visio 模具库，很多免费，例如 Palo Alto Networks 和 Juniper。💲
- [Paul Herber Software](https://www.paulherber.co.uk/) - 电气、电子、UML、暖通等领域的 Visio 形状集，部分免费。💲

### 社区模具

- [Microsoft Integration and Azure Stencils Pack](https://github.com/sandroasp/Microsoft-Integration-and-Azure-Stencils-Pack-for-Visio) - 大型 Visio 模具包，覆盖 Azure、BizTalk、Power Platform 和 Microsoft 365。
- [visioStencils](https://github.com/bhdicaire/visioStencils) - 4,000 多个 IT 基础设施形状、模具和图标合集。
- [VisioStencils](https://github.com/girlpunk/VisioStencils) - 600 多个 `.vss` 和 `.vssx` 模具文件合集。
- [Visio-Azure](https://github.com/xeeva/Visio-Azure) - 可搜索的 Azure 模具（1,259 个图标），带连接点和形状数据。
- [Visio-Cisco](https://github.com/xeeva/Visio-Cisco) - 可搜索的非官方 Cisco 模具，分公制和美制两个版本。
- [C4 model Visio stencil](https://github.com/pihalve/c4model-visio-stencil) - 用于 C4 软件架构图的形状。
- [ntwrk-clean-and-flat](https://github.com/DukeNuke3D/ntwrk-clean-and-flat) - 简洁扁平的 2D 网络图符号，提供 Visio 模具。
- [VMware Visio stencils](https://github.com/uldyssian-sh/vmware-visio-stencils) - 100 多个 VMware 产品图标和模板，用于基础设施图。
- [Microsoft Fabric Visio stencils](https://github.com/PatrickGallucci/fabric-stencils) - 90 多个形状，用于画 Microsoft Fabric 架构图。
- [Unifi Visio Stencils](https://github.com/brightmethods/Unifi-Visio-Stencils) - 常见 Ubiquiti UniFi 设备的模具。
- [Ubiquiti Visio stencils](https://github.com/digiservnet/ubiquiti-visio-stencils) - Ubiquiti 设备模具，每个端口都有对应的连接点。
- [Domotic Visio stencils](https://github.com/rrobinet/Visio-Stencils) - 智能家居和电气模具。
- [IEC 61131-3 Visio stencils](https://github.com/avafab/IEC-61131-3-Visio-stencils) - 用于 PLC 软件设计的顺序功能图（SFC）形状。
- [DMN Visio stencils](https://github.com/debasishdalui/dmn-visio-stencils) - 决策模型与标记法（DMN 1.0）形状。
- [bootstrap-visio-templates](https://github.com/henck/bootstrap-visio-templates) - 可配置的 Bootstrap 网页界面原型模具，已不活跃。
- [Shapes-n-stencils](https://github.com/Visio-Resources/Shapes-n-stencils) - 按类别整理的第三方 Visio 模具和加载项链接清单。

### 没有 Visio 模具的图标集

- [Azure 架构图标](https://learn.microsoft.com/en-us/azure/architecture/icons/) - Azure 官方 SVG 图标。微软不打算提供 Visio 模具版本，但可以直接拖进 Visio 使用。
- [AWS 架构图标](https://aws.amazon.com/architecture/icons/) - AWS 官方图标包和 PowerPoint 工具包，没有 Visio 模具。
- [Google Cloud 图标](https://cloud.google.com/icons) - Google Cloud 官方产品图标，提供 SVG 和 PNG。
- [Microsoft Power Platform 图标](https://learn.microsoft.com/en-us/power-platform/guidance/icons) - Power Platform 官方 SVG 图标。
- [Microsoft Fabric 图标](https://learn.microsoft.com/en-us/fabric/fundamentals/icons) - Fabric 官方产品和项目 SVG 图标。

### 模具制作工具

- [Visio Stencil Factory](https://github.com/rezanid/visiostencilfactory) - 用一个文件夹的 SVG 文件生成自己的 Visio 模具。
- [visio-stencil-creator](https://github.com/hoveytechllc/visio-stencil-creator) - 不装 Visio 也能从 PNG 图片生成 `.vssx` 模具，也提供 Docker 镜像。已不活跃。

## 用代码生成 Visio 图

Visio 本身没有文本语法。下面是在代码和 `.vsdx` 之间转换的几条实用路线。

- [md2visio](https://github.com/Megre/md2visio) - 把 Markdown 里的 Mermaid 转成 `.vsdx`。
- [mermaid-to-visio](https://github.com/FBklyra/mermaid-to-visio) - 在本地把渲染后的 Mermaid 转成原生 `.vsdx` 形状和连接线，提供库、命令行和网页编辑器。
- [convert2mermaid](https://github.com/jgreywolf/convert2mermaid) - 把 `.vsdx`、draw.io、Excalidraw 和 PlantUML 图表转成 Mermaid 的命令行工具和 npm 包。
- [draw.io：用代码生成图表](https://www.drawio.com/docs/tutorials/diagrams-from-code/) - draw.io 的 Mermaid、PlantUML 和 CSV 导入方式总览，导入后可导出 VSDX。
- [Mermaid](https://mermaid.js.org/) - 流行的类 Markdown 图表语法，通常经 draw.io 或上面的转换工具变成 Visio。
- [PlantUML](https://plantuml.com/) - 用文本写 UML。draw.io 可以插入 PlantUML，再导出为 VSDX。
- [Graphviz](https://graphviz.org/) - 经典的图布局引擎（DOT 语言），导出的 SVG 可以导入 Visio。
- [D2](https://d2lang.com/) - 新一代图表脚本语言，支持导出 SVG。
- [Diagrams](https://diagrams.mingrammer.com/) - 用 Python 代码画云架构图，输出图片。
- [Kroki](https://kroki.io/) - 一个 HTTP API 把 Mermaid、PlantUML、Graphviz、D2 等渲染为 SVG 或 PNG。（[源码](https://github.com/yuzutech/kroki)）

## 能输出 Visio 的 AI 工具

- [VSDX.ai](https://vsdx.ai?utm_source=awesome-visio) - ⭐ AI Visio 图表生成器，可以从文字、文档、数据、图表代码或图片生成原生 `.vsdx`，连接线粘附在形状上。提供 REST API 和远程 MCP 服务（`https://vsdx.ai/api/mcp`）。💲
- [LayerBack](https://layerback.com?utm_source=awesome-visio) - ⭐ 把图表的图片或 PDF 重建为可编辑的 VSDX、PPTX、draw.io 或 SVG，提供 API 和 [MCP 服务](https://github.com/TopLocalAI/layerback-mcp)。💲
- [Visiomaster](https://github.com/Rss3208/Visiomaster) - Codex 工具包，把图片里的流程图和论文配图重建为可编辑的 `.vsdx`。需要 Windows 和 Visio（中文文档）。
- [codex-visio-paper-figure-skill](https://github.com/pengjunchi0/codex-visio-paper-figure-skill) - Codex Skill，通过 COM 把论文配图从图片重建为 Visio 原生图形。需要 Visio（中文文档）。
- [visio-com-skill](https://github.com/WUXU-Tech/visio-com-skill) - Codex Skill，通过本地 Visio COM 自动化生成可编辑的 `.vsdx`。需要 Windows 和 Visio。
- [Visio Scientific Figures](https://github.com/ywq177995212697-droid/visio-scientific-figures) - Agent Skill，根据 YAML 描述把科研配图渲染为 `.vsdx`，并做版式质量检查。需要 Visio。
- [VSDX Trace](https://github.com/ZJUZhiyuCai/vsdx-trace) - Agent Skill 加 Python 工具链，把截图和科研配图描摹成可编辑的 `.vsdx`。
- [CVPR-Figure](https://github.com/ChizkiyahuOhayon/CVPR-Figure) - 根据描述或模型代码生成 AI 会议论文配图，可在 Visio 和 PowerPoint 中编辑。

## 加载项与开发者工具

- [SvgPublish](https://unmanagedvisio.com/products/svg-publish/) - Visio 加载项，把图表发布为可交互的 HTML/SVG 网页。💲（[发布版本](https://github.com/nbelyh/svgpublish-releases)）
- [Extended Visio Addin Project](https://github.com/nbelyh/VisioPanelAddinVSTO) - Visual Studio 项目模板，用于开发带任务窗格、功能区和安装包的 VSTO 或 COM Visio 加载项。
- [visiowings](https://github.com/twobeass/visiowings) - 在 VS Code 里编辑 Visio VBA 模块，实时同步。
- [VisioImportExportVba](https://github.com/nbelyh/VisioImportExportVba) - 导入导出 Visio VBA 代码，方便做版本管理。已不活跃。
- [ShapeSheetWatch](https://github.com/nbelyh/ShapeSheetWatch) - 带额外功能的 ShapeSheet 监视窗口，适合形状开发者。已不活跃。

## 集成

- [FlowToVisio](https://github.com/LinkeD365/FlowToVisio) - XrmToolBox 工具，把 Power Automate 云端流和 Logic Apps 生成 Visio 图表文档。
- [StartLeft](https://github.com/iriusrisk/startleft) - 从 Visio 图表等多种来源生成 Open Threat Model 威胁模型文件。

## 书籍、博客与社区

- [Visualize Complex Processes with Microsoft Visio](https://www.packtpub.com/product/visualize-complex-processes-with-microsoft-visio/9781837631926) - David Parker 和 Senaj Lelic 合著，讲解在 Visio 中画流程图和 BPMN（Packt，2023）。💲
- [bVisual](https://bvisual.net/) - 资深 Visio MVP David Parker 的博客，深入讲解 ShapeSheet、数据链接和文件格式。
- [Visio Guy](https://www.visguy.com/) - 老牌 Visio 技巧站，有免费形状和 ShapeSheet 技巧。
- [VisGuy 论坛](https://visguy.com/vgforum/) - 活跃的 Visio 开发和 ShapeSheet 问答社区。
- [Unmanaged Visio](https://unmanagedvisio.com/) - Nikolay Belyh 的 Visio 加载项、网页工具和文章。
- [Microsoft Visio 博客](https://techcommunity.microsoft.com/category/microsoft-visio/blog/visioblog) - 微软技术社区上的官方产品公告。
- [Stack Overflow visio 标签](https://stackoverflow.com/questions/tagged/visio) - 关于 Visio 自动化和文件格式的编程问答。
- [r/visio](https://www.reddit.com/r/visio/) - Visio 用户的 Reddit 社区。

## 相关清单

- [awesome-visio（bhdicaire）](https://github.com/bhdicaire/awesome-visio) - 更早的一份社区 Visio 资源清单，侧重形状和模具。
- [awesome-diagramming](https://github.com/shubhamgrg04/awesome-diagramming) - 通用的软件绘图工具清单。

## 参与贡献

欢迎参与贡献！请先阅读[贡献指南](CONTRIBUTING.md)。本清单以 [CC0](LICENSE) 协议发布。

*Microsoft、Visio 和 Microsoft 365 是微软集团的商标。本清单与微软没有任何关联，也未获得微软的认可或赞助。其他产品名称均为其各自所有者的商标。*
