---
title: Aspose.Tasks での簡単な MS プロジェクトの定期的な間隔
linktitle: Aspose.Tasks での定期的な間隔の管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project で定期的な間隔を簡単に管理する方法をご覧ください。
weight: 12
url: /ja/net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での簡単な MS プロジェクトの定期的な間隔

## 導入
Aspose.Tasks for .NET を使用して、Microsoft Project ファイルで定期的な間隔を効率的に管理したいと考えていますか?この包括的なチュートリアルでは、プロセスを段階的にガイドし、プロジェクトで繰り返し発生する間隔を簡単に処理できるようにします。チュートリアルに入る前に、開始する準備ができているかどうかを確認するために、いくつかの前提条件を確認してください。
## 前提条件
このチュートリアルを進める前に、次のものが揃っていることを確認してください。
1. C# プログラミングの知識: C# プログラミング言語とその構文の基本的な理解が必要です。
2. Visual Studio がインストールされている: .NET アプリケーションのコーディングとコンパイルのために、システムに Visual Studio がインストールされていることを確認します。
3. Aspose.Tasks for .NET ライブラリ: Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。から入手できます[ここ](https://releases.aspose.com/tasks/net/).

## 名前空間のインポート
まず、Aspose.Tasks for .NET ライブラリが提供する機能にアクセスするために必要な名前空間をインポートします。
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
次に、各例を複数のステップに分けて詳しく説明します。
## ステップ 1: プロジェクト オブジェクトを初期化します。
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
ここでは、の新しいインスタンスを初期化します。`Project` Microsoft Project ファイルへのパスを指定してクラスを作成します。
## ステップ 2: ステータス日付を設定します:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
このステップでは、プロジェクトの状況報告日を開始日に設定します。
## ステップ 3: ガント チャート ビューにアクセスします:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
プロジェクトのガント チャート ビューにアクセスします。
## ステップ 4: 進行状況行を読み取る:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
このステップでは、ガント チャート ビューから進捗ラインの繰り返し間隔を取得します。
## ステップ 5: 間隔情報の表示:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
ここでは、間隔、週番号、週日に関する情報が表示されます。
## ステップ 6: 定期的な間隔を再定義します。
```csharp
var newInterval = new RecurringInterval();
```
新しいインスタンスを作成します`RecurringInterval`繰り返しの間隔を再定義します。
## ステップ 7: 毎月の進捗ラインを設定します。
```csharp
//月次の進捗ラインを日ごとに設定します。
interval.MonthlyDay = true;
//毎月の進捗ラインの日数を設定します。
interval.MonthlyDayDayNumber = 1;
//月次進捗線の月数を設定します。
interval.MonthlyDayMonthNumber = 1;
//事前定義された最初または最後の日ごとに進捗ラインを設定します。
interval.MonthlyFirstLast = true;
//月次進捗線の初日または最終日の種類を設定します。
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
//進捗ラインの月数を設定します。
interval.MonthlyFirstLastMonthNumber = 1;
```
これらの手順では、指定されたパラメーターに従って月次の進捗ラインを構成します。
## ステップ 8: 進捗ラインを更新します。
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
新しく定義された繰り返し間隔でガント チャート ビューの進捗ラインを更新します。
## ステップ 9: プロジェクトを PDF として保存:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
最後に、更新された繰り返し間隔を含むプロジェクトを PDF ファイルとして保存します。

## 結論
結論として、Aspose.Tasks for .NET を使用した Microsoft Project ファイルでの定期的な間隔の管理は、ライブラリが提供する包括的な機能により簡単になります。このチュートリアルで概説されているステップバイステップのガイドに従うことで、プロジェクト内の定期的な間隔を効率的に処理し、生産性と組織性を向上させることができます。
### よくある質問
### Aspose.Tasks for .NET を他のプログラミング言語で使用できますか?
はい、Aspose.Tasks for .NET は、C# や VB.NET などの .NET でサポートされている言語で使用できます。
### Aspose.Tasks for .NET の試用版はありますか?
はい、無料試用版を次からダウンロードできます。[ここ](https://releases.aspose.com/).
### Aspose.Tasks for .NET のサポートを受けるにはどうすればよいですか?
 Aspose.Tasks フォーラムからサポートを受けることができます[ここ](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for .NET の一時ライセンスを購入できますか?
はい、次から一時ライセンスを購入できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Tasks for .NET の完全なドキュメントはどこで見つけられますか?
完全なドキュメントはこちらからご覧いただけます[ここ](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
