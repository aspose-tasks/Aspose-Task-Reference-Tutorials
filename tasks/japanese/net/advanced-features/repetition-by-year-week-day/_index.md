---
date: 2026-04-03
description: Aspose.Tasks を使用して繰り返しタスクのプロジェクトを追加し、プロジェクトを MPP として保存する方法を学びましょう。このガイドでは、年・週・日単位の繰り返し機能をステップバイステップで示します。
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Aspose.Tasks の年・週・日単位の繰り返し
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks の使い方 – 年・週・日単位の繰り返し
url: /ja/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks における年・週・日の繰り返し

## はじめに

複雑な繰り返しスケジュールを扱う際に **how to use Aspose.Tasks** が必要な場合、ライブラリは年単位のパターンに対して細かい制御を提供します。このチュートリアルでは、特定の月の特定の曜日に繰り返すタスクを作成し、複数年にわたるスケジュールを設定する方法を解説します。最後まで読むと、数行の C# で **add recurring task project** エントリを追加し、**save project as MPP** できるようになります。

## クイック回答

- **「年・週・日の繰り返し」とは何ですか？** 毎年、指定した月の選択した曜日（例：第1日曜日）にタスクを繰り返します。  
- **対応している .NET バージョンは？** すべての最新 .NET Framework および .NET Core/5/6 バージョンをサポートしています。  
- **コード実行にライセンスは必要ですか？** 開発目的であれば無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **繰り返し範囲を変更できますか？** はい – 開始日、終了日、または固定回数のいずれかを設定できます。  
- **出力は MPP ファイルですか？** もちろんです – プロジェクトは Microsoft Project 用の MPP ファイルとして保存されます。

## 「年・週・日の繰り返し」機能とは？

この機能を使用すると、特定の **曜日**（例：日曜日）と月内の **位置**（第1、第2、最終など）を対象とした年次繰り返しを定義できます。四半期レビュー、年次監査、カレンダーに基づくリズムで行われるイベントに最適です。

## 繰り返しタスクに Aspose.Tasks を使用する理由

- **Precision** – 月、曜日、序数位置をフルコントロールできます。  
- **Compatibility** – Microsoft Project で問題なく開くネイティブ MPP ファイルを生成します。  
- **No COM interop** – 純粋な .NET API で、Office のインストールは不要です。  
- **Scalability** – 小規模プロジェクトからエンタープライズ規模のスケジュールまで対応します。

## 前提条件

1. **Basic .NET knowledge** – C# とオブジェクト指向の概念に慣れていること。  
2. **Aspose.Tasks for .NET** – [download link](https://releases.aspose.com/tasks/net/) からダウンロードし、DLL をプロジェクトに追加してください。  
3. **Access to the official docs** – [documentation](https://reference.aspose.com/tasks/net/) にはすべてのクラスに関する詳細が掲載されています。  
4. **A development IDE** – Visual Studio、Rider、または任意の .NET 対応エディタ。

これで準備が整ったので、実装を見てみましょう。

## 繰り返しタスクで Aspose.Tasks を使用する方法

### 必要な名前空間のインポート

まず、プロジェクト、タスク、保存オプションを操作できるように必要な名前空間をスコープに持ち込みます。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 手順 1: プロジェクトとタスクパラメータの初期化

新しい `Project` インスタンスを作成し、繰り返しパターンを記述した `RecurringTaskParameters` オブジェクトを定義します。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** `Month`、`WeekDay`、`Position` を実際のスケジュールに合わせて調整してください。

### 手順 2: パラメータをプロジェクトに追加

繰り返しタスク定義をプロジェクトのルートに挿入します。

```csharp
project.RootTask.Children.Add(parameters);
```

### 手順 3: プロジェクトを MPP として保存

最後に、プロジェクトを MPP ファイルとして永続化し、Microsoft Project や互換ビューアで開けるようにします。

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> これは **save project as mpp** を 1 行のコードで実現する例です。

## よくある問題と解決策

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| MPP ファイルを開いたときにタスクが表示されない | 繰り返し範囲の日付がプロジェクトカレンダーの外にある | `Start` と `Finish` の日付がプロジェクトの稼働時間内にあることを確認する |
| `Add` 時に例外 `ArgumentNullException` が発生 | `parameters` が null であるか、完全に初期化されていない | 必須プロパティ (TaskName、Duration、RecurrencePattern) がすべて設定されていることを確認する |
| 誤った曜日が選択されている | `WeekDay` 列挙値が一致しない | 必要に応じて `DayOfWeek.Monday` から `DayOfWeek.Sunday` を使用する |

## よくある質問

**Q: 提供された例以外に繰り返しパターンをカスタマイズできますか？**  
A: はい、Aspose.Tasks では `MonthlyRecurrencePattern`、`WeeklyRecurrencePattern`、あるいはカスタム `RecurrenceRange` オブジェクトを組み合わせて、任意のスケジュールに対応できます。

**Q: Aspose.Tasks for .NET は他のプロジェクト管理ソフトウェアと互換性がありますか？**  
A: もちろんです – ライブラリは MPP、XML、Primavera 形式の読み書きが可能で、データ交換がスムーズに行えます。

**Q: 繰り返しタスクの例外や変更はどのように処理しますか？**  
A: `ExceptionTask` クラスを使用して特定の発生回数に対する上書きを作成するか、`RecurringTaskParameters` を編集してプロジェクトを再保存します。

**Q: Aspose.Tasks はクラウドベースのソリューションに対応していますか？**  
A: はい、Azure Functions、AWS Lambda、または任意の .NET 対応クラウドサービス上で API を実行できます。

**Q: Aspose.Tasks for .NET のトライアル版はありますか？**  
A: はい、[website](https://releases.aspose.com/) から Aspose.Tasks for .NET の無料トライアルを入手でき、購入前に機能を試すことができます。

**Q: 既存プロジェクトに繰り返しタスクを追加する際、他のデータを上書きしない方法は？**  
A: `new Project("Existing.mpp")` で既存プロジェクトをロードし、`RecurringTaskParameters` を `RootTask.Children` に追加してから `Save` してください。

## 結論

**how to use Aspose.Tasks** の **Repetition by Year Week Day** シナリオをマスターすれば、実際のカレンダーに完全に合致した **add recurring task project** エントリを作成し、**save project as MPP** でシームレスに共同作業できるようになります。これらのコードスニペットを自分のソリューションに組み込んで、スケジューリング精度を向上させ、手作業の手間を削減しましょう。

---

**最終更新日:** 2026-04-03  
**テスト環境:** Aspose.Tasks 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}