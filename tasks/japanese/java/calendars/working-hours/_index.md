---
title: Aspose.Tasks を使用してカレンダーから労働時間を取得する
linktitle: Aspose.Tasks を使用してカレンダーから労働時間を取得する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して、MS Project カレンダーから作業時間を簡単に抽出します。プロジェクト管理タスクを簡素化します。
weight: 13
url: /ja/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用してカレンダーから労働時間を取得する

## 導入
プロジェクト カレンダーを管理し、作業時間を抽出することは、効果的なプロジェクト管理に不可欠です。 Aspose.Tasks for Java は、MS Project カレンダーから作業時間を簡単に取得するための堅牢な機能を提供します。このチュートリアルでは、プロセスを段階的に説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1. Java Development Kit (JDK) がシステムにインストールされています。
2.  Aspose.Tasks for Java ライブラリがダウンロードされ、プロジェクトに追加されました。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
3. Java プログラミング言語の基本的な理解。
## パッケージのインポート
まず、Aspose.Tasks for Java で動作するために必要なパッケージをインポートします。
```java
import com.aspose.tasks.*;
```
## ステップ 1: プロジェクト ファイルをロードする
まず、MS Project ファイルをロードします。
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## ステップ 2: タスクとカレンダー情報を取得する
プロジェクトからタスクとカレンダーの詳細を抽出します。
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## ステップ 3: 開始日と終了日を定義する
タスクの開始日と終了日を設定します。
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## ステップ 4: 日付を反復処理する
タスク期間内の日付を反復処理します。
```java
java.util.Calendar tempDate = calStartDate;
```
## ステップ 5: 期間を計算する
期間を分、時間、日で計算します。
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project カレンダーから作業時間を取得する方法について説明しました。これらの手順に従うことで、プロジェクトのスケジュールを効率的に管理し、タスクの期間を簡単に計算できます。
## よくある質問
### Q: Aspose.Tasks for Java は複雑なプロジェクト構造を処理できますか?
A: はい、Aspose.Tasks for Java は、タスク、リソース、カレンダーなどの複雑なプロジェクト構造を処理するための包括的なサポートを提供します。
### Q: Aspose.Tasks for Java は、MS Project のさまざまなバージョンと互換性がありますか?
A: もちろん、Aspose.Tasks for Java はさまざまなバージョンの MS Project をサポートしており、さまざまな環境間での互換性を確保しています。
### Q: プロジェクト カレンダーの勤務時間と休日をカスタマイズできますか?
A: はい、Aspose.Tasks for Java API を使用すると、プロジェクトの要件に応じて勤務時間と休日を簡単にカスタマイズできます。
### Q: Aspose.Tasks for Java はサポートとドキュメントを提供しますか?
A: はい、Aspose.Tasks for Java は、開発者がその機能を効果的に利用できるように、広範なドキュメントと専用のサポート フォーラムを提供しています。
### Q: Aspose.Tasks for Java の試用版はありますか?
 A: はい、Aspose.Tasks for Java の無料試用版には、次のサイトからアクセスできます。[ここ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
