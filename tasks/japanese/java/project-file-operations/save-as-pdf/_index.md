---
date: 2026-03-27
description: Aspose.Tasks for Java を使用してプロジェクトを PDF として保存する方法を学び、MPP を PDF に変換し、プロジェクトファイルを効率的にエクスポートするシンプルなガイドです。
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.TasksでプロジェクトをPDFとして保存する方法 – エクスポートガイド
url: /ja/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でプロジェクトを PDF として保存する方法 – エクスポートガイド

## Introduction
このチュートリアルでは、Aspose.Tasks for Java を使用して **プロジェクトを PDF として保存する方法** をご紹介します。1 行の変換から高度な PDF カスタマイズまで、あらゆる手順を丁寧に解説しますので、MPP（または他のサポート形式）を洗練された共有可能な PDF ドキュメントに変換できます。簡単な印刷レポートが必要な場合でも、完全にスタイリングされたガントチャートが必要な場合でも、この手順で迅速に実現できます。

## Quick Answers
- **「PDF エクスポート」とは Aspose.Tasks で何を意味しますか？** プロジェクト ファイル（例: MPP）を、視覚レイアウトを保持した PDF ドキュメントに変換することを指します。  
- **必要なライブラリ バージョンはどれですか？** `PdfSaveOptions` をサポートしている任意の Aspose.Tasks for Java バージョン（最新リリースを推奨）です。  
- **この変換にライセンスは必要ですか？** 開発目的であれば無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **PDF の外観をカスタマイズできますか？** はい – `PdfSaveOptions` でタイムスケール、凡例、その他の設定が可能です。  
- **大規模プロジェクトでも変換は高速ですか？** 通常は数秒で完了します。パフォーマンスはプロジェクトのサイズと選択したオプションに依存します。

## What is “save project as pdf” in the context of Aspose.Tasks?
Aspose.Tasks でプロジェクトを PDF として保存することは、`.mpp`、`.xml`、`.xlsx` などのプロジェクト ファイルを読み込み、ガントチャート、タスク使用ビュー、または構成した任意の表示形式を忠実に再現した PDF を生成することです。レポート作成、文書化、技術的でないステークホルダーへの読み取り専用ビュー共有に便利です。

## Why Export Gantt Chart to PDF?
- **汎用的な可読性:** PDF は元のプロジェクト ソフトウェアが不要で、あらゆるデバイスで開くことができます。  
- **プロフェッショナルな提示:** 色、フォント、レイアウトを保持し、クライアント向けレポートに最適です。  
- **簡単な配布:** メール、イントラネット、クラウドストレージを介して共有でき、バージョン管理の問題がありません。  
- **コンプライアンスとアーカイブ:** 長期保存や規制遵守に PDF が最適です。

## Prerequisites
開始する前に、以下を用意してください。

1. **Java Development Kit (JDK):** JDK 8 以降がインストールされていること。  
2. **Aspose.Tasks for Java ライブラリ:** 公式サイトからライブラリをダウンロードしてください [here](https://releases.aspose.com/tasks/java/)。  
3. **プロジェクト ファイル:** 変換対象となる既存のプロジェクト ファイル（例: `HomeMovePlan.mpp`）を用意してください。

## Import Packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Step‑by‑Step Guide

### Step 1: Read the Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
`"Your Data Directory"` を、`.mpp` ファイルが格納されている絶対パスに置き換えてください。これによりプロジェクトがメモリに読み込まれ、操作やエクスポートが可能になります。

### Step 2: Save the Project as PDF (Basic Conversion)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
上記のコードはシンプルな **プロジェクトを PDF として保存** 操作を実行し、同じフォルダーに `Project5.pdf` を作成します。

### Step 3: Fit Contents to Cell Size (Advanced PDF Save Options)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
ここではレイアウト制御のために **pdf save options** を使用する例を示します:
- `setFitContent(true)` はコンテンツをセル幅に合わせて強制的に収めます。  
- `setTimescale(Timescale.Months)` はタイムスケールを月単位に変更します。  
- `setPresentationFormat(PresentationFormat.TaskUsage)` はタスク使用ビューを選択します。

### Step 4: Hide Legends (Cleaner Output)
```java
o.setLegendOnEachPage(false);
```
凡例を無効にすると、特に大規模プロジェクトの場合に PDF がコンパクトになります。

### Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
この最終ステップで、上記で定義したカスタム オプションを使用して PDF を書き出し、ページごとの凡例なしで月単位にスケーリングされたクリーンなドキュメントが生成されます。

## Export Gantt Chart to PDF – Custom Styling
ガントチャートだけを特定の外観でエクスポートしたい場合は、`PresentationFormat` を `GanttChart` に設定し、`setBarColor` や `setShowCriticalTasks` などの追加オプションを調整します。この方法により、**ガントチャートを PDF にエクスポート** する際にビジュアル要素をフルコントロールできます。

## Common Issues & Tips
- **ファイルが見つからない:** `dataDir` がファイル区切り文字（`/` または `\\`）で終わり、正しいディレクトリを指していることを確認してください。  
- **空白ページが生成される:** 選択した `PresentationFormat` が期待するビュー（例: ガント、タスク使用）と一致しているか確認してください。  
- **大容量ファイルは時間がかかる:** 非常に大きなプロジェクトの場合は `o.setFitContent(false)` を設定して処理時間を短縮することを検討してください。

## Frequently Asked Questions

**Q: Aspose.Tasks はすべての Java バージョンと互換性がありますか？**  
A: はい、Aspose.Tasks は JDK 6 以降のすべての Java バージョンをサポートしています。

**Q: PDF 出力の外観をカスタマイズできますか？**  
A: もちろんです！Aspose.Tasks はタイムスケール、凡例の表示可否、プレゼンテーション形式など、多数の **pdf save options** を提供しており、PDF をニーズに合わせて調整できます。

**Q: Aspose.Tasks は他のファイル形式への変換もサポートしていますか？**  
A: はい、MPP、XML、XLSX など多数の形式間で変換可能です。これにより、**MPP を PDF に変換** するだけでなく、さまざまな変換シナリオに対応できます。

**Q: Aspose.Tasks のトライアル版はありますか？**  
A: はい、無料トライアルを [here](https://releases.aspose.com/) から入手できます。

**Q: Aspose.Tasks のサポートはどこで受けられますか？**  
A: サポートや質問は公式 [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) をご利用ください。

## Conclusion
このガイドに従うことで、Aspose.Tasks を使用して任意の Java プロジェクトから **プロジェクトを PDF として保存** する方法をマスターできます。シンプルな 1 行保存から `PdfSaveOptions` を用いた高度なカスタマイズまで、レポート作成、クライアント向けプレゼンテーション、アーカイブ目的の洗練された共有可能な PDF を簡単に生成できます。

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}