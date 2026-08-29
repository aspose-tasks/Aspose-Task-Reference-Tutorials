---
date: 2026-08-29
description: Aspose.Tasks を使用して、Microsoft Project を使わずに Java でプロジェクトにタスクを追加し、タスクリストを作成し、ベースラインを設定する方法を学びます。
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Aspose.Tasks でタスクベースラインを作成する
og_description: Aspose.Tasks を使用して、Java でプロジェクトにタスクを追加し、ベースラインを設定する方法を学びます。このガイドでは、Microsoft
  Project が不要なステップバイステップのコードを示します。
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Javaでプロジェクトにタスクを追加し、ベースラインを設定する方法
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Javaでプロジェクトにタスクを追加し、ベースラインを設定する方法
url: /ja/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Javaでプロジェクトにタスクを追加し、ベースラインを設定する方法

## はじめに
このチュートリアルでは、プログラムから **add task to project** を行い、Microsoft Project のタスクベースラインを生成し、ファイルを保存します――Microsoft Project を開くことは一切不要です。Aspose.Tasks for Java は、任意のプラットフォームで動作する純粋な Java API を提供し、ビルドパイプラインの自動化、レポーティングサービス、または .mpp ファイルを操作するサーバーサイドソリューションに最適です。

## クイック回答
- **What does Aspose.Tasks do?** Aspose.Tasks は、Microsoft Project を必要とせずに Microsoft Project ファイルの作成、読み取り、編集を行う Java API を提供します。  
- **Do I need Microsoft Project installed?** いいえ、このライブラリは完全に独立して動作します。  
- **Which Java version is required?** JDK 8 以上が必要です。  
- **Can I set a baseline for a single task?** はい。対象タスクだけを含むリストに対して `setBaseline` を呼び出します。  
- **Is a license needed for production?** はい。商用ライセンスを取得すると評価制限が解除され、すべての機能が利用可能になります。

## タスクベースラインとは何ですか？
タスクベースラインは、スケジュールが最初に保存された時点でのタスクの元々計画された開始日、終了日、作業量を記録します。このスナップショットは基準点として機能し、プロジェクトマネージャーが実際の進捗やコストを初期計画と比較し、パフォーマンス分析のための差異を算出できるようにします。

## Javaでプロジェクトにタスクを追加する際に Aspose.Tasks を使用する理由は？
デスクトップにインストールすることなくタスクの作成、変更、ベースライン設定が可能で、完全に自動化されたワークフローを実現します。Aspose.Tasks は **50 以上の入力および出力フォーマット** をサポートし、**数百のタスク** を持つプロジェクトでもメモリ使用量を 200 MB 未満に抑えることができるため、クラウドサービスや CI/CD パイプラインに最適です。

## 前提条件
1. **Java Development Kit (JDK)** – JDK 8 以上をインストールしてください。  
2. **Aspose.Tasks for Java** – ライブラリは [download link](https://releases.aspose.com/tasks/java/) からダウンロードしてください。

## パッケージのインポート
To start working with Aspose.Tasks in your Java project, import the necessary packages:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## ステップ 1: プロジェクトオブジェクトの作成
`Project` クラスは、Aspose.Tasks のトップレベルオブジェクトで、メモリ上の Microsoft Project ファイルを表します。インスタンス化すると、タスク、リソース、カレンダーを追加できる空のプロジェクトが得られます。
```java
Project project = new Project();
```
ここでは新しい `Project` オブジェクトをインスタンス化しています――このオブジェクトはタスクリストを保持する MS Project ファイルを表します。

## ステップ 2: プロジェクトにタスクを追加する
`Task` クラスは、プロジェクトスケジュール内の個々の作業項目を表します。各 `Task` は独自の期間、開始日、リソース割り当てを持つことができます。
```java
Task task = project.getRootTask().getChildren().add("Task");
```
`getRootTask()` を使用してプロジェクト階層のルートにアクセスし、**add task to Microsoft Project** を実行します。文字列 `"Task"` はタスク名ですので、必要に応じて任意の説明に置き換えることができます。

## ステップ 3: 指定タスクのベースラインを設定する
`BaselineType` は、どのベースラインスロット（Baseline、Baseline1 … Baseline10）に書き込むかを定義する列挙型です。タスクのリストを渡すことで、選択した項目だけにベースラインを設定できます。
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
**set baseline without MS Project** を行うには、ベースラインを設定したいタスクのリスト（ここでは `myList`）を作成し、`setBaseline` に渡します。選択的なベースラインが必要な場合は、追加したタスクを `myList` に格納してください。

## ステップ 4: プロジェクト全体のベースラインを設定する
`setBaseline` は、選択したベースライン値をプロジェクト内のすべてのタスクに書き込みます。  
プロジェクト全体を一度にベースライン設定したい場合は、目的の `BaselineType` を指定して `setBaseline` を呼び出すだけです。
```java
project.setBaseline(BaselineType.Baseline);
```
この呼び出しはプロジェクト内の **every task** に対して選択したベースライン値を書き込み、元のスケジュールの完全なスナップショットを確保します。

## Aspose.Tasks を使用して Microsoft Project にタスクを追加する方法
`add()` は、指定された親タスクの下に新しい子タスクを作成し、新しく作成された `Task` オブジェクトを返します。  
タスクは、親 `Task` オブジェクト（通常はルートタスク）に対して `add()` を呼び出すことで追加します。このメソッドは新しい `Task` インスタンスを返すので、期間、開始日、リソース、カスタムフィールドなどをさらに設定し、プロジェクトファイルを保存する前に構成できます。

## MS Project を使用せずにベースラインを設定する方法
Aspose.Tasks は、コードだけでベースライン作成を可能にします。`BaselineType`（例: `BaselineType.Baseline`）を選択し、`setBaseline` を呼び出します。`Baseline1`‑`Baseline10` を使用すれば、複数のリビジョンベースラインを保持でき、すべて Microsoft Project を開くことなく実行できます。

## 一般的な問題と解決策
- **Baseline not appearing:** ベースライン設定後に `project.save("output.mpp")` を呼び出していることを確認してください（ここでは保存手順を省略しています）。  
- **Task list appears empty:** タスクを正しい親（`getRootTask()` またはサブタスク）に追加しているか確認してください。  
- **Version mismatch errors:** 最新の Aspose.Tasks JAR を使用して、最新の .mpp フォーマットとの互換性を確保してください。

## よくある質問

**Q: Can I use Aspose.Tasks for Java without Microsoft Project installed?**  
A: はい、Aspose.Tasks は独立して動作し、ホストマシンに Microsoft Project がインストールされている必要はありません。

**Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project?**  
A: もちろんです。このライブラリは 2007 年版から最新の 2024 年版までの Project ファイルをサポートしています。

**Q: Can I manipulate project resources using Aspose.Tasks for Java?**  
A: はい、タスクと同様に、リソースをプログラムで追加、更新、削除できます。

**Q: Does Aspose.Tasks for Java support setting task dependencies?**  
A: はい、`TaskLink` クラスを使用して前任者‑後続者の関係を定義できます。

**Q: Is technical support available for Aspose.Tasks for Java?**  
A: はい、[support forum](https://forum.aspose.com/c/tasks/15) で Aspose のスタッフやコミュニティからサポートを受けられます。

## 結論
これらの手順に従うことで、Java で **add task to project** を行い、タスクリストを作成し、Aspose.Tasks を使用して **set baseline without MS Project** を実現する方法を学びました。このアプローチにより、プロジェクトの自動化が簡素化され、デスクトップ版 Project のインストールが不要になり、スケジュールのすべての側面をプログラムから完全に制御できるようになります。

---

**最終更新日:** 2026-08-29  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [プロジェクト作成方法 aspose.tasks – 新しいタスク属性の設定](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Aspose.Tasks for Java でベースライン期間を設定する方法](/tasks/java/task-baselines/task-baseline-duration/)
- [タスク作成 Aspose Java – タスクプロパティ](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}