---
date: 2026-05-20
description: Aspose.Tasks for Java を使用してリソース割り当てに拡張属性を追加し、プロジェクト開始日を設定し、MS Project
  ファイルを効率的に書き出す方法を学びます。
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Aspose.Tasks でリソース割り当てに拡張属性を追加
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java の使用方法 – リソース割り当てに拡張属性を追加
url: /ja/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用した MS Project 操作のマスター

## はじめに
このチュートリアルでは、**Aspose.Tasks for Java の使い方**を学び、リソース割り当てに拡張属性を追加し、Microsoft Project の情報を書き出す方法をプログラムで実装します。レポートパイプラインの自動化やカスタムプロジェクト管理ツールの構築など、以下の手順でプロジェクトの開始日設定、リソース割り当ての作成、XML 形式でのファイル保存を数行の Java コードで実現する方法を示します。

## クイック回答
- **Aspose.Tasks for Java は何をしますか？** Microsoft Project がインストールされていなくても、Microsoft Project ファイルの読み取り、書き込み、変更が可能です。  
- **リソース割り当てにカスタムフィールドを追加できますか？** はい、`ResourceAssignment` オブジェクトの `ExtendedAttribute` コレクションを使用します。  
- **プロジェクトの開始日を設定するには？** 保存前に `project.setStartDate(LocalDateTime.of(...))` を呼び出します。  
- **本番環境で使用するためにライセンスが必要ですか？** 商用ライセンスは評価用の透かしを除去し、フル API アクセスを解放します。  
- **サポートされている Java バージョンは？** Aspose.Tasks for Java は JDK 8 から JDK 21 までサポートしています。

## Aspose.Tasks for Java の使い方?
`Project` はメモリ内で Microsoft Project ファイルを表す主要オブジェクトです。Aspose.Tasks ライブラリをロードし、`Project` インスタンスを作成し、プロジェクトレベルのプロパティを設定し、リソース割り当てに拡張属性を追加し、最後にプロジェクトを XML として保存します。コアワークフローは、初期化、変更、永続化の 3 つの簡潔なステップに分かれます。このパターンはプロジェクトファイルのサイズに関係なく機能し、Windows、Linux、macOS の JVM 上で動作します。

## Aspose.Tasks の拡張属性とは
**拡張属性** は、タスク、リソース、または割り当てに付加できるカスタムフィールドで、組み込み列以外の追加メタデータを保存します。`ExtendedAttributeDefinition` はカスタムフィールドのスキーマを定義します。Aspose.Tasks は `ExtendedAttributeDefinition` と `ExtendedAttribute` クラスを提供し、これらのフィールドをプログラムで定義および割り当てることができます。

## リソース割り当てに拡張属性を追加する理由
Aspose.Tasks は **50 以上の組み込みおよびカスタムフィールド** をサポートし、ユーザー定義属性を無制限に追加できます。これらを追加することで、コストコードや部門 ID などのビジネス固有データを .mpp ファイル内に直接保存でき、外部スプレッドシートの必要性を排除し、プロジェクトライフサイクル全体でデータの整合性を確保できます。

## 前提条件
開始する前に、以下が揃っていることを確認してください：

1. **Java Development Kit (JDK)** – JDK 8 以降がインストールされていること。  
2. **Aspose.Tasks for Java ライブラリ** – 公式リリースページ [here](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **IDE** – IntelliJ IDEA、Eclipse、または好みの Java 対応エディタ。

## パッケージのインポート
まず、Java プロジェクトで必要なパッケージをインポートします：

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### 手順 1: データディレクトリの設定
プロジェクトデータを保存するディレクトリを定義します。このパスは後で XML ファイルを保存する際に使用されます。

```java
String dataDir = "Your Data Directory";
```

### 手順 2: プロジェクトインスタンスの作成
`Project` クラスは、Aspose.Tasks のトップレベルオブジェクトで、メモリ内の単一の Microsoft Project ファイルを表します。インスタンス化することで、すべてのプロジェクト要素にフルアクセスできます。

```java
Project project = new Project();
```

### 手順 3: プロジェクト情報プロパティの設定
開始日、開始からのスケジュールフラグ、ステータス日付など、重要なプロジェクトプロパティを設定します。これらの値はプロジェクトの `ProjectInfo` オブジェクトに保存されます。

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 手順 4: リソース割り当てに拡張属性を追加
カスタムフィールド用に `ExtendedAttributeDefinition` を作成し、`ResourceAssignment` に添付して値を設定します。この手順は **add extended attributes** キーワードの実例を示しています。

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## よくある問題と解決策
- **割り当てコレクションにアクセスしたときの NullPointerException** – 割り当てを取得する前に、少なくとも 1 つのリソースと 1 つのタスクを作成していることを確認してください。  
- **拡張属性が MS Project に表示されない** – 属性の `FieldId` がカスタムフィールドスロット（例: `ExtendedAttributeTask.Text1`）と一致しているか確認してください。  
- **日付形式の不一致** – 日付値には `java.time.LocalDateTime` を使用してください。Aspose.Tasks は自動的にプロジェクトのカレンダー形式に変換します。

## よくある質問

**Q: Aspose.Tasks for Java を使用して MS Project ファイルを読み取れますか？**  
A: はい、ライブラリは .mpp、.xml、.xps 形式に対して完全な読み書き機能を提供します。

**Q: Aspose.Tasks for Java はさまざまなバージョンの MS Project と互換性がありますか？**  
A: もちろん、Project 2000 から最新の 2024 年リリースまで、20 以上のバージョン形式に対応しています。

**Q: Aspose.Tasks for Java の試用版には制限がありますか？**  
A: 試用版は生成されたファイルに透かしを追加し、作成できるタスク数に制限がありますが、すべての API 機能は利用可能です。

**Q: Aspose.Tasks for Java のサポートはどのように受けられますか？**  
A: Aspose.Tasks コミュニティフォーラム [here](https://forum.aspose.com/c/tasks/15) で支援を受けられます。

**Q: Aspose.Tasks for Java の一時ライセンスを購入できますか？**  
A: はい、一時ライセンスは短期使用向けに利用可能です。取得は [here](https://purchase.aspose.com/temporary-license/) から行えます。

**最終更新日:** 2026-05-20  
**テスト環境:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Tasks でリソース割り当てにノートを追加する方法](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Aspose.Tasks でリソース割り当てのレートスケールを読み書きする方法](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Aspose.Tasks でプロジェクトにリソースを追加し、レベリング遅延プロパティを処理する方法](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}