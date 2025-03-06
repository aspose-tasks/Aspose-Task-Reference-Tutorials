---
title: Aspose.Tasks で親タスクと子タスクを管理する
linktitle: Aspose.Tasks で親タスクと子タスクを管理する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してプロジェクト管理の効率を高めます。親タスクと子のタスクを段階的に管理する方法を学びます。今すぐ始めましょう！
weight: 24
url: /ja/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で親タスクと子タスクを管理する

## 導入
プロジェクト管理の分野では、効果的なタスクの組織化が非常に重要です。 Aspose.Tasks for Java は、親タスクと子タスクを効率的に管理するための堅牢なソリューションを提供します。このチュートリアルでは、Aspose.Tasks for Java を使用してプロジェクト タスクを効率化するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java プログラミングの基本的な理解。
-  Aspose.Tasks for Java ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
- システム上にセットアップされた Java 統合開発環境 (IDE)。
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。これらのパッケージにより、Aspose.Tasks for Java 機能とのシームレスな統合が容易になります。
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
## ステップ 1: プロジェクトの開始日を設定する
まず、プロジェクトの開始日とその他の関連パラメーターを設定します。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
//パッケージインポート用の追加コードをここに追加できます
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## ステップ 2: 親タスクの追加 (タスク 1)
「タスク 1」という名前の親タスクを作成し、そのプロパティを構成します。
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## ステップ 3: 親タスク (タスク 2) と子タスクを追加する
ここで、「タスク 2」という名前の別の親タスクを追加し、子タスク (タスク 3 とタスク 4) を含めます。
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
//子タスクをタスク 2 に追加する
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
//タスク 3 とタスク 4 の追加構成をここに追加できます
```
## ステップ 4: 子タスクを構成する
タスク 3 とタスク 4 の開始日、期間、制約を指定します。
```java
//タスク 3 の構成
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
//タスク 4 の構成
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## ステップ 5: タスク完了率を更新する
タスク 3 とタスク 4 の完了率を調整します。
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## ステップ 6: プロジェクトを保存する
最後に、変更を適用してプロジェクトを保存します。
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
このステップバイステップのガイドでは、Aspose.Tasks for Java を使用して親タスクと子タスクを効果的に管理する方法を説明します。プロジェクトの要件に合わせて、さまざまな構成を試してください。
## 結論
結論として、Aspose.Tasks for Java を使用すると、開発者はプロジェクト タスクを効率的に処理できるようになり、シームレスな編成と追跡が保証されます。概要を示した手順を実行して、プロジェクト管理機能を強化します。
## よくある質問
### Aspose.Tasks for Java はさまざまなプロジェクト ファイル形式と互換性がありますか?
はい、Aspose.Tasks for Java は、MPP や XML などのさまざまなプロジェクト ファイル形式をサポートしています。
### このチュートリアルで説明されている内容を超えてタスクのプロパティをカスタマイズできますか?
絶対に！ Aspose.Tasks for Java は、タスク プロパティの広範なカスタマイズ オプションを提供します。
### サポートを求めることができる Aspose.Tasks のコミュニティ フォーラムはありますか?
はい、次の場所にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティサポートのために。
### Aspose.Tasks for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Tasks for Java の包括的なドキュメントはどこで見つけられますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
