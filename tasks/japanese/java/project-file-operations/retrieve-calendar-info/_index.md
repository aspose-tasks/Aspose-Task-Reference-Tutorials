---
title: Aspose.Tasks で MS プロジェクトのカレンダー情報を取得する
linktitle: Aspose.Tasks でカレンダー情報を取得する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して MS Project カレンダー情報を取得する方法を学びます。プログラムでカレンダーの詳細にアクセスするためのステップバイステップのガイド。
weight: 14
url: /ja/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で MS プロジェクトのカレンダー情報を取得する

## 導入
このチュートリアルでは、Aspose.Tasks for Java ライブラリを使用して Microsoft Project ファイルからカレンダー情報を取得する方法を説明します。 Aspose.Tasks は、稼働日や営業時間などのカレンダーの詳細へのアクセスなど、プロジェクト データを操作するための強力な機能を提供します。
## 前提条件
始める前に、以下のものがあることを確認してください。
- Java プログラミングの基本的な知識。
- Java Development Kit (JDK) がシステムにインストールされています。
-  Java ライブラリの Aspose.Tasks。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
## パッケージのインポート
まず、Aspose.Tasks 機能を使用するために必要なパッケージを Java コードにインポートする必要があります。
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
ここで、理解を深めるために、提供された例を複数のステップに分解してみましょう。
## ステップ 1: データ ディレクトリを設定する
```java
String dataDir = "Your Data Directory";
```
交換する`"Your Data Directory"`プロジェクト ファイル ディレクトリへのパスを置き換えます。
## ステップ 2: 時間単位を定義する
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
これらの定数は時間単位をマイクロ秒で表します。
## ステップ 3: プロジェクト インスタンスを作成する
```java
Project project = new Project(dataDir + "project.mpp");
```
この行は、`Project`クラスをプロジェクト ファイルへのパスで初期化します (`project.mpp`）。
## ステップ 4: カレンダー情報を取得する
```java
CalendarCollection alCals = project.getCalendars();
```
ここでは、プロジェクト ファイル内に存在するカレンダーのコレクションを取得します。
## ステップ 5: カレンダーを反復処理する
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        //カレンダー情報
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        //平日を反復処理する
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); //ミリ秒単位の時間
            double time = ts / (OneHour); //時間に換算する
            if (wd.getDayWorking()) {
                //営業日と営業時間を表示する
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
このループは各カレンダーを反復処理し、その UID、名前、および稼働日とそれぞれの稼働時間を出力します。
## ステップ6: 完了メッセージの表示
```java
System.out.println("Process completed Successfully");
```
最後に、プロセスの完了を示すメッセージが表示されます。
## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project ファイルからカレンダー情報を取得する方法を学びました。これらの手順に従うことで、Java アプリケーション内のプロジェクト データに効率的にアクセスして操作できるようになります。

## よくある質問
### Q: Aspose.Tasks を他のプログラミング言語で使用できますか?
A: はい、Aspose.Tasks は、.NET、C などの複数のプラットフォームとプログラミング言語をサポートしています。++、Python、Java。
### Q: Aspose.Tasks に利用できる無料トライアルはありますか?
 A: はい、以下から無料試用版をダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks のサポートを受けるにはどうすればよいですか?
A: Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks の一時ライセンスを購入できますか?
 A: はい、一時ライセンスを購入できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks の詳細なドキュメントはどこで見つけられますか?
 A: ドキュメントを参照してください。[ここ](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
