---
date: 2026-02-26
description: Aspose.Tasks for Java を使ってタスクを分割する方法を学びましょう – タスクの分割方法、プロジェクト カレンダーの設定、リソース割り当ての作成に関する決定的なガイドです。
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでタスクを分割する方法
url: /ja/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でタスクを分割する方法

## Introduction
Java ベースのプロジェクトで **タスクの分割方法** をお探しなら、ここが最適です。Aspose.Tasks for Java は、長時間実行されるタスクを小さく管理しやすい部分に分割するためのクリーンでプログラム的な手段を提供し、リソースの平準化、正確なレポート作成、プロジェクトのスケジュール短縮に役立ちます。このチュートリアルでは、プロジェクト カレンダーの設定からリソース割り当ての作成、そしてタスクを複数のセグメントに分割するまでの全工程を順に解説します。

## Quick Answers
- **タスク分割とは？** 単一のタスクを総期間を保ったまま、いくつかの小さな区間に分割することです。  
- **Java でタスクを分割する理由は？** 正確なリソース割り当てと進捗管理が可能になるためです。  
- **どのライブラリが役立ちますか？** Aspose.Tasks for Java が分割および時間フェーズ用の組み込みメソッドを提供します。  
- **ライセンスは必要ですか？** 開発目的なら無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **対応している Java バージョンは？** Java 8 以降で動作します。

## Prerequisites
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
- マシンに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Tasks for Java ライブラリをダウンロードし、プロジェクトに追加していること。ダウンロードは [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) から行えます。

## Import Packages
Java プロジェクトに必要なパッケージをインポートします:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Step 1: Create a New Project
Aspose.Tasks ライブラリを使用して新しいプロジェクトを作成します:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Step 2: Set Project Calendar
**プロジェクト カレンダー** を設定すると、作業日、祝日、全体のスケジュールが定義されます。この手順は正確な時間フェーズ計算に不可欠です。

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Step 3: Add a Root Task
すべてのプロジェクトにはルート コンテナが必要です。ルート タスクを追加すると、以降のタスクをすべてこの下に配置できます。

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Step 4: Add a New Task to Split
分割したいタスクを作成します。ここでは例として 3 日間の期間を設定します。

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Step 5: Create a Resource Assignment
**リソース割り当て** はリソース（またはプレースホルダー）をタスクに結び付けます。時間フェーズ データを生成する前に必要です。

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Step 6: Generate Timephased Data
時間フェーズ データは、作業がタスクの期間にわたってどのように分配されるかを表します。これを生成することでタスクの分割準備が整います。

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Step 7: Split the Task
ここで **タスクをパートに分割** します。この例では、3 日間のタスクを 1 日ずつの 3 セグメントに分割します。

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Why Split Tasks?
タスクを分割すると、以下のような細かな制御が可能になります。
- **リソース平準化:** 各セグメントに異なるリソースを割り当てられます。  
- **進捗追跡:** セグメント単位でステータスを更新できます。  
- **レポート作成:** より詳細なガントチャートやレポートを生成できます。

## Common Issues and Solutions
- **カレンダー データが欠如している:** 分割前に `timephasedDataFromTaskDuration` を呼び出していることを確認してください。  
- **ゼロ期間のセグメント:** 各分割区間がゼロでない期間を持つことを確認してください。ゼロの場合、ライブラリは無視します。  
- **ライセンス例外:** 有効なライセンスなしで実行すると、エクスポート ファイルに透かしが付くことがあります。

## Frequently Asked Questions
### 異なる期間でタスクを分割できますか？
はい、各パートの期間はプロジェクトの要件に合わせて調整可能です。

### Aspose.Tasks for Java はすべての Java バージョンと互換性がありますか？
Aspose.Tasks for Java は Java 8 以降でシームレスに動作するよう設計されており、広範な互換性を提供します。

### Aspose.Tasks for Java を無料で使用できますか？
Aspose.Tasks for Java は無料トライアルを提供しており、購入前に機能を試すことができます。

### Aspose.Tasks for Java のサポートはどこで受けられますか？
[Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) で支援を受け、コミュニティと交流できます。

### Aspose.Tasks for Java 用の一時ライセンスは必要ですか？
テストや評価目的であれば、[このリンク](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

---

**最終更新日:** 2026-02-26  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}