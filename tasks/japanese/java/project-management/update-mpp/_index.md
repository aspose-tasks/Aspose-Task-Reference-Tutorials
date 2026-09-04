---
date: 2026-06-25
description: Aspose.Tasks for Java を使用してタスクを追加し、MPP ファイルを更新する方法を学びます。これは、タスクの Microsoft
  Project ファイルを作成し、プロジェクトを MPP として保存できる Java のプロジェクト管理ライブラリです。
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Aspose.Tasksでタスクを追加し、MPPファイルを更新する方法
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでタスクを追加し、MPPファイルを更新する方法
url: /ja/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasksでタスクを追加しMPPファイルを更新する方法

## はじめに
このチュートリアルでは、既存の Microsoft Project (MPP) ファイルに **タスクを追加する方法** を学び、Aspose.Tasks for Java（業界トップクラスの **Java プロジェクト管理ライブラリ**）を使用して更新されたスケジュールを保存する方法を紹介します。カスタムスケジューラの構築、バルク更新の自動化、またはプロジェクトデータを大規模システムに統合する場合でも、以下のステップバイステップガイドでは、プロジェクトの読み込み、新しいタスクの挿入、日付の設定、そして結果を新しい MPP ドキュメントとして永続化する手順を正確に示します。

## クイック回答
- **「タスクを追加する方法」とはこの文脈で何を意味しますか？** 既存の MPP ファイル内に新しい作業項目をプログラムで作成することを指します。  
- **どのライブラリがこの操作を処理しますか？** Aspose.Tasks for Java、堅牢な Java プロジェクト管理ライブラリです。  
- **ライセンスは必要ですか？** 開発には無料トライアルが利用できますが、本番環境では商用ライセンスが必要です。  
- **結果を MPP として保存できますか？** はい—`project.save(..., SaveFileFormat.Mpp)` を使用して **プロジェクトを MPP として保存** します。  
- **必要な Java バージョンは何ですか？** Java 8 以降です。

## MPP ファイルにおける「タスクを追加する方法」とは何ですか？
タスクを追加することは、プロジェクト階層に新しい作業項目を挿入し、開始日と終了日を定義し、変更を MPP ファイルに戻すことを意味します。Aspose.Tasks は低レベルのファイル形式の詳細を抽象化し、ビジネスロジックに集中できるようにしながら、リソース割り当て、カレンダー、依存関係の計算を自動的に処理します。また、関連する割り当ても更新し、依存タスク間の整合性を保つようにプロジェクトスケジュールを再計算します。

## なぜ Aspose.Tasks for Java を使用するのか？
- **完全な互換性**：Microsoft Project 2007‑2021 の機能を 100% サポート（150 種類以上のタスクと 200 項目以上のリソースフィールド）。  
- **ゼロ依存**：COM、Office、ネイティブライブラリは不要—純粋な Java API で、JRE が動作する場所ならどこでも実行可能です。  
- **豊富な機能セット**：タスクリンク、リソース割り当て、カスタムフィールド、組み込みレポート機能を含みます。  
- **高性能**：最大 10,000 件のタスクを 200 MB 未満の RAM で処理でき、サーバー側の自動化に最適です。

## 前提条件
1. **Java 開発環境** – JDK 8 以上がインストールされ、設定されていること。  
2. **Aspose.Tasks for Java** – [ダウンロードページ](https://releases.aspose.com/tasks/java/) から入手してください。  
3. **基本的な Java 知識** – クラス、オブジェクト、日付処理に慣れていること。  

## パッケージのインポート
まず、必要なクラスをインポートします。これにより、プロジェクト操作、タスクプロパティ、日付処理にアクセスできます。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` はメモリ上に読み込まれた Microsoft Project ファイルを表します。`SaveFileFormat` は MPP や PDF など、保存可能な形式を列挙します。`Task` はプロジェクト階層内の個々の作業項目をモデル化します。`Tsk` はタスクフィールドの定数を提供し、値の設定や取得に使用します。`Calendar` はスケジュール定義のための日付時刻ユーティリティを提供します。

## 手順 1: データディレクトリの定義
```java
String dataDir = "Your Data Directory";
```  
`"Your Data Directory"` を、ソース MPP ファイルが存在する絶対パスに置き換えてください。

## 手順 2: 既存プロジェクトの読み込み
`Project` クラスは Aspose.Tasks のコアオブジェクトで、メモリ上の Microsoft Project ファイルを表します。  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
コンストラクタは **SampleMSP2010.mpp** を読み込み、完全に操作可能なオブジェクトモデルを提供します。

## 手順 3: 新しいタスクの作成（タスクを追加する方法）
`Task` クラスはプロジェクト階層内の個々の作業項目を表します。  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
この行は **MPP にタスクを作成** し、ルートタスクに *Task1* という子タスクを追加します。

## 手順 4: 開始日と終了日の設定
`Calendar` クラスは日付時刻ユーティリティを提供します。月はゼロベース（例: `Calendar.JULY`）です。  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
ここで新しく追加したタスクのスケジュールを定義します。日付はプロジェクトのタイムラインに合わせて調整してください。

## 手順 5: プロジェクトの保存（MPP として保存）
`SaveFileFormat.Mpp` は Aspose.Tasks に対し、ファイルをネイティブの Microsoft Project 形式で書き戻すよう指示します。  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
更新されたプロジェクトは新しいタスクを含み、**AfterLinking.mpp** として永続化されます。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **File not found** | `dataDir` がパス区切り文字（`/` または `\\`）で終わっているか、ファイル名が正しいか確認してください。 |
| **Incorrect dates** | `Calendar` の月はゼロベースであることを忘れないでください。`Calendar.JULY` は 7 月を表します。 |
| **License exception** | 評価版の透かしを防ぐため、API を呼び出す前に有効な Aspose.Tasks ライセンスをインストールしてください。 |

## よくある質問
**Q: 複数のタスクを一度に追加するにはどうすればよいですか？**  
A: タスク名のコレクションをループし、ループ内で「タスク作成」ブロックを繰り返します。

**Q: 新しいタスクにカスタムフィールドを設定できますか？**  
A: はい—`task.set(Tsk.CUSTOM_FIELD_x, value)` を使用し、*x* はフィールドインデックスです。

**Q: 既存のタスクをテンプレートとしてコピーすることは可能ですか？**  
A: ソースタスクをクローン（`Task cloned = sourceTask.clone();`）し、目的の親タスクに追加します。

**Q: 新しいタスクを追加するのではなく、既存のタスクを更新する必要がある場合はどうすればよいですか？**  
A: ID でタスクを取得（`Task existing = project.getRootTask().getChildren().getById(id);`）し、プロパティを変更します。

**Q: Aspose.Tasks は PDF や PNG など他の形式での保存をサポートしていますか？**  
A: はい—`project.save("output.pdf", SaveFileFormat.Pdf);` や `SaveFileFormat.Png` を使用してビジュアル表現を保存できます。

---

**最終更新日:** 2026-06-25  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [MPP ファイルの作成方法 – Aspose.Tasks で空のプロジェクトを作成・保存 (MPP 形式)](/tasks/java/project-configuration/create-save-mpp/)
- [プロジェクトの作成方法 – Aspose.Tasks で新しいタスク属性を設定](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Java でタスクリスト作成 – Aspose.Tasks を使用した MS Project ベースライン](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}