---
date: 2026-08-08
description: Aspose.Tasks for Java を使用して、calendar ms project の設定方法、日々の作業時間の設定、週末の作業日を追加する方法を学びます。数行のコードでプロジェクトを
  XML として保存できます。
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: カレンダー ms project の設定方法と平日の定義
og_description: Aspose.Tasks for Java を使用して calendar ms project を設定し、平日を定義し、週末の作業日を追加します。ステップバイステップのチュートリアルに従い、XML
  として保存してください。
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Aspose.Tasks で calendar ms project を設定 – Java ガイド
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: カレンダー ms project の設定方法と平日の定義
url: /ja/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project のカレンダー設定と平日の定義方法

このチュートリアルでは、**how to set calendar ms project** をプログラムで行い、平日を定義し、Aspose.Tasks ライブラリ for Java を使用してカスタム稼働日を設定する方法を学びます。スケジューリングエンジンの構築、ERP システムとの統合、または Microsoft Project を開かずにプロジェクト計画を生成する必要がある場合でも、以下の手順でカレンダーの作成、日々の稼働時間の設定、週末の稼働日の追加を数行のコードで示します。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Tasks for Java。  
- **週末の稼働日を追加できますか？** はい – 土曜日と日曜日を稼働日としてマークするだけです。  
- **プロジェクトはどのように保存しますか？** `prj.save(..., SaveFileFormat.Xml)` を呼び出します。  
- **ライセンスは必要ですか？** 無料トライアルは評価に使用できますが、本番利用にはライセンスが必要です。  
- **サポートされている Java バージョンはどれですか？** Java 8 以上。

## set calendar ms project とは何ですか？
MS Project のカレンダーを設定すると、どの日が稼働日とみなされるか、1 日あたりの稼働時間、休日や全社的な休業などの特別な例外が決まります。この情報はタスクのスケジューリング、リソース割り当て、全体のプロジェクトタイムラインに影響し、計算が組織の実際の作業パターンを反映するようにします。

## カレンダー操作に Aspose.Tasks を使用する理由は？
Aspose.Tasks は Microsoft Project の UI を起動せずにカレンダーをプログラムで制御できます。Java をサポートする任意の OS 上で動作し、50 以上の入出力フォーマットに対応し、ファイル全体をメモリにロードせずに数百ページ規模のプロジェクトを処理できるため、サーバーサイドの自動化に最適です。

## 前提条件
- **Java Development Kit (JDK) 8+** – [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) からダウンロードしてください。  
- **Aspose.Tasks for Java** – 最新の JAR を [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) から取得してください。  
- Aspose.Tasks JAR をクラスパスに追加できる IDE またはビルドツール（Maven/Gradle）。

## パッケージのインポート
プロジェクト、カレンダー、稼働時間オブジェクトへのアクセスを提供するクラスをインポートします。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## ステップバイステップガイド

### 手順 1: プロジェクト インスタンスの作成
`Project` オブジェクトをインスタンス化します。これは操作対象となる MS Project ファイルを表します。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### 手順 2: 新しいカレンダーの定義
`Calendar` はプロジェクトの稼働時間、例外、休日の集合を表します。

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### 手順 3: 標準稼働日（月曜〜木曜）の追加
`WeekDay` は特定の曜日の稼働時間を定義します。

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### 手順 4: 週末の稼働日の追加
プロジェクトが週末にも実行される場合、土曜日と日曜日を通常の稼働日として追加します。これは **add weekend working days** を示す例です。

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### 手順 5: カスタム短時間稼働日（金曜）の設定
金曜日に午前シフト（9 am‑12 pm）と午後シフト（1 pm‑4 pm）を設定し、**set daily working hours** とカスタム短時間稼働日を示します。

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

### 手順 6: プロジェクトを XML として保存
`SaveFileFormat` はプロジェクト保存時にサポートされるファイル形式（XML や MPP など）を列挙します。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **作業時間が適用されない** | 各カスタム `WeekDay` で `setDayWorking(true)` が呼び出されていることを確認してください。 |
| **保存時にファイルが見つからない** | `dataDir` が既存のフォルダーを指しており、アプリケーションに書き込み権限があることを確認してください。 |
| **カレンダーがタスクに反映されない** | 新しく作成したカレンダーを `task.setCalendar(cal)` を使用してリソースまたはタスクに割り当てます。 |

## よくある質問

**Q: Aspose.Tasks for Java を使用してカスタムの非稼働日を定義できますか？**  
A: はい。非稼働日として扱いたい任意の `WeekDay` の `DayWorking` プロパティを `false` に設定します。

**Q: 休日や全社的な例外を追加するにはどうすればよいですか？**  
A: `CalendarException` オブジェクトを作成し、例外日付を指定して `cal.getExceptions()` に追加します。

**Q: ライブラリは古い MS Project バージョンと互換性がありますか？**  
A: 完全に対応しています。Aspose.Tasks は MPP、MPT、XML 形式を複数の Project バージョンでサポートします。

**Q: インポートしたプロジェクトの既存カレンダーを変更できますか？**  
A: `new Project("existing.mpp")` でプロジェクトをロードし、目的のカレンダーを取得して変更し、保存します。

**Q: Aspose.Tasks は繰り返しタスクも扱えますか？**  
A: はい、`RecurringTask` クラスを使用して繰り返しタスクの作成と編集が可能です。

## 結論
これで **how to set calendar ms project** の方法、平日の定義、週末の稼働日の追加、短時間の金曜スケジュールの構成を Aspose.Tasks for Java で実装できました。結果を XML として保存し、任意の Java ベースのプロジェクト管理ソリューションにカレンダー ロジックを統合してください。

---

**Last Updated:** 2026-08-08  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## 関連チュートリアル

- [Aspose.Tasks for Java を使用してプロジェクトにカレンダーを追加](/tasks/java/calendars/create/)
- [Aspose.Tasks で稼働日と稼働時間を決定](/tasks/java/calendars/working-hours/)
- [Aspose.Tasks でカレンダーに休日を追加し MPP として保存](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}