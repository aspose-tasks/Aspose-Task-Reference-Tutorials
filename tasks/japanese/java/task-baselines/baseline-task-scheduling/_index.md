---
date: 2026-08-29
description: Aspose.Tasks for Java を使用してベースライン データを読み取り、タスクをスケジュールする方法を学び、計画と実績の進捗を効率的に比較できるようにします。
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Aspose.Tasks のベースライン タスク スケジューリング
og_description: Aspose.Tasks for Java を使用してベースライン データを読み取り、タスクをスケジュールし、計画と実績の進捗を正確に比較できるようにします。
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Aspose.Tasks を使用したベースラインの読み取りとタスクのスケジュール方法
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Aspose.Tasks を使用したベースラインの読み取りとタスクのスケジュール方法
url: /ja/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用したベースラインの読み取りとタスクのスケジュール方法

このガイドでは、**ベースラインの読み取り方法**情報と Aspose.Tasks for Java を使用してタスクをプログラムでスケジュールする方法を紹介します。チュートリアルの最後までに、元のプロジェクト計画を取得し、実際の進捗と比較し、差異レポートを生成できるようになります—Microsoft Project をインストールする必要はありません。

## プロジェクト管理ベースラインの概要

**プロジェクト管理ベースライン**を管理することは、効果的なプロジェクト管理の基礎です。元の計画を取得し、後で**計画対実績の進捗**と比較できるため、早期に差異を発見できます。このチュートリアルでは、Aspose.Tasks for Java を使用してタスクベースラインをスケジュールする方法を解説し、**プロジェクトベースラインを管理**するためのツールを提供し、プロジェクトを軌道に乗せます。

## クイック回答
- **プロジェクト管理ベースラインは何を表しますか？**  
  プロジェクト開始時に承認されたスケジュール、コスト、スコープを記録し、差異分析の参照として提供します。  
- **Java でベースラインスケジューリングを処理するライブラリはどれですか？**  
  Aspose.Tasks for Java は、45 以上の入力および出力フォーマットをサポートし、最大 100 000 タスクのプロジェクトを処理できる純粋な Java API を提供します。  
- **コードを実行するためにライセンスは必要ですか？**  
  無料トライアルはテストに使用できますが、本番環境では商用ライセンスが必要です。  
- **主な前提条件は何ですか？**  
  Java Development Kit (JDK) 11 以上と Aspose.Tasks for Java ライブラリ。  
- **ベースライン日付を設定後に確認できますか？**  
  はい—`TaskBaseline` オブジェクトを使用して開始日、完了日、期間の値を読み取ります。

## プロジェクト管理ベースラインとは何か？

プロジェクト管理ベースラインは、実行開始時に承認されたスケジュール、予算、スコープを記録したものです。パフォーマンス測定とプロジェクトライフサイクル全体での逸脱の特定の基準点として機能します。計画された開始日と完了日、総コスト、スコープの詳細を含み、将来の比較のための包括的なスナップショットを提供します。

## ベースラインスケジューリングに Aspose.Tasks を使用する理由

Aspose.Tasks は、Microsoft Project をインストールせずに動作する純粋な Java API を提供します。**45 以上の入力および出力フォーマット**をサポートし、**最大 100 000 タスク**をメモリ効率モードで処理でき、ベースラインデータの読み書き用の組み込みメソッドを提供するため、自動レポート作成や統合が簡単になります。

## 前提条件
- **Java Development Kit (JDK)** – JDK 11 以降をインストールします。以下の[website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)からダウンロードできます。  
- **Aspose.Tasks for Java library** – 最新リリースを[download page](https://releases.aspose.com/tasks/java/)からダウンロードし、JAR をプロジェクトのクラスパスに追加します。

## パッケージのインポート
`Project`、`Task`、`TaskBaseline` クラスは `com.aspose.tasks` 名前空間にあります。ソースファイルの先頭でインポートしてください。

`Project` クラスは Aspose.Tasks のトップレベルオブジェクトで、メモリ内の単一プロジェクト ファイルを表します。タスク、リソース、ベースライン コレクションへのアクセスを提供します。

## ベースラインの読み取り方法は？

プロジェクトをロードし、各タスクの `TaskBaseline` コレクションを照会します。`TaskBaseline` オブジェクトは、`setBaseline` を呼び出したときにキャプチャされたベースラインの開始、完了、期間を返します。この直接的なアプローチにより、XML やバイナリ ファイルを解析せずにベースライン値を読み取れます。

## ステップ 1: 新しいプロジェクト インスタンスの作成
`Project` クラスはメモリ内のプロジェクト全体を表します。
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## ステップ 2: タスクを定義しベースラインを設定
`Task` は個々の作業項目を表し、`setBaseline` は現在のスケジュールをベースラインとしてキャプチャします。
```java
Project project = new Project();
```

## ステップ 3: ベースライン情報へのアクセス
`TaskBaseline` はベースラインの保存された開始、完了、期間の値を保持します。
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## ステップ 4: ベースライン期間の表示
`Duration` はタスクまたはベースラインの時間長さを表します。
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## ステップ 5: ベースライン開始日の表示
`Start` はベースラインの予定開始日です。
```java
System.out.println(baseline.getDuration().toString());
```

## ステップ 6: ベースライン完了日の表示
`Finish` はベースラインの予定完了日です。
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## 一般的な問題と解決策
- **ベースラインが設定されていない:** タスクを追加した **after** `project.setBaseline(BaselineType.Baseline)` を呼び出してください。そうしないとベースライン コレクションは空になります。  
- **Null 値:** `task.getBaselines()` が空リストを返す場合、ベースラインを設定する前にタスクがプロジェクト階層に追加されているか確認してください。  
- **日付形式:** `getStart()` と `getFinish()` メソッドは `java.util.Date` オブジェクトを返します。カスタム表示形式が必要な場合は `SimpleDateFormat` を使用してください。

## よくある質問

**Q: Aspose.Tasks で新しいプロジェクト インスタンスを作成する方法は？**  
A: `Project` クラスをインスタンス化します（`Project project = new Project();`）。これにより、タスクとベースラインの追加が可能な新しいプロジェクト ファイルが作成されます。

**Q: `BaselineType.Baseline` と他のベースラインタイプの違いは何ですか？**  
A: `BaselineType.Baseline` はプライマリベースライン（ベースライン 1）を指します。Aspose.Tasks はベースライン 2‑10 もサポートし、追加のスナップショットを提供します。

**Q: ベースライン データを Excel や CSV にエクスポートできますか？**  
A: はい、`TaskBaseline` オブジェクトを反復処理し、標準的な Java I/O を使用して CSV ファイルに値を書き出すことができます。

**Q: ベースラインを設定すると既存のタスク日付に影響しますか？**  
A: ベースラインの設定は現在の日付をキャプチャしますが、タスクのアクティブ スケジュールは変更しません。ベースライン設定後も開始日/完了日を調整できます。

**Q: 複数のベースラインをプログラムで比較することは可能ですか？**  
A: もちろん可能です。`task.getBaselines().get(index)` で各ベースラインを取得し、`Start`、`Finish`、`Duration` プロパティを比較してください。

**最終更新日:** 2026-08-29  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 関連チュートリアル

- [Java タスクリスト作成 – Aspose.Tasks を使用した MS Project ベースライン](/tasks/java/task-baselines/create-task-baseline/)
- [Aspose.Tasks for Java でベースライン期間を設定する方法](/tasks/java/task-baselines/task-baseline-duration/)
- [Java で MPP プロジェクト作成 – Aspose.Tasks でタスクの進捗を変更](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}