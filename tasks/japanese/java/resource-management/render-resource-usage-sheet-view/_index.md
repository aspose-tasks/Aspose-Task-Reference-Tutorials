---
date: 2026-01-15
description: Aspose.Tasks for Java を使用して、プロジェクトを PDF として保存し、MS Project のリソース使用状況ビューとシートビューをレンダリングする方法を学びましょう。ステップバイステップのガイドに従って、プロジェクトを簡単に
  PDF にエクスポートできます。
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: プロジェクトをPDFとして保存 – Aspose.Tasksでリソース使用状況とシートビューをレンダリング
url: /ja/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクトをPDFとして保存 – Aspose.Tasksでリソース使用状況とシートビューをレンダリング

## はじめに
このチュートリアルでは、Microsoft Project ファイルのリソース使用状況ビューとシートビューをレンダリングしながら **save project as PDF** を行う方法を学びます。ステークホルダー向けの印刷可能なレポートを作成したい場合や、MPP ファイルを汎用的に閲覧できる形式に変換したい場合でも、Aspose.Tasks for Java を使用すれば、Microsoft Project のインストールは不要で手順はシンプルです。

## クイック回答
- **“save project as pdf” は何をしますか？** プロジェクトファイル（MPP）を選択したビューを保持した PDF ドキュメントに変換します。  
- **どのビューをエクスポートできますか？** リソース使用状況、シート、ガント、タスク使用状況など多数のビューに対応しています。  
- **PDF のタイムスケールを変更できますか？** はい、Days、ThirdsOfMonths、Months などを選択できます。  
- **Microsoft Project のインストールは必要ですか？** いいえ、Aspose.Tasks は単体で動作します。  
- **本番環境でライセンスは必要ですか？** はい、トライアル以外の使用には商用ライセンスが必要です。

## “save project as PDF” とは？
プロジェクトを PDF として保存すると、選択した Project ビューの静的で高解像度な表現が生成されます。クライアントへの共有、アーカイブ、印刷など、元のプロジェクトファイルを公開せずに情報を提供したいシーンに最適です。

## なぜ Aspose.Tasks を使ってプロジェクトを PDF にエクスポートするのか？
- **外部依存なし** – Java が動作する任意のプラットフォームで利用可能。  
- **細かな制御** – ビュー、タイムスケール、レイアウトを自由に選択できる。  
- **高忠実度** – PDF は元の Project ビューと同一の外観を再現。  
- **自動化対応** – CI パイプライン、レポートサービス、バッチ変換などに組み込み可能。

## 前提条件
作業を始める前に、以下を用意してください。

1. **Java Development Kit (JDK)** – 最新バージョンを推奨。  
2. **Aspose.Tasks for Java** – [download page](https://releases.aspose.com/tasks/java/) からダウンロード。

## パッケージのインポート
まず、必要なクラスを Java プロジェクトにインポートします。

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## ステップバイステップガイド

### ステップ 1: ソースプロジェクトを読み込む
変換したい MPP ファイルをロードします。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### ステップ 2: 必要なタイムスケールで SaveOptions を定義 (Export Project to PDF)
PDF エクスポートオプションを設定し、目的のタイムスケールを指定します。  
*ここでは **Days** を例として使用しています。*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### ステップ 3: PresentationFormat を ResourceUsage に設定
レンダリングしたいビューを選択します。この例では **Resource Usage** ビューです。

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### ステップ 4: プロジェクトを保存 (MPP から PDF へ変換)
変換を実行し、PDF ファイルを生成します。

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### ステップ 5: 他のタイムスケール設定でビューをレンダリング (Change Timescale PDF)
前の手順を繰り返し、**ThirdsOfMonths** や **Months** など異なるタイムスケールの PDF を作成します。

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## よくある問題と解決策
- **ファイルが見つからないエラー** – `dataDir` が正しいフォルダーを指しているか、MPP ファイル名が正確か確認してください。  
- **PDF が空白になる** – `PresentationFormat` がデータを含むビュー（例: ResourceUsage）に設定されているか確認してください。  
- **タイムスケールが正しく反映されない** – 各 `project.save()` の前に必ず `options.setTimescale()` を呼び出してください。

## よくある質問

### Aspose.Tasks は Resource Usage と Sheet 以外のビューもレンダリングできますか？
Aspose.Tasks はガントチャート、タスク使用状況、カレンダーなど、さまざまなビューのレンダリングに対応しています。

### Aspose.Tasks は異なるバージョンの Microsoft Project ファイルに対応していますか？
はい、Aspose.Tasks は MPP、MPT、XML 形式など、幅広い Microsoft Project ファイル形式をサポートしています。

### Aspose.Tasks でレンダリングビューの外観をカスタマイズできますか？
もちろんです。Aspose.Tasks はレンダリングビューの外観やレイアウトを細かくカスタマイズできる豊富なオプションを提供しています。

### Aspose.Tasks の利用に Microsoft Project のインストールは必要ですか？
いいえ、Aspose.Tasks は単体のライブラリであり、動作に Microsoft Project のインストールは不要です。

### Aspose.Tasks ユーザー向けのテクニカルサポートはありますか？
はい、Aspose.Tasks ユーザーは [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) からテクニカルサポートを受けられます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-01-15  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作成者:** Aspose