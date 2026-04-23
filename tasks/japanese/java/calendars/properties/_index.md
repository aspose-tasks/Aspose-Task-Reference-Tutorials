---
date: 2026-02-07
description: Aspose.Tasks を使用して、プロジェクト カレンダー（Java）の設定方法と MS Project のカレンダー プロパティの管理方法を学びましょう。カレンダーの稼働時間を表示し、スケジュールをカスタマイズするステップバイステップ
  ガイドです。
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使って Java でプロジェクト カレンダーを設定する方法
url: /ja/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用した Java のプロジェクト カレンダー設定方法

## Introduction
このチュートリアルでは、Aspose.Tasks for Java ライブラリを使用して **how to set project calendar java** をプログラムで設定する方法を学びます。カレンダーのプロパティを制御することで、**display calendar working hours** を表示したり、カスタムの作業日を定義したり、プロジェクトスケジュールを実際の制約に合わせて調整できます。環境構築からカレンダーの列挙、プロパティの取得まで、すべての手順を詳しく解説するので、アプリケーション内で **manage ms project calendar** 設定を自信を持って行えるようになります。

## Quick Answers
- **What does “set project calendar” mean?** MS Project ファイル内のカレンダーの作業時間、ベースカレンダー、日種別を作成または更新することを指します。  
- **Which library is required?** Aspose.Tasks for Java（最新バージョン）。  
- **Do I need a license?** 開発段階では無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **Can I display calendar working hours?** はい。各 `WeekDay` を読み取ることで、すべての日種別の作業時間を出力できます。  
- **Is this compatible with Maven/Gradle?** 完全に対応しています。Aspose.Tasks の JAR を依存関係として追加してください。

## How to Set Project Calendar Java
このセクションでは、主要キーワードである **set project calendar java** の具体的な手順を直接解説します。カレンダーの作業日を変更したり、Java スタイルで作業時間を計算したりする方法をカバーします。

## What Is a Project Calendar?
プロジェクト カレンダーは、タスク、リソース、全体のプロジェクト タイムラインに対する作業日と作業時間を定義します。MS Project では、カレンダーはベース カレンダーから継承でき、各日種別（例: **Standard**, **Non‑working**）は独自の作業時間を持ちます。これらの設定をプログラムで管理することで、手動編集なしに動的なスケジュール調整が可能になります。

## Why Manage MS Project Calendar Programmatically?
- **Automation:** 多数のプロジェクトに対してスクリプト一つでカレンダーを調整できます。  
- **Consistency:** 組織全体の作業時間ポリシーを統一して適用できます。  
- **Integration:** カレンダーを外部システム（HR、ERP）と同期できます。  
- **Visibility:** **display calendar working hours** をすぐに出力でき、レポートやデバッグに便利です。  
- **Flexibility:** **modify calendar working days** や例外をリアルタイムで追加できます。

## Prerequisites
開始する前に以下を用意してください。

- **Java Development Kit (JDK) 8+** がインストールされ、`JAVA_HOME` が設定済みであること。  
- **Aspose.Tasks for Java** ライブラリを [download page](https://releases.aspose.com/tasks/java/) から取得し、JAR をプロジェクトのクラスパスまたは Maven/Gradle の依存関係に追加します。  

## Import Packages
チュートリアル全体で使用する Aspose.Tasks のコアクラスをインポートします。

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up the Data Directory
プロジェクト ファイルが格納されているフォルダーを定義します。プレースホルダーは実際のパスに置き換えてください。

```java
String dataDir = "Your Data Directory";
```

## Step 2: Define Time Units
作業時間はミリ秒で表現されます。再利用可能な定数を定義するとコードが読みやすくなり、**calculate working hours java** を正確に行えます。

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: Load Project Data
既存の MS Project XML ファイル（`.xml` または `.mpp`）を読み込み、`Project` インスタンスを作成します。これにより、ファイル内のすべてのカレンダーにアクセスできます。

```java
Project project = new Project(dataDir + "project.xml");
```

## Iterate Through Calendars Java
ここではすべてのカレンダーをループし、UID、名前、ベース カレンダー、各日種別の作業時間を出力します。これにより **how to set project calendar java** の値設定と **display calendar working hours** の取得方法が分かります。

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### What This Code Does
- **Filters unnamed calendars**（名前が `null` の内部カレンダーを除外）。  
- **Prints UID and name** – 後でカレンダーを特定する際に便利です。  
- **Shows the base calendar** – 「Self」（カレンダー自身がベース）または継承元カレンダー名を表示します。  
- **Loops through each `WeekDay`** で作業時間合計を計算し出力（`workingTime` はミリ秒なので `OneHour` で除算）。

## Common Issues and Solutions
| 問題 | 原因 | 対策 |
|------|------|------|
| `NullPointerException` on `cal.getBaseCalendar()` | カレンダーがベース カレンダー自体である（`isBaseCalendar()` が `true`） | 示された三項演算子 (`cal.isBaseCalendar() ? "Self" : ...`) を使用してください。 |
| No output for working hours | プロジェクト ファイルが別の時間単位（ticks）を使用している | ファイル形式を確認してください。Aspose.Tasks はミリ秒に正規化しますが、正しいファイルタイプを読み込んでいるか確認しましょう。 |
| Unable to locate `project.xml` | `dataDir` パスが誤っている | 絶対パスを使用するか、`Paths.get(dataDir, "project.xml").toString()` に変更してください。 |

## Frequently Asked Questions

**Q: Can I modify calendar properties programmatically using Aspose.Tasks?**  
A: はい。API はカレンダーへのフル読み書きアクセスを提供し、作業時間、例外、ベース カレンダーの関係を追加・編集・削除できます。

**Q: Are there any limitations to calendar customization with Aspose.Tasks?**  
A: ライブラリは Microsoft Project の機能をほぼすべて再現しています。非常に古い Project ファイル バージョンだけが若干の互換性問題を抱える可能性があります。

**Q: Can I integrate calendar management into existing Java projects?**  
A: もちろんです。Aspose.Tasks の JAR をビルド パスに追加し、ここで示したコード パターンをそのまま使用すれば統合できます。

**Q: Does Aspose.Tasks support other project management functionalities besides calendar management?**  
A: はい。タスク、リソース、割り当て、アウトライン、ベースラインなど、Java ベースのプロジェクト自動化に必要な機能を網羅しています。

**Q: Is technical support available for developers using Aspose.Tasks?**  
A: はい。Aspose は専用フォーラム、メールサポート、そしてすべてのライセンスユーザー向けに充実したドキュメントを提供しています。

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}