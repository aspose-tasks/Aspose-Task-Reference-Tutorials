---
date: 2026-07-29
description: Aspose.Tasks for Java を使用してプロジェクトカレンダーを作成し、平日の例外を定義し、祝日スケジュールを管理することで、非稼働日をスケジュールする方法を学びます。
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: 非稼働日をスケジュール – Asposeでプロジェクトカレンダーを作成
og_description: Aspose.Tasks for Java を使用して非稼働日をスケジュールします。平日を定義し、カレンダー例外を追加し、祝日スケジュールを効率的に管理する方法を学びます。
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: 非稼働日をスケジュール – Asposeでプロジェクトカレンダーを作成
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: 非稼働日をスケジュール – Asposeでプロジェクトカレンダーを作成
url: /ja/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 非稼働日をスケジュール – Aspose のプロジェクトカレンダー作成

### はじめに
プロジェクトで **非稼働日をスケジュール** する必要がある場合、祝日や特別シフト、一時的な閉鎖などをプロジェクト計画に直接モデル化できる必要があります。Aspose.Tasks for Java はカレンダー定義を完全に制御でき、実際のスケジュールを反映した例外を追加できます。このチュートリアルでは、カレンダー例外の平日を定義する正確な手順を順に説明し、プロジェクトのタイムラインを正確かつ信頼できるものに保ちます。最後には、**非稼働日スケジュール** 戦略がエンタープライズプロジェクト全体でどのように適用されるかも確認できます。

## クイック回答
- **「非稼働日をスケジュールする」とは何ですか？**  
  Aspose.Tasks を使用して、特定の日付を非稼働としてマークし、タスクの日付に自動的に影響を与えるカレンダーを作成することを意味します。  
- **サンプルを実行するのにライセンスは必要ですか？**  
  開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている IDE はどれですか？**  
  IntelliJ IDEA、Eclipse、NetBeans、または Java 8+ をサポートする任意の IDE。  
- **同じカレンダーに複数の例外を追加できますか？**  
  はい – 必要に応じて任意の数の `CalendarException` オブジェクトを追加できます。  
- **プロジェクトを保存できるファイル形式は何ですか？**  
  XML、MPP、その他 Aspose.Tasks がサポートする複数の形式。  

## Aspose.Tasks のプロジェクトカレンダーとは？
**プロジェクトカレンダー** は、Aspose.Tasks の最上位オブジェクトで、プロジェクトの稼働日と稼働時間を定義します。タスクの開始/終了日、リソース割り当て、全体のスケジュール計算に直接影響します。カレンダーをカスタマイズすることで、会社の祝日や週末勤務ポリシーなど、実際の制約をスケジュールに反映させることができます。

## カレンダー例外の平日を定義する理由は？
平日の例外を定義することで、プロジェクトエンジンはそれらの日を非稼働として扱い、タスクが自動的にその日にスケジュールされるのを防ぎ、祝日、メンテナンスウィンドウ、組織全体の特別シフトパターンなど、実際の制約に合わせてタイムラインを調整できます。

- **正確なタイムライン:** タスクは祝日やブラックアウト期間に配置されません。  
- **リソース計画:** リソースは有効な稼働日にのみ割り当てられ、過剰割り当てを防止します。  
- **コンプライアンス:** スケジュールは組織のポリシーや法定祝日カレンダーに自動的に従います。  

## カレンダー例外を使用した非稼働日スケジュール
**非稼働日スケジュール** を管理する場合、通常は祝日、メンテナンスウィンドウ、その他のブラックアウト期間のマスターリストがあります。これらの日付を `CalendarException` オブジェクトとして追加すると、クリティカルパス分析やリソース平準化など、すべての計算が自動的にこれらの制約を考慮します。この方法により、手動での日付調整が不要になり、スケジュールのずれリスクが低減されます。

## 前提条件
1. **Java Development Kit (JDK)** – バージョン 8 以上。  
2. **Aspose.Tasks for Java** – 公式の [Aspose.Tasks Java ダウンロードページ](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **IDE** – IntelliJ IDEA、Eclipse、NetBeans、または任意の Java 対応エディタ。  

## カレンダー例外を使用して非稼働日をスケジュールする方法

プロジェクトをロードし、カスタムカレンダーを作成し、目的の平日を非稼働としてマークする `CalendarException` オブジェクトを追加します。この一連のプロセスは数ステップで完了し、生成されたカレンダーはすべてのタスクスケジューリングロジックに自動的に影響します。

### 手順ガイド

### 手順 1: 必要なパッケージのインポート
日付処理のために、Aspose.Tasks のコアクラスと Java の `GregorianCalendar` が必要です。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### 手順 2: データディレクトリの定義
生成されたプロジェクトファイルの保存先を指定します。

```java
String dataDir = "Your Data Directory";
```

### 手順 3: Project インスタンスの作成
`Project` は、タスク、リソース、カレンダーなど、すべてのプロジェクトデータを保持する主要オブジェクトです。

```java
Project project = new Project();
```

### 手順 4: カレンダーの定義
`Calendar` は、プロジェクト内の稼働時間と非稼働時間のスケジュールを表します。

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### 手順 5: 平日例外の定義
`CalendarException` は、カレンダー内で非稼働としてマークされた期間を表します。

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### 手順 6: プロジェクトの保存
カスタムカレンダーとその例外を含むプロジェクトを XML ファイルに永続化します。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **例外日付が適用されない** | `setEnteredByOccurrences(false)` と正しい `FromDate/ToDate` の値を確認してください。 |
| **保存されたファイルが空** | `dataDir` が書き込み可能なフォルダを指しているか、ファイル名が `.xml` で終わっているかを確認してください。 |
| **カレンダーがタスクスケジューリングに反映されない** | `task.setCalendar(cal)` または `resource.setCalendar(cal)` を使用して、タスクまたはリソースにカレンダーを割り当ててください。 |

## よくある質問

- **Q: 同じカレンダー内で異なる平日に対して複数の例外を定義できますか？**  
  A: はい。各異なる期間またはルールごとに `cal.getExceptions()` に追加の `CalendarException` オブジェクトを追加してください。  

- **Q: Aspose.Tasks for Java はさまざまな Java IDE と互換性がありますか？**  
  A: もちろんです。このライブラリは IntelliJ IDEA、Eclipse、NetBeans、標準的な Java プロジェクトをサポートする任意の IDE で動作します。  

- **Q: 日次例外以外の例外タイプをカスタマイズできますか？**  
  A: はい。スケジュール要件に合わせて `CalendarExceptionType.Weekly`、`Monthly`、または `Yearly` を使用してください。  

- **Q: プロジェクト要件に基づいて例外を動的に処理するにはどうすればよいですか？**  
  A: 例外オブジェクトをプログラムで構築します。たとえば、データベースや設定ファイルから祝日の日付を読み取り、ループで `CalendarException` インスタンスを作成します。  

- **Q: Aspose.Tasks for Java のトライアル版はありますか？**  
  A: はい、[Aspose.Tasks Java ダウンロードページ](https://releases.aspose.com/tasks/java/) から無料トライアルをダウンロードできます。  

## 結論
これらの手順に従うことで、**非稼働日をスケジュール** する方法、つまりプロジェクトカレンダーを作成し、祝日や特別な非稼働期間を正確に反映する平日例外を定義する方法が分かります。適切なカレンダー設定は、現実的なスケジュール、リソース割り当て、プロジェクト全体の成功に不可欠です。カスタムカレンダーをタスクやリソースに割り当て、他の例外タイプを試すことで、あらゆるプロジェクト向けの包括的な **非稼働日スケジュール** を構築してください。

---

**最終更新日:** 2026-07-29  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks for Java を使用してプロジェクトにカレンダーを追加](/tasks/java/calendars/create/)
- [Aspose for Java でカレンダー例外を作成](/tasks/java/calendar-exceptions/add-remove/)
- [Aspose.Tasks を使用して MS Project でカレンダーを設定し平日を定義する方法](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}