---
date: 2026-04-09
description: Aspose.Tasks を使用して、.NET プロジェクトで標準カレンダーを設定し、プロジェクトの祝日を管理して正確なスケジューリングを実現する方法を学びましょう。
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Aspose.Tasksで標準カレンダーを設定し、例外を処理する
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksで標準カレンダーを設定し、例外を処理する
url: /ja/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasksで標準カレンダーを設定し例外を処理する

## はじめに

正確なスケジューリングは、あらゆる成功プロジェクトの基盤です。実際の計画では、祝日、特別イベント、予期せぬ停止などの理由でデフォルトの作業カレンダーから外れる必要があります。Aspose.Tasks for .NET を使用すると、**標準カレンダー**設定を簡単に行い、その上にカスタム例外を重ねることができます。このチュートリアルでは、プロジェクトカレンダーを読み込み、標準カレンダーを設定し、カレンダー例外コレクション機能を使ってプロジェクトの祝日を管理する方法を学びます。

## クイック回答
- **“set standard calendar”は何をしますか？** カスタム例外を追加する前に、カレンダーをデフォルトの作業時間（午前9時〜午後5時、月曜〜金曜）にリセットします。  
- **既存の例外をクリアするメソッドはどれですか？** `Calendar.Exceptions.Clear()` は以前に定義されたすべての例外を削除します。  
- **休日はどうやって追加しますか？** `DayWorking = false` の `CalendarException` を作成し、コレクションに追加します。  
- **変更後にプロジェクトを再読み込みする必要がありますか？** いいえ、変更はメモリ上の `Project` オブジェクトに直接適用されます。  
- **必要なライブラリは何ですか？** Aspose.Tasks for .NET（サポートされている任意の .NET バージョン）と `System` 名前空間。

## 前提条件

コードに取り掛かる前に、以下を用意してください。

1. **Aspose.Tasks for .NET** – こちらからダウンロードしてください [here](https://releases.aspose.com/tasks/net/)。  
2. **C#** の基本知識 – 短いコードスニペットをいくつか書きます。  
3. **Visual Studio** や **JetBrains Rider** などの開発環境。

## 名前空間のインポート

これらの `using` ディレクティブにより、カレンダー操作に必要なクラスへアクセスできます。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## カレンダー例外とは？

*カレンダー例外* は、通常の作業スケジュールが変更される期間を表します。たとえば、全社的な祝日や一時的な残業スケジュールなどです。カレンダーに例外を追加することで、ベースカレンダーを変更せずに実世界の制約をモデル化できます。

## Aspose.Tasksで標準カレンダーを設定する方法

最初のステップは、プロジェクトファイルを読み込み、操作したいカレンダーを取得することです。

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### 手順 1: 既存の例外をクリアし標準カレンダーにリセットする

新しいルールを追加する前に、古い例外をすべてクリアし、**標準カレンダー**設定を行うのがベストプラクティスです。これによりクリーンなベースラインが確保されます。

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### 手順 2: 作業時間例外を定義する

製品発売などで一時的にスケジュールを拡張する必要がある場合があります。以下のスニペットは、数日間にわたる作業時間例外を定義し、1日2回の作業期間を含めています。

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### 手順 3: 非作業時間例外（休日）を追加する

**プロジェクトの休日** を管理するには、`DayWorking` を `false` に設定した例外を作成します。以下の例は、2 日間の休日ブロックを追加します。

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### 手順 4: カレンダー例外を表示（検証）

例外を追加した後、正しく記録されたかを確認したいことが多いでしょう。次のループは、各例外の詳細をコンソールに出力します。

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### 手順 5: すべての例外を削除（クリーンアップ）

カレンダーを元の状態に戻す必要がある場合は、プログラムで全例外を削除できます。

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## よくある問題と解決策

| 問題 | 原因 | 解決策 |
|------|------|--------|
| 保存後に例外が表示されない | 変更後にプロジェクトが保存されていない | 変更後に `project.Save("output.mpp")` を呼び出してください。 |
| 重複する例外により予期しない作業時間になる | Aspose.Tasks は重複期間に最後に追加された例外を使用します | `Add` 呼び出しの順序に注意するか、優先順位を手動で調整してください。 |
| `MakeStandardCalendar` はカスタム作業時間をリセットします | 意図的にカスタム時間をクリアするため、必要に応じて呼び出し後に再度追加してください。 | `MakeStandardCalendar` 呼び出し後にカスタム `WorkingTime` オブジェクトを追加してください。 |

## よくある質問

**Q: 1つのカレンダーに複数の例外を追加できますか？**  
A: はい、`AddRange` メソッドを使用してカレンダーに複数の例外を追加できます。

**Q: 週次の休日など、繰り返し発生する例外はどう処理しますか？**  
A: 繰り返し例外をプログラムで計算し、カスタムロジックでカレンダーに追加できます。

**Q: 外部ソースからカレンダー例外をインポートできますか？**  
A: はい、データベースや CSV ファイルなどの外部ソースからカレンダー例外を読み取り、プロジェクトに統合できます。

**Q: カレンダーに重複する例外がある場合はどうなりますか？**  
A: Aspose.Tasks for .NET は、優先順位を定義したり、プロジェクト要件に基づいて競合を解決したりすることで、重複する例外を処理できます。

**Q: 例外内の各日の作業時間をカスタマイズできますか？**  
A: はい、例外内の個々の日に対してカスタム作業時間を指定でき、特定のスケジュール要件に対応できます。

## 結論

まず **標準カレンダー** を設定し、その上にカスタム例外を重ねることで、プロジェクトスケジューリングを完全にコントロールでき、**プロジェクトの休日** やその他の特別なタイムラインを簡単に **管理** できます。Aspose.Tasks のカレンダー例外コレクションは、.NET アプリケーション内で実世界のカレンダーを直接モデル化するためのクリーンでプログラム的な方法を提供します。

---

**最終更新日:** 2026-04-09  
**テスト環境:** Aspose.Tasks 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}