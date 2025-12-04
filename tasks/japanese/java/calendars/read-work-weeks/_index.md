---
date: 2025-12-03
description: Aspose.Tasks を使用して Microsoft Project カレンダーから Java の作業週を読み取る方法を学びましょう。完全なコード例付きのステップバイステップガイドをご覧ください。
language: ja
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して MS Project カレンダーから作業週を Java で読み取る
url: /java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project カレンダーから Aspose.Tasks を使用して Work Weeks Java を読み取る

## Introduction
このチュートリアルでは、Aspose.Tasks ライブラリを使用して Microsoft Project カレンダーから **read work weeks Java** を取得します。レポートツールの構築、スケジュールの同期、プロジェクトデータ抽出の自動化など、プログラムから作業週定義にアクセスできれば、手作業の時間を大幅に削減できます。必要なセットアップ手順を示し、作業週の詳細を取得する正確なコードを提示し、各ステップを解説するので、独自のプロジェクトに合わせて応用できます。

## Quick Answers
- **“read work weeks java” とは何ですか？** Java コードで Project ファイルから作業週定義を抽出することを指します。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（無料トライアルあり）。  
- **開発にライセンスは必要ですか？** テストにはトライアルで可。商用利用には商用ライセンスが必要です。  
- **対応ファイル形式は？** *.mpp* と Project XML の両方に対応しています。  
- **実装にかかる時間は？** ライブラリを設定すれば、通常 10 分未満で完了します。

## What is “read work weeks java”?
Java で作業週を読み取るとは、Aspose.Tasks API を使用して Microsoft Project ファイル内のカレンダーオブジェクトの `WorkWeekCollection` にアクセスすることです。各 `WorkWeek` には開始/終了日と、リソースのスケジュールに影響する日別の作業時間定義が含まれます。

## Why read work weeks java from a Microsoft Project calendar?
- **Automation（自動化）:** スケジュールデータの手動コピー＆ペーストを排除します。  
- **Integration（統合）:** 作業週情報を ERP、HR、またはカスタムレポートシステムに供給します。  
- **Consistency（一貫性）:** すべての下流ツールが Project ファイルで定義された同一カレンダー規則を遵守することを保証します。

## Prerequisites
コードに入る前に、以下を用意してください。

1. **Java Development Kit (JDK)** – バージョン 8 以降がインストール済み。  
2. **Aspose.Tasks for Java** – 公式サイトから最新 JAR をダウンロード: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)。  
3. **サンプル Project ファイル** (`ReadWorkWeeksInformation.mpp`) を既知のフォルダーに配置。

## Import Packages
カレンダーと作業週を操作するために必要なクラスをインポートします:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Step 1: Set Up Your Data Directory
`.mpp` ファイルが格納されているフォルダーを定義します。プレースホルダーを実際のパスに置き換えてください:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Create a Project Instance and Access the Calendar
`Project` オブジェクトをインスタンス化し、目的のカレンダー（UID 指定）を取得して、その `WorkWeekCollection` を取得します:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** カレンダー UID が不明な場合は、`project.getCalendars()` をイテレートして各カレンダーの名前と UID を出力すると便利です。

## Step 3: Iterate Through Work Weeks
各 `WorkWeek` をループし、名前、開始/終了日、日別の作業時間を表示します:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**What you’ll see:** コンソールに各作業週のラベル（例: “Standard”）、有効期間、そして各日の正確な作業時間が出力されます。

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | UID が間違っている、またはカレンダーが存在しない | `project.getCalendars().size()` で UID を確認し、利用可能なカレンダーを先に一覧表示してください。 |
| No output for work weeks | 選択したカレンダーにカスタム作業週がなく、デフォルトを使用している | デフォルトカレンダー (`project.getDefaultCalendar()`) を使用するか、プログラムで作業週を作成してください。 |
| Date format looks odd | `System.out.println` がデフォルトの `java.util.Date` 形式を使用している | 必要に応じて `SimpleDateFormat` を適用し、日付を整形してください。 |

## Frequently Asked Questions

**Q: Aspose.Tasks for Java を使って作業週情報を変更できますか？**  
A: はい。`addWorkWeek()`、`removeWorkWeek()`、およびプロパティセッターを使用して、名前、日付、作業時間を変更できます。

**Q: Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルに対応していますか？**  
A: 完全に対応しています。Project 98 から最新バージョンまでの MPP ファイル、および Project XML ファイルをサポートします。

**Q: Aspose.Tasks を他の Java フレームワークと統合できますか？**  
A: 可能です。純粋な Java ライブラリなので、Spring、Jakarta EE、その他任意のフレームワークと併用できます。

**Q: Aspose.Tasks のトライアル版はありますか？**  
A: はい。公式サイトから 30 日間の無料トライアルをダウンロードできます: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Aspose.Tasks のサポートはどこで受けられますか？**  
A: Aspose コミュニティフォーラムが最適です: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

## Conclusion
これで **read work weeks java** を Aspose.Tasks でマスターしました。上記手順に従えば、任意の MS Project カレンダーから作業週定義をプログラムで取得し、アプリケーションに統合してスケジュール関連のワークフローを自動化できます。作業週の作成や更新にも挑戦してみてください—Aspose.Tasks なら簡単に実現できます。

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}