---
title: Aspose.Tasks のタスク リストとフッターの間のギャップを減らす
linktitle: Aspose.Tasks のタスク リストとフッターの間のギャップを減らす
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して MS Project のタスク リストとフッターの間のギャップを減らす方法を学びます。プロジェクトドキュメントのレイアウトを簡単に最適化します。
weight: 10
url: /ja/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のタスク リストとフッターの間のギャップを減らす

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して、Microsoft Project ファイルのタスク リストとフッターの間のギャップを減らす方法について詳しく説明します。これらの手順に従うことで、プロジェクト ドキュメントのレイアウトを簡単に最適化できるようになります。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリをダウンロードしてプロジェクトに組み込みます。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).

## パッケージのインポート
コーディング部分に入る前に、必要なパッケージをインポートしましょう。
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
## ステップ 1: データ ディレクトリへのパスを指定する
```java
String dataDir = "Your Data Directory";
```
必ず交換してください`"Your Data Directory"`Microsoft Project ファイルが保存されている実際のデータ ディレクトリへのパス (`HomeMovePlan.mpp`この例では) が見つかります。
## ステップ 2: MPP ファイルを読み取る
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
このコード行は、という名前の Microsoft Project ファイルを読み取ります。`HomeMovePlan.mpp`.
## ステップ 3: ImageSaveOptions を設定する
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
画像保存オプションの構成、設定`ReduceFooterGap`に`true`タスクリストとフッターの間のギャップを減らすため。
## ステップ 4: 画像として保存
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
構成されたオプションを使用して、プロジェクトを画像として保存します。
## ステップ 5: PdfSaveOptions を設定する
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
PDF 保存オプションを定義し、必ず設定してください`ReduceFooterGap`に`true`.
## ステップ 6: PDF として保存
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
設定したオプションを使用してプロジェクトを PDF として保存します。
## ステップ 7: HtmlSaveOptions を設定する
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); //trueに設定
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
HTML 保存オプションの指定、設定`ReduceFooterGap`に`true`.
## ステップ 8: HTML として保存する
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
構成されたオプションを使用して、プロジェクトを HTML ファイルとして保存します。

## 結論
結論として、Microsoft Project ファイル内のタスク リストとフッターの間のギャップを減らすことは、Aspose.Tasks for Java を使用する簡単なプロセスです。このチュートリアルで概説されている手順に従うことで、プロジェクト ドキュメントのレイアウトを効率的に最適化できます。

## よくある質問

### Q: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか?

A: Aspose.Tasks は Microsoft Project 2003 ～ 2019 形式をサポートしており、さまざまなバージョン間の互換性を確保しています。

### Q: プロジェクト ドキュメントのフッターの外観をカスタマイズできますか?

A: はい、Aspose.Tasks には、ギャップの削減やコンテンツの配置の調整など、フッターの外観をカスタマイズするための広範なオプションが用意されています。

### Q: Aspose.Tasks は、PNG、PDF、HTML 以外の形式でのプロジェクトの保存をサポートしていますか?

A: はい、Aspose.Tasks は、XLSX、XML、MPP などの幅広い形式をサポートしています。

### Q: Aspose.Tasks の試用版はありますか?

 A: はい、Aspose.Tasks の無料試用版を次のサイトからダウンロードできます。[ここ](https://releases.aspose.com/).

### Q: Aspose.Tasks の使用中に問題が発生した場合、どこでサポートを受けられますか?

 A: Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
