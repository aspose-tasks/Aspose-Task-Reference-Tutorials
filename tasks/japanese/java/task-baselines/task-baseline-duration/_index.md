---
date: 2026-08-29
description: Aspose.Tasks for Java を使用してベースライン期間を設定し、プロジェクトの進捗を追跡する方法を学びます。このステップバイステップガイドは、タスクのベースラインを効率的に管理するのに役立ちます。
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Aspose.Tasks for Java でベースライン期間を設定する方法
og_description: Aspose.Tasks for Java を使用してベースライン期間を設定し、プロジェクトの進捗を追跡する方法を学びます。この詳細なガイドに従って、タスクのベースラインを効率的に管理してください。
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: プロジェクトの進捗を追跡するためのベースライン期間の設定方法
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: プロジェクトの進捗を追跡するためのベースライン期間の設定方法
url: /ja/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ベースライン期間を設定してプロジェクトの進捗を追跡する方法

## はじめに
プロジェクトの進捗を追跡するには、確固たるベースラインから始めます。このチュートリアルでは、Java 用 Aspose.Tasks ライブラリを使用して Microsoft Project ファイルのタスクに対して **ベースライン期間の設定方法** を学び、ベースラインを早期に設定することで、プロジェクトのライフサイクル全体でスケジュールのずれ、コストのばらつき、リソースの過剰割り当てを監視できる理由を理解します。

## クイック回答
- **「set baseline」とは何ですか？** タスクの元の開始日、終了日、期間を記録し、将来の変更と比較できるようにします。  
- **どの Aspose.Tasks クラスがプロジェクトを作成しますか？** `Project` クラスです – 正しく **プロジェクト インスタンスを作成** する方法も学びます。  
- **コードを実行するのにライセンスは必要ですか？** 無料の評価ライセンスはテストに使用できますが、本番環境では商用ライセンスが必要です。  
- **中間ベースラインを取得できますか？** はい、Aspose.Tasks を使用すると中間ベースラインとその固定コストをクエリできます。  
- **必要な Java バージョンは何ですか？** Java 8 以降が推奨されます。  
- **これがプロジェクトの進捗追跡にどのように役立ちますか？** ベースラインを設定すると、組み込みのレポート機能を使用して実際の日付を元の計画と即座に比較できます。

## タスクベースラインとは何か、そしてなぜ設定するのか
タスクベースラインは、特定の時点での計画されたスケジュール（開始日、終了日、期間）を記録します。ベースラインを設定することで、プロジェクトが進行するにつれてスケジュールのずれ、コスト超過、リソースの過剰割り当てを簡単に把握できる参照ポイントが作成されます。

## ベースライン管理に Aspose.Tasks を使用する理由
Aspose.Tasks は **完全な .mpp 互換性** を提供します – Microsoft Office をインストールせずにネイティブの Microsoft Project ファイルを読み書きできます。API は **50 以上の入出力フォーマット** へのプログラム的アクセスを可能にし、**中間ベースライン 1‑10** をサポートし、ファイル全体をメモリにロードせずに **数百ページに及ぶプロジェクト** を処理できるため、高性能バッチ処理に不可欠です。

## 前提条件
1. **Java 開発環境** – JDK 8 以上がインストールされ、設定されていること。  
2. **Aspose.Tasks for Java** – ライブラリは [Aspose.Tasks for Java ダウンロードページ](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **IDE またはビルドツール** – Maven、Gradle、またはお好みの IDE。

## パッケージのインポート
以下のインポートは、プロジェクト、タスク、ベースライン、タイムフェーズ データを操作するために必要な Aspose.Tasks のコアクラスを取り込みます。

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## ステップ 1: プロジェクト インスタンスの作成
`Project` クラスは、メモリ内の Microsoft Project ファイルを表し、すべての操作のエントリーポイントです。

```java
Project project = new Project();
```

## ステップ 2: タスクベースラインの作成
`TaskBaseline` は、特定のタスクの計画された開始日、終了日、期間を保存します。

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## ステップ 3: タスクベースライン情報の表示
`getBaselines()` メソッドは、タスクに関連付けられたベースラインのコレクションを返します。

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## ステップ 4: 中間ベースラインと固定コストの確認
`BaselineType` は、主ベースラインと中間ベースライン（Baseline、Baseline1‑Baseline10）を列挙します。

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## ステップ 5: タイムフェーズ データの出力
`TimephasedData` は、特定の時間間隔に対するスケジュール情報の一部を表します。

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

これらの手順に従うことで、任意のタスクに対して **ベースライン期間を設定** でき、Aspose.Tasks for Java を使用して詳細なベースライン情報を取得できるため、プロジェクトのライフサイクル全体で **プロジェクトの進捗を追跡** する信頼できる方法が得られます。

## 一般的な問題と解決策
- **ベースラインが MS Project に表示されない:** タスクを追加した **後** に `project.setBaseline(BaselineType.Baseline)` を呼び出したことを確認してください。  
- **`getBaselines()` で NullPointerException が発生:** ベースラインを設定する前にタスクがプロジェクトに追加されていることを確認してください。  
- **時間単位の不一致:** カスタム カレンダーを使用する場合など、期間を正しくフォーマットするために `TimeUnitType` を使用してください。

## FAQ
### MS Project のタスクベースラインとは何ですか？
MS Project のタスクベースラインは、タスクの最初の計画スケジュール（開始日、終了日、期間）をスナップショットとして保存したものです。

### タスクベースラインの管理が重要な理由は何ですか？
タスクベースラインを管理することで、計画されたスケジュールと実際のプロジェクト進捗を比較でき、より良い追跡と意思決定を促進します。

### ベースラインを設定した後にタスクベースラインを変更できますか？
はい、MS Project ではプロジェクト計画の変更を反映するためにタスクベースラインを変更できます。ただし、元のベースラインからの逸脱は必ず記録してください。

### Aspose.Tasks は他のプロジェクト管理機能もサポートしていますか？
はい、Aspose.Tasks はタスクスケジューリング、リソース割り当て、ガントチャート生成など、プロジェクト管理の幅広い機能を提供します。

### Aspose.Tasks のサポートはどこで得られますか？
Aspose.Tasks のサポートは [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) で利用でき、質問や他のユーザーとのやり取りが可能です。

## 追加のよくある質問
**Q: 各タスクに個別に `setBaseline` を呼び出す必要がありますか？**  
A: いいえ。`project.setBaseline(BaselineType.Baseline)` を呼び出すと、プロジェクト内のすべてのタスクのベースラインが一度に記録されます。

**Q: 特定のタスクに中間ベースラインを設定するにはどうすればよいですか？**  
A: タスクのスケジュールを更新した後、`project.setBaseline(BaselineType.Baseline1)`（または Baseline2‑Baseline10）を使用します。

**Q: ベースラインデータを CSV にエクスポートできますか？**  
A: はい。`task.getBaselines()` を反復処理し、標準の Java I/O を使用して必要なフィールドを CSV ファイルに書き出します。

**Q: 既にベースラインが含まれている既存の .mpp ファイルを読み取れますか？**  
A: もちろんです。`new Project("myproject.mpp")` でファイルをロードし、上記のように各タスクのベースラインにアクセスできます。

**Q: Aspose.Tasks はマルチプロジェクト ファイルを扱えますか？**  
A: Aspose.Tasks は単一プロジェクトの .mpp ファイルに対応しています。マルチプロジェクトのシナリオでは、プログラムでプロジェクトを結合してください。

---

**最終更新日:** 2026-08-29  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [Java でタスクリスト作成 – Aspose.Tasks を使用した MS Project ベースライン](/tasks/java/task-baselines/create-task-baseline/)
- [Java で MPP プロジェクト作成 – Aspose.Tasks でタスクの進捗を変更](/tasks/java/task-properties/change-progress/)
- [プロジェクト管理ベースライン – Aspose.Tasks を使用したタスクスケジューリング](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}