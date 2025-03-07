---
title: Aspose.Tasks に CSV、テキスト、およびテンプレートとして保存
linktitle: Aspose.Tasks に CSV、テキスト、およびテンプレートとして保存
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して Microsoft Project ファイルを CSV、テキスト、およびテンプレート形式で保存する方法を学びます。
weight: 16
url: /ja/java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks に CSV、テキスト、およびテンプレートとして保存

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して、CSV、テキスト、テンプレートなどのさまざまな形式でプロジェクト ファイルを保存する方法を説明します。 Aspose.Tasks は、開発者が Microsoft Project をインストールしなくても Microsoft Project ファイルを操作できるようにする強力な Java ライブラリです。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java Development Kit (JDK) がシステムにインストールされています。
2.  Aspose.Tasks for Java ライブラリがダウンロードされ、Java プロジェクトに構成されます。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
3. Java プログラミング言語の基本的な知識。

## パッケージのインポート
まず、必要なパッケージを Java ファイルにインポートする必要があります。
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## プロジェクトを CSV として保存
プロジェクトを CSV として保存する手順を詳しく見てみましょう。
### ステップ 1: プロジェクトをロードする
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### ステップ 2: CSV として保存
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## プロジェクトをテキストとして保存
プロジェクトをテキストとして保存する方法は次のとおりです。
### ステップ 1: プロジェクトをロードする
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### ステップ 2: テキストとして保存
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## プロジェクトをテンプレートとして保存
プロジェクトをテンプレートとして保存するには、次の手順を実行します。
### ステップ 1: プロジェクトをロードする
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### ステップ 2: テンプレート オプションを設定する
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### ステップ 3: テンプレートとして保存
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project ファイルを CSV、テキスト、およびテンプレートとして保存する方法を学習しました。これらの簡単な手順を使用すると、さまざまな形式のプロジェクト ファイルを効率的に管理でき、Java 開発者としての生産性が向上します。
## よくある質問
### Q: Aspose.Tasks for Java は複雑なプロジェクト ファイルを処理できますか?
A: もちろんです！ Aspose.Tasks for Java は、さまざまな複雑さのプロジェクトを簡単に処理でき、Microsoft Project ファイル形式の包括的なサポートを提供します。
### Q: Aspose.Tasks for Java の試用版はありますか?
 A: はい、Aspose.Tasks for Java の無料トライアルを次のサイトから入手できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java のサポートはどこで見つけられますか?
 A: にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15) Aspose.Tasks for Java に関するサポートや質問については、こちらをご覧ください。
### Q: Aspose.Tasks for Java の一時ライセンスを購入できますか?
 A: はい、次から一時ライセンスを購入できます。[ここ](https://purchase.aspose.com/temporary-license/)を使用すると、ライブラリの可能性を最大限に評価できます。
### Q: Aspose.Tasks for Java はさまざまなオペレーティング システムと互換性がありますか?
A: はい、Aspose.Tasks for Java は、Windows、macOS、Linux などのさまざまなオペレーティング システムと互換性があります。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
