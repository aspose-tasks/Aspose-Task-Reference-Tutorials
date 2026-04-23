---
date: 2026-02-20
description: Aspose.Tasks for Java を使用して、プロジェクトにタスクを追加し、期間を管理する方法を探ります。期間の設定方法と、期間を簡単に変換する方法を学びます。
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでプロジェクトにタスクを追加し、期間を管理する
url: /ja/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でプロジェクトにタスクを追加し、期間を管理する

## Introduction
このチュートリアルでは、**プロジェクトにタスクを追加する方法**と、Aspose.Tasks for Java を使用してタスクの期間を制御する方法を学びます。新しいプロジェクト管理ツールを構築する場合でも、既存のソリューションを拡張する場合でも、タスク期間の取り扱いをマスターすることは、正確なスケジューリングとレポート作成に不可欠です。

## Quick Answers
- **“add task to project” とは何ですか？** プロジェクトのルートまたは特定のサマリータスクの下に新しいタスクオブジェクトを作成します。  
- **期間を表すクラスはどれですか？** `com.aspose.tasks.Duration`。  
- **期間はどう設定しますか？** `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))` を使用します。  
- **期間を別の単位に変換できますか？** はい、`duration.convert(TimeUnitType.Hour)` など、任意の `TimeUnitType` を呼び出します。  
- **本番環境でライセンスは必要ですか？** 商用利用には有効な Aspose.Tasks ライセンスが必要です。

## What is “add task to project”?
プロジェクトにタスクを追加するとは、`Task` オブジェクトを作成し、プロジェクトのタスク階層に結び付けることを意味します。この操作は、タスクに作業、リソース、または期間を定義する前の最初のステップです。

## Why manage task durations?
正確な期間は、現実的なタイムライン、リソース配分、クリティカルパス分析を実現します。Aspose.Tasks を使用すれば、期間の設定、取得、変換、調整をプログラムから行えるため、プロジェクトスケジュールを完全にコントロールできます。

## Prerequisites
開始する前に、以下を用意してください。

- Java Development Kit (JDK): マシンに Java がインストールされていることを確認してください。ダウンロードは [here](https://www.oracle.com/java/technologies/javase-downloads.html) から可能です。  
- Aspose.Tasks Library: Aspose.Tasks ライブラリをダウンロードし、プロジェクトに組み込んでください。ライブラリは [here](https://releases.aspose.com/tasks/java/) にあります。

## Import Packages
Java プロジェクトで Aspose.Tasks を使用するために必要なパッケージをインポートします。
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step 1: Set Up Your Project
```java
// Create a new project
Project project = new Project();
```

## Step 2: Add a New Task (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## How to set duration
タスクが作成されたので、期間を定義できます。デフォルトでは、期間は日単位で表されます。

## Step 3: Get and Convert Task Duration
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## How to convert duration
`convert` メソッドを使用すると、`Duration` をある `TimeUnitType` から別の `TimeUnitType`（例: 日 → 時間、週 → 日）へ変換できます。

## Step 4: Update Task Duration to 1 Week
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Step 5: Decrease Task Duration
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

これらの手順を実行することで、**プロジェクトにタスクを追加し**、Aspose.Tasks for Java を使って期間を管理できました。

## Common Pitfalls & Tips
- **落とし穴:** 演算を行う前に期間を変換し忘れると、結果が正しくありません。必ず `duration.getTimeUnit()` で単位を確認してください。  
- **ヒント:** 後から変換するのではなく、`project.getDuration(value, TimeUnitType)` を使って目的の単位で期間を作成しましょう。  
- **落とし穴:** 負の期間を設定すると例外がスローされます。入力値は必ず検証してください。

## Conclusion
本ガイドでは、**プロジェクトにタスクを追加する方法**、デフォルト期間の取得、**期間の設定**、および **期間の単位変換** について説明しました。これらのテクニックを活用して、より正確なプロジェクト計画を実現してください。

## FAQs
### Aspose.Tasks はすべての Java バージョンと互換性がありますか？
Aspose.Tasks は Java 6 以降のバージョンと互換性があります。

### 商用プロジェクトで Aspose.Tasks を使用できますか？
はい、個人利用でも商用利用でも Aspose.Tasks を使用できます。ライセンスの詳細は [here](https://purchase.aspose.com/buy) をご覧ください。

### 追加のサポートやリソースはどこで入手できますか？
コミュニティサポートやディスカッションは [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) でご利用いただけます。

### テスト目的の一時ライセンスはどこで取得できますか？
テストおよび評価用の一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Aspose.Tasks の無料トライアルはありますか？
はい、購入前に Aspose.Tasks を試すための無料トライアルは [here](https://releases.aspose.com/) で利用可能です。

## Frequently Asked Questions

**Q: 設定したタスクの期間を後から変更するにはどうすればよいですか？**  
A: `task.get(Tsk.DURATION)` で現在の期間を取得し、`add`、`subtract`、`convert` などで変更した後、`task.set(Tsk.DURATION, newDuration)` で再設定します。

**Q: 分単位で期間を設定できますか？**  
A: はい、`project.getDuration(value, TimeUnitType.Minute)` を使用してください。

**Q: 期間を変更するとタスクの開始日と終了日も自動的に更新されますか？**  
A: プロジェクトのスケジューリングモードが自動に設定されている場合のみ自動更新されます。手動の場合は `project.calculateCriticalPath()` でスケジュールを再計算する必要があります。

**Q: 期間を数値だけで取得することは可能ですか？**  
A: `duration.getTimeSpan()` を呼び出すと、現在の時間単位で数値が取得できます。

**Q: 現在の期間より大きく減算した場合はどうなりますか？**  
A: API は `ArgumentOutOfRangeException` をスローします。結果の期間が正の値になるよう必ず検証してください。

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}