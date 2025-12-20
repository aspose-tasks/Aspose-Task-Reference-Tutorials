---
date: 2025-12-20
description: Aspose.Tasks for JavaでPDFをエクスポートする方法を学びましょう。MPPをPDFに変換し、プロジェクトファイルを効率的に保存するシンプルなガイドです。
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.TasksでPDFをエクスポートする方法 – PDFとして保存
url: /ja/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TasksでPDFをエクスポートする方法 – PDFとして保存

## Introduction
このチュートリアルでは、Aspose.Tasks for Javaで**PDFをエクスポートする方法**を示し、プロジェクトをPDFとして保存する手順をご案内します。Aspose.Tasksを使用すると、MPPをPDFに**変換**でき、チームやステークホルダー間での互換性と共有の容易さが確保されます。手順を見ていけば、任意のプロジェクトファイルからすぐに印刷可能なPDFを取得できます。

## Quick Answers
- **Aspose.Tasksで「PDFをエクスポートする」とは何ですか？** プロジェクトファイル（例: MPP）を視覚的レイアウトを保持したPDFドキュメントに変換することを意味します。  
- **どのライブラリバージョンが必要ですか？** `PdfSaveOptions` をサポートする任意の Aspose.Tasks for Java バージョン（最新リリースが推奨）です。  
- **この変換にライセンスは必要ですか？** 開発目的であれば無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **PDFの外観をカスタマイズできますか？** はい、timescale、legends、その他の `PdfSaveOptions` を設定できます。  
- **大規模プロジェクトでも変換は高速ですか？** 通常は数秒で、パフォーマンスはプロジェクトのサイズと選択したオプションに依存します。

## What is “how to export pdf” in the context of Aspose.Tasks?
Aspose.TasksでPDFをエクスポートするとは、`.mpp`、`.xml`、`.xlsx` などのプロジェクトファイルを取得し、設定したガントチャート、タスク使用ビュー、またはその他の表示形式を忠実に再現したPDFを生成することです。これは、レポート作成、文書化、あるいは非技術的なステークホルダーと読み取り専用ビューを共有する際に便利です。

## Why Export Project Files to PDF?
- **ユニバーサルな可読性:** PDFは元のプロジェクトソフトウェアを必要とせず、あらゆるデバイスで閲覧可能です。  
- **プロフェッショナルなプレゼンテーション:** フォーマット、色、レイアウトを保持し、クライアント向けレポートに最適です。  
- **配布の容易さ:** メール、イントラネット、クラウドストレージで共有でき、バージョン管理の懸念がありません。  
- **コンプライアンスとアーカイブ:** PDFは長期保存や規制遵守に最適です。

## Prerequisites
開始する前に、以下が揃っていることを確認してください：

1. **Java Development Kit (JDK):** JDK 8 以上がマシンにインストールされていること。  
2. **Aspose.Tasks for Java ライブラリ:** 公式サイトからライブラリをダウンロードしてください [here](https://releases.aspose.com/tasks/java/)。  
3. **プロジェクトファイル:** 変換対象となる既存のプロジェクトファイル（例: `HomeMovePlan.mpp`）を用意してください。

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
`"Your Data Directory"` を `.mpp` ファイルが存在する絶対パスに置き換えてください。これによりプロジェクトがメモリに読み込まれ、操作やエクスポートが可能になります。

### Step 2: Save the Project as PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
上記の行はシンプルな **プロジェクトをPDFとして保存** 操作を実行し、同じフォルダーに `Project5.pdf` を作成します。

### Step 3: Fit Contents to Cell Size (Advanced PDF Save Options)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
ここではレイアウト制御のために **pdf save options** を使用する例を示します：

- `setFitContent(true)` はコンテンツをセル幅に合わせます。  
- `setTimescale(Timescale.Months)` はタイムスケールを月単位に変更します。  
- `setPresentationFormat(PresentationFormat.TaskUsage)` はタスク使用ビューを選択します。

### Step 4: Hide Legends (Cleaner Output)
```java
o.setLegendOnEachPage(false);
```
凡例を無効にすると、特に大規模プロジェクトでPDFがよりコンパクトになります。

### Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
この最終ステップでは、上記で定義したカスタムオプションを使用してPDFを書き出し、ページごとの凡例なしで月単位にスケーリングされたクリーンなドキュメントを生成します。

## Common Issues & Tips
- **ファイルが見つかりません:** `dataDir` がファイルセパレーター（`/` または `\\`）で終わり、正しいディレクトリを指していることを確認してください。  
- **空白ページ:** 選択した `PresentationFormat` が期待するビュー（例: ガント、タスク使用）と一致しているか確認してください。  
- **大きなファイルは時間がかかります:** 非常に大規模なプロジェクトの場合、処理時間短縮のために `o.setFitContent(false)` の設定を検討してください。  

## Frequently Asked Questions

**Q: Aspose.TasksはすべてのJavaバージョンと互換性がありますか？**  
A: はい、Aspose.TasksはJDK 6以降のJavaバージョンをサポートしています。

**Q: PDFの外観をカスタマイズできますか？**  
A: もちろんです！Aspose.Tasksは timescale、凡例の表示/非表示、プレゼンテーション形式など、多数の **pdf save options** を提供しており、PDFをニーズに合わせて調整できます。

**Q: Aspose.Tasksは他のファイル形式への変換もサポートしていますか？**  
A: はい、MPP、XML、XLSX など多数の形式間で変換でき、**convert mpp to pdf** をはじめとしたさまざまな変換に対応する汎用性の高いツールです。

**Q: Aspose.Tasksのトライアル版はありますか？**  
A: はい、[here](https://releases.aspose.com/) から Aspose.Tasks の無料トライアルを入手できます。

**Q: Aspose.Tasksのサポートはどこで受けられますか？**  
A: サポートや質問は公式の [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) をご利用ください。

## Conclusion
このガイドに従うことで、Aspose.Tasks を使用して任意の Java プロジェクトから **PDF をエクスポートする方法** を習得しました。シンプルなワンライン保存から `PdfSaveOptions` を用いた高度なカスタマイズまで、これらの手法を活用して、レポートやクライアント向けプレゼンテーション、アーカイブ用途に適した洗練された共有可能な PDF を作成してください。

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}