---
title: Aspose.Tasks に PDF として保存
linktitle: Aspose.Tasks に PDF として保存
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してプロジェクト ファイルを PDF に変換する方法を学びます。効率的に変換するための簡単な手順。
type: docs
weight: 17
url: /ja/java/project-file-operations/save-as-pdf/
---
## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用してプロジェクトを PDF として保存するプロセスを説明します。 Aspose.Tasks を使用すると、プロジェクト ファイルを PDF 形式に効率的に変換して、互換性と共有の容易さを確保できます。手順を詳しく見てみましょう。
## 前提条件
開始する前に、次のものが揃っていることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks ライブラリをダウンロードしてインストールします。ダウンロードリンクが見つかります[ここ](https://releases.aspose.com/tasks/java/).
3. プロジェクト ファイル: PDF に変換するプロジェクト ファイル (HomeMovePlan.mpp など) を用意します。

## パッケージのインポート
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## ステップ 1: 入力プロジェクト ファイルを読み取る
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
必ず交換してください`"Your Data Directory"`プロジェクト ファイルを含むデータ ディレクトリへのパスを置き換えます。
## ステップ 2: プロジェクトを PDF として保存する
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
このコード スニペットは、プロジェクトを「Project5.pdf」という名前の PDF ファイルとして保存します。
## ステップ 3: 内容をセル サイズに合わせる
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
ここでは、コンテンツ、タイムスケール、プレゼンテーション形式の調整など、PDF を保存するためのオプションを設定します。
## ステップ 4: 凡例を非表示にする
```java
o.setLegendOnEachPage(false);
```
この手順により、PDF の各ページの凡例が非表示になります。
## ステップ 5: 適用されたオプションを使用してプロジェクトを保存する
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
最後に、このコードは、オプションが適用されたプロジェクトを PDF ファイルに保存します。

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用してプロジェクトを PDF として保存する方法を学びました。これらの簡単な手順に従うことで、プロジェクト ファイルを効率的に変換して、共有や配布を簡単に行うことができます。
## よくある質問
### Q: Aspose.Tasks は Java のすべてのバージョンと互換性がありますか?
A: はい、Aspose.Tasks は JDK 6 以降の Java バージョンをサポートしています。
### Q: PDF 出力の外観をカスタマイズできますか?
A: もちろんです！ Aspose.Tasks には、要件に応じて PDF 出力をカスタマイズするためのさまざまなオプションが用意されています。
### Q: Aspose.Tasks は他のファイル形式の変換をサポートしていますか?
A: はい、Aspose.Tasks は MPP、XML、XLSX などを含む幅広いファイル形式をサポートしています。
### Q: Aspose.Tasks の試用版はありますか?
 A: はい、Aspose.Tasks の無料トライアルを次のサイトから入手できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks のサポートはどこで入手できますか?
 A: サポートと支援が必要な場合は、次のサイトにアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).