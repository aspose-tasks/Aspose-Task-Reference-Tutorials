---
date: 2026-02-23
description: Aspose.Tasks for Java を使用して、プロジェクトの開始日を設定し、タスクの期間を設定し、プロジェクトを MPP として保存する方法を学びます。親タスクと子タスクを効率的に管理します。
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでプロジェクト開始日を設定し、親子タスクを管理する
url: /ja/java/task-properties/parent-child-tasks/
weight: 24
---

}}

Make sure to keep blank lines as needed.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でプロジェクト開始日を設定し、親子タスクを管理する

## はじめに
効果的なタスクの整理は、成功するプロジェクト管理の基盤であり、**プロジェクト開始日を正しく設定すること**は、構造化されたスケジュールへの第一歩です。このチュートリアルでは、**プロジェクト開始日を設定**し、タスク期間を構成し、Aspose.Tasks for Java を使用して親子関係を管理する方法を紹介します。最後まで実施すれば、**プロジェクトを MPP として保存**し、タスクの完了率を更新し、実際のシナリオに合わせてタスクプロパティをカスタマイズできるようになります。

## クイック回答
- **プロジェクト開始日を設定するにはどうすればよいですか？** `proj.set(Prj.START_DATE, startDate);` を `Project` オブジェクトの初期化後に使用します。  
- **親タスクの下に子タスクを追加できますか？** はい – `parentTask.getChildren().add("Child Task")` を呼び出します。  
- **Aspose.Tasks はどの形式でファイルを保存しますか？** `SaveFileFormat.Mpp` を使用して **プロジェクトを MPP として保存**します。  
- **タスクの完了率を更新するにはどうすればよいですか？** タスクオブジェクトの `Tsk.PERCENT_COMPLETE` を設定します。  
- **一時ライセンスはどこで取得できますか？** FAQ にリンクされた一時ライセンスページをご覧ください。

## 前提条件
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
- Java プログラミングの基本的な理解。  
- Aspose.Tasks for Java ライブラリがインストールされていること。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から。  
- システムに Java 統合開発環境 (IDE) が設定されていること。

## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートします。これらのパッケージは Aspose.Tasks for Java の機能とシームレスに統合するために必要です。
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## 手順 1: プロジェクト開始日の設定
プロジェクトの開始日とその他の関連パラメータを設定します。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## 手順 2: 親タスク (Task 1) の追加
「Task 1」という名前の親タスクを作成し、**タスク期間の設定** を含むプロパティを構成します。
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## 手順 3: 子タスク付きの親タスク (Task 2) の追加
次に、別の親タスク「Task 2」を追加し、子タスク（Task 3 と Task 4）を含めます。
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## 手順 4: 子タスクの構成
Task 3 と Task 4 の開始日、期間、制約を指定します。
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## 手順 5: タスク完了率の更新
Task 3 と Task 4 の完了率を調整します – これが **タスク完了率の更新** 方法です。
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## 手順 6: プロジェクトの保存
最後に、適用した変更と共に **プロジェクトを MPP として保存** します。
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

このステップバイステップ ガイドは、Aspose.Tasks for Java を使用して親子タスクを効果的に管理する方法を示しています。プロジェクトの要件に合わせてさまざまな構成を試してみてください。

## なぜタスクプロパティをカスタマイズするのか？
開始日、期間、制約、完了率などのタスクプロパティをカスタマイズすることで、スケジュールの動作を細かく制御できます。リソースの可用性に合わせてタスクを調整したり、ビジネスルールを強制したりする場合でも、Aspose.Tasks を使用すればプログラムから **タスクプロパティをカスタマイズ** できます。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **開始日が適用されない** | `proj.set(Prj.START_DATE, …)` を `Project` オブジェクト作成 **後**、タスク追加 **前** に呼び出していることを確認してください。 |
| **子タスクが誤った制約を継承する** | Step 4 に示すように、各子タスクの `ConstraintType` と `ConstraintDate` を明示的に設定してください。 |
| **保存したファイルが MS Project で開けない** | 最新の Aspose.Tasks バージョンを使用し、`SaveFileFormat.Mpp` で保存していることを確認してください。 |
| **UI に完了率が反映されない** | `Tsk.PERCENT_COMPLETE` を設定した後、日付を再計算する必要がある場合は `proj.calculateTaskSchedule()` を呼び出してください。 |

## FAQ
### Aspose.Tasks for Java はさまざまなプロジェクトファイル形式に対応していますか？
はい、Aspose.Tasks for Java は MPP や XML などさまざまなプロジェクトファイル形式をサポートしています。

### このチュートリアルで扱っている以外のタスクプロパティもカスタマイズできますか？
もちろんです！Aspose.Tasks for Java はタスクプロパティの幅広いカスタマイズオプションを提供しています。

### Aspose.Tasks のサポートを受けられるコミュニティフォーラムはありますか？
はい、[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) でコミュニティサポートをご利用いただけます。

### Aspose.Tasks for Java の一時ライセンスはどこで取得できますか？
一時ライセンスは[here](https://purchase.aspose.com/temporary-license/) で取得できます。

### Aspose.Tasks for Java の包括的なドキュメントはどこにありますか？
ドキュメントは[here](https://reference.aspose.com/tasks/java/) にあります。

**追加の Q&A**

**Q: プログラムで一時ライセンスを取得するには？**  
A: 一時ライセンスファイルを `License license = new License(); license.setLicense("Aspose.Tasks.lic");` でロードします。

**Q: デフォルトのタスク期間単位を変更できますか？**  
A: はい – `proj.getDuration(value, TimeUnitType.YourChoice)` の `TimeUnitType` 引数を変更してください。

**Q: `SaveFileFormat.Mpp` を使用するにはどのバージョンの Aspose.Tasks が必要ですか？**  
A: 2022‑2026 のすべての最新バージョンで MPP 保存がサポートされています。リリースノートで破壊的変更がないか確認してください。

**最終更新日:** 2026-02-23  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}