---
date: 2026-09-25
description: Aspose.Tasks を使用して Java でプロジェクトスケジュールを作成する方法を学びます。このガイドでは、summary tasks
  の追加、project hierarchy の管理、document directory の効率的な設定方法を示します。
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Aspose.Tasks でタスクを作成
og_description: Aspose.Tasks を使用して Java でプロジェクトスケジュールを作成する方法を学びます。step‑by‑step の手順に従って
  summary tasks を追加し、hierarchy を管理し、document directory を設定します。
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Aspose.Tasks for Java を使用してプロジェクトスケジュールを作成する方法
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java を使用してプロジェクトスケジュールを作成する方法
url: /ja/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用したプロジェクトスケジュールの作成方法

## はじめに
このチュートリアルでは、Aspose.Tasks を使用して Java アプリケーションで **プロジェクトスケジュールを作成**する方法を学びます。シンプルなやることリストから複雑なエンタープライズレベルのプランナーまで、以下の手順でサマリータスクの追加、プロジェクト階層の管理、ドキュメントディレクトリの設定を行う方法を、明確で実行可能なコードスニペットとともに解説します。最後まで実行すれば、さらなる操作やエクスポートが可能な完全に構造化されたスケジュールが手に入ります。

## クイック回答
- **Aspose.Tasks は何を管理しますか？** タスク階層、リソース、カレンダー、そしてプロジェクトファイル形式（MS‑Project、Primavera など）を扱います。  
- **開発にライセンスは必要ですか？** 評価用の無料一時ライセンスで動作しますが、本番環境では正式ライセンスが必要です。  
- **対応している Java バージョンは？** Java 8 以降が完全にサポートされています。  
- **タスクにカスタムフィールドを追加できますか？** はい、API を通じてユーザー定義フィールドでタスクを拡張できます。  
- **ガントチャートの組み込みサポートはありますか？** Aspose.Tasks はガント可視化を含む PDF/HTML へのエクスポートが可能です。

## Aspose.Tasks におけるプロジェクトスケジュールとは何ですか？
プロジェクトスケジュールとは、作業の実行方法を定義するタスク、依存関係、タイムラインの完全な集合です。Aspose.Tasks はこの情報を `Project` オブジェクトに格納し、さまざまな形式で読み取り、変更、保存できます。開始日・終了日、制約、リソース割り当てを含み、包括的な計画とレポートを実現します。

## Java プロジェクト管理に Aspose.Tasks を使用する理由
Aspose.Tasks は **30 以上の入出力形式** をサポートし、**最大 10,000 タスク** のプロジェクトをファイル全体をメモリにロードせずに処理できるため、大規模な Java プロジェクト管理シナリオでも高性能を発揮します。

## 前提条件
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
- **Java Development Kit (JDK)** – JDK 8 以降がマシンにインストールされていること。  
- **Aspose.Tasks for Java ライブラリ** – ライブラリは [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/) からダウンロードしてインストールしてください。  
- **統合開発環境 (IDE)** – Eclipse、IntelliJ IDEA、またはお好みの Java 対応 IDE を使用してください。

## パッケージのインポート
`Project`、`Task`、および関連クラスは `com.aspose.tasks` 名前空間にあります。Java ファイルの先頭でこれらをインポートします。

`Project` クラスは完全なプロジェクトスケジュールを表し、タスクやリソースを操作するためのメソッドを提供します。

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

`Project` クラスはプロジェクトファイルに対するすべての操作のエントリーポイントです。

## Aspose.Tasks を使用したプロジェクトスケジュールの作成方法

新しい `Project` インスタンスをロードし、ドキュメントディレクトリを設定してタスクの追加を開始します。この段落では、コアフローを直接説明します。まず `Project` を作成し、`RootFolder`（ドキュメントディレクトリ）を構成し、次にサマリータスクとサブタスクを追加します。すべての変更はメモリ上に保持され、`save` を呼び出すまでスケジュールはファイルに永続化されません。

### ステップ 1: ドキュメントディレクトリの設定
結果として生成されるプロジェクトファイルの書き込み先を定義します。ディレクトリを早期に設定することで、以降のすべての保存操作が一貫したパスを使用します。

`RootFolder` プロパティは、プロジェクトファイルの読み取りまたは書き込みが行われる基礎フォルダーを指定します。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### ステップ 2: 新しいプロジェクトの作成
スケジュールを保持する新しい `Project` オブジェクトをインスタンス化します。既存のスケジュールを変更したい場合は、事前にファイルパスを渡すことも可能です。

`Project` コンストラクタは、タスク追加の準備ができた空のスケジュールを作成します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ステップ 3: サマリータスクの追加
サマリータスクは関連するサブタスクをグループ化し、ガントチャート上では折りたたみ可能なノードとして表示されます。`Task` クラスを使用し、`IsSummary` を `true` に設定します。

`addTask` メソッドは指定された親の下に新しいタスクを作成し、その ID を返します。

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### ステップ 4: サブタスクの追加
サブタスクは、親サマリータスクから開始日・終了日を継承します（上書きしない限り）。サブタスクの追加は、`addTask` を再度呼び出し、親タスクの ID を指定するだけです。

親 ID を指定して `addTask` を呼び出すと、そのサマリータスクの下にサブタスクが追加されます。

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

プロジェクトに必要なだけタスクやサブタスクを追加し続けてください。各ステップは、MS‑Project、PDF、その他サポート形式へのエクスポートが可能な構造化されたプロジェクト階層の構築に寄与します。

## 一般的な問題と解決策
- **Problem:** “Document directory not found.”  
  **Solution:** `RootFolder` に割り当てたパスがファイルシステム上に存在し、Java プロセスに書き込み権限があることを確認してください。
- **Problem:** Subtasks not appearing under the summary task.  
  **Solution:** `addTask` 呼び出し時に正しい親タスク ID を渡しているか確認してください。API では親 ID を第2引数として指定する必要があります。
- **Problem:** Large projects cause OutOfMemoryError.  
  **Solution:** Aspose.Tasks はストリーミングモードでタスクを処理します。JVM のヒープサイズを増やす（例: `-Xmx2g`）か、スケジュールを複数ファイルに分割してください。

## よくある質問
**Q: Aspose.Tasks は小規模プロジェクトにも適していますか？**  
A: はい。単一タスクのリストから数千タスク規模のエンタープライズレベルスケジュールまで、ライブラリはシームレスにスケールします。

**Q: Aspose.Tasks for Java の詳細なドキュメントはどこで確認できますか？**  
A: ドキュメントは [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/) を参照してください。

**Q: Aspose.Tasks の一時ライセンスはどのように取得できますか？**  
A: 開発・テスト用の期間限定ライセンスは [temporary license request page](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Tasks でタスク属性をカスタマイズできますか？**  
A: はい、カスタムフィールドの追加、リソースの割り当て、カレンダーのプログラム的変更などが可能です。

**Q: Aspose.Tasks ユーザー向けのサポートコミュニティはありますか？**  
A: あります！[the support forum](https://forum.aspose.com/c/tasks/15) で Aspose.Tasks コミュニティに参加してください。

---

**Last Updated:** 2026-09-25  
**Tested With:** Aspose.Tasks 24.12 for Java  
**Author:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## 関連チュートリアル

- [Aspose.Tasks for Java を使用した MS Project の開始日設定](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks でプロジェクト管理タスクの依存関係を作成](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks でリソースをプロジェクトに追加し、リソース割り当てを作成](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}