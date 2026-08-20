---
date: 2026-08-13
description: Aspose.Tasks for Java を使用して MS Project カレンダーから作業週を読み取る方法を学びます。コード例とトラブルシューティングのヒントを含むステップバイステップガイドをご覧ください。
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Aspose.Tasks でカレンダーから作業週を読み取る
og_description: Aspose.Tasks for Java を使用して MS Project カレンダーから作業週を読み取る方法。セットアップ手順、コードスニペット、トラブルシューティングのヒントを含む簡潔なチュートリアルをご覧ください。
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Aspose.Tasks を使用して MS カレンダーから作業週を読み取る方法
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Aspose.Tasks を使用して MS カレンダーから作業週を読み取る方法
url: /ja/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS カレンダーから Aspose.Tasks を使用して作業週を読み取る方法

## はじめに
このチュートリアルでは、Aspose.Tasks ライブラリ for Java を使用して Microsoft Project カレンダーから **作業週を読み取る方法** を学びます。レポート ダッシュボードの構築、ERP システムとのスケジュール同期、または分析用データ抽出の自動化など、作業週定義へのプログラムによるアクセスは膨大な手作業時間を削減します。Aspose.Tasks は **50 以上の入出力フォーマット** をサポートし、プロジェクト ファイル全体をメモリにロードせずに数百ページのファイルを処理できるため、柔軟性とパフォーマンスの両方を提供します。

## 簡単な回答
- **“read workweeks” は何を意味しますか？** Java コードで Project ファイルから作業週の定義（日付と日々の作業時間ルール）を抽出することを指します。  
- **どのライブラリが必要ですか？** Aspose.Tasks for Java（無料トライアル利用可能）。  
- **開発にライセンスは必要ですか？** テストにはトライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされているファイル形式は何ですか？** *.mpp* と Project XML ファイルの両方に対応し、さらに 50 以上のインポート/エクスポート形式があります。  
- **実装にどれくらい時間がかかりますか？** ライブラリを設定すれば、通常 10 分未満です。

## MS Project の作業週とは何ですか？
作業週は、特定の期間にリソースが利用可能な時間帯を規定するカレンダー ルールです。開始日、終了日、そして日々の作業時間間隔（例：午前 9 時〜午後 5 時）を含みます。MS Project では、各カレンダーに複数の作業週を設定でき、祝日、シフト パターン、季節スケジュールなどをモデル化できます。

## Aspose.Tasks はカレンダーから作業週をどのように読み取りますか？
Aspose.Tasks は `Calendar` オブジェクトの `WorkWeekCollection` を公開します。`Project` インスタンスを作成し、目的のカレンダー（UID または名前で）を選択して `WorkWeekCollection` を反復することで、各作業週のラベル、適用日付範囲、詳細な日々の作業時間スロットを取得できます。API はすべての日付時刻変換を処理し、プロジェクトのタイムゾーン設定を自動的に尊重します。

## なぜ Microsoft Project カレンダーから Java で作業週を読み取るのか？
作業週をプログラムで取得することで、手作業のコピーペーストを排除し、下流システム（ERP、HR、レポート）が正確に同一のスケジュール ルールを使用できるようになります。また、複数プロジェクト間での一貫性が保証され、人為的エラーが減少し、特に毎晩多数のプロジェクト ファイルを処理する統合パイプラインの速度が向上します。

## 前提条件
1. **Java Development Kit (JDK)** – バージョン 8 以降がインストールされていること。  
2. **Aspose.Tasks for Java** – 公式サイトから最新の JAR をダウンロードしてください: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)。  
3. サンプル Project ファイル (`ReadWorkWeeksInformation.mpp`) をマシン上の既知のフォルダーに配置します。

## パッケージのインポート
まず、カレンダーと作業週とやり取りするために必要なクラスをインポートします。

`Project` は Microsoft Project ファイルを表し、`Calendar` はそのカレンダーを提供し、`WorkWeek` は作業週を定義し、`WeekDay` は1日を表します。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## ステップ 1: データディレクトリの設定
`.mpp` ファイルが格納されているフォルダーを定義します。プレースホルダーを実際のパスに置き換えてください。

```java
String dataDir = "Your Data Directory";
```

## ステップ 2: Project インスタンスを作成しカレンダーにアクセスする
`Project` クラスは Microsoft Project ファイルを表し、カレンダー、タスク、リソースなどのデータ構造へのアクセスを提供します。  
`Project` オブジェクトをインスタンス化し、取得したいカレンダー（UID で）を選択し、その `WorkWeekCollection` を取得します。

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** カレンダーの UID が不明な場合は、`project.getCalendars()` を反復し、各カレンダーの名前と UID を最初に出力してください。

## ステップ 3: 作業週を反復処理する
`WorkWeek` クラスは作業週の定義をカプセル化し、開始/終了日と日々の作業時間設定を含みます。  
各 `WorkWeek` をループして、名前、開始/終了日、日々の作業時間を表示します。

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

**表示される内容:** コンソールは各作業週のラベル（例: “Standard”）、有効な日付範囲を出力し、各日の正確な作業時間を詳しく確認できます。

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|-------|--------|-----|
| `calendar` にアクセスしたときの NullPointerException | UID が間違っているか、カレンダーが存在しない | `project.getCalendars().size()` で UID を確認し、まず利用可能なカレンダーを一覧表示してください。 |
| 作業週の出力がない | 選択したカレンダーにカスタム作業週がなく（デフォルトを使用） | デフォルトカレンダー (`project.getDefaultCalendar()`) を使用するか、プログラムで作業週を作成してください。 |
| 日付形式が変です | `System.out.println` がデフォルトの `java.util.Date` 形式を使用している | 必要に応じて `SimpleDateFormat` を使用して日付をフォーマットしてください。 |

## よくある質問
**Q: Aspose.Tasks for Java を使用して作業週情報を変更できますか？**  
A: はい。API は `addWorkWeek()`、`removeWorkWeek()`、およびプロパティのセッターを提供し、名前、日付、作業時間を変更できます。

**Q: Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: もちろんです。Project 98 から最新リリースまでの MPP ファイル、および Project XML ファイルをサポートしています。

**Q: Aspose.Tasks を他の Java フレームワークと統合できますか？**  
A: はい。ライブラリは純粋な Java なので、Spring、Jakarta EE、その他のフレームワークと併用できます。

**Q: Aspose.Tasks のトライアル版はありますか？**  
A: はい、公式サイトから 30 日間の無料トライアルをダウンロードできます: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Aspose.Tasks のサポートはどこで受けられますか？**  
A: Aspose コミュニティフォーラムが最適です: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

---

**最終更新日：** 2026-08-13  
**テスト環境：** Aspose.Tasks for Java 24.12（執筆時点での最新）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Tasks for Java を使用してプロジェクトにカレンダーを追加する](/tasks/java/calendars/create/)
- [Aspose.Tasks でカレンダー例外を取得する – Java チュートリアル](/tasks/java/calendar-exceptions/retrieve/)
- [Aspose.Tasks を使用して MS Project でカレンダーを設定し、平日を定義する方法](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}