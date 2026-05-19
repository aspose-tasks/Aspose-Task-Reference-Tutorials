---
date: 2026-01-15
description: Aspose.Tasks for Java を使用して、プロジェクトにリソースを追加し、リソース データを更新し、プロジェクトを MPP
  として保存する方法を学びます。
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java を使用してプロジェクトにリソースを追加する
url: /ja/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用してプロジェクトにリソースを追加する

## Introduction
このハンズオンチュートリアルでは、Aspose.Tasks Java API を使って **プロジェクトにリソースを追加する方法** をプログラムで実装する方法を学びます。既存の MS Project XML ファイルを読み込み、新しいリソースを挿入し、プロパティを更新し、最後に **プロジェクトを MPP として保存** します。これにより、Java ベースのレポート作成や自動化ツールに組み込める明確で再利用可能なパターンが手に入ります。

## Quick Answers
- **“add resource to project” とは何ですか？** Microsoft Project ファイル内に新しいリソースエントリ（人物、機器、材料など）を作成します。  
- **どのライブラリがこれを処理しますか？** Aspose.Tasks for Java – Microsoft Project のインストールは不要です。  
- **ライセンスは必要ですか？** 開発目的なら無料トライアルで動作しますが、製品環境では商用ライセンスが必要です。  
- **XML を MPP に変換できますか？** はい – XML ファイルを読み込み、`project.save(...)` を使って **プロジェクトを MPP として保存** します。  
- **必要な Java バージョンは？** Java 6 以降（Java 8 以上推奨）。

## What is “add resource to project”?
プロジェクトにリソースを追加するとは、MS Project ファイルの Resources テーブルに新しい行を挿入することです。この行には、名前、コストレート、グループ、タスクが後で参照できるカスタムフィールドなどの情報が格納されます。

## Why use Aspose.Tasks for Java?
- **Microsoft Project への依存が不要** – 任意の OS や CI サーバーで動作します。  
- **完全な忠実度** – フォーマット間の変換時にもすべてのネイティブ Project 機能が保持されます。  
- **豊富な API** – タスク、リソース、カレンダーなどを読み書き・操作できます。

## Prerequisites
開始する前に以下を用意してください。

1. Java Development Kit (JDK) 8 以上がインストールされていること。  
2. Aspose.Tasks for Java ライブラリ – [こちら](https://releases.aspose.com/tasks/java/) からダウンロード。  
3. Java の構文と Maven/Gradle プロジェクト設定に関する基本的な知識。

## Import Packages
Java ソースファイルに必要な Aspose.Tasks クラスを追加します。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Set Up Your Data Directory
ソース XML と生成される MPP ファイルの保存先ディレクトリを定義します。

```java
String dataDir = "Your Data Directory";
```

## Step 2: Specify Input and Output Files
変換したい XML ファイル（**convert XML to MPP**）と、新しいリソースを含む対象 MPP ファイルを指定します。

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Step 3: Load the Project
XML ソースから `Project` オブジェクトを作成します。

```java
Project project = new Project(file);
```

## Step 4: Add a Resource and Set Attributes
ここで **add resource to project** を実行し、レートやグループを設定します。

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Pro tip:* ループ内で `add` 呼び出しを繰り返すことで、**複数のリソースを一度に更新** できます。

## Step 5: Save the Project
最後に **save project as MPP** して変更を永続化します。

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusion
**プロジェクトにリソースを追加する方法** を学び、プロパティを更新し、Aspose.Tasks for Java を使って **プロジェクトを MPP として保存** できるようになりました。この手法は、レポート自動化パイプラインや大量リソースのインポート、デスクトップアプリケーションなしで MS Project ファイルを操作するあらゆるシナリオに最適です。

## Frequently Asked Questions

**Q1: Aspose.Tasks for Java を使って同じプロジェクト内の複数リソースを更新できますか？**  
A: はい、`project.getResources()` をイテレートするか、`add` を繰り返し呼び出して各リソースのフィールドを設定します。

**Q2: Aspose.Tasks は MS Project 以外のファイル形式もサポートしていますか？**  
A: もちろんです – XML、MPP、MPX、Primavera など多数の形式に対応しています。

**Q3: Aspose.Tasks はさまざまな Java バージョンと互換性がありますか？**  
A: ライブラリは Java 6 以降で動作し、Java 8 以上を推奨しています。

**Q4: MS Project ファイルで他の操作も可能ですか？**  
A: はい、タスク、カレンダー、割り当て、カスタムフィールドの読み書きやレポート生成も行えます。

**Q5: Aspose.Tasks の追加サポートやヘルプはどこで得られますか？**  
A: コミュニティ支援と公式サポートは [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) をご利用ください。

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}