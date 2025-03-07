---
title: Aspose.Tasks での定期的なタスクのパラメーターの設定
linktitle: Aspose.Tasks での定期的なタスクのパラメーターの設定
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project で定期的なタスクのパラメーターを設定する方法を学習します。ステップバイステップのガイドを備えた包括的なチュートリアル。
weight: 14
url: /ja/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での定期的なタスクのパラメーターの設定

## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project の定期タスクのパラメーターを設定するプロセスを説明します。
## 前提条件
始める前に、次のものが揃っていることを確認してください。
1. C# プログラミング言語の基本的な理解。
2. Visual Studio またはその他の C# IDE がインストールされている。
3. Aspose.Tasks for .NET ライブラリがプロジェクトにインストールされ、参照されます。

## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートする必要があります。
```csharp
using Aspose.Tasks;
using System;

```
## ステップ 1: ドキュメント ディレクトリを定義する
```csharp
String DataDir = "Your Document Directory";
```
交換する`"Your Document Directory"`ドキュメント ディレクトリへのパスを置き換えます。
## ステップ 2: プロジェクト ファイルをロードする
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
このコード行は、Microsoft Project ファイルを`project`変数。
## ステップ 3: 定期的なタスクのパラメータを定義する
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
ここでは、タスク名、期間、繰り返しパターン、繰り返し範囲、リソース カレンダーを無視するかどうかなど、繰り返しタスクのパラメーターを定義します。
## ステップ 4: 定期的なタスクのカレンダーを設定する
```csharp
parameters.SetCalendar(project, "Standard");
```
この手順では、定期的なタスクのカレンダーを設定します。この例では、カレンダーを「標準」に設定します。
## ステップ 5: プロジェクトにパラメータを追加する
```csharp
project.RootTask.Children.Add(parameters);
```
最後に、パラメーターをプロジェクトのルート タスクに追加します。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project の定期タスク パラメーターを設定する方法を説明しました。これらの手順に従うことで、プロジェクト内の定期的なタスクを効率的に管理できます。
## よくある質問
### 繰り返しパターンをさらにカスタマイズできますか?
はい。Aspose.Tasks には、プロジェクトの要件に応じてカスタマイズできるさまざまな繰り返しパターンとオプションが用意されています。
### 購入前に利用できる試用版はありますか?
はい、Aspose.Tasks から無料トライアルをダウンロードできます。[Webサイト](https://purchase.aspose.com/buy)ライブラリの機能を評価します。
### Aspose.Tasks は他のプロジェクト ファイル形式をサポートしていますか?
はい、Aspose.Tasks は、MPP、XML、XLSX などを含むさまざまなプロジェクト ファイル形式をサポートしています。
### 導入中に問題が発生した場合、サポートを受けることはできますか?
はい、Aspose.Tasks フォーラムにアクセスしてコミュニティからの支援を得るか、サポートに問い合わせて直接支援を得ることができます。
### Aspose.Tasks の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスは以下から取得できます。[Webサイト](https://purchase.aspose.com/temporary-license/)テスト目的のため。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
