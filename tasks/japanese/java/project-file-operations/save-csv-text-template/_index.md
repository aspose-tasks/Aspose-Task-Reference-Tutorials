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

## Introduction
このチュートリアルでは、**プロジェクトをテンプレートとして保存する方法**と、Aspose.Tasks ライブラリ for Java を使用して Microsoft Project（MPP）ファイルを CSV およびプレーンテキスト形式にエクスポートする方法を紹介します。再利用可能なプロジェクトテンプレートを作成したい場合や、分析用に CSV レポートを生成したい場合、または統合用にシンプルなテキスト抽出を行いたい場合、以下の手順で迅速かつ効率的に実行できます。

## Quick Answers
- **Can I export MPP to CSV?** Yes – use `project.save(..., SaveFileFormat.CSV)`.  
- **How to export text?** Save with `SaveFileFormat.TEXT`.  
- **What does “save project as template” do?** It creates an `.mpt` file that strips actual and baseline values, ready for reuse.  
- **Do I need a license?** A trial is available; a commercial license is required for production.  
- **Which Java version is required?** Java 8+ is supported.

## What is “save project as template”?
プロジェクトをテンプレート（`.mpt`）として保存すると、構造、タスク階層、リソース割り当ては保持されますが、実際の開始/終了日やベースラインデータは除去されます。これにより、標準的なプロジェクトレイアウトを複数の新規プロジェクトで再利用できるテンプレートが作成されます。

## Why use Aspose.Tasks for Java?
Aspose.Tasks を使用すれば、Microsoft Project をインストールせずに Microsoft Project ファイルを操作できます。**MPP のエクスポート方法**、**テキストへのエクスポート方法**、**MPP から CSV への変換** をすべて純粋な Java コードで実現でき、サーバーサイドの自動化、CI パイプライン、デスクトップユーティリティに最適です。

## Prerequisites
開始する前に、以下を確認してください。

1. Java Development Kit (JDK) 8 以上がインストールされていること。  
2. Aspose.Tasks for Java ライブラリをプロジェクトに追加すること。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から。  
3. Java の基本構文と Maven/Gradle のプロジェクト設定に慣れていること。

## Import Packages
最初に、Java ソースファイルで必要なクラスをインポートします:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Save Project as CSV (Export MPP to CSV)
MPP ファイルを CSV にエクスポートすると、Excel や BI ツールでのデータ分析に便利です。

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Save as CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Save Project as Text (How to Export Text)
タスク、リソース、割り当て情報をプレーンテキストで取得したい場合は、プロジェクトをテキストファイルとして保存します。

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Save as Text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Save Project as Template (Create Project Template Java)
再利用可能なテンプレートを作成すると、実際の日付やベースラインが除去され、新規プロジェクト用のクリーンな骨格が得られます。

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Set Template Options
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Step 3: Save as Template
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Common Issues & Tips
- **File Not Found:** `YourProject.mpp` へのパスが正しいか、絶対パスを使用してください。  
- **License Exceptions:** 有効なライセンスが無い場合、ライブラリは評価モードで動作し、透かしが追加されることがあります。コードの早い段階でライセンスを適用してください（`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`）。  
- **Large Projects:** 非常に大きな MPP ファイルを扱う場合は、JVM のヒープサイズを増やすことを検討してください（例: `-Xmx2g`）で `OutOfMemoryError` を回避できます。

## Conclusion
**プロジェクトをテンプレートとして保存する方法**、**MPP を CSV にエクスポートする方法**、そして **MPP をテキストに変換する方法** を Aspose.Tasks for Java を使って解説しました。これらの機能により、プロジェクトデータの自動処理、再利用可能なテンプレートの生成、他システムへの統合が、Microsoft Project をインストールせずに実現できます。

## FAQ's
### Q: Can Aspose.Tasks for Java handle complex project files?
A: Absolutely! Aspose.Tasks for Java can handle projects of varying complexity with ease, providing comprehensive support for Microsoft Project file formats.  
### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can get a free trial of Aspose.Tasks for Java from [here](https://releases.aspose.com/).  
### Q: Where can I find support for Aspose.Tasks for Java?
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any assistance or queries regarding Aspose.Tasks for Java.  
### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
A: Yes, you can purchase a temporary license from [here](https://purchase.aspose.com/temporary-license/), allowing you to evaluate the full potential of the library.  
### Q: Is Aspose.Tasks for Java compatible with different operating systems?
A: Yes, Aspose.Tasks for Java is compatible with various operating systems, including Windows, macOS, and Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

---