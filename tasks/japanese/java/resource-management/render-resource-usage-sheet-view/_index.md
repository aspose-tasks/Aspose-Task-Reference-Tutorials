---
date: 2026-06-15
description: Aspose.Tasks for Java を使用して、MPP を PDF に変換し、Resource Usage と Sheet ビューをレンダリングする方法を学びましょう。タイムスケールを設定し、詳細な
  PDF レポートを簡単に生成するステップバイステップのガイドに従ってください。
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: MPP を PDF に変換し、Resource Usage ビューをレンダリング – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MPP を PDF に変換し、Resource Usage ビューをレンダリング – Aspose.Tasks
url: /ja/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP を PDF に変換し、リソース使用状況ビューをレンダリング – Aspose.Tasks

このチュートリアルでは、Microsoft Project ファイルのリソース使用状況ビューとシートビューをレンダリングしながら、**MPP を PDF に変換する方法**を学びます。Java 用 Aspose.Tasks を使用すると、サーバー上で Microsoft Project が不要になり、MPP ファイルから PDF レポートを高速かつ信頼性の高い方法で作成できます。また、**タイムスケールの設定方法**も示し、出力がレポート要件に合致するようにします。

## クイック回答
- **Aspose.Tasks は何をしますか？** Microsoft Project (MPP) ファイルを読み取り、変更し、変換します。MS Project のインストールは不要です。  
- **1 行のコードで MPP を PDF に変換できますか？** はい – プロジェクトをロードし、SaveOptions を設定して `save` を呼び出すだけです。  
- **サポートされているタイムスケールは何ですか？** Days、ThirdsOfMonths、Months。  
- **本番環境でライセンスが必要ですか？** トライアル以外の導入には商用ライセンスが必要です。  
- **このライブラリは Java 8+ と互換性がありますか？** もちろんです – Java 8 以降をサポートしています。

## convert mpp to pdf とは何ですか？
*Convert mpp to pdf* は、Microsoft Project (.mpp) ファイルを取得し、プロジェクトの表、スケジュール、チャート、リソース割り当てを忠実に再現した Portable Document Format (PDF) バージョンを生成するプロセスを指します。生成された PDF は、受信者のマシンに Microsoft Project をインストールせずに、簡単に共有、印刷、アーカイブできます。

## Aspose.Tasks でプロジェクトを PDF に変換する理由は？
Aspose.Tasks は **50 以上の入力および出力フォーマット** をサポートし、ファイル全体をメモリにロードせずに数百ページに及ぶプロジェクトをレンダリングでき、RAM 使用量を最大 70 % 削減します。PDF 出力は表、チャート、リソース割り当てを保持するため、ステークホルダーへの配布やアーカイブに最適です。

## 前提条件
1. **Java Development Kit (JDK)** – マシンに Java 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java** – 最新の JAR を [download page](https://releases.aspose.com/tasks/java/) からダウンロードしてください。

## Aspose.Tasks for Java を使用して mpp を pdf に変換する方法は？
ソースの MPP ファイルをロードし、目的のタイムスケールを設定し、プレゼンテーション形式を **ResourceUsage** に設定して、結果を PDF として保存します。このエンドツーエンドのフローは数回の API 呼び出しだけで済み、一般的なプロジェクトサイズでは 1 秒未満で完了します。

### 手順 1: ソースプロジェクトの読み取り
`Project` クラスは、メモリにロードされた Microsoft Project ファイルを表し、そのデータと構造へのアクセスを提供します。  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### 手順 2: 必要な TimeScale 設定で SaveOptions を定義する
`SaveOptions` はプロジェクトの保存方法を構成し、タイムスケールなどのフォーマット固有の設定を指定できます。  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### 手順 3: プレゼンテーション形式を ResourceUsage に設定する
`PresentationFormat` は、出力ドキュメントにレンダリングされる Project ビュー（例: ResourceUsage）を決定します。  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### 手順 4: プロジェクトを PDF として保存する
`project.save` は、提供された `SaveOptions` を使用してプロジェクトをファイルに書き込み、最終的な PDF を生成します。  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### 手順 5: 他の TimeScale 設定用にビューをレンダリングする
前の手順を繰り返し、`TimeScale` の値を変更して追加のタイムスケールビューをレンダリングします。  
```java
// Save the Project
project.save(dataDir + days, options);
```

### 手順 6: オプション – バッチで複数プロジェクトを変換する
多数のファイルに対して **project を pdf に変換** する必要がある場合、上記のロジックを *.mpp* ファイルのディレクトリを反復処理するループ内に配置します。このアプローチは、最小限のコード変更で大量に **ms project pdf** ファイルを保存します。  
以下のコードは、目的の設定で MPP ファイルを PDF に変換する完全な例を示しています。  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## よくある問題と解決策
- **PDF のフォントが欠如** – 必要なフォントがサーバーにインストールされていることを確認するか、`PdfSaveOptions` で埋め込んでください。  
- **大規模プロジェクトファイルで OutOfMemoryError が発生** – `LoadOptions.setLoadAllResources(false)` を使用して、リソースをオンデマンドでロードします。  
- **タイムスケールのレンダリングが正しくない** – `options.setTimeScale(TimeScale.Days)`（または他の列挙型）が目的の粒度と一致していることを確認してください。

## よくある質問

**Q: Aspose.Tasks は Resource Usage と Sheet 以外のビューもレンダリングできますか？**  
A: はい、Gantt Chart、Task Usage、Calendar など多数のビューもサポートしています。

**Q: Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: もちろんです – Project 2000 から Project 2021 までの MPP、MPT、XML フォーマットを処理します。

**Q: レンダリングされたビューの外観をカスタマイズできますか？**  
A: はい、`PdfSaveOptions` と `PresentationOptions` を通じて色、フォント、列レイアウトを変更できます。

**Q: Aspose.Tasks は Microsoft Project のインストールが必要ですか？**  
A: いいえ、スタンドアロンのライブラリであり、任意の Java 対応環境で動作します。

**Q: 技術サポートはどこで受けられますか？**  
A: サポートは [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/) で利用可能です。

**最終更新日:** 2026-06-15  
**テスト環境:** Aspose.Tasks 24.12 for Java  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks でリソース使用状況とシートビューをレンダリング](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Aspose.Tasks で PDF をエクスポートする方法 – PDF として保存](/tasks/java/project-file-operations/save-as-pdf/)
- [Java 用 Aspose.Tasks で MPP ファイルを作成する方法](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}