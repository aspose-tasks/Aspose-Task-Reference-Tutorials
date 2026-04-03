---
date: 2026-04-03
description: Aspose.Tasks for .NET を使用したプロジェクト管理のタスクスケジューリングと繰り返しタスクの追加方法、さらにプロジェクトを
  MPP として保存する方法を学びます。
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Aspose.Tasks の年ごとの繰り返し
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksでの年単位繰り返しを使用したプロジェクト管理タスクスケジューリング
url: /ja/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks における年次日繰り返しによるプロジェクト管理タスクスケジューリング

## はじめに

Effective **project management task scheduling** is the backbone of any successful project. When tasks repeat on a yearly basis—such as annual audits, maintenance windows, or seasonal reviews—handling those recurrences manually can become error‑prone and time‑consuming. Aspose.Tasks for .NET simplifies this by letting you programmatically define year‑day patterns, so you can focus on what matters most: delivering value. In this tutorial you’ll learn **how to add recurring task** logic based on a specific day of the year and see exactly **how to save project as MPP** for seamless integration with Microsoft Project.

## クイック回答
- **“year day repetition”とは何ですか？** 毎年特定の月の特定の日にタスクをスケジュールします。  
- **どの API クラスが繰り返しを作成しますか？** `YearlyRecurrencePattern` と `ByYearDayRepetition` を組み合わせます。  
- **開始日と終了日を設定できますか？** はい、`EndByRecurrenceRange` を使用します。  
- **生成されるファイル形式は何ですか？** プロジェクトは MPP ファイル (`SaveFileFormat.Mpp`) として保存されます。  
- **本番環境でライセンスが必要ですか？** 評価版以外の使用には商用ライセンスが必要です。

## 前提条件

Before diving into the tutorial, ensure that you have the following prerequisites in place:

1. Aspose.Tasks for .NET ライブラリ: [website](https://releases.aspose.com/tasks/net/) から Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。  
2. 開発環境: Visual Studio またはその他のお好みの .NET 開発用 IDE を使用して、適切な開発環境を設定します。  
3. C# の基本知識: コード例に沿って学習できるよう、C# プログラミング言語の基礎を理解しておきます。  
4. プロジェクト管理の概念: プロジェクト管理の概念とタスクスケジューリングの理解は、チュートリアルの概念を効果的に把握するのに役立ちます。

## 名前空間のインポート

Before we begin coding, let's import the necessary namespaces to facilitate our task manipulation using Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Now, let's break down the provided example into multiple steps and elucidate each step in detail.

## 年次日パターンで繰り返しタスクを追加する方法

### ステップ 1: プロジェクトファイルの読み込み

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Here, we initialize a new `Project` object and load an existing project file named **Project1.mpp**.

### ステップ 2: 繰り返しタスクのパラメータを定義する

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

In this step, we define parameters for our recurring task. We specify the task name, duration, and recurrence pattern. For yearly recurrence, we use the `YearlyRecurrencePattern` and set the repetition to occur on the **1st day of July** using `ByYearDayRepetition`. Additionally, we define the recurrence range from July 1 2018 to July 1 2019.

### ステップ 3: タスクをプロジェクトに追加する

```csharp
project.RootTask.Children.Add(parameters);
```

Here, we add the defined recurring task parameters to the root task of the project.

### ステップ 4: プロジェクトを MPP として保存する

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Finally, we **save the project as an MPP file**, making it ready for opening in Microsoft Project or any compatible viewer.

## なぜこれが重要か

- **Automation** – 年次タスクの手動入力を排除し、人為的エラーを減らします。  
- **Consistency** – 同じ日‑月パターンが複数年にわたって適用されることを保証します。  
- **Integration** – 作成された MPP ファイルは、Microsoft Project を使用するステークホルダーと共有できます。  

## 一般的な落とし穴とヒント

- **DateTime precision** – 開始時刻がプロジェクトカレンダーと一致していることを確認してください。そうでないと、タスクがずれて表示される可能性があります。  
- **Time zones** – API は `DateTime` オブジェクトで動作します。アプリケーションが複数の地域にまたがる場合は、UTC 変換を検討してください。  
- **License enforcement** – 評価モードでは、保存された MPP に透かしが入る可能性があります。本番環境では有効なライセンスを使用してください。

## よくある質問

**Q: Aspose.Tasks は複雑な繰り返しパターンを処理できますか？**  
A: はい、Aspose.Tasks は年次、月次、週次、日次の繰り返しを含むさまざまな繰り返しパターンを包括的にサポートしています。

**Q: Aspose.Tasks はさまざまなプロジェクトファイル形式に対応していますか？**  
A: もちろんです。Aspose.Tasks は MPP、XML、CSV などの一般的なプロジェクトファイル形式をサポートしており、異なるプロジェクト管理ツール間の互換性を確保します。

**Q: Aspose.Tasks は開発者向けのドキュメントやサポートを提供していますか？**  
A: はい、開発者は豊富なドキュメントにアクセスでき、問題や質問がある場合は Aspose.Tasks コミュニティフォーラムで支援を受けることができます。

**Q: Aspose.Tasks を使用して、期間や開始日などのタスクプロパティをカスタマイズできますか？**  
A: もちろんです。Aspose.Tasks はタスクプロパティを動的に操作できる強力な API を提供しており、期間、開始日、依存関係などをカスタマイズできます。

**Q: Aspose.Tasks は小規模からエンタープライズ規模のプロジェクトまで対応していますか？**  
A: はい、Aspose.Tasks は個々のタスクから大規模エンタープライズプロジェクトまで、あらゆる規模のプロジェクトに取り組む開発者のニーズに応えるよう設計されています。

---

**最終更新日:** 2026-04-03  
**テスト環境:** Aspose.Tasks 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}