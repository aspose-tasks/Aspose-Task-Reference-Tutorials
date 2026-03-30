---
date: 2026-02-28
description: Aspose.Tasks for Java を使用して、分、日、時間、週、月単位で期間を取得する方法を学びましょう。コード例付きの詳細ガイドです。
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して異なる単位で期間を取得する方法
url: /ja/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でさまざまな単位の期間を取得する方法

## Introduction
タスクの **期間の取得方法** を理解することは、プロジェクト管理ワークフローの重要な要素です。細かい追跡のために分単位が必要でも、上位レベルの計画のために月単位が必要でも、Aspose.Tasks for Java を使用すれば変換は簡単です。このチュートリアルでは、タスクの期間を分、日、時間、週、月単位で取得する方法を順を追って説明し、各単位が実務プロジェクトでどのように役立つかを解説します。

## Quick Answers
- **「期間の取得方法」とは何ですか？** タスクの時間幅を抽出し、必要な単位に変換するプロセスです。  
- **どの API メソッドが変換を実行しますか？** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`。  
- **コード実行にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **カスタム単位に変換できますか？** 変換をチェーンしたり、`TimeSpan` を使用してカスタム計算が可能です。  
- **コードは Java 17 と互換性がありますか？** はい、Aspose.Tasks は Java 8 以降のバージョンをサポートしています。

## What is “how to get duration” in Aspose.Tasks?
Aspose.Tasks はタスクの長さを `Duration` オブジェクトとして保持します。`convert` メソッドに `TimeUnitType`（Minute、Hour、Day、Week、Month）を指定することで、同じ基礎値を希望の単位で取得できます。この柔軟性により、レポート作成や計算、他システムへのデータ連携を手動で計算することなく実現できます。

## Why use Aspose.Tasks for duration conversion?
- **Accuracy:** カレンダー例外、稼働時間、非標準カレンダーを自動的に処理します。  
- **Performance:** 1 行の変換でループやカスタムパースが不要です。  
- **Portability:** Windows、Linux、macOS いずれの環境でも同様に動作します。  
- **Integration:** 既存の Aspose.Tasks を使用している Java アプリケーションにシームレスに組み込めます。

## Prerequisites
コードに入る前に、以下が揃っていることを確認してください。

- Java Development Kit (JDK) がインストール済み  
- Aspose.Tasks for Java ライブラリ。ダウンロードは[こちら](https://releases.aspose.com/tasks/java/)  
- Java プログラミングの基本的な知識

## Import Packages
Java プロジェクトに Aspose.Tasks ライブラリを追加し、コード冒頭に次のインポート文を記述します。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step 1: Set Up Your Project
好きな IDE（IntelliJ、Eclipse、VS Code など）で新規 Java プロジェクトを作成し、Aspose.Tasks の JAR をプロジェクトのクラスパスに追加します。これにより、コンパイル時に上記クラスが利用可能になります。

## Step 2: Read Project Template
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

`"Your Document Directory"` を、`.xml` または `.mpp` プロジェクトファイルが格納されている実際のフォルダーに置き換えてください。

## Step 3: Retrieve a Task
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

`getById(1)` は ID が 1 のタスクを取得します。別のタスクを対象にしたい場合は ID を変更してください。

## Step 4: Duration in Minutes – How to get duration in minutes?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

`mins` 変数にタスクの長さが分単位で格納されます。

## Step 5: Duration in Days – How to get duration in days?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

日単位の粒度が必要なレポートやリソース割り当てでこの値を使用します。

## Step 6: Duration in Hours – How to get duration in hours?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

時間単位はタイムシートや、1 日をシフトに分割して管理したいときに便利です。

## Step 7: Duration in Weeks – How to get duration in weeks?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

週単位は上位レベルのガントチャートやマイルストーン計画でよく使用されます。

## Step 8: Duration in Months – How to get duration in months?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

月単位の期間は、プロジェクトフェーズを会計期間と合わせる際に役立ちます。

## Common Issues and Solutions
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `NullPointerException` on `task` | Wrong task ID or missing children | Verify the task ID exists using `project.getRootTask().getChildren()` |
| Unexpected values (e.g., 0) | Project uses a custom calendar with non‑working days | Ensure the project’s calendar is correctly defined or use `project.getCalendar()` to inspect it |
| Conversion returns fractional weeks | Weeks are calculated based on the project’s default week length (usually 5 days) | Multiply by 5 if you need calendar weeks, or adjust the calendar settings |

## Frequently Asked Questions
### Q: Can I use Aspose.Tasks for Java with any Java IDE?
A: Yes, Aspose.Tasks for Java is compatible with any Java Integrated Development Environment (IDE).

### Q: How can I obtain a task's ID in a Microsoft Project file?
A: You can inspect the project file manually or call `project.getRootTask().getChildren()` and iterate through the collection to read each task’s `ID`.

### Q: Is Aspose.Tasks suitable for handling large‑scale projects?
A: Absolutely. Aspose.Tasks is designed to efficiently process projects with thousands of tasks and resources.

### Q: Where can I find further documentation?
A: Visit the [documentation](https://reference.aspose.com/tasks/java/) for comprehensive API references, code samples, and best‑practice guides.

### Q: Can I try Aspose.Tasks for Java before purchasing?
A: Yes, you can explore a [free trial](https://releases.aspose.com/) to evaluate its capabilities.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}