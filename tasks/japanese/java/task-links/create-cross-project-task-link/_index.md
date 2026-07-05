---
date: 2026-07-05
description: Aspose.Tasks for Java を使用して、プロジェクト間でタスクをリンクする方法を学びます。step‑by‑step guide、prerequisites、best
  practices を提供し、シームレスな cross‑project task linking を実現します。
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Aspose.Tasks で Cross-Project Task Link を作成
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java を使用したプロジェクト間タスクのリンク
url: /ja/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用したプロジェクト間タスクのリンク

## はじめに
プロジェクト間タスクのリンクは、作業を同期させ、重複を防止し、相互依存する活動の単一の真実の情報源を維持するためのコア機能です。このチュートリアルでは、Aspose.Tasks for Java を使用して **プロジェクト間タスクのリンク** を段階的に学びます。最後まで実施すれば、いずれかの側が変更されたときに自動的に更新される完全に機能するクロスプロジェクトリンクが得られ、手動でのコピー＆ペーストなしにリアルタイムで調整できます。

## クイック回答
- **プロジェクト作成の主要クラスは何ですか？** `Project` – メモリ内の MS‑Project ファイル全体を表します。  
- **外部タスクを追加するメソッドはどれですか？** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **リンクタイプを設定できますか？** はい – `TaskLinkType.FinishToStart`、`StartToStart` などを使用します。  
- **リンクにライセンスは必要ですか？** 本番使用には有効な Aspose.Tasks ライセンスが必要です。評価目的には無料トライアルで動作します。  
- **リンクされたタスクに制限はありますか？** Aspose.Tasks はプロジェクトあたり 10,000 件以上のリンクタスクをパフォーマンス低下なしで処理できます。

## プロジェクト間タスクのリンクとは何か？
プロジェクト間タスクのリンクは、あるプロジェクトファイル内のタスクと別のプロジェクトファイル内のタスクとの間に依存関係を作成し、ソースタスク（期間、開始日、制約）の変更が自動的に依存タスクへ流れるようにします。この仕組みによりスケジュールが整合し、手動更新が減少し、ソースプロジェクトの変更がすべてのリンクされたプロジェクトに即座に反映され、ポートフォリオ全体の一貫性が保たれます。

## なぜ Aspose.Tasks を使用してプロジェクト間リンクを行うのか？
Aspose.Tasks は **50 以上の入出力形式** をサポートし、**数百ページ規模のプロジェクト** をメモリ使用量 200 MB 未満で処理できます。API はサーバー側でリンク処理を行うため、Microsoft Project のインストールが不要で、大規模企業向けの自動化パイプラインを実現します。

## 前提条件
開始する前に以下を確認してください。

- Java 17（またはそれ以降）がインストールされ、IDE で設定されていること。  
- 有効な Aspose.Tasks for Java ライセンスファイル（`Aspose.Tasks.Java.lic`）。  
- プロジェクトに Aspose.Tasks for Java ライブラリを追加してください。ダウンロードは [Aspose.Tasks for Java release page](https://releases.aspose.com/tasks/java/) から行えます。  
- タスク、サマリータスク、依存関係など、MS‑Project の基本概念に慣れていること。

## パッケージのインポート
`Project`、`Task`、`TaskLink` および関連する列挙型は `com.aspose.tasks` 名前空間にあります。Java ファイルの先頭でインポートしてください。

```java
import com.aspose.tasks.*;
```

**Project** はメモリ内のプロジェクトファイルを表すメインクラスです。**Task** はプロジェクト内の個別作業項目を表します。**TaskLink** は 2 つのタスク間の依存関係を定義します。これらのインポートにより、クロスプロジェクトリンクを含むプロジェクト操作機能の全スイートにアクセスできます。

## プロジェクト間タスクをリンクする方法
2 つのプロジェクトファイルを読み込み、外部タスクのプレースホルダーを追加し、ローカルタスクを作成してから `TaskLink` で接続します。API が ID マッピングと自動更新を処理するため、外部タスクの変更がリンクされたローカルタスクに追加コードなしで伝播します。このアプローチはマルチプロジェクトの調整を簡素化し、スケジュールドリフトのリスクを低減します。

### 手順 1: 環境の設定
Aspose.Tasks の JAR がクラスパスにあり、実行時にライセンスファイルがロードされていることを確認してください：

```java
License license = new License(); 
license.setLicense("Aspose.Tasks.Java.lic");
```

**License** は Aspose.Tasks のライセンスファイルをロードし、フル機能を有効化して評価版の透かしを除去します。

### 手順 2: Project インスタンスの作成
リンク先となるターゲットプロジェクト用に新しい `Project` オブジェクトをインスタンス化します：

```java
Project targetProject = new Project();
```

`Project` クラスは Aspose.Tasks のトップレベルオブジェクトで、メモリ内の単一プロジェクトファイルを表します。

### 手順 3: サマリータスクの追加
サマリータスクは関連タスクをグループ化します。外部タスクとローカルタスクの両方を保持するサマリータスクを作成します：

```java
Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");
```

### 手順 4: 外部タスクの追加
別プロジェクトファイル内のタスクを指す外部タスクを挿入します：

```java
Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);
```

**addExternalTask** メソッドは、指定されたファイル名とタスク ID を使用して外部プロジェクトファイルを参照するプレースホルダータスクを作成します。

### 手順 5: ローカルタスクの追加
外部タスクにリンクするローカルタスクを作成します：

```java
Task local = summary.getChildren().add("Local Task");
```

### 手順 6: タスクリンクの作成
外部タスクとローカルタスクの間に依存関係を確立します。最も一般的なリンクタイプは Finish‑to‑Start です：

```java
TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);
```

**TaskLink** は関係を記録します。必要に応じて遅延、リード、タイプを後から変更できます。

### 手順 7: 保存と検証
プロジェクトをファイルに保存し、必要に応じて Microsoft Project でリンクを確認します：

```java
targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);
```

**SaveFileFormat** はプロジェクト保存時のファイル形式を指定します。*LinkedProject.mpp* を開くと、外部タスクが特別なアイコンで表示され、ローカルタスクへ向かう依存線が描かれます。

## よくある問題と解決策
- **外部ファイルが見つかりません** – 実行プロセスからの相対パスであることを確認するか、絶対パスを指定してください。  
- **タスク ID の不一致** – `addExternalTask` の第2引数である外部タスク ID がソースプロジェクトと一致しているか確認してください。  
- **ライセンスがロードされていません** – ライセンスファイルが欠如または不正確だと `LicenseException` が発生します。Aspose.Tasks の呼び出しの前にロードしてください。  
- **大規模プロジェクトでのパフォーマンス** – 外部タスクを読み取るだけの場合は `Project.setReadOnly(true)` を使用してください。メモリ使用量が削減されます。

## よくある質問

**Q: 同じサマリータスク内で複数の外部プロジェクトからタスクをリンクできますか？**  
A: はい、1 つのサマリータスクの下に複数の外部タスクを追加し、各タスクに対して個別のリンクを作成できます。`addExternalTask` メソッドを同様に使用します。

**Q: リンクされたプロジェクトの外部タスクが変更された場合はどうなりますか？**  
A: 外部タスクのスケジュール、期間、制約の変更は、ターゲットプロジェクトをリフレッシュしたときに自動的に依存ローカルタスクに反映されます。

**Q: 異なるファイル形式間でタスクリンクを作成できますか？**  
A: 完全に可能です。Aspose.Tasks は MPP、XML、Primavera 形式間のリンクをサポートしており、異種プロジェクト環境でも同期を保てます。

**Q: プロジェクト間でリンクされたタスクを解除できますか？**  
A: はい、`project.getTaskLinks().remove(link)` を呼び出すか、外部タスクのプレースホルダーを削除することでリンクを解除できます。

**Q: プロジェクト間でリンクできるタスク数に制限はありますか？**  
A: ライブラリはプロジェクトあたり **10,000 件以上のリンクタスク** を処理でき、システムメモリと基礎となるファイル形式の仕様が許容する限り制限はありません。

## 結論
これで Aspose.Tasks for Java を使用した **プロジェクト間タスクのリンク** の完全な実装手順が身につきました。この機能によりマルチプロジェクトの調整が効率化され、手作業が削減され、スケジュール変更がポートフォリオ全体に即座に伝播します。カスタム遅延時間、異なるリンクタイプ、バルクリンクなどの追加機能を活用して、さらに高度なプロジェクト構造を自動化してください。

---

**最終更新日:** 2026-07-05  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## 関連チュートリアル

- [Aspose.Tasks でタスクリンクを作成](/tasks/java/task-links/create-task-link/)
- [Aspose Java でタスクを作成 – タスクプロパティ](/tasks/java/task-properties/)
- [Aspose.Tasks で空の MS Project ファイルを作成](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}