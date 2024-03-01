---
title: Aspose.Tasks でのカレンダー コレクションの管理
linktitle: Aspose.Tasks でのカレンダー コレクションの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でカレンダー コレクションを効率的に管理する方法を学びます。カレンダーを簡単に作成、変更、操作できます。
type: docs
weight: 11
url: /ja/net/calendar-scheduling/calendar-collection/
---
## 導入

このチュートリアルでは、Aspose.Tasks for .NET でカレンダー コレクションを管理する方法を検討します。カレンダーはプロジェクト管理において重要な役割を果たし、稼働日、休日、例外を定義します。 Aspose.Tasks は、プロジェクト内でカレンダーを操作するための堅牢な機能を提供します。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. Visual Studio: Visual Studio または .NET 開発用のその他の互換性のある IDE をインストールします。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET をダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. C# の基本的な理解: C# プログラミング言語に精通していると有益です。

## 名前空間のインポート

まず、Aspose.Tasks を操作するために必要な名前空間をインポートしましょう。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## 新しいカレンダーを作成する

### ステップ 1: 新しいファイルを初期化する`Project` object.
```csharp
var project = new Project();
```

### ステップ 2: プロジェクトのカレンダー コレクションにカレンダーを追加します。
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### ステップ 3: カレンダーを繰り返し処理し、カレンダーの名前を表示します。
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## カレンダーを新しいカレンダーに置き換える

### ステップ 1: 既存のプロジェクトをロードします。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ステップ 2: 既存のカレンダーを削除します (存在する場合)。
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### ステップ 3: 新しいカレンダーを追加します。
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## 名前または ID でカレンダーを取得する

### ステップ 1: プロジェクトをロードします。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ステップ 2: 名前または UID でカレンダーを取得します。
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### ステップ 3: カレンダーの詳細を表示します。
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## カレンダーの反復処理

### ステップ 1: プロジェクトをロードします。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ステップ 2: カレンダーの数を取得します。
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### ステップ 3: カレンダー コレクションと表示名を繰り返し処理します。
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 標準カレンダーの作成

### ステップ 1: 新しいプロジェクトを初期化します。
```csharp
var project = new Project();
```

### ステップ 2: 新しいカレンダーを定義し、それを標準にします。
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### ステップ 3: プロジェクトを保存します。
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## 結論

Aspose.Tasks for .NET でカレンダー コレクションを管理することは、効果的なプロジェクト管理に不可欠です。提供されている機能を使用すると、プロジェクトの要件に応じてカレンダーを効率的に作成、変更、操作できます。

## よくある質問

### Q1: Aspose.Tasks でカスタム稼働日を作成できますか?

A1: はい、カレンダーに例外を追加することで、カスタムの稼働日を作成できます。

### Q2: Microsoft Project ファイルからカレンダーをインポートすることはできますか?

A2: もちろん、Aspose.Tasks は Microsoft Project ファイルからのカレンダーのインポートをサポートしています。

### Q3: プロジェクトから特定のカレンダーを削除するにはどうすればよいですか?

 A3: コレクションからカレンダーを取得して、`Remove`方法。

### Q4: Aspose.Tasks は、カレンダーのさまざまな形式へのエクスポートをサポートしていますか?

A4: はい、Aspose.Tasks を使用すると、カレンダーを XML、MPP などのさまざまな形式にエクスポートできます。

### Q5: カレンダーの特定の日の勤務時間をカスタマイズできますか?

A5: 確かに、カレンダーの例外を使用して、個々の日の労働時間を定義できます。