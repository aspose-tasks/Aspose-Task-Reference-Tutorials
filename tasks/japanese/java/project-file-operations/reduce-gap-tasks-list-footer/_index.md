---
date: 2026-05-20
description: Aspose.Tasks for Java を使用して、プロジェクトを PDF にエクスポートし、フッターの余白を減らし、プロジェクトを画像として保存する方法を学びます。MS
  Project のレイアウトを簡単に最適化できます。
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Aspose.TasksでプロジェクトをPDFにエクスポートし、タスク一覧とフッターの間の余白を縮小する
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.TasksでプロジェクトをPDFにエクスポートし、タスク一覧とフッターの間の余白を縮小する
url: /ja/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TasksでプロジェクトをPDFにエクスポートし、タスク一覧とフッター間の余白を削減する

## はじめに  
このチュートリアルでは、Microsoft Project ファイルにおけるタスク一覧とフッター間の不要な余白を削減しながら、**プロジェクトを PDF にエクスポートする方法**を学びます。ガイドの最後までに、Aspose.Tasks for Java を使用して、コンパクトなレイアウトのクリーンな PDF、PNG 画像、HTML ページを生成できるようになります。ステップバイステップでプロセスを進め、なぜこれがプロフェッショナルなレポート作成に重要なのかをご確認ください。

## クイック回答  
- **“export project to PDF” とは何ですか？** MPP ファイルをタスク、タイムライン、書式設定を保持した PDF ドキュメントに変換します。  
- **なぜフッターの余白を削減するのですか？** 余白を小さくすることで、特に印刷物やウェブ表示のドキュメントで、よりタイトでプロフェッショナルな外観のレポートが作成できます。  
- **プロジェクトを画像として保存できますか？** はい – Aspose.Tasks は PNG、JPEG、その他の画像形式をサポートしています。  
- **特別なライセンスが必要ですか？** 無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **必要な Java バージョンは？** 現在の Aspose.Tasks ライブラリは Java 8 以上で動作します。  

## “export project to PDF” とは何ですか？  
プロジェクトを PDF にエクスポートすると、内部の MPP 構造がポータブルドキュメントに変換され、Microsoft Project がなくても任意のデバイスで開くことができます。ステータスレポートやステークホルダーへの更新、プロジェクト計画のアーカイブ共有に最適です。元のレイアウト、色、タスク階層を保持し、PDF が元ファイルと同一に見えるようにします。

## なぜフッターの余白を削減するのか？  
デフォルトのフッター余白は不要な空白を生み、ページ分割の問題やバランスの取れない外観を引き起こすことがあります。余白を削減することで、コンテンツがページを効率的に利用でき、最終的な PDF や画像の可読性が向上します。レイアウトがタイトになることで総ページ数も減少し、印刷コストの削減や画面上のナビゲーションが改善されます。

## タスク一覧とフッター間の余白を削減する方法は？  
`setReduceFooterGap` はエクスポート時のフッター間隔を制御する Boolean プロパティです。  
Aspose.Tasks は画像、PDF、HTML の保存操作に対して `setReduceFooterGap(true)` オプションを提供します。このフラグを有効にすると、エンジンは最終タスク行とページフッター間のスペースを圧縮します。true に設定すると、レンダラーは余白を自動的にトリミングし、タスクデータを切り落とすことなく、よりクリーンなページレイアウトを実現します。

## Aspose.Tasks でプロジェクトを画像として保存  
`ImageSaveOptions` はプロジェクトを画像ファイルにレンダリングする方法を構成します。  
`ImageSaveOptions` クラスを使用すると、スケジュールのスナップショットを PNG、JPEG、BMP としてエクスポートできます。`setReduceFooterGap(true)` も有効にすると、生成された画像はコンパクトな PDF レイアウトを反映し、プレゼンテーションやダッシュボード向けのクリーンなビジュアルを提供します。

## Java プロジェクトの PDF エクスポート  
以下のセクションでは、MPP ファイルの読み込みから 3 つの異なる形式での保存まで、完全な **java project export** ワークフローを順に解説します。

## 前提条件
開始する前に、以下の前提条件が揃っていることを確認してください:
1. Java Development Kit (JDK) – バージョン 8 以上。  
2. Aspose.Tasks for Java ライブラリ – [here](https://releases.aspose.com/tasks/java/) からダウンロードしてください。

## パッケージのインポート  
コーディング部分に入る前に、必要なパッケージをインポートしましょう:

```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 手順 1: データディレクトリへのパスを指定  
```java
String dataDir = "Your Data Directory";
```  
必ず `"Your Data Directory"` を、Microsoft Project ファイル（この例では `HomeMovePlan.mpp`）が配置されている実際のデータディレクトリへのパスに置き換えてください。

## 手順 2: MPP ファイルを読み込む  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
このコード行は `HomeMovePlan.mpp` という名前の Microsoft Project ファイルを読み込みます。

## 手順 3: ImageSaveOptions を設定 (プロジェクトを画像として保存)  
`ImageSaveOptions` はプロジェクトを画像ファイルにレンダリングする方法を構成します。  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
画像保存オプションを構成し、`ReduceFooterGap` を `true` に設定してタスク一覧とフッター間の余白を削減します。

## 手順 4: 画像として保存  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
構成したオプションでプロジェクトを画像として保存します。

## 手順 5: PdfSaveOptions を設定 (プロジェクトを PDF にエクスポート)  
`PdfSaveOptions` はプロジェクトを PDF 形式でエクスポートする際の設定を指定します。  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
`ReduceFooterGap` を `true` に設定することを確認しながら、PDF 保存オプションを定義します。

## 手順 6: PDF として保存  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
構成したオプションでプロジェクトを PDF として保存します。

## 手順 7: HtmlSaveOptions を設定  
`HtmlSaveOptions` はプロジェクトを HTML に変換する際のスタイルやレイアウトオプションを制御します。  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
`ReduceFooterGap` を `true` に設定して HTML 保存オプションを指定します。

## 手順 8: HTML として保存  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
構成したオプションでプロジェクトを HTML ファイルとして保存します。

## 一般的な使用例とヒント  
- **ステークホルダー向けレポート:** フッター余白を削減した PDF にエクスポートし、レポートを簡潔で印刷に適した形に保ちます。  
- **ダッシュボードのスナップショット:** Power BI や Confluence 用に迅速なビジュアルが必要な場合は画像エクスポートを使用します。  
- **ウェブ公開:** HTML エクスポートはインタラクティブ性を保持し、イントラネットポータルに直接埋め込むことができます。  
- **プロのコツ:** 非常に大規模なプロジェクトの場合、`ImageSaveOptions` の `Resolution` を 300 dpi に上げると、クリアさを保ちつつ余白削減の効果を活かせます。

## よくある質問 (追加)

**Q: フッター余白を削減するとページ分割にどのような影響がありますか？**  
A: 各ページ下部の空白が最小化され、1 ページに収まるタスク数が増え、総ページ数が減少します。

**Q: 同じ余白削減設定を単一ページのみに適用できますか？**  
A: はい、`ImageSaveOptions` で `setRenderToSinglePage(true)` を設定すれば、ページ分割を制御しつつ余白を削減できます。

**Q: `setReduceFooterGap` オプションは他の出力形式でも利用可能ですか？**  
A: 現在は PNG、PDF、HTML エクスポートでサポートされています。他の形式の場合は手動でレイアウト調整が必要になることがあります。

**Q: プロジェクトにカスタムフィールドが含まれている場合、保持されますか？**  
A: エクスポート時にすべてのカスタムフィールドは保持されます。レイアウト調整は間隔にのみ影響し、データには影響しません。

**Q: ライブラリは大規模プロジェクトを効率的に処理できますか？**  
A: Aspose.Tasks はデータをストリーミングし、数百ページに及ぶ MPP ファイルを全体をメモリに読み込まずに処理できます。ただし、高解像度画像をエクスポートする際は十分なヒープ領域を確保してください。

---

**最終更新日:** 2026-05-20  
**テスト環境:** Aspose.Tasks 24.11 for Java  
**作者:** Aspose

## 関連チュートリアル

- [プロジェクトを画像として保存 – 24bppRgb 形式 (Aspose.Tasks)](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [プロジェクトをテンプレート、CSV、テキストとして保存 (Aspose.Tasks for Java)](/tasks/java/project-file-operations/save-csv-text-template/)
- [MPP ファイルの作成方法 – 空のプロジェクトを MPP 形式で作成・保存 (Aspose.Tasks)]( /tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}