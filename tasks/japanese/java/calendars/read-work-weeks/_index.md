---
title: Aspose.Tasks を使用して MS Project カレンダーから勤務週間を読み取る
linktitle: Aspose.Tasks を使用してカレンダーから勤務週を読み取る
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して MS Project カレンダーから稼働週を読み取る方法を学びます。この包括的なチュートリアルで段階的な手順を確認してください。
weight: 15
url: /ja/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用して MS Project カレンダーから勤務週間を読み取る

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して、Microsoft Project カレンダーから勤務週間情報を読み取る方法を説明します。 Aspose.Tasks は、Microsoft Project ドキュメントをプログラムで操作および管理できる強力な Java ライブラリです。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java Development Kit (JDK) がシステムにインストールされています。
2.  Aspose.Tasks for Java ライブラリがダウンロードされ、インストールされます。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
## パッケージのインポート
まず、コードを開始するために必要なパッケージをインポートしましょう。
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## ステップ 1: データ ディレクトリを設定する
MS Project ファイルが存在するディレクトリ パスを設定します。
```java
String dataDir = "Your Data Directory";
```
## ステップ 2: プロジェクト インスタンスを作成し、カレンダーにアクセスする
Project クラスの新しいインスタンスを作成し、カレンダーと稼働週のコレクションにアクセスします。
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## ステップ 3: 勤務週間を通じて反復する
週労働時間のコレクションを反復処理し、その情報を表示します。
```java
for (WorkWeek workWeek : collection) {
    //勤務週名、開始日と終了日を表示します
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    //曜日と勤務時間へのアクセス
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        //必要に応じてさらなるプロセスの作業時間
    }
}
```
## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project カレンダーから稼働週情報を読み取る方法を学習しました。この強力なライブラリにより、プロジェクト ファイルのシームレスな操作が可能になり、開発者はさまざまなタスクを効率的に自動化できます。
## よくある質問
### Aspose.Tasks for Java を使用して稼働週情報を変更できますか?
はい。Aspose.Tasks は、週労働時間とそれに関連する情報を変更、追加、削除するための API を提供します。
### Aspose.Tasks は、さまざまなバージョンの Microsoft Project ファイルと互換性がありますか?
はい、Aspose.Tasks は、MPP 形式や XML 形式など、さまざまなバージョンの Microsoft Project ファイルをサポートしています。
### Aspose.Tasks を他の Java フレームワークと統合できますか?
もちろん、Aspose.Tasks は他の Java フレームワークやライブラリとシームレスに統合して、機能を強化できます。
### Aspose.Tasks の試用版はありますか?
はい、Aspose.Tasks の無料試用版を次のサイトからダウンロードできます。[ここ](https://releases.aspose.com/).
### Aspose.Tasks のサポートはどこで見つけられますか?
Aspose.Tasks フォーラムでサポートと支援を見つけることができます。[ここ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
