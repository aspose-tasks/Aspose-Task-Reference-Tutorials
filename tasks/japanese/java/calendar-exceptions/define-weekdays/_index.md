---
date: 2026-01-28
description: Aspose.Tasks for Java を使用して、プロジェクト カレンダーの作成方法、カレンダー例外の平日設定方法、そして非稼働日スケジュールの管理方法を学びましょう。
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Asposeでプロジェクトカレンダーを作成 – カレンダー例外の曜日を定義
url: /ja/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクト カレンダー Aspose の作成 – カレンダー例外の平日を定義する

### Introduction
**create project calendar aspose** が必要なときは、祝日や特別シフト、臨時休業といった標準外の稼働日をモデル化できなければなりません。Aspose.Tasks for Java はカレンダー定義をフルコントロールできる機能を提供し、実際のスケジュールを反映した例外を追加できます。本チュートリアルでは、カレンダー例外の平日を定義する具体的な手順を順を追って解説し、プロジェクトのタイムラインを正確かつ信頼できるものにします。最後には、あらゆるエンタープライズ プロジェクト向けの **non‑working days schedule** 戦略全体にどのように組み込むかも示します。

## Quick Answers
- **“create project calendar aspose” とは何ですか？**  
  Aspose.Tasks を使用して、タスクのスケジューリングを制御するカスタム カレンダー オブジェクトを作成することを指します。
- **サンプルを実行するのにライセンスは必要ですか？**  
  開発目的であれば無料トライアルで動作しますが、製品環境では商用ライセンスが必要です。
- **対応している IDE はどれですか？**  
  IntelliJ IDEA、Eclipse、NetBeans、または Java 8+ に対応した任意の IDE。
- **同じカレンダーに複数の例外を追加できますか？**  
  はい、必要なだけ `CalendarException` オブジェクトを追加できます。
- **プロジェクトを保存できるファイル形式は何ですか？**  
  XML、MPP、その他 Aspose.Tasks がサポートする多数の形式。

## What is a Project Calendar in Aspose.Tasks?
**プロジェクト カレンダー** は、プロジェクトの稼働日と稼働時間を定義します。タスクの開始/終了日、リソース割り当て、全体のスケジュール計算に影響を与えます。カレンダーをカスタマイズすることで、会社の祝日や週末作業ポリシーなど、実際の制約をスケジュールに反映させることができます。

## Why define weekdays for calendar exceptions?
- **正確なタイムライン**：非稼働日としてマークされた日にはタスクがスケジュールされません。  
- **リソース計画**：有効な稼働日のみでリソースが割り当てられます。  
- **コンプライアンス**：組織の方針や法定祝日とスケジュールを合わせられます。

## Non‑working Days Schedule with Calendar Exceptions
**non‑working days schedule** を管理する場合、祝日・メンテナンスウィンドウ・ブラックアウト期間などのマスタ一覧があります。これらの日付を `CalendarException` オブジェクトとして追加すれば、クリティカルパス分析やリソース平準化など、すべての計算が自動的にその制約を考慮します。この方法により手動での日付調整が不要になり、スケジュールのずれリスクが大幅に低減します。

## Prerequisites
開始する前に以下を用意してください。

1. **Java Development Kit (JDK)** – バージョン 8 以上。  
2. **Aspose.Tasks for Java** – 公式の [Aspose.Tasks Java ダウンロードページ](https://releases.aspose.com/tasks/java/) から取得。  
3. **IDE** – IntelliJ IDEA、Eclipse、NetBeans、または Java 対応エディタ。

## How to create project calendar aspose – Define weekdays for calendar exceptions

### Step‑by‑Step Guide

### Step 1: Import Required Packages
カレンダー定義に必要な Aspose.Tasks のコアクラスと、日付処理用の Java `GregorianCalendar` をインポートします。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Step 2: Define the Data Directory
生成されたプロジェクト ファイルの保存先ディレクトリを指定します。

```java
String dataDir = "Your Data Directory";
```

### Step 3: Create a Project Instance
新しい `Project` オブジェクトをインスタンス化します。これがカレンダーを含むすべてのプロジェクト データのコンテナになります。

```java
Project project = new Project();
```

### Step 4: Define a Calendar
プロジェクトにカスタム カレンダーを追加します。このカレンダーが例外情報を保持します。

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Step 5: Define Weekdays Exception
例として、12 月最終週（**2009 年 12 月 24 日**〜**2009 年 12 月 31 日**）を非稼働日とする `CalendarException` を作成します。例外は日単位のタイプとして設定し、該当期間の作業を無効化します。

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Step 6: Save the Project
カスタム カレンダーとその例外を含むプロジェクトを XML ファイルとして永続化します。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Exception dates not applied** | `setEnteredByOccurrences(false)` と正しい `FromDate/ToDate` の設定を確認してください。 |
| **Saved file is empty** | `dataDir` が書き込み可能なフォルダーを指しているか、ファイル名が `.xml` で終わっているかを確認してください。 |
| **Calendar not reflected in task scheduling** | タスクやリソースに `task.setCalendar(cal)` または `resource.setCalendar(cal)` でカレンダーを割り当てます。 |

## Frequently Asked Questions

**Q: 同じカレンダー内で異なる平日の例外を複数定義できますか？**  
A: はい。`cal.getExceptions()` に対して追加の `CalendarException` オブジェクトをそれぞれの期間やルールごとに追加してください。

**Q: Aspose.Tasks for Java はさまざまな Java IDE と互換性がありますか？**  
A: もちろんです。IntelliJ IDEA、Eclipse、NetBeans、標準的な Java プロジェクトをサポートする任意の IDE で利用できます。

**Q: 日次以外の例外タイプもカスタマイズできますか？**  
A: はい。`CalendarExceptionType.Weekly`、`Monthly`、`Yearly` などを使用して、スケジュール要件に合わせた例外を作成できます。

**Q: プロジェクト要件に応じて例外を動的に処理するには？**  
A: 例外オブジェクトをプログラムで生成します。たとえば、データベースや設定ファイルから祝日一覧を読み込み、ループ内で `CalendarException` インスタンスを作成します。

**Q: Aspose.Tasks for Java のトライアル版はありますか？**  
A: はい、[Aspose.Tasks Java ダウンロードページ](https://releases.aspose.com/tasks/java/) から無料トライアルをダウンロードできます。

## Conclusion
この手順に従うことで、**create project calendar aspose** を実現し、祝日や特別な非稼働期間を正確に反映した平日例外を定義できました。カレンダー設定は、現実的なスケジュール、リソース割り当て、プロジェクト全体の成功に不可欠です。カスタム カレンダーをタスクやリソースに適用したり、他の例外タイプを試したりして、あらゆるプロジェクト向けの包括的な **non‑working days schedule** を構築してください。

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}