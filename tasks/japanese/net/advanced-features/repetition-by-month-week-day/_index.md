---
title: Aspose.Tasks での月週日による繰り返し
linktitle: Aspose.Tasks での月週日による繰り返し
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET で月、週、日ごとに繰り返しを設定し、定期的なタスクを効率的に自動化する方法を学びます。
weight: 26
url: /ja/net/advanced-features/repetition-by-month-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での月週日による繰り返し

## 導入

ソフトウェア開発の分野、特にプロジェクト管理アプリケーションでは、繰り返し発生するタスクを効率的に処理できることが最も重要です。 Aspose.Tasks for .NET は、定期的なタスクを含むプロジェクト タスクの作成と管理を合理化するように設計された強力なライブラリです。 Aspose.Tasks が提供するそのような機能の 1 つは、月、週、日ごとに繰り返しを設定する機能で、手動介入なしでタスクがスケジュールどおりに実行されるようにします。

## 前提条件

Aspose.Tasks for .NET を使用して月、週、日ごとの繰り返しを設定する複雑な作業に入る前に、次の前提条件が満たされていることを確認してください。

1. C# の基本的な理解: 提供されているコード例を理解して実装するには、C# プログラミング言語に精通していることが不可欠です。
   
2.  Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET ライブラリをダウンロードしてインストールしていることを確認してください。ライブラリは次から入手できます。[ダウンロードページ](https://releases.aspose.com/tasks/net/).

3. .mpp プロジェクト ファイルへのアクセス: 月、週、日ごとの繰り返しの実装を示すために使用するため、Microsoft Project ファイル (.mpp) を用意します。

## 名前空間のインポート

C# アプリケーションで Aspose.Tasks for .NET の利用を開始するには、必要な名前空間をインポートする必要があります。その方法は次のとおりです。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

提供されたコード スニペットを複数のステップに分割して、各部分を完全に理解しましょう。

## ステップ 1: プロジェクト ファイルをロードする

```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

この手順には、`Project`クラスを作成し、既存の Microsoft Project ファイルをロードする (`Project1.mpp`) 指定されたディレクトリから。

## ステップ 2: 定期的なタスクのパラメータを定義する

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

このステップでは、定期的なタスクのパラメーターを定義します。タスク名、期間、繰り返しパターン (毎月)、および繰り返し範囲 (特定の日付までに終了) を指定します。

## ステップ 3: 定期的なタスクをプロジェクトに追加する

```csharp
project.RootTask.Children.Add(parameters);
```

ここでは、定義された繰り返しタスクのパラメーターをプロジェクトのルート タスクに追加します。

## ステップ 4: プロジェクト ファイルを保存する

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

最後に、追加した定期タスクを含む変更したプロジェクト ファイルを保存します。

## 結論

結論として、Aspose.Tasks for .NET で月、週、日ごとに繰り返しを設定することは、開発者がプロジェクト内の繰り返しタスクの管理を効率的に自動化できる簡単なプロセスです。このチュートリアルで概説されている手順に従うことで、この機能を C# アプリケーションにシームレスに統合でき、プロジェクト管理の時間と労力を節約できます。

## よくある質問

###Q1: 提供されている例以外に繰り返しパターンをカスタマイズできますか?

A1: はい。Aspose.Tasks for .NET には、繰り返しパターンの広範なカスタマイズ オプションが用意されており、特定の要件に合わせてカスタマイズできます。

###Q2: Aspose.Tasks for .NET の試用版はありますか?

 A2: はい、Aspose.Tasks for .NET の無料トライアルを次のサイトから入手できます。[リリースページ](https://releases.aspose.com/).

###Q3: Aspose.Tasks for .NET のサポートを取得するにはどうすればよいですか?

 A3: 支援を求めたり、コミュニティに参加したりできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).

###Q4: Aspose.Tasks for .NET の一時ライセンスは利用できますか?

 A4: はい、次のサイトから一時ライセンスを取得できます。[購入ページ](https://purchase.aspose.com/temporary-license/)テストと評価の目的で。

###Q5: Aspose.Tasks for .NET の包括的なドキュメントはどこで見つけられますか?

 A5: 詳細な説明を参照できます。[ドキュメンテーション](https://reference.aspose.com/tasks/net/)ライブラリの利用に関する詳細なガイダンスについては、Aspose Web サイトで入手できます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
