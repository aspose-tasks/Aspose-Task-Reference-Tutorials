---
title: Aspose.Tasks でタスクを分割する
linktitle: Aspose.Tasks でタスクを分割する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks で Java のタスク管理をマスターしましょう!プロジェクトのタイムラインを最適化するためにタスクを効率的に分割する方法を学びます。ダウンロード中！
type: docs
weight: 29
url: /ja/java/task-properties/split-tasks/
---
## 導入
Java プロジェクトのタスク管理に苦労していますか? Aspose.Tasks for Java は、タスクを効率的に分割し、プロジェクト管理機能を強化するための強力なソリューションを提供します。このチュートリアルでは、Aspose.Tasks for Java を使用してタスクを分割するプロセスを説明し、プロジェクトのタイムラインとリソース割り当てを最適化するのに役立ちます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java Development Kit (JDK) がマシンにインストールされています。
-  Aspose.Tasks for Java ライブラリがダウンロードされ、プロジェクトに追加されました。からダウンロードできます。[Aspose.Tasks for Java ドキュメント](https://reference.aspose.com/tasks/java/).
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。
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
## ステップ 1: 新しいプロジェクトを作成する
まず、Aspose.Tasks ライブラリを使用して新しいプロジェクトを作成します。
```java
//新しいプロジェクトを作成する
Project splitTaskProject = new Project();
```
## ステップ 2: プロジェクト カレンダーを設定する
プロジェクトのカレンダー設定を設定してタイムラインを確立します。
```java
//標準カレンダーを入手する
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
//プロジェクトのカレンダー設定を行う
java.util.Calendar cal = java.util.Calendar.getInstance();
//... (例を続けます)
```
## ステップ 3: ルートタスクを追加する
ルート タスクをプロジェクトに追加します。
```java
//ルートタスク
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## ステップ 4: 分割する新しいタスクを追加する
分割する新しいタスクをプロジェクトに追加します。
```java
//新しいタスクを追加する
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## ステップ 5: リソース割り当てを作成する
タスクの新しいリソース割り当てを作成します。
```java
//新しいリソース割り当てを作成する
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## ステップ 6: タイムスケール データを生成する
リソース割り当てのタイムスケール データを生成します。
```java
//リソース割り当てのタイムスケール データを生成する
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## ステップ 7: タスクを分割する
タスクを複数の部分に分割します。
```java
//タスクを 3 つの部分に分割する
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
//... (例を続けます)
```
## 結論
おめでとう！ Aspose.Tasks for Java を使用してタスクを分割する方法を学習しました。この強力なライブラリは、Java プロジェクトのタスク管理を簡素化し、プロジェクトのタイムラインとリソース割り当てを最適化するための効率的なソリューションを提供します。
## よくある質問
### 異なる期間のタスクを分割できますか?
はい、プロジェクトの要件に応じてタスクの期間を調整できます。
### Aspose.Tasks for Java はすべての Java バージョンと互換性がありますか?
Aspose.Tasks for Java は、さまざまな Java バージョンとシームレスに動作し、互換性を確保するように設計されています。
### Aspose.Tasks for Java を無料で使用できますか?
Aspose.Tasks for Java は無料トライアルを提供しており、購入する前にその機能を調べることができます。
### Aspose.Tasks for Java のサポートを受けるにはどうすればよいですか?
訪問[Aspose.Tasks for Java サポート フォーラム](https://forum.aspose.com/c/tasks/15)支援を受けたり、コミュニティとつながったりするためです。
### Aspose.Tasks for Java の一時ライセンスは必要ですか?
一時ライセンスは次から取得できます。[このリンク](https://purchase.aspose.com/temporary-license/)テストと評価の目的で。