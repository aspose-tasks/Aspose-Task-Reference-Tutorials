---
title: Aspose.Tasks を使用してカレンダーの平日を定義する
linktitle: Aspose.Tasks を使用してカレンダーの平日を定義する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して MS Project Calendar で曜日を定義する方法を学びます。稼働日とタイミングを簡単にカスタマイズできます。
type: docs
weight: 12
url: /ja/java/calendars/define-weekdays/
---
## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project カレンダーで平日を定義するプロセスを順を追って説明します。 Aspose.Tasks は、開発者が Microsoft Project ファイルをプログラムで操作できるようにする強力な Java ライブラリです。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1.  Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。からダウンロードできます。[オラクルのWebサイト](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)まだ行っていない場合は。
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードページ](https://releases.aspose.com/tasks/java/)。ドキュメントに記載されているインストール手順に従ってください。

## パッケージのインポート
まず、Java プロジェクトで Aspose.Tasks を操作するために必要なパッケージをインポートします。
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## ステップ 1: プロジェクト インスタンスを作成する
作業する MS Project ファイルを表す Project オブジェクトをインスタンス化します。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## ステップ 2: カレンダーを定義する
新しいカレンダー インスタンスを作成し、プロジェクトに追加します。
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## ステップ 3: 営業日を追加する
月曜日から木曜日までをデフォルトのタイミングで追加して営業日を定義します。
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## ステップ 4: カスタム稼働日を設定する
土曜日と日曜日を営業日として定義します。
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## ステップ 5: 短時間勤務日を設定する
カスタムの勤務時間を使用して金曜日を短い勤務日として設定します。
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
## ステップ 6: プロジェクトを保存する
変更したプロジェクトを XML ファイルに保存します。
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 結論
おめでとう！ Aspose.Tasks for Java を使用して、MS Project カレンダーで平日を正常に定義できました。この機能を Java アプリケーションに統合して、MS Project ファイルをプログラムで操作できるようになりました。
## よくある質問
### Q1: Aspose.Tasks for Java を使用してカスタムの非稼働日を定義できますか?
 A: はい、設定することでカスタムの非稼働日を定義できます。`DayWorking`財産を`false`それぞれの平日の。
### Q2: カレンダーに休日を追加するにはどうすればよいですか?
 A: インスタンスを作成することで休日を追加できます。`CalendarExceptions`そして非稼働日を指定します。
### Q3: Aspose.Tasks は、MS Project ファイルのさまざまなバージョンと互換性がありますか?
A: はい、Aspose.Tasks は、MPP、MPT、XML 形式など、さまざまなバージョンの MS Project ファイルをサポートしています。
### Q4: MS Project ファイル内の既存のカレンダーを変更できますか?
A: はい、カレンダーを含む既存のプロジェクトをロードし、変更を加えて、変更を元のファイルに保存できます。
### Q5: Aspose.Tasks は定期的なタスクをサポートしていますか?
A: はい、Aspose.Tasks を使用すると、繰り返しのパターンや期間の定義など、繰り返しのタスクを操作できます。