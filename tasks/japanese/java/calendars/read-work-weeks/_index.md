---
date: 2026-02-05
description: Aspose.Tasks を使用して Microsoft Project カレンダーから Java の作業週を読み取る方法を学びましょう。完全なコード例付きのステップバイステップガイドをご確認ください。
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project カレンダーから Aspose.Tasks を使用して Java の作業週を読み取る方法
url: /ja/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read Workweeks Java from MS Project Calendar Aspose.Tasks

## はじめに
このチュートリアルでは、Aspose.Tasks ライブラリを使用して Microsoft Project カレンダーから **Workweeks Java を読み取る方法** を学びます。レポートツールの作成、スケジュールの同期、プロジェクトデータ抽出の自動化など、作業週定義にプログラムからアクセスできれば、手作業の時間を大幅に削減できます。必要なセットアップ手順を示し、作業週の詳細を取得する正確なコードを提示し、各ステップを解説しますので、独自のプロジェクトに応用できます。

## クイック回答
- **「read workweeks java」とは何ですか？** Java コードで Project ファイルから作業週定義を抽出することを指します。  
- **必要なライブラリは？** Aspose.Tasks for Java（無料トライアルあり）。  
- **開発にライセンスは必要ですか？** テストにはトライアルで可。商用利用には正式ライセンスが必要です。  
- **対応ファイル形式は？** *.mpp* と Project XML の両方に対応。  
- **実装にかかる時間は？** ライブラリを設定すれば、通常 10 分未満で完了します。

## Microsoft Project カレンダーから Workweeks Java を読み取る方法
Java で作業週を読み取るとは、Aspose.Tasks API を使用して Microsoft Project ファイル内のカレンダーオブジェクトの `WorkWeekCollection` にアクセスすることです。各 `WorkWeek` には開始/終了日と、リソースのスケジュールに影響する日別作業時間定義が含まれます。

## なぜ Microsoft Project カレンダーから Workweeks Java を読み取るのか？
- **自動化:** スケジュールデータの手動コピー＆ペーストを排除。  
- **統合:** 作業週情報を ERP、HR、カスタムレポートシステムへ供給。  
- **一貫性:** すべての下流ツールが Project ファイルで定義された同一カレンダー規則を遵守。

## 前提条件
コードに入る前に、以下を用意してください。

1. **Java Development Kit (JDK)** – バージョン 8 以上がインストール済み。  
2. **Aspose.Tasks for Java** – 公式サイトから最新 JAR をダウンロード: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)。  
3. **サンプル Project ファイル** (`ReadWorkWeeksInformation.mpp`) を既知のフォルダーに配置。

## パッケージのインポート
カレンダーと作業週を操作するために必要なクラスをインポートします。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## 手順 1: データディレクトリの設定
`.mpp` ファイルが格納されているフォルダーを定義します。プレースホルダーを実際のパスに置き換えてください。

```java
String dataDir = "Your Data Directory";
```

## 手順 2: Project インスタンスを作成しカレンダーにアクセスする
`Project` オブジェクトを生成し、目的のカレンダー（UID で指定）を取得し、その `WorkWeekCollection` を取得します。

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **プロのコツ:** カレンダー UID が不明な場合は、`project.getCalendars()` を反復して各カレンダーの名前と UID を出力すると便利です。

## 手順 3: 作業週を反復処理する
各 `WorkWeek` をループし、名前、開始/終了日、日別作業時間を表示します。

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

**期待される出力:** コンソールに各作業週のラベル（例: “Standard”）、有効期間、そして各日の正確な作業時間が表示されます。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| `NullPointerException` が `calendar` 取得時に発生 | UID が間違っている、またはカレンダーが存在しない | `project.getCalendars().size()` で UID を確認し、利用可能なカレンダーを先に一覧表示 |
| 作業週が出力されない | 選択したカレンダーにカスタム作業週が設定されていない（デフォルト使用） | デフォルトカレンダー (`project.getDefaultCalendar()`) を使用するか、プログラムで作業週を作成 |
| 日付形式が見づらい | `System.out.println` がデフォルトの `java.util.Date` 形式を使用 | `SimpleDateFormat` を利用して必要な形式に整形 |

## よくある質問

**Q: Aspose.Tasks for Java を使って作業週情報を変更できますか？**  
A: はい。`addWorkWeek()`、`removeWorkWeek()`、および各種プロパティのセッターを使用して、名前、日付、作業時間を変更できます。

**Q: Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルに対応していますか？**  
A: 対応しています。Project 98 から最新バージョンまでの MPP ファイル、さらに Project XML ファイルもサポートします。

**Q: Aspose.Tasks を他の Java フレームワークと統合できますか？**  
A: できます。純粋な Java ライブラリなので、Spring、Jakarta EE、その他任意のフレームワークと併用可能です。

**Q: Aspose.Tasks のトライアル版はありますか？**  
A: はい。公式サイトから 30 日間の無料トライアルをダウンロードできます: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Aspose.Tasks のサポートはどこで受けられますか？**  
A: Aspose コミュニティフォーラムが最適です: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

## 結論
これで **Workweeks Java を読み取る方法** を Aspose.Tasks を使って習得しました。上記手順に従えば、任意の MS Project カレンダーから作業週定義をプログラムで取得し、アプリケーションに統合してスケジュール関連のワークフローを自動化できます。作業週の作成や更新にも挑戦してみてください—Aspose.Tasks なら簡単に実装できます。

---

**最終更新日:** 2026-02-05  
**テスト環境:** Aspose.Tasks for Java 24.12（執筆時点での最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}