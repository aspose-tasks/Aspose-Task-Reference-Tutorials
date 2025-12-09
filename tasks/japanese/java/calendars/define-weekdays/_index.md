---
date: 2025-12-02
description: Aspose.Tasks for Java を使用して、カレンダーの設定、MS Project の平日の定義、カスタム作業日の設定方法を学びましょう。数行のコードでプロジェクトを
  XML として保存できます。
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して MS Project のカレンダーを設定し、平日を定義する方法
url: /ja/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Projectでカレンダーを設定し、平日を定義する方法（Aspose.Tasks使用）

## Introduction
このチュートリアルでは、**カレンダーの設定方法** をプログラムで行い、Aspose.Tasks for Java ライブラリを使用して Microsoft Project ファイル内の平日を定義する方法を学びます。標準の作業週を作成したり、週末の作業日を追加したり、短い金曜日スケジュールを設定したりする必要がある場合でも、本ガイドはプロジェクトの作成から XML 形式での保存まで、すべての手順を丁寧に案内します。

## Quick Answers
- **必要なライブラリは？** Aspose.Tasks for Java  
- **週末の作業日を追加できますか？** はい – 土曜日と日曜日を作業日として追加するだけです。  
- **プロジェクトはどのように保存しますか？** `prj.save(..., SaveFileFormat.Xml)` を使用します。  
- **ライセンスは必要ですか？** 評価用の無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **必要な Java バージョンは？** Java 8 以上。

## What is “how to set calendar” in the context of MS Project?
MS Project におけるカレンダー設定とは、作業日や作業時間、祝日などの例外を定義することを指します。このカレンダーはタスクのスケジューリング、リソース割り当て、全体的なプロジェクト期間に影響を与えます。

## Why use Aspose.Tasks for calendar manipulation?
- **Full control** – UI を開かずにプログラムからカレンダーを作成、変更、削除できます。  
- **Cross‑platform** – Java をサポートする任意の OS で動作します。  
- **Supports all file formats** – MPP、MPT、XML をサポートしているため、*save project as XML* して他システムとの連携が容易です。  
- **No COM dependencies** – Microsoft Project Interop ライブラリとは異なり COM 依存がありません。

## Prerequisites
開始する前に以下を用意してください。

1. **Java Development Kit (JDK) 8+** – [Oracle のウェブサイト](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)からダウンロード。  
2. **Aspose.Tasks for Java** – [Aspose.Tasks ダウンロードページ](https://releases.aspose.com/tasks/java/)から最新の JAR を取得。  
3. IDE またはビルドツール（Maven/Gradle）で Aspose.Tasks JAR をプロジェクトのクラスパスに追加。

## Import Packages
まず、必要なクラスをインポートします。これらのインポートにより、プロジェクト、カレンダー、作業時間オブジェクトにアクセスできます。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Project Instance
新しい `Project` オブジェクトを作成します。このオブジェクトは編集対象の MS Project ファイルを表します。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Step 2: Define a New Calendar
プロジェクトに新しいカレンダーを追加します。複数のカレンダーを扱う場合は、分かりやすい名前を付けると便利です。

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Step 3: Add Standard Working Days (Monday‑Thursday)
組み込みヘルパー `WeekDay.createDefaultWorkingDay` を使用して、コア作業週のデフォルト 9 am‑5 pm スケジュールを設定します。

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Step 4: Add Weekend Working Days
プロジェクトが週末にも稼働する場合は、土曜日と日曜日を通常の作業日として追加します。これが **add weekend working days** の例です。

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Step 5: Set a Custom Short Working Day (Friday)
ここでは金曜日の **set custom working days** として、午前シフト（9 am‑12 pm）と午後シフト（1 pm‑4 pm）を設定します。

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Step 6: Save the Project as XML
最後に変更を永続化します。`SaveFileFormat.Xml` オプションを使用すると **save project as XML** が可能で、他ツールとの統合に便利です。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Working times not applied** | カスタム `WeekDay` に対して `setDayWorking(true)` が呼び出されていることを確認してください。 |
| **File not found when saving** | `dataDir` が既存のフォルダーを指しているか、書き込み権限があるかを確認してください。 |
| **Calendar not reflected in tasks** | `task.setCalendar(cal)` を使用して、作成したカレンダーをリソースまたはタスクに割り当ててください。 |

## Frequently Asked Questions

**Q: Can I define custom non‑working days using Aspose.Tasks for Java?**  
A: はい。任意の `WeekDay` の `DayWorking` プロパティを `false` に設定すれば、非作業日として扱えます。

**Q: How can I add holidays or company‑wide exceptions?**  
A: `CalendarException` オブジェクトを作成し、例外日付を指定して `cal.getExceptions()` に追加します。

**Q: Is the library compatible with older MS Project versions?**  
A: 完全に対応しています。Aspose.Tasks は複数バージョンの MPP、MPT、XML フォーマットをサポートしています。

**Q: Can I modify an existing calendar in an imported project?**  
A: `new Project("existing.mpp")` でプロジェクトを読み込み、目的のカレンダーを取得して変更し、保存できます。

**Q: Does Aspose.Tasks handle recurring tasks as well?**  
A: はい、`RecurringTask` クラスを使用して繰り返しタスクの作成・編集が可能です。

## Conclusion
これで **カレンダーの設定方法**、**MS Project の平日定義**、週末作業日の追加、短い金曜日スケジュールの作成方法をすべて Aspose.Tasks for Java で実装できました。結果を XML として保存し、任意の Java ベースのプロジェクト管理ソリューションにカレンダー ロジックを統合してください。

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}