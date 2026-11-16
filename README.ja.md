# Awesome Visio [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Microsoft Visio と `.vsdx` に関する厳選リソース集：ファイル形式仕様、開発ライブラリ、変換ツール、ビューア、ステンシル、Diagram-as-Code 連携、および AI 作図ツール。

[English](./README.md) | [简体中文](./README.zh-CN.md) | 日本語

Microsoft Visio は、フローチャート、スイムレーン図、ネットワーク図、アーキテクチャ図、組織図、フロアプランなど、ビジネスおよび技術図面の分野で長年にわたり標準として使われてきた作図ツールです。Visio 2013 以降のデフォルトファイル形式は **`.vsdx`** であり、ページ、マスター、ShapeSheet セル、テーマなどの XML パーツを格納した Open Packaging Conventions 準拠の ZIP アーカイブとなっています。関連する拡張子には `.vssx`（ステンシル）、`.vstx`（テンプレート）、マクロ有効形式の `.vsdm` があります。それ以前のバージョンではバイナリ形式の **`.vsd`** や、Visio 2003–2010 の XML 形式である **`.vdx`** が使われていました。

`.vsdx` は ZIP 内に格納されたプレーンな XML であるため、Visio 本体がなくてもファイルの読み取り、生成、変換が可能です。このリストでは、それを実用的に行うためのツール、仕様書、図形リソースをまとめています。

本リストは VSDX.ai および LayerBack の開発チームがメンテナンスしています。私たちが開発したツールには ⭐ を付け、他の代替ツールと並んで同じ形式・同じ基準で掲載しています。

凡例：💲 有料または商用製品（無料枠がある場合を含む） · ⭐ 本リストのメンテナが開発したツール

Awesome Visio は、VSDX.ai（公式サイト：[vsdx.ai](https://vsdx.ai/ja)）および LayerBack チームがメンテナンスする Visio と `.vsdx` の厳選リソース集です。`.vsdx` 形式の仕様、各言語向けライブラリ、変換・閲覧・編集ツール、ベンダー公式およびコミュニティ製ステンシル、コードからの作図手法、ならびにネイティブ `.vsdx` 出力に対応した AI ツールを収録しています。便利なツールの追加やリンク切れの修正は Issue や PR で歓迎しています。投稿前に末尾の [コントリビューション](#コントリビューション) をご確認ください。内容は CC0 ライセンスで公開されています。

## 目次

- [Microsoft 公式リソース](#microsoft-公式リソース)
  - [製品とドキュメント](#製品とドキュメント)
  - [ファイル形式](#ファイル形式)
  - [プログラミングと自動化](#プログラミングと自動化)
- [ライブラリ](#ライブラリ)
  - [Python](#python)
  - [.NET と PowerShell](#net-と-powershell)
  - [Java](#java)
  - [JavaScript と TypeScript](#javascript-と-typescript)
  - [C、C++、Rust、Go と PHP](#ccrustgo-と-php)
- [変換ツール](#変換ツール)
  - [デスクトップとコマンドライン](#デスクトップとコマンドライン)
  - [オンライン変換ツール](#オンライン変換ツール)
- [ビューアとエディタ](#ビューアとエディタ)
- [ステンシル、テンプレート、アイコン](#ステンシルテンプレートアイコン)
  - [ベンダー公式ステンシル](#ベンダー公式ステンシル)
  - [コミュニティ製ステンシル](#コミュニティ製ステンシル)
  - [Visio ステンシルなしのアイコンセット](#visio-ステンシルなしのアイコンセット)
  - [ステンシル作成ツール](#ステンシル作成ツール)
- [Diagram-as-Code から Visio への変換](#diagram-as-code-から-visio-への変換)
- [Visio 出力に対応した AI ツール](#visio-出力に対応した-ai-ツール)
- [アドインと開発者ツール](#アドインと開発者ツール)
- [連携ツール](#連携ツール)
- [書籍、ブログ、コミュニティ](#書籍ブログコミュニティ)
- [関連リスト](#関連リスト)

## Microsoft 公式リソース

### 製品とドキュメント

- [Microsoft Visio](https://www.microsoft.com/en-us/microsoft-365/visio) - Visio Plan 1、Plan 2、およびデスクトップアプリの製品ホームです。💲
- [Visio in Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/visio/visio-in-microsoft-365) - 多くの Microsoft 365 サブスクリプションに付属する軽量な Web 版 Visio です。
- [Visio support](https://support.microsoft.com/en-us/visio) - 公式ヘルプ、使い方記事、およびトレーニング資料です。
- [Create a Data Visualizer diagram](https://support.microsoft.com/en-us/office/create-a-data-visualizer-diagram-17211b46-d144-4ca2-9ea7-b0f48f0ae0a6) - Excel テーブルから Visio 上でフローチャート、組織図、スイムレーン図を生成する手順です。
- [Create Azure diagrams in Visio](https://support.microsoft.com/office/efbb25e7-c80e-42e1-b1ad-7ef630ff01b7) - 20 種類以上のステンシルを備えた組み込みの Azure 図テンプレートの案内です。
- [Microsoft Visio 2013 Viewer](https://www.microsoft.com/en-us/download/details.aspx?id=35811) - Internet Explorer 内で動作する `.vsdx`、`.vsd`、`.vdx` 向けの無料 ActiveX ビューアです。現在の Windows 環境では用途が限られます。

### ファイル形式

- [Introduction to the Visio file format (.vsdx)](https://learn.microsoft.com/en-us/office/client-developer/visio/introduction-to-the-visio-file-formatvsdx) - パッケージ構造、パーツ、およびリレーションシップの概要です。
- [Manipulate the Visio file format programmatically](https://learn.microsoft.com/en-us/office/client-developer/visio/how-to-manipulate-the-visio-file-format-programmatically) - System.IO.Packaging を用いて `.vsdx` パッケージを読み書きする手順の解説です。
- [Visio file format reference](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-file-format-reference) - `.vsdx` パッケージ内の XML 要素のリファレンスです。
- [Schema map (Visio XML)](https://learn.microsoft.com/en-us/office/client-developer/visio/schema-mapvisio-xml) - Visio 2013 ファイル形式の XSD スキーマ定義です。
- [MS-VSDX: Visio Graphics Service VSDX File Format](https://learn.microsoft.com/en-us/openspecs/sharepoint_protocols/ms-vsdx/50c23601-c943-4ff2-b4a1-02445f52daf0) - `.vsdx` 形式の正式な公開仕様書です。
- [Visio ShapeSheet reference](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-shapesheet-reference) - `.vsdx` 内の XML に直接対応するセル、関数、行、およびセクションのリファレンスです。
- [Open the ShapeSheet](https://learn.microsoft.com/en-us/office/client-developer/visio/open-the-shapesheet-for-a-shape-page-or-document) - すべての Visio 図形の背後にある数式エンジン ShapeSheet を学ぶための入門ガイドです。
- [ECMA-376 (Office Open XML)](https://ecma-international.org/publications-and-standards/standards/ecma-376/) - `.vsdx` の基盤となっている Open Packaging Conventions 標準規格です。

### プログラミングと自動化

- [Visio developer documentation](https://learn.microsoft.com/en-us/office/client-developer/visio/visio-home) - Visio クライアント開発、ファイル形式、ShapeSheet ドキュメントの総合ハブです。
- [Visio JavaScript API overview](https://learn.microsoft.com/en-us/office/dev/add-ins/visio/visio-overview) - SharePoint Online に埋め込まれた Visio 図面向けの Office アドイン API です。
- [Visio JavaScript API reference](https://learn.microsoft.com/en-us/javascript/api/visio) - `Visio` 名前空間の完全なリファレンスです。
- [Office Add-ins platform](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins) - Web ベースの Office アドイン構築に関する総合ドキュメントです。
- [Office Add-in samples](https://github.com/OfficeDev/Office-Add-in-samples) - Office アドインプラットフォームの公式コードサンプル集です。
- [Visio VBA reference](https://learn.microsoft.com/en-us/office/vba/api/overview/visio) - VBA および COM オートメーション向けの Visio オブジェクトモデルです。デスクトップ版 Visio が必要です。
- [Visio Application object](https://learn.microsoft.com/en-us/office/vba/api/visio.application) - VBA、C#、PowerShell、Python から利用される COM オブジェクトモデルのエントリポイントです。
- [Visio solutions in Visual Studio (VSTO)](https://learn.microsoft.com/en-us/visualstudio/vsto/visio-solutions) - デスクトップ版 Visio 向けの VSTO アドインを構築するガイドです。
- [Visio 2013 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=36825) - Visio 2013 ソリューション向けのドキュメント、サンプル、ヘッダー、および Event Monitor などのツール群です。
- [Open XML SDK](https://github.com/dotnet/Open-XML-SDK) - Office Open XML パッケージ向けの Microsoft 製 .NET SDK で、`.vsdx` の低レベルなパーツやリレーションシップ操作に便利です。

## ライブラリ

### Python

- [vsdx](https://github.com/dave-howard/vsdx) - `.vsdx` の図形、テキスト、コネクタの読み書きや、Jinja テンプレートからのファイル生成を行えます。Visio 不要で動作します。
- [libvisio-ng](https://github.com/yeager/libvisio-ng) - `.vsdx` と `.vsd` ファイルを解析して SVG に変換します。vsdview ビューアから抽出されたライブラリです。
- [pywin32](https://github.com/mhammond/pywin32) - COM 経由でデスクトップ版 Visio を操作する際によく使われる Windows 向け Python 拡張です。Windows と Visio が必要です。
- [visioplot](https://github.com/jchliao/visioplot) - Matplotlib の図を Office と相性の良い SVG として書き出し、`.vsdx` に変換します。VSDX 出力には Windows と Visio が必要です（中国語ドキュメント）。
- [Aspose.Diagram for Python via .NET](https://products.aspose.com/diagram/python-net/) - Visio なしで Visio 形式の作成、編集、変換を行えます。💲

### .NET と PowerShell

- [VisioAutomation](https://github.com/saveenr/VisioAutomation) - デスクトップ版 Visio を自動化するための実績ある .NET ライブラリおよび PowerShell コマンドレットです。
- [VisioBot3000](https://github.com/MikeShepard/VisioBot3000) - オートメーション経由で Visio 図面を構築するための PowerShell DSL です。Visio が必要です。
- [NetOffice](https://github.com/netoffice/NetOffice) - Visio を含む Office オートメーション向けのバージョン非依存 .NET ラッパーです。2020 年以降メンテナンスされていません。
- [Aspose.Diagram for .NET](https://products.aspose.com/diagram/net/) - Visio なしで VSD、VSDX、VDX などの読み書き、レンダリング、変換を行えます。💲

### Java

- [Apache POI](https://poi.apache.org/components/diagram/) - `.vsdx` 向けの XDGF コンポーネントと従来の `.vsd` 向けの HDGF を備えています。読み取り中心の実装です。
- [Aspose.Diagram for Java](https://products.aspose.com/diagram/java/) - Visio ファイルを作成、編集、変換するための Java API です。💲

### JavaScript と TypeScript

- [ooxml](https://github.com/ChristopherVR/ooxml) - Visio ドキュメント API と、React、Vue、Angular、Svelte、Solid、バニラ JS 向けの組み込みビューアを備えたローカルファーストな OOXML エンジンです。
- [vsdx-kit](https://github.com/TopLocalAI/vsdx-kit) - ⭐ Visio やブラウザを使わずに JSON または draw.io ファイルから接着コネクタ付きのネイティブ `.vsdx` を生成できます。自動レイアウト、CLI、ローカル MCP サーバーを備えています。
- [ts-visio](https://github.com/zimmermanw84/ts-visio) - TypeScript から `.vsdx` ファイルを生成できます。
- [vsdx-js](https://github.com/jgreywolf/vsdx-js) - `.vsdx` ファイルを解析して JavaScript オブジェクトに変換します。
- [cytoscape-vsdx](https://github.com/ShanteshSindgi/cytoscape-vsdx) - Cytoscape.js のグラフ（ノード、エッジ、グループ、スタイル）をブラウザ上で `.vsdx` にエクスポートします。
- [JointJS+ Visio plugin](https://docs.jointjs.com/learn/features/export-import/visio) - `.vsdx` を JointJS の図にインポートし、JointJS のキャンバスを `.vsdx` としてエクスポートできます。💲
- [Syncfusion Diagram Visio import and export](https://ej2.syncfusion.com/documentation/diagram/visio) - Syncfusion ダイアグラムコンポーネント向けの実験的な VSDX インポート・エクスポート機能です。💲
- [Aspose.Diagram for Node.js via Java](https://products.aspose.com/diagram/nodejs-java/) - Visio ファイル向けの Node.js API です。💲

### C、C++、Rust、Go と PHP

- [libvisio](https://github.com/LibreOffice/libvisio) - LibreOffice や Inkscape で使われている、`.vsd`、`.vdx`、`.vsdx` をインポートする Document Liberation Project の C++ ライブラリです。
- [MisterDiagram](https://github.com/MisterDiagram/MisterDiagram) - `.vsdx` と ShapeSheet の読み書き・描画を行うクリーンルーム実装の Rust コアで、CLI と MCP サーバーを備えています。ベータ版です。
- [libvisio-rs](https://github.com/yeager/libvisio-rs) - `.vsdx` と `.vsd` を解析して SVG に変換する Rust ライブラリです。
- [vsdx-go](https://github.com/wijnberg-net/vsdx-go) - `.vsdx` ファイルの読み取り、編集、書き込みを行う Go ライブラリです。
- [PhpDiagram](https://github.com/PHPOffice/PhpDiagram) - PHPOffice による図面ファイルの読み書き用ピュア PHP ライブラリです。2019 年以降メンテナンスされていません。

## 変換ツール

### デスクトップとコマンドライン

- [LibreOffice headless conversion](https://help.libreoffice.org/latest/en-US/text/shared/guide/start_parameters.html) - `soffice --headless --convert-to pdf` により、Visio なしで任意の OS 上で `.vsd` や `.vsdx` を PDF、SVG、PNG に変換できます。
- [libvisio2svg](https://github.com/kakwa/libvisio2svg) - 埋め込み EMF 図形を含め、Visio 図面やステンシル（VSD、VSS）を SVG に変換するライブラリおよび CLI ツールです。
- [weasyvsdx](https://github.com/grigoriev/weasyvsdx) - HTML から PDF への出力時に VSDX や VSD 図面をベクター SVG として描画する WeasyPrint プラグインです。
- [bpmn-to-visio](https://github.com/Mgabr90/bpmn-to-visio) - 外部依存なしのピュア Python で BPMN 2.0 XML を `.vsdx` に変換します。
- [svg2vsdx_gui](https://github.com/kinglonh/svg2vsdx_gui) - SVG ファイルを `.vsdx` に変換する Windows 用 GUI です（中国語ドキュメント）。現在は非アクティブです。
- [Visio-Export-Pages-To-Docs](https://github.com/saveenr/Visio-Export-Pages-To-Docs) - 複数ページの Visio 文書を 1 ページ 1 ファイルに分割する CLI です。Visio が必要です。
- [VSDtoVSDX-Converter](https://github.com/jprtf/VSDtoVSDX-Converter) - Visio 経由で従来の `.vsd` ファイルを `.vsdx` へ一括変換する PowerShell GUI です。
- [visio2img](https://github.com/visio2img/visio2img) - Visio 経由で `.vsd` や `.vsdx` のページを画像として書き出す Python CLI です。2018 年以降メンテナンスされていません。

### オンライン変換ツール

- [VSDX.ai 無料ツール](https://vsdx.ai/ja/tools?utm_source=awesome-visio) - ⭐ アカウント不要・ブラウザ完結で `.vsdx` を draw.io や PNG / SVG に無料変換でき、有料の Mermaid・PlantUML・Excel から Visio への変換ツールも備えています。
- [draw.io import formats](https://www.drawio.com/docs/manual/import/import-formats/) - draw.io は `.vsdx`、`.vsd`、`.vssx` ステンシルのインポートに対応しており、VSDX エクスポート（ベータ表記）も可能です。
- [SVG to Visio](https://mcmarius11.github.io/svgtovisio/) - SVG や draw.io ファイルを接着コネクタ付きの `.vsdx`、`.drawio`、`.fodg` に変換するクライアントサイド変換ツールです。（[ソースコード](https://github.com/McMarius11/svgtovisio)）
- [Aspose Visio Converter](https://products.aspose.app/diagram/conversion) - Visio ファイルを PDF、画像、HTML、SVG、PPTX、DRAWIO などに変換できる無料 Web アプリです。
- [GroupDocs Viewer for VSDX](https://products.groupdocs.app/viewer/vsdx) - 無料のオンライン VSDX ビューアおよびレンダラーです。
- [AnyConv](https://anyconv.com/vsdx-converter/) - VSDX を PDF や画像形式に変換できる無料のオンラインコンバータです。
- [Convertio](https://convertio.co/vsdx-converter/) - VSDX から PDF や画像形式へ変換できる汎用オンラインコンバータです。制限付きの無料枠があります。
- [Zamzar](https://www.zamzar.com/convert/vsdx-to-pdf/) - VSDX から PDF へのオンライン変換サービスです。制限付きの無料枠があります。

## ビューアとエディタ

- [vsdx.app](https://vsdx.app?utm_source=awesome-visio) - ⭐ `.vsdx` と `.vsd` の閲覧・編集・保存に対応し、Finder の Quick Look プレビューも備えたネイティブ macOS アプリです。閲覧は無料です。💲
- [LayerBack VSDX Viewer](https://layerback.com/ja/vsdx-viewer?utm_source=awesome-visio) - ⭐ Visio なしでブラウザ上から `.vsdx` ファイルを開ける無料オンラインビューアです。
- [draw.io](https://www.drawio.com/) - Visio ファイルのインポート・エクスポートに対応した無料・オープンソースの Web / デスクトップ作図エディタです。（[デスクトップ版](https://github.com/jgraph/drawio-desktop)）
- [LibreOffice Draw](https://www.libreoffice.org/) - libvisio 経由で `.vsd`、`.vdx`、`.vsdx` を開けますが、Visio 形式での再保存はできません。（[制限事項](https://help.libreoffice.org/latest/en-US/text/shared/guide/ms_import_export_limitations.html)）
- [Inkscape](https://inkscape.org/) - libvisio 経由で Visio ファイルをインポートできるベクターエディタです。
- [vsdview](https://github.com/yeager/vsdview) - Linux 向けの GTK4 / Adwaita 製 `.vsdx`・`.vsd` ビューアです。
- [VSD Viewer](https://nektony.com/products/visio-viewer-mac) - レイヤーや図形データ表示に対応した Mac 向け VSD・VDX・VSDX ビューアです。無料ダウンロードと有料の Pro 版があります。💲
- [Aspose Visio Viewer](https://products.aspose.app/diagram/viewer) - VSD、VSDX、VDX、およびステンシルファイルを画像として描画する無料 Web アプリです。
- [Lucidchart](https://www.lucidchart.com/) - Visio ファイルのインポートに対応した Web 作図ツールです。💲（[インポートガイド](https://help.lucid.co/hc/en-us/articles/16389149809428)）
- [Miro](https://help.miro.com/hc/en-us/articles/11842818558738) - `.vsdx` 図面をボードとしてインポートできるオンラインホワイトボードです。💲
- [SmartDraw](https://www.smartdraw.com/) - Visio のインポート・エクスポートに対応した Web 作図ツールです。💲
- [EdrawMax](https://www.edrawsoft.com/edraw-max/) - Visio のインポート・エクスポートに対応したクロスプラットフォーム作図エディタです。💲
- [ConceptDraw DIAGRAM](https://www.conceptdraw.com/) - Visio 形式の読み込みと保存に対応した Mac / Windows 向け作図エディタです。💲
- [OmniGraffle](https://www.omnigroup.com/omnigraffle) - Visio ファイルのインポート・エクスポートに対応した Mac / iPad 向け作図アプリです。💲
- [Visual Paradigm Online](https://online.visual-paradigm.com/) - Visio インポートと無料枠を備えた Web 作図スイートです。💲

## ステンシル、テンプレート、アイコン

### ベンダー公式ステンシル

- [VisioCafe](https://www.visiocafe.com/) - HPE、Dell、NetApp、IBM、Lenovo、富士通などのベンダー公式 Visio ステンシルを集めた歴史ある無料インデックスサイトです。
- [Cisco network topology icons](https://www.cisco.com/c/en/us/about/brand-center/network-topology-icons.html) - Cisco 公式のアイコンおよび Visio ステンシルのダウンロードページです。
- [Fortinet icon library](https://www.fortinet.com/resources/icon-library) - Visio ステンシルを含む Fortinet 公式の製品・サイバーセキュリティアイコン集です。
- [Microsoft 365 architecture icons and templates](https://learn.microsoft.com/en-us/previous-versions/microsoft-365/solutions/architecture-icons-templates) - Microsoft 365 のアイコンセットおよび Visio テンプレートです（アーカイブページ）。
- [ShapeSource](https://www.shapesource.com/) - Palo Alto Networks や Juniper など多くの無料ステンシルを含む、Visimation によるメーカー製 Visio ステンシルライブラリです。💲
- [Paul Herber Software](https://www.paulherber.co.uk/) - 電気、電子回路、UML、空調（HVAC）などの Visio 図形セットで、一部の図形は無料で提供されています。💲

### コミュニティ製ステンシル

- [Microsoft Integration and Azure Stencils Pack](https://github.com/sandroasp/Microsoft-Integration-and-Azure-Stencils-Pack-for-Visio) - Azure、BizTalk、Power Platform、Microsoft 365 向けの大規模な Visio ステンシルパックです。
- [visioStencils](https://github.com/bhdicaire/visioStencils) - 4,000 点以上の IT インフラ図形、ステンシル、アイコンのコレクションです。
- [VisioStencils](https://github.com/girlpunk/VisioStencils) - 600 個以上の `.vss` および `.vssx` ステンシルファイル集です。
- [Visio-Azure](https://github.com/xeeva/Visio-Azure) - 1,259 個のアイコン、接続ポイント、図形データを備えた検索可能な Azure ステンシルセットです。
- [Visio-Cisco](https://github.com/xeeva/Visio-Cisco) - メートル法版と米国単位版を備えた検索可能な非公式 Cisco ステンシルセットです。
- [C4 model Visio stencil](https://github.com/pihalve/c4model-visio-stencil) - C4 ソフトウェアアーキテクチャ図向けの図形セットです。
- [ntwrk-clean-and-flat](https://github.com/DukeNuke3D/ntwrk-clean-and-flat) - クリーンでフラットな 2D ネットワークシンボルと Visio ステンシルです。
- [VMware Visio stencils](https://github.com/uldyssian-sh/vmware-visio-stencils) - インフラ構成図向けの 100 点以上の VMware 製品アイコンとテンプレートです。
- [Microsoft Fabric Visio stencils](https://github.com/PatrickGallucci/fabric-stencils) - Microsoft Fabric アーキテクチャ図向けの 90 点以上の図形セットです。
- [Unifi Visio Stencils](https://github.com/brightmethods/Unifi-Visio-Stencils) - 主要な Ubiquiti UniFi ハードウェア向けのステンシルです。
- [Ubiquiti Visio stencils](https://github.com/digiservnet/ubiquiti-visio-stencils) - 各ポートに接続ポイントを備えた Ubiquiti デバイスのステンシルです。
- [Domotic Visio stencils](https://github.com/rrobinet/Visio-Stencils) - ホームオートメーションおよび電気配線向けのステンシルです。
- [IEC 61131-3 Visio stencils](https://github.com/avafab/IEC-61131-3-Visio-stencils) - PLC ソフトウェア設計向けの Sequential Function Chart（SFC）図形セットです。
- [DMN Visio stencils](https://github.com/debasishdalui/dmn-visio-stencils) - Decision Model and Notation（DMN 1.0）向けの図形セットです。
- [bootstrap-visio-templates](https://github.com/henck/bootstrap-visio-templates) - Bootstrap の Web UI モックアップ向けの設定可能なステンシルです。現在は非アクティブです。
- [Shapes-n-stencils](https://github.com/Visio-Resources/Shapes-n-stencils) - サードパーティ製 Visio ステンシルとアドオンをカテゴリ別にまとめたリンク集です。

### Visio ステンシルなしのアイコンセット

- [Azure architecture icons](https://learn.microsoft.com/en-us/azure/architecture/icons/) - SVG 形式の公式 Azure アイコン集です。Microsoft から Visio ステンシルとして配布される予定はありませんが、そのまま Visio へドラッグ＆ドロップできます。
- [AWS architecture icons](https://aws.amazon.com/architecture/icons/) - 公式の AWS アイコンパッケージおよび PowerPoint ツールキットです。Visio ステンシルはありません。
- [Google Cloud icons](https://cloud.google.com/icons) - SVG および PNG 形式の公式 Google Cloud 製品アイコン集です。
- [Microsoft Power Platform icons](https://learn.microsoft.com/en-us/power-platform/guidance/icons) - SVG 形式の公式 Power Platform アイコン集です。
- [Microsoft Fabric icons](https://learn.microsoft.com/en-us/fabric/fundamentals/icons) - SVG 形式の公式 Fabric 製品・アイテムアイコン集です。

### ステンシル作成ツール

- [Visio Stencil Factory](https://github.com/rezanid/visiostencilfactory) - SVG ファイルのフォルダから独自の Visio ステンシルを構築できます。
- [visio-stencil-creator](https://github.com/hoveytechllc/visio-stencil-creator) - Visio なしで PNG 画像から `.vssx` ステンシルを作成でき、Docker イメージとしても利用できます。現在は非アクティブです。

## Diagram-as-Code から Visio への変換

Visio にはネイティブのテキスト記法がありません。以下はコードと `.vsdx` の間をつなぐ実用的なルートです。

- [md2visio](https://github.com/Megre/md2visio) - Markdown 内の Mermaid を `.vsdx` に変換します。
- [mermaid-to-visio](https://github.com/FBklyra/mermaid-to-visio) - レンダリングされた Mermaid をクライアントサイドでネイティブの `.vsdx` 図形とコネクタに変換します。ライブラリ、CLI、Web エディタを備えています。
- [convert2mermaid](https://github.com/jgreywolf/convert2mermaid) - `.vsdx`、draw.io、Excalidraw、PlantUML の図を Mermaid へ変換する CLI および npm パッケージです。
- [draw.io diagrams from code](https://www.drawio.com/docs/tutorials/diagrams-from-code/) - draw.io における Mermaid、PlantUML、CSV インポートの概要で、インポート後に VSDX へエクスポートできます。
- [Mermaid](https://mermaid.js.org/) - 広く使われている Markdown 風の作図記法で、通常は draw.io または上記の変換ツール経由で Visio に取り込みます。
- [PlantUML](https://plantuml.com/) - テキストベースの UML 記法で、draw.io に挿入してから VSDX へエクスポートできます。
- [Graphviz](https://graphviz.org/) - DOT 言語による定番のグラフレイアウトエンジンで、出力した SVG を Visio にインポートできます。
- [D2](https://d2lang.com/) - SVG エクスポートに対応したモダンな作図スクリプト言語です。
- [Diagrams](https://diagrams.mingrammer.com/) - クラウドアーキテクチャ図を画像として描画する Python 製の Diagram-as-Code ツールです。
- [Kroki](https://kroki.io/) - Mermaid、PlantUML、Graphviz、D2 などを SVG や PNG にレンダリングする HTTP API です。（[ソースコード](https://github.com/yuzutech/kroki)）

## Visio 出力に対応した AI ツール

- [VSDX.ai](https://vsdx.ai/ja?utm_source=awesome-visio) - ⭐ テキスト、ドキュメント、データ、作図コード、または画像から接着コネクタ付きのネイティブ `.vsdx` を出力する AI Visio ジェネレーターです。REST API とリモート MCP サーバー（`https://vsdx.ai/api/mcp`）を提供しています。💲
- [LayerBack](https://layerback.com/ja?utm_source=awesome-visio) - ⭐ 図の画像や PDF を編集可能な VSDX、PPTX、draw.io、または SVG として再構築します。API と [MCP サーバー](https://github.com/TopLocalAI/layerback-mcp)を提供しています。💲
- [Visiomaster](https://github.com/Rss3208/Visiomaster) - 画像内のフローチャートや論文図版を編集可能な `.vsdx` として再構築する Codex ツールキットです。Windows と Visio が必要です（中国語ドキュメント）。
- [codex-visio-paper-figure-skill](https://github.com/pengjunchi0/codex-visio-paper-figure-skill) - COM 経由で研究論文の図版画像をネイティブの Visio 図形として再構築する Codex スキルです。Visio が必要です（中国語ドキュメント）。
- [visio-com-skill](https://github.com/WUXU-Tech/visio-com-skill) - ローカルの Visio COM オートメーションを通じて編集可能な `.vsdx` を生成する Codex スキルです。Windows と Visio が必要です。
- [Visio Scientific Figures](https://github.com/ywq177995212697-droid/visio-scientific-figures) - YAML 仕様から研究用図版をレイアウト品質チェック付きで `.vsdx` として描画するエージェントスキルです。Visio が必要です。
- [VSDX Trace](https://github.com/ZJUZhiyuCai/vsdx-trace) - スクリーンショットや科学図版をトレースして編集可能な `.vsdx` に変換するエージェントスキルおよび Python ツールチェーンです。
- [CVPR-Figure](https://github.com/ChizkiyahuOhayon/CVPR-Figure) - 仕様記述やモデルコードから AI 国際会議向けの論文図版を生成し、Visio や PowerPoint で編集できます。

## アドインと開発者ツール

- [SvgPublish](https://unmanagedvisio.com/products/svg-publish/) - 図面をインタラクティブな HTML / SVG ページとして公開できる Visio アドインです。💲（[リリース一覧](https://github.com/nbelyh/svgpublish-releases)）
- [Extended Visio Addin Project](https://github.com/nbelyh/VisioPanelAddinVSTO) - 作業ウィンドウ、リボン、インストーラーを備えた VSTO または COM Visio アドイン用の Visual Studio テンプレートです。
- [visiowings](https://github.com/twobeass/visiowings) - VS Code 上でライブ同期しながら Visio の VBA モジュールを編集できます。
- [VisioImportExportVba](https://github.com/nbelyh/VisioImportExportVba) - バージョン管理向けに Visio VBA コードをインポート・エクスポートするツールです。現在は非アクティブです。
- [ShapeSheetWatch](https://github.com/nbelyh/ShapeSheetWatch) - シェイプ開発者向けの追加機能を備えた ShapeSheet ウォッチウィンドウです。現在は非アクティブです。

## 連携ツール

- [FlowToVisio](https://github.com/LinkeD365/FlowToVisio) - Power Automate のクラウドフローや Logic Apps を Visio 図面としてドキュメント化する XrmToolBox ツールです。
- [StartLeft](https://github.com/iriusrisk/startleft) - Visio 図面など複数のソースから Open Threat Model ファイルを生成します。

## 書籍、ブログ、コミュニティ

- [Visualize Complex Processes with Microsoft Visio](https://www.packtpub.com/product/visualize-complex-processes-with-microsoft-visio/9781837631926) - David Parker と Senaj Lelic による、Visio でのプロセス図および BPMN 解説書です（Packt、2023 年）。💲
- [bVisual](https://bvisual.net/) - 長年 Visio MVP を務める David Parker のブログで、ShapeSheet、データリンク、ファイル形式を深く解説しています。
- [Visio Guy](https://www.visguy.com/) - 定番の Visio 活用術、無料シェイプ、ShapeSheet テクニックを紹介するサイトです。
- [VisGuy forum](https://visguy.com/vgforum/) - Visio 開発や ShapeSheet の質問が活発に交わされているフォーラムです。
- [Unmanaged Visio](https://unmanagedvisio.com/) - Nikolay Belyh による Visio アドイン、Web ツール、技術記事のサイトです。
- [Microsoft Visio blog](https://techcommunity.microsoft.com/category/microsoft-visio/blog/visioblog) - Microsoft Tech Community 上の公式製品アナウンスブログです。
- [Stack Overflow visio tag](https://stackoverflow.com/questions/tagged/visio) - Visio の自動化やファイル形式に関するプログラミング Q&A です。
- [r/visio](https://www.reddit.com/r/visio/) - Visio ユーザー向けの Reddit コミュニティです。

## 関連リスト

- [awesome-visio by bhdicaire](https://github.com/bhdicaire/awesome-visio) - 図形やステンシルを中心にまとめられた先行コミュニティの Visio リソース集です。
- [awesome-diagramming](https://github.com/shubhamgrg04/awesome-diagramming) - ソフトウェア作図ツール全般のリストです。

## コントリビューション

コントリビューションを歓迎します。まずは[コントリビューションガイドライン](CONTRIBUTING.md)をお読みください。本リストは [CC0](LICENSE) の下で公開されています。

*Microsoft、Visio、および Microsoft 365 は Microsoft グループ企業の商標です。本リストは Microsoft と提携しておらず、Microsoft による承認や後援を受けたものでもありません。その他の製品名はすべて各所有者の商標です。*
