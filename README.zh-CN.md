# Awesome Visio [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 精选的 Microsoft Visio 与 `.vsdx` 资源清单：文件格式规范、开发库、格式转换、查看与编辑工具、模具（Stencil）、代码生成图表，以及 AI 绘图工具。

[English](README.md) | **简体中文**

Microsoft Visio 是业务和技术图表领域用了很多年的标准工具，常用来画流程图、泳道图、网络拓扑、架构图、组织架构图和平面图。从 Visio 2013 开始，默认文件格式是 **`.vsdx`**。它本质上是一个遵循 [Open Packaging Conventions](https://ecma-international.org/publications-and-standards/standards/ecma-376/) 的 ZIP 压缩包，里面是一组 XML 文件，分别记录页面、母版、ShapeSheet 单元格和主题。相关扩展名还有 `.vssx`（模具）、`.vstx`（模板）和带宏的 `.vsdm`。更早的版本用二进制格式 **`.vsd`**，Visio 2003–2010 还有一种 XML 格式 **`.vdx`**。

既然 `.vsdx` 就是 ZIP 包里的 XML，那么不装 Visio 也能读取、生成和转换 Visio 文件。这份清单收集的就是这类工具。

图例：💲 商业或付费产品 · 🆓 免费/开源（仅在不明显时标注）

## 目录

- [维护者出品的工具](#维护者出品的工具)
  - [对比](#对比)
  - [VSDX.ai](#vsdxai)
  - [LayerBack](#layerback)
  - [vsdx.app](#vsdxapp)
- [微软官方资源](#微软官方资源)
  - [产品与帮助文档](#产品与帮助文档)
  - [文件格式](#文件格式)
  - [编程与自动化](#编程与自动化)
- [开发库](#开发库)
  - [Python](#python)
  - [.NET / PowerShell](#net--powershell)
  - [Java](#java)
  - [JavaScript / TypeScript](#javascript--typescript)
  - [C++ / Rust / Go](#c--rust--go)
- [格式转换](#格式转换)
- [查看与编辑工具](#查看与编辑工具)
- [模具与图形库](#模具与图形库)
- [用代码生成 Visio 图](#用代码生成-visio-图)
- [AI 绘图工具](#ai-绘图工具)
- [博客、教程与社区](#博客教程与社区)
- [相关清单](#相关清单)
- [参与贡献](#参与贡献)

---

## 维护者出品的工具

> **说明：** 本清单由 [TopLocalAI](https://github.com/TopLocalAI) 维护，本节介绍的三款工具都是我们团队做的。本节之后的内容是中立的社区清单，欢迎提交 PR 补充其他同类工具，包括我们的竞品。

这三款工具生成的都是**真正的 Visio 内容**：原生形状、粘附在形状上的连接线、可编辑的文字，而不是把一张图片塞进 `.vsdx` 外壳里。用它们创建或查看文件，都不需要 Visio 许可证。

### 对比

| | [VSDX.ai](https://vsdx.ai) | [LayerBack](https://layerback.com) | [vsdx.app](https://vsdx.app) |
|---|---|---|---|
| **输入** | 文字、文档、表格、数据、Mermaid/PlantUML 代码 | 现成图表的图片或 PDF | 已有的 `.vsdx` / `.vsd` 文件 |
| **得到什么** | 一张全新的原生 Visio 图，外加多种格式互转 | 把原图重建成可编辑文件 | 在 Mac 上原生打开、编辑、保存 Visio 文件 |
| **输出格式** | `.vsdx`、`.drawio`、PNG、SVG | VSDX、PPTX、draw.io XML、SVG | `.vsdx`、`.vsd`（两种都能打开） |
| **运行方式** | 浏览器（网页应用） | 浏览器（网页应用） | macOS 应用（Swift/AppKit） |
| **免费部分** | 浏览器内免费工具（Visio 转 draw.io、Visio 转 PNG/SVG）；注册送 20 积分 | 免登录免费转换和预览；免费在线 VSDX 查看器 | 免费打开、查看、打印任意 `.vsdx`/`.vsd`，支持访达快速查看 |
| **付费起步** | Pro 每月 $20 | Pro 每月 $20 | Pro 或终身版 |
| **开发者 / Agent 接入** | REST API、OpenAPI 规范、远程 MCP 服务 | REST API、开源 MCP 服务和 Agent Skill | — |
| **界面语言** | 7 种（英、中、德、法、西、日、韩） | 7 种，能识别中日文等非拉丁文字 | — |

**怎么选？** 手里是一张图表的*图片*，想变成可编辑文件，用 LayerBack。手里是*内容*（文字、文档、数据或图表代码），想生成新的 Visio 图，或者需要让 AI Agent 产出 `.vsdx`，用 VSDX.ai。要在 *Mac 上打开和编辑 Visio 文件*，用 vsdx.app。

### VSDX.ai

**[VSDX.ai](https://vsdx.ai)** 是一个 AI Visio 图表生成器，能把文字、文档和数据变成原生 `.vsdx` 文件。

- **支持多种输入。** 可以读取表格（Excel、CSV）、PDF、Word、纯文本、Markdown、JSON、YAML、图片、音频和短视频。一个项目里可以同时放多份资料，资料私密保存。
- **输出真正的 Visio 文件。** 先理解内容，再整理成结构化的图，导出的 `.vsdx` 里是可编辑的形状和粘附好的连接线，不是一张平面图片，也不是把 PNG 改了扩展名。文件已在 Windows 版 Microsoft Visio 中实测能正常打开。也可以导出 `.drawio`，已有的 `.vsdx` / `.drawio` 文件也能导回来继续改。
- **图表类型。** 流程图、泳道图、BPMN、组织架构图、架构图、网络图、ER 图、UML。
- **生成后还能接着改。** 每张图都能在内嵌的 draw.io 编辑器里修改，也可以用对话的方式改，保存过的版本可以随时恢复。
- **布局整齐。** 内置基于 ELK 的自动布局引擎。"整理图表"工具可以把杂乱的 draw.io 或 Visio 图重新排版。
- **格式转换工具**（[全部工具](https://vsdx.ai/tools)）：图片转 Visio、Excel 转组织架构图、大纲转组织架构图、[Mermaid 转 Visio](https://vsdx.ai/tools/mermaid-to-visio)、PlantUML 转 Visio、draw.io 转 Visio、[Visio 转 draw.io](https://vsdx.ai/tools/visio-to-drawio)、Visio 转 PNG/SVG、整理图表。另见 [Excel 转组织架构图](https://vsdx.ai/tools/excel-to-org-chart)。
- **免费、免注册、完全在浏览器里运行：** Visio 转 draw.io、Visio 转 PNG/SVG。仅支持新版 `.vsdx`，不支持旧版 `.vsd`。
- **面向开发者和 Agent。** 提供公开的 REST API 和 [OpenAPI 规范](https://vsdx.ai/api/v1/openapi.json)（[开发者页面](https://vsdx.ai/developers)、[文档](https://vsdx.ai/docs)）。远程 MCP 服务地址是 `https://vsdx.ai/api/mcp`，提供 `generate_diagram`、`convert_diagram`、`get_credits` 三个工具。[配置指南](https://vsdx.ai/mcp)覆盖 Claude Code、Cursor 和 Codex，网页版 ChatGPT 和 Claude 可以通过 OAuth 连接。所有账号都能通过 API/MCP 导出 PNG、SVG 和 draw.io；导出 `.vsdx` 需要付费套餐或积分包。
- **界面语言：** 英语、中文、德语、法语、西班牙语、日语、韩语。

**价格**（[详情](https://vsdx.ai/pricing)）：每次生成或修改消耗 10 积分，每次使用工具消耗 10 积分（免费工具不扣积分）。新账号赠送 20 积分。

| 套餐 | 月付 | 年付 | 每月积分 |
|---|---|---|---|
| Free | $0 | — | 注册赠送 20 积分 |
| Pro | $20 | $120 | 300 |
| Business | $50 | $300 | 1,000 |
| Team | $100 | $600 | 3,000 |

积分加购：$20 买 300、$50 买 1,000、$100 买 3,000，有效期均为 90 天。

### LayerBack

**[LayerBack](https://layerback.com)** 能把图表图片或 PDF 转成可编辑的 Visio、PowerPoint、draw.io 或 SVG 文件。

- **重建图表，而不是描摹。** 支持截图、PNG、JPG、WebP 和 PDF 页面。矢量描摹工具只能得到轮廓，有的工具干脆把原图嵌进文件里。LayerBack 会把每个框做成原生形状，每个箭头做成粘附在形状上的连接线，每段文字都是可以直接改的文本。已在 Visio 和 PowerPoint 中实测验证。
- **一张图，四种格式。** 每次转换大约 30 秒。转换和预览免费，不用登录。一张图第一次下载或编辑时扣 10 积分，同时解锁 VSDX、PPTX、draw.io XML、SVG 全部四种格式。转换失败不扣费。
- **内置在线编辑器**，有不满意的地方可以直接改，改完重新导出。
- **隐私。** 上传的文件 72 小时后自动删除。
- **多语言。** 能识别中文、日文等非拉丁文字，界面支持 7 种语言。
- **免费的[在线 VSDX 查看器](https://layerback.com/vsdx-viewer)。** 不装 Visio，在浏览器里就能打开 `.vsdx`。
- **功能页面：** [图片转 Visio](https://layerback.com/image-to-visio) · [PDF 转 Visio](https://layerback.com/pdf-to-visio) · [图片转 PPTX](https://layerback.com/image-to-pptx) · [图片转 draw.io](https://layerback.com/image-to-drawio) · [全部工具](https://layerback.com/tools)
- **面向开发者和 Agent：**
  - [公开 API](https://layerback.com/docs/api)（通过 `x-api-key` 请求头鉴权）。
  - [layerback-mcp](https://github.com/TopLocalAI/layerback-mcp)：开源 MCP 服务，提供 `convert_diagram_image`、`get_conversion_status`、`download_converted_diagram`，可在 Claude Desktop、Claude Code 和 Cursor 中使用。
  - [layerback-image-to-vsdx-skill](https://github.com/TopLocalAI/layerback-image-to-vsdx-skill)：开源 Agent Skill。安装命令：

    ```sh
    npx -y skills@latest add TopLocalAI/layerback-image-to-vsdx-skill --skill layerback-image-to-vsdx --agent codex --global
    ```

**价格**（[详情](https://layerback.com/pricing)）：Pro 每月 $20（1,000 积分），Plus 每月 $40（3,000 积分），Max 每月 $80（10,000 积分）。积分包 $10 起，永不过期。

### vsdx.app

**[vsdx.app](https://vsdx.app)** 是一款独立开发的 macOS 原生应用，可以打开、编辑和保存 Visio 的 `.vsdx` 和 `.vsd` 文件。

- **真正的原生 Mac 应用。** 用 Swift 和 AppKit 开发，不是网页套壳。采用大家熟悉的功能区（Ribbon）界面。
- **文件保真。** 保存时保留原始 XML。
- **与访达集成。** 支持 Visio 文件的快速查看预览和缩略图。
- **离线可用。** 首次登录后即可离线使用。登录在浏览器中完成，应用里不保存任何密码或 API 密钥。
- **AI 起草。** 用一句话描述，就能生成一份图表初稿（由 VSDX.ai 提供支持）。
- **免费功能：** 打开、查看、打印任意 `.vsdx` 或 `.vsd`，在访达中预览。编辑、保存和 AI 功能需要 **Pro** 或**终身版**。终身版是永久授权，每月含 100 AI 积分，另有积分包可买。

---

## 微软官方资源

### 产品与帮助文档

- [Microsoft Visio](https://www.microsoft.com/en-us/microsoft-365/visio) - 产品主页，包括 Visio Plan 1、Plan 2 和桌面版。💲
- [Visio in Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/visio/visio-in-microsoft-365) - 轻量网页版 Visio，很多 Microsoft 365 订阅已包含。
- [Visio 帮助与学习](https://support.microsoft.com/en-us/visio) - 官方帮助、操作指南和培训内容。
- [创建数据可视化工具图表](https://support.microsoft.com/en-us/office/create-a-data-visualizer-diagram-17211b46-d144-4ca2-9ea7-b0f48f0ae0a6) - 在 Visio 中用 Excel 表格直接生成流程图、组织架构图和泳道图。
- [Visio Viewer（旧版）](https://www.microsoft.com/en-us/download/details.aspx?id=35811) - 免费的 Visio 图纸查看器。版本较老，依赖 Internet Explorer，在新版 Windows 上大概率不好用。（[背景介绍](https://learn.microsoft.com/en-us/archive/blogs/office_resource_kit/download-the-new-microsoft-visio-viewer)）

### 文件格式

- [Visio 文件格式（.vsdx）简介](https://learn.microsoft.com/en-us/office/client-developer/visio/introduction-to-the-visio-file-formatvsdx) - 包结构、各个部件和它们之间的关系。
- [以编程方式操作 Visio 文件格式](https://learn.microsoft.com/en-us/office/client-developer/visio/how-to-manipulate-the-visio-file-format-programmatically) - 一步步演示如何用 System.IO.Packaging 读取和修改 `.vsdx` 包。
- [Visio 文件格式参考](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-file-format-reference) - `.vsdx` 包内 XML 元素的参考文档。
- [[MS-VSDX]：Visio Graphics Service VSDX 文件格式](https://learn.microsoft.com/en-us/openspecs/sharepoint_protocols/ms-vsdx/50c23601-c943-4ff2-b4a1-02445f52daf0) - `.vsdx` 格式的正式公开规范。
- [Visio ShapeSheet 参考](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-shapesheet-reference) - 单元格、函数、行和节的说明，与 `.vsdx` 内的 XML 一一对应。
- [ECMA-376（Office Open XML）](https://ecma-international.org/publications-and-standards/standards/ecma-376/) - `.vsdx` 所依据的 Open Packaging Conventions 标准。

### 编程与自动化

- [Visio JavaScript API 概述](https://learn.microsoft.com/en-us/office/dev/add-ins/visio/visio-overview) - 面向嵌入在 SharePoint Online 中的 Visio 图表的 Office 加载项 API。
- [Visio JavaScript API 参考](https://learn.microsoft.com/en-us/javascript/api/visio) - `Visio` 命名空间的完整参考。
- [Office 加载项平台](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins) - 开发基于网页的 Office 加载项的总体文档。
- [Office 加载项示例](https://github.com/OfficeDev/Office-Add-in-samples) - Office 加载项平台的官方示例代码。
- [Visio VBA 参考](https://learn.microsoft.com/en-us/office/vba/api/overview/visio) - 用于 VBA 和 COM 自动化的 Visio 对象模型。
- [Visio Application 对象](https://learn.microsoft.com/en-us/office/vba/api/visio.application) - COM 对象模型的入口，VBA、C#、PowerShell 和 Python（pywin32）都从这里开始。
- [Visual Studio 中的 Visio 解决方案（VSTO）](https://learn.microsoft.com/en-us/visualstudio/vsto/visio-solutions) - 为桌面版 Visio 开发 VSTO 加载项。
- [Open XML SDK](https://learn.microsoft.com/en-us/office/open-xml/open-xml-sdk) - 微软官方的 Office Open XML 包 .NET SDK，适合在底层直接处理 `.vsdx` 包（部件、关系、XML）。（[GitHub](https://github.com/dotnet/Open-XML-SDK)、[NuGet](https://www.nuget.org/packages/DocumentFormat.OpenXml)）

## 开发库

### Python

- [vsdx](https://github.com/dave-howard/vsdx) - 读取和修改 `.vsdx` 文件（形状、文字、连接线），也能用 Jinja 模板生成新文件。无需安装 Visio。（[PyPI](https://pypi.org/project/vsdx/)、[文档](https://vsdx.readthedocs.io/)）
- [libvisio-ng](https://github.com/yeager/libvisio-ng) - 解析 `.vsdx` 和 `.vsd` 并转成 SVG，从 vsdview 查看器中拆分出来。（[PyPI](https://pypi.org/project/libvisio-ng/)）
- [pywin32](https://github.com/mhammond/pywin32) - Python 的 Windows 扩展，用 Python 通过 COM 驱动桌面版 Visio 的常用方式。需要 Windows 和 Visio。
- [Aspose.Diagram for Python via .NET](https://products.aspose.com/diagram/python-net/) - 创建、编辑和转换 Visio 格式。💲（[PyPI](https://pypi.org/project/aspose-diagram-python/)）

### .NET / PowerShell

- [VisioAutomation](https://github.com/saveenr/VisioAutomation) - 维护多年的 .NET 库和 PowerShell cmdlet，用于自动化操作桌面版 Visio。
- [VisioBot3000](https://github.com/MikeShepard/VisioBot3000) - 用 PowerShell DSL 自动生成 Visio 图表。
- [Aspose.Diagram for .NET](https://products.aspose.com/diagram/net/) - 不依赖 Visio，读写、渲染和转换 VSD、VSDX、VDX 等格式。💲（[NuGet](https://www.nuget.org/packages/Aspose.Diagram)）

### Java

- [Apache POI – XDGF](https://poi.apache.org/components/diagram/) - Apache POI 中处理 `.vsdx`（XDGF）和旧版 `.vsd`（HDGF）的组件，以读取为主。（[API 文档](https://poi.apache.org/apidocs/dev/org/apache/poi/xdgf/usermodel/package-summary.html)、[GitHub 镜像](https://github.com/apache/poi)）
- [Aspose.Diagram for Java](https://products.aspose.com/diagram/java/) - 商业 Java Visio 文件 API。💲

### JavaScript / TypeScript

- [ooxml（visio-core 及查看器）](https://github.com/ChristopherVR/ooxml) - 本地优先的 OOXML 引擎，提供 Visio 文档 API，以及 React、Vue、Angular、Svelte、Solid 和原生 JS 的现成查看器组件。（[演示/文档](https://christophervr.github.io/ooxml/)）
- [ts-visio](https://github.com/zimmermanw84/ts-visio) - 用 TypeScript 生成 `.vsdx` 文件。
- [vsdx-js](https://github.com/jgreywolf/vsdx-js) - 把 `.vsdx` 文件解析成 JavaScript 对象。
- [cytoscape-vsdx](https://github.com/ShanteshSindgi/cytoscape-vsdx) - 在浏览器里把 Cytoscape.js 图（节点、边、分组、样式）导出为 `.vsdx`。
- [Aspose.Diagram for Node.js via Java](https://products.aspose.com/diagram/nodejs-java/) - 商业 Node.js Visio 文件 API。💲

### C++ / Rust / Go

- [libvisio](https://github.com/LibreOffice/libvisio) - LibreOffice / Document Liberation Project 的 C++ 库，可导入 `.vsd`、`.vdx` 和 `.vsdx`，LibreOffice 和 Inkscape 的 Visio 导入功能都靠它。（[项目主页](https://wiki.documentfoundation.org/DLP/Libraries/libvisio)）
- [MisterDiagram](https://github.com/MisterDiagram/MisterDiagram) - 用 Rust 从零实现的无界面 `.vsdx` 和 ShapeSheet 引擎，能读写图纸、模具和模板，渲染为 PNG/SVG/PDF，附带命令行工具和 MCP 服务。目前是 Beta。
- [libvisio-rs](https://github.com/yeager/libvisio-rs) - 解析 `.vsdx` / `.vsd` 并转成 SVG 的 Rust 库。
- [vsdx-go](https://github.com/wijnberg-net/vsdx-go) - 读取、编辑和写入 `.vsdx` 的 Go 库。

## 格式转换

- [draw.io 支持的导入格式](https://www.drawio.com/docs/manual/import/import-formats/) - draw.io 可导入 `.vsdx`、`.vsd`、`.vssx` 模具等格式，也能导出为 VSDX（*文件 > 导出为 > VSDX*，标注为 Beta）。（[VSDX 导入说明](https://drawio-app.com/blog/import-vsdx-files/)）
- [LibreOffice Draw](https://www.libreoffice.org/) - 通过 libvisio 打开 `.vsd`、`.vdx` 和 `.vsdx`，可导出为 PDF、SVG、ODG，但不能存回 Visio 格式。（[导入导出限制](https://help.libreoffice.org/latest/en-US/text/shared/guide/ms_import_export_limitations.html)）
- [Inkscape](https://inkscape.org/) - 矢量绘图软件，通过 libvisio 导入 Visio 文件，可再导出为 SVG/PDF。（[源码](https://gitlab.com/inkscape/inkscape)）
- [weasyvsdx](https://github.com/grigoriev/weasyvsdx) - WeasyPrint 插件，在 HTML 转 PDF 时把 VSDX/VSD 图纸渲染为矢量 SVG（基于 libvisio）。
- [visio2img](https://github.com/visio2img/visio2img) - 把 `.vsd` / `.vsdx` 页面导出为图片的 Python 命令行工具。需要 Windows、pywin32 和 Visio，已不再维护。
- [VSDtoVSDX-Converter](https://github.com/jprtf/VSDtoVSDX-Converter) - 带图形界面的 PowerShell 脚本，借助 Visio 把旧版 `.vsd` 批量转成 `.vsdx`。
- [bpmn-to-visio](https://github.com/Mgabr90/bpmn-to-visio) - 把 BPMN 2.0 XML 转成 `.vsdx`，纯 Python，无依赖。
- [GroupDocs Viewer – VSDX](https://products.groupdocs.app/viewer/vsdx) - GroupDocs 提供的免费在线 VSDX 查看和渲染工具。
- [Convertio](https://convertio.co/vsdx-converter/) - 通用在线转换工具，可把 VSDX 转成 PDF 和图片。免费版有限制。
- [Zamzar](https://www.zamzar.com/convert/vsdx-to-pdf/) - 在线把 VSDX 转成 PDF。免费版有限制。

## 查看与编辑工具

- [draw.io / diagrams.net](https://www.drawio.com/) - 免费开源的图表编辑器，有网页版和桌面版，能导入和导出 Visio 文件。（[网页版](https://app.diagrams.net/)、[桌面版](https://github.com/jgraph/drawio-desktop)、[源码](https://github.com/jgraph/drawio)）
- [vsdview](https://github.com/yeager/vsdview) - Linux 上基于 GTK4/Adwaita 的 `.vsdx` / `.vsd` 查看器。
- [Lucidchart](https://www.lucidchart.com/) - 在线绘图工具，可导入 Visio 文件。💲（[导入指南](https://help.lucid.co/hc/en-us/articles/16389149809428)）
- [SmartDraw](https://www.smartdraw.com/) - 在线绘图工具，支持 Visio 导入导出。💲
- [EdrawMax（亿图图示）](https://www.edrawsoft.com/edraw-max/) - 跨平台图表软件（Windows、Mac、Linux、网页），支持 Visio 导入导出。💲
- [ConceptDraw DIAGRAM](https://www.conceptdraw.com/) - Mac 和 Windows 图表软件，能打开和保存 Visio 格式。💲
- [OmniGraffle](https://www.omnigroup.com/omnigraffle) - Mac 和 iPad 绘图应用，可导入导出 Visio 文件。💲
- [Visual Paradigm Online](https://online.visual-paradigm.com/) - 在线绘图套件，支持导入 Visio，有免费版。💲
- [yEd](https://www.yworks.com/products/yed) - 免费的桌面图编辑器，自动布局能力很强，适合先排好版再搬进 Visio。

## 模具与图形库

- [VisioCafe](https://www.visiocafe.com/) - 老牌的免费厂商官方 Visio 模具索引（HPE、Dell、NetApp、IBM、联想、富士通等）。
- [Cisco 网络拓扑图标](https://www.cisco.com/c/en/us/about/brand-center/network-topology-icons.html) - Cisco 官方图标和 Visio 模具下载。
- [Azure 架构图标](https://learn.microsoft.com/en-us/azure/architecture/icons/) - Azure 官方图标。以 SVG 提供，不是 Visio 模具，但可以直接拖进 Visio 使用。
- [Microsoft 365 架构图标与模板](https://learn.microsoft.com/en-us/previous-versions/microsoft-365/solutions/architecture-icons-templates) - Microsoft 365 图标集和 Visio 模板（已归档页面）。
- [Microsoft Integration & Azure Stencils Pack](https://github.com/sandroasp/Microsoft-Integration-and-Azure-Stencils-Pack-for-Visio) - 社区维护的大型 Visio 模具包，覆盖 Azure、BizTalk、Power Platform 和 Microsoft 365。
- [visioStencils](https://github.com/bhdicaire/visioStencils) - 4,000 多个 IT 基础设施形状、模具和图标合集。
- [Visio-Azure](https://github.com/xeeva/Visio-Azure) - 可搜索的 Azure 模具（1,259 个图标），带连接点和形状数据。
- [Visio-Cisco](https://github.com/xeeva/Visio-Cisco) - 社区制作的可搜索 Cisco 模具，分公制和美制两个版本。非官方。
- [C4 model Visio stencil](https://github.com/pihalve/c4model-visio-stencil) - 用于 C4 软件架构图的形状。
- [ntwrk-clean-and-flat](https://github.com/DukeNuke3D/ntwrk-clean-and-flat) - 简洁扁平的 2D 网络图符号，提供 Visio 模具。
- [Unifi Visio Stencils](https://github.com/brightmethods/Unifi-Visio-Stencils) - 常见 Ubiquiti UniFi 设备的模具。
- [Visio Stencil Factory](https://github.com/rezanid/visiostencilfactory) - 用一个文件夹的 SVG 文件生成自己的 Visio 模具。
- [ShapeSource](https://www.shapesource.com/) - 由 Visimation 制作的各厂商 Visio 形状，部分收费。💲
- [draw.io libraries](https://github.com/jgraph/drawio-libs) - draw.io 的社区图形库，配合 draw.io 的 VSDX 导出，也是一条通往 Visio 的路。

## 用代码生成 Visio 图

Visio 本身没有文本语法。下面是从代码得到 `.vsdx` 的几条实用路线。

- [Mermaid](https://mermaid.js.org/) - 流行的类 Markdown 图表语法。常见做法：Mermaid → draw.io（[插入 Mermaid](https://www.drawio.com/docs/manual/mermaid/)）→ 导出 VSDX，或者用下面的直接转换工具。
- [PlantUML](https://plantuml.com/) - 用文本写 UML 等图。draw.io 可以[插入 PlantUML](https://www.drawio.com/docs/manual/insert/insert_plantuml/)，再导出为 VSDX。
- [Graphviz](https://graphviz.org/) - 经典的图布局引擎（DOT 语言）。先导出 SVG，再导入 Visio 或 draw.io。（[输出格式](https://graphviz.org/docs/outputs/)）
- [md2visio](https://github.com/Megre/md2visio) - 把 Markdown 里的 Mermaid 转成 `.vsdx`。
- [mermaid-to-visio](https://github.com/FBklyra/mermaid-to-visio) - 在本地把渲染后的 Mermaid 转成原生 `.vsdx` 形状和连接线，提供库、命令行和网页编辑器。
- [draw.io：用代码生成图表](https://www.drawio.com/docs/tutorials/diagrams-from-code/) - draw.io 的 Mermaid、PlantUML 和 CSV 导入方式总览。
- [D2](https://d2lang.com/) - 新一代图表脚本语言。导出 SVG 后可用于基于 Visio 的工作流。
- [Diagrams](https://diagrams.mingrammer.com/) - 用 Python 代码画云架构图。输出图片，可以照着在 Visio 里重画。
- [Kroki](https://kroki.io/) - 一个 HTTP API 渲染多种文本图表语言（Mermaid、PlantUML、Graphviz、D2 等）为 SVG/PNG。（[源码](https://github.com/yuzutech/kroki)）

## AI 绘图工具

- [Visiomaster](https://github.com/Rss3208/Visiomaster) - Windows 工具包兼 Codex Skill，通过 Visio COM 把图片里的流程图、论文配图重建为可编辑的 `.vsdx`（中文文档）。
- [visio-com-skill](https://github.com/WUXU-Tech/visio-com-skill) - Codex Skill，在 Windows 上通过本地 Visio COM 自动化生成可编辑的 `.vsdx`。
- [MisterDiagram](https://github.com/MisterDiagram/MisterDiagram) - MCP 服务，用自然语言描述就能生成 `.vsdx`，不需要 Visio（开发库一节也有收录）。
- [Eraser DiagramGPT](https://www.eraser.io/diagramgpt) - 用自然语言或代码生成技术图表。💲
- [Mermaid Chart](https://www.mermaidchart.com/) - Mermaid 团队推出的商业版编辑器，带 AI 辅助绘图。💲
- [Napkin AI](https://www.napkin.ai/) - 把文字变成配图和简单图表。💲
- [Excalidraw](https://excalidraw.com/) - 开源的手绘风白板，支持文字生成图表。（[源码](https://github.com/excalidraw/excalidraw)）

## 博客、教程与社区

- [bVisual](https://bvisual.net/) - 资深 Visio MVP David Parker 的博客，深入讲解 ShapeSheet、数据链接和文件格式。
- [Visio Guy](https://www.visguy.com/) - 老牌 Visio 技巧站，有免费形状和 ShapeSheet 技巧。
- [VisGuy 论坛](https://visguy.com/vgforum/) - 活跃的 Visio 开发和 ShapeSheet 问答社区。
- [Microsoft Visio 博客](https://techcommunity.microsoft.com/category/microsoft-visio/blog/visioblog) - 微软技术社区上的官方产品公告。
- [打开 ShapeSheet](https://learn.microsoft.com/en-us/office/client-developer/visio/open-the-shapesheet-for-a-shape-page-or-document) - 学习 ShapeSheet 的起点。ShapeSheet 是每个 Visio 形状背后的公式引擎。
- [visiowings](https://github.com/twobeass/visiowings) - 在 VS Code 里编辑 Visio VBA 模块，实时同步。
- [VisioImportExportVba](https://github.com/nbelyh/VisioImportExportVba) - 导入导出 Visio VBA 代码，方便做版本管理。

## 相关清单

- [awesome-visio（bhdicaire）](https://github.com/bhdicaire/awesome-visio) - 更早的一份社区 Visio 资源清单，侧重形状和模具。
- [awesome-diagramming](https://github.com/shubhamgrg04/awesome-diagramming) - 通用的软件绘图工具清单。
- [awesome](https://github.com/sindresorhus/awesome) - Awesome 清单的总目录。

## 参与贡献

欢迎参与贡献！请先阅读[贡献指南](CONTRIBUTING.md)。

---

## 许可证

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

在法律允许的范围内，贡献者已放弃本清单的全部著作权及相关权利。详见 [LICENSE](LICENSE)。

*Microsoft、Visio 和 Microsoft 365 是微软集团的商标。本清单与微软没有任何关联，也未获得微软的认可或赞助。VSDX.ai、LayerBack 和 vsdx.app 是 TopLocalAI 开发的独立产品，并非微软出品。其他产品名称均为其各自所有者的商标。*
