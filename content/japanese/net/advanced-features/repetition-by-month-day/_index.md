---
title: Aspose.Tasks での月日ごとの繰り返し
linktitle: Aspose.Tasks での月日ごとの繰り返し
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks を使用して .NET プロジェクトの繰り返しタスクを管理する方法を学びます。月日ごとの繰り返しを処理するためのステップバイステップのガイド。
type: docs
weight: 25
url: /ja/net/advanced-features/repetition-by-month-day/
---
## 導入

.NET 開発の分野では、Aspose.Tasks はプロジェクトのタスクとスケジュールを管理するための強力なツールとして機能します。定期的なタスクの処理など、プロジェクト管理ワークフローを合理化するための機能が多数提供されています。月日ごとの繰り返しはプロジェクトのスケジューリングにおける一般的な要件であり、Aspose.Tasks はこのシナリオを強力にサポートします。

## 前提条件

チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。

1. C# の基本的な理解: このチュートリアルで説明する概念を理解するには、C# プログラミング言語に精通している必要があります。
2. Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET がインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
3. 統合開発環境 (IDE): コーディングを容易にするために、Visual Studio などの IDE をシステムにインストールします。

## 名前空間のインポート

C# プロジェクトで、Aspose.Tasks 機能にアクセスするために必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

提供されているコード例をステップバイステップのガイド形式に分解してみましょう。

## ステップ 1: プロジェクト ファイルをロードする

```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

このコード行は、`Project`クラスで、「Project1.mpp」という名前のプロジェクト ファイルをロードします。

## ステップ 2: 定期的なタスクのパラメータを定義する

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

このセクションでは、名前、期間、繰り返しパターン、繰り返し範囲など、繰り返しタスクのパラメータを定義します。

## ステップ 3: タスクをプロジェクトに追加する

```csharp
project.RootTask.Children.Add(parameters);
```

ここでは、定期的なタスクのパラメーターをプロジェクトに追加します。

## ステップ 4: プロジェクト ファイルを保存する

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

最後に、変更したプロジェクトが追加された定期タスクとともに保存されます。

## 結論

このチュートリアルでは、Aspose.Tasks for .NET で月日ごとの繰り返しを処理する方法を検討しました。提供されている手順に従うことで、プロジェクトのスケジュール内で繰り返し発生するタスクを効率的に管理できます。

## よくある質問

### Q1: Aspose.Tasks は .NET のすべてのバージョンと互換性がありますか?

A1: Aspose.Tasks は、.NET Framework のさまざまなバージョンをサポートし、さまざまな環境間での互換性を確保します。

### Q2: 繰り返しパターンをさらにカスタマイズできますか?

A2: はい、Aspose.Tasks は、特定のプロジェクト要件に従って繰り返しパターンを定義するための広範なカスタマイズ オプションを提供します。

### Q3: Aspose.Tasks は他のプロジェクト管理機能をサポートしますか?

A3: もちろん、Aspose.Tasks は、タスクの追跡、リソースの割り当て、ガント チャートの生成など、プロジェクト管理のための幅広い機能を提供します。

### Q4: Aspose.Tasks の試用版はありますか?

 A4: はい、以下から無料トライアルをご利用いただけます。[ここ](https://releases.aspose.com/)購入を決定する前に、Aspose.Tasks の機能を調べてください。

### Q5: 問題が発生したり質問がある場合は、どこにサポートを求めればよいですか?

 A5: をご覧いただけます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティまたは Aspose チームからのサポートを求めます。