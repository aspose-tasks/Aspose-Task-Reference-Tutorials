---
date: 2026-02-28
description: Aspose.Tasks for Java を使用してタスクの時間別データを管理する方法を学び、ライブラリをダウンロードし、無料で試して、プロジェクト追跡を効率化しましょう。
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用してタスクの時間別データを管理する方法 (Java)
url: /ja/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用したタスクの時間分割データの使用方法

## Introduction
プロジェクトスケジュールをしっかり管理したい **Aspose の使い方** をお探しなら、ここが最適です。タスクの時間分割データを正確に追跡することは、プロジェクト管理の成功に欠かせない要素であり、Aspose.Tasks for Java はそのプロセスを自動化するためのツールを提供します。本チュートリアルでは、プロジェクトの作成、リソースの割り当て、ベースラインの設定、そして最終的に時間分割データを取得・表示するまでの、エンドツーエンドの完全な例を順を追って解説します。

## Quick Answers
- **「時間分割データ」とは何ですか？** 時間間隔（日、週、月）ごとに分割されたデータで、プロジェクト期間中の作業量、コスト、または残作業量を示します。  
- **どのライブラリがこの機能を提供しますか？** Aspose.Tasks for Java。  
- **サンプルを実行するのにライセンスは必要ですか？** 開発段階では無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **必要な Java バージョンは？** Java 8 以上。  
- **結果を Excel にエクスポートできますか？** はい。`TimephasedData` コレクションをイテレートして、任意の形式に書き出すことができます。

## What is Task Timephased Data?
タスクの時間分割データは、プロジェクトカレンダーの各時間スライスに対してタスクに割り当てられた作業量（またはコスト）を表します。これにより、作業の分布状況や過剰割り当ての有無、計画と実績の比較が容易になります。

## Why Use Aspose.Tasks to Manage Timephased Data?
- **Full control** – Microsoft Project を開かずに、プログラムから時間分割情報の作成、変更、クエリが可能です。  
- **Cross‑platform** – Java が動作する任意の OS で利用できます。  
- **No COM dependencies** – サーバーサイドの自動化に最適です。  
- **Rich API** – ベースライン、作業コンター、カスタムフィールドを標準でサポートします。

## Prerequisites
コードに取り掛かる前に、以下を準備してください。

- **Java Development Environment** – JDK 8 以上がインストールされ、`JAVA_HOME` が設定されていること。  
- **Aspose.Tasks for Java Library** – Aspose.Tasks ライブラリをダウンロードし、プロジェクトに組み込んでください。ライブラリは [here](https://releases.aspose.com/tasks/java/) から入手できます。  
- **Document Directory** – サンプルプロジェクトファイル（`project.xml`）の読み書きを行うフォルダーを用意します。

## Import Packages
Java プロジェクトで必要な Aspose.Tasks クラスをインポートします:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explanation:* `Project` インスタンスを作成し、目的の開始日で `Calendar` を初期化し、プロジェクトの `START_DATE` プロパティに割り当てます。

## Step 2: Define Task and Resource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explanation:* ルートタスクの下に **Task** という名前の新しいタスクを追加します。また、**Rsc** というリソースを作成し、標準レートと残業レートを設定します。

## Step 3: Set Task Duration
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explanation:* タスクの期間を **6 日** に設定します。

## Step 4: Assign Resource to Task
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explanation:* 前述のリソースを `ResourceAssignment` を介してタスクにリンクします。

## Step 5: Configure Resource Assignment
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explanation:* アサインメントの停止日と再開日（プレースホルダー値）を設定し、**Back‑Loaded** 作業コンターを適用します。これにより、作業がアサインメントの後半に集中します。

## Step 6: Set Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Explanation:* ベースラインを取得することで、後で計画値と実績値を比較できるようになります。

## Step 7: Update Task Completion
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explanation:* タスクを **50 % 完了** とマークし、残作業量の計算に反映させます。

## Step 8: Retrieve Timephased Data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explanation:* この呼び出しは、プロジェクトの時間間隔ごとに分割された **残作業量** を取得します。

## Step 9: Display Timephased Data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explanation:* 時間分割エントリの数と最初のエントリの値を単純に出力します。実務ではリストをイテレートしてレポートや UI にエクスポートすることになるでしょう。

## Common Issues and Solutions
- **`getTimephasedData` で NullPointerException が発生** – メソッド呼び出し前にアサインメントの `START` と `FINISH` が設定されていることを確認してください。  
- **作業コンターが正しくない** – 選択した `WorkContourType` がスケジューリング戦略と合致しているか確認してください。`BackLoaded` はオプションの一つです。  
- **ベースラインが変更を反映しない** – タスク、リソース、アサインメントを定義した **後** に `project.setBaseline` を呼び出す必要があります。

## Frequently Asked Questions
### Q: Aspose.Tasks for Java は任意の Java プロジェクトで使用できますか？
A: はい、Aspose.Tasks for Java はすべての Java ベースのプロジェクトで互換性があります。

### Q: Aspose.Tasks for Java の追加サポートはどこで得られますか？
A: サポートやディスカッションは [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) をご利用ください。

### Q: Aspose.Tasks for Java の無料トライアルはありますか？
A: はい、無料トライアルは [here](https://releases.aspose.com/) からお試しいただけます。

### Q: Aspose.Tasks for Java の一時ライセンスはどこで取得できますか？
A: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得可能です。

### Q: Aspose.Tasks for Java の購入先はどこですか？
A: 購入は [here](https://purchase.aspose.com/buy) から行えます。

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}