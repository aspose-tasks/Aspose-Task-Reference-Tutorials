---
date: 2025-12-21
description: Aspose.Tasks for Java を使用して、プロジェクトをテンプレートとして保存する方法、MPP を CSV にエクスポートする方法、MPP
  をテキストに変換する方法を学びましょう。
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java を使用して、プロジェクトをテンプレート、CSV、テキストとして保存
url: /ja/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspise.Tasks を使用したプロジェクトのテンプレート、CSV、テキストへの保存

## はじめに
このチュートリアルでは、**プロジェクトをテンプレートとして保存する方法**と、Aspose.Tasks ライブラリ for Java を使用して Microsoft Project（MPP）ファイルを CSV およびプレーンテキスト形式にエクスポートする方法を紹介します。再利用可能なプロジェクトテンプレートを作成したい場合や、分析用に CSV レポートを生成したい場合、または統合用にシンプルなテキスト抽出を行いたい場合、以下の手順で迅速かつ効率的に実行できます。

## よくある質問
- **MPPをCSVにエクスポートできますか？** はい、`project.save(..., SaveFileFormat.CSV)`を使用してください。
- **テキストをエクスポートするにはどうすればよいですか？** `SaveFileFormat.TEXT`で保存してください。
- **「プロジェクトをテンプレートとして保存」とは？** 実際の値と基準値を削除した`.mpt`ファイルを作成し、再利用できるようにします。
- **ライセンスは必要ですか？** トライアル版をご利用いただけます。製品版のご利用には商用ライセンスが必要です。
- **必要なJavaバージョンは？** Java 8以降に対応しています。

## 「プロジェクトをテンプレートとして保存」とは？
プロジェクトをテンプレート（`.mpt`）として保存すると、構造、タスク階層、リソース割り当ては保持されますが、実際の開始/終了日やベースラインデータは除去されます。これにより、標準的なプロジェクトレイアウトを複数の新規プロジェクトで再利用できるテンプレートが作成されます。

## Aspose.Tasks for Java を使用する理由
Aspose.Tasks を使用すれば、Microsoft Project をインストールせずに Microsoft Project ファイルを操作できます。**MPP のエクスポート方法**、**テキストへのエクスポート方法**、**MPP から CSV への変換** をすべて純粋な Java コードで実現でき、サーバーサイドの自動化、CI パイプライン、デスクトップユーティリティに最適です。

## 前提条件
開始する前に、以下を確認してください。

1. Java Development Kit (JDK) 8 以上がインストールされていること。  
2. Aspose.Tasks for Java ライブラリをプロジェクトに追加すること。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から。  
3. Java の基本構文と Maven/Gradle のプロジェクト設定に慣れていること。

## パッケージのインポート
最初に、Java ソースファイルで必要なクラスをインポートします:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## プロジェクトを CSV 形式で保存（MPP を CSV にエクスポート）
MPP ファイルを CSV にエクスポートすると、Excel や BI ツールでのデータ分析に便利です。

### ステップ 1: プロジェクトの読み込み
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### ステップ 2: CSV 形式で保存
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## プロジェクトをテキスト形式で保存（テキストのエクスポート方法）
タスク、リソース、割り当て情報をプレーンテキストで取得したい場合は、プロジェクトをテキストファイルとして保存します。

### ステップ 1: プロジェクトの読み込み
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### ステップ 2: テキスト形式で保存
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## プロジェクトをテンプレートとして保存（Java プロジェクトテンプレートの作成）
再利用可能なテンプレートを作成すると、実際の日付やベースラインが除去され、新規プロジェクト用のクリーンな骨格が得られます。

### ステップ 1: プロジェクトの読み込み
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### ステップ 2: テンプレートオプションの設定
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

## よくある問題とヒント
- **File Not Found:** `YourProject.mpp` へのパスが正しいか、絶対パスを使用してください。  
- **License Exceptions:** 有効なライセンスが無い場合、ライブラリは評価モードで動作し、透かしが追加されることがあります。コードの早い段階でライセンスを適用してください（`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`）。  
- **Large Projects:** 非常に大きな MPP ファイルを扱う場合は、JVM のヒープサイズを増やすことを検討してください（例: `-Xmx2g`）で `OutOfMemoryError` を回避できます。

## 結論
**プロジェクトをテンプレートとして保存する方法**、**MPP を CSV にエクスポートする方法**、そして **MPP をテキストに変換する方法** を Aspose.Tasks for Java を使って解説しました。これらの機能により、プロジェクトデータの自動処理、再利用可能なテンプレートの生成、他システムへの統合が、Microsoft Project をインストールせずに実現できます。

## よくある質問

### Q: Aspose.Tasks for Java は複雑なプロジェクトファイルを処理できますか？

A: もちろんです！ Aspose.Tasks for Java は、さまざまな複雑さのプロジェクトを容易に処理でき、Microsoft Project ファイル形式を包括的にサポートしています。

### Q: Aspose.Tasks for Java の試用版はありますか？

A: はい、[こちら](https://releases.aspose.com/) から Aspose.Tasks for Java の無料試用版を入手できます。

### Q: Aspose.Tasks for Java のサポートはどこで受けられますか？

A: Aspose.Tasks for Java に関するご質問やサポートが必要な場合は、[Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) をご覧ください。

### Q: Aspose.Tasks for Java の一時ライセンスを購入できますか？

A: はい、[こちら](https://purchase.aspose.com/temporary-license/)から一時ライセンスをご購入いただけます。これにより、ライブラリの機能を最大限に活用して評価できます。

### Q: Aspose.Tasks for Javaは、さまざまなオペレーティングシステムに対応していますか？

A: はい、Aspose.Tasks for Javaは、Windows、macOS、Linuxなど、さまざまなオペレーティングシステムに対応しています。

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
