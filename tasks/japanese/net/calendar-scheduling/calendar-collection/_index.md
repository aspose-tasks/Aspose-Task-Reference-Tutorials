---
date: 2026-04-13
description: Aspose.Tasks for .NETで作業時間の設定方法とカレンダーコレクションの管理方法を学びましょう。Microsoft Projectからカレンダーをインポートし、カレンダー
  プロジェクトを削除し、名前でカレンダーを簡単に取得できます。
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Aspose.Tasks のカレンダー コレクションの管理
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks カレンダーコレクションで作業時間を設定する
url: /ja/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks カレンダー コレクションで作業時間を設定する

このチュートリアルでは、**set working hours** を設定し、Aspose.Tasks for .NET を使用してカレンダー コレクションを管理する方法を学びます。カレンダーは作業日、休日、例外を定義するため、これらをマスターするとプロジェクト スケジュールを正確に制御できます。また、Microsoft Project からカレンダーをインポートし、プロジェクトからカレンダーを削除し、名前でカレンダーを取得する方法も示します。

## クイック回答
- **What is the primary class for calendars?** `Project.Calendars` collection.
- **How do I set working hours?** Create or modify a `Calendar` object and define its `WorkingTime`.
- **Can I import calendars from Microsoft Project?** Yes – load an MPP file and access its calendars.
- **How to remove a calendar from a project?** Use `Project.Calendars.Remove(calendar)`.
- **How to retrieve a calendar by name?** Call `Project.Calendars.GetByName("YourCalendar")`.

## 前提条件

1. Visual Studio: Install Visual Studio or any other compatible IDE for .NET development.  
2. Aspose.Tasks for .NET: Download and install Aspose.Tasks for .NET from [here](https://releases.aspose.com/tasks/net/).  
3. Basic understanding of C#: Familiarity with C# programming language will be beneficial.

## 名前空間のインポート

First, let's import the necessary namespaces to work with Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## 新しいカレンダーの作成

### 手順 1: 新しい `Project` オブジェクトを初期化する。
```csharp
var project = new Project();
```

### 手順 2: カレンダーをプロジェクトのカレンダー コレクションに追加する。
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 手順 3: カレンダーを反復処理し、名前を表示する。
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## カレンダーの作業時間を設定する方法

To **set working hours**, you modify the `WorkingTime` collection of a `Calendar`.  
For example, you can define a standard 9 am‑5 pm workday or add custom exceptions.  
The code for this is identical to the examples shown later when we create a standard calendar.

## カレンダーを新しいカレンダーに置き換える

### 手順 1: 既存のプロジェクトをロードする。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 手順 2: 既存のカレンダーを削除する（存在する場合）。  
この例は **remove calendar project** シナリオを示しています。
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### 手順 3: 新しいカレンダーを追加する。
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## 名前または ID でカレンダーを取得する

### 手順 1: プロジェクトをロードする。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 手順 2: 名前または UID でカレンダーを取得する。  
この例は **get calendar by name** 操作を示しています。
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### 手順 3: カレンダーの詳細を表示する。
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## カレンダーの反復処理

### 手順 1: プロジェクトをロードする。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 手順 2: カレンダーの数を取得する。
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 手順 3: カレンダー コレクションを反復し、名前を表示する。
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 標準カレンダーの作成

### 手順 1: 新しいプロジェクトを初期化する。
```csharp
var project = new Project();
```

### 手順 2: 新しいカレンダーを定義し、標準に設定する。
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 手順 3: プロジェクトを保存する。
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## 一般的な問題と解決策

- **Calendar not found when using `GetByName`** – Ensure the exact name matches the case used when the calendar was added.  
- **Working hours not applied** – After setting `WorkingTime`, remember to save the project; otherwise changes remain in memory only.  
- **Importing calendars from an MPP file fails** – Verify that the source file is a valid Microsoft Project file and that you have read permissions.

## FAQ

### Q1: Aspose.Tasks でカスタム作業日を作成できますか？

A1: はい、カレンダーに例外を追加することでカスタム作業日を作成できます。

### Q2: Microsoft Project ファイルからカレンダーをインポートできますか？

A2: もちろん、Aspose.Tasks は Microsoft Project ファイルからカレンダーをインポートすることをサポートしています。

### Q3: プロジェクトから特定のカレンダーを削除するにはどうすればよいですか？

A3: コレクションからカレンダーを取得し、`Remove` メソッドを呼び出すことでカレンダーを削除できます。

### Q4: Aspose.Tasks はカレンダーをさまざまな形式にエクスポートすることをサポートしていますか？

A4: はい、Aspose.Tasks は XML、MPP などのさまざまな形式へのカレンダーのエクスポートを可能にします。

### Q5: カレンダー内の特定の日の作業時間をカスタマイズできますか？

A5: もちろん、カレンダーの例外を使用して個々の日の作業時間を定義できます。

## よくある質問

**Q: 24 時間シフトのカレンダーを設定する最適な方法は何ですか？**  
A: 新しいカレンダーを作成し、既存の `WorkingTime` エントリをクリアして、各平日に 00:00 から 24:00 までの単一の `WorkingTime` 範囲を追加します。

**Q: カレンダーをあるプロジェクトから別のプロジェクトにコピーできますか？**  
A: はい — `project.Save` を使用してカレンダーを XML にエクスポートし、`new Project(xmlPath)` で別のプロジェクトにインポートします。

**Q: プログラムで Microsoft Project からカレンダーをインポートするにはどうすればよいですか？**  
A: `new Project("source.mpp")` で MPP ファイルをロードすると、カレンダーは `project.Calendars` から利用可能になります。

**Q: プロジェクト内のカレンダー数に上限はありますか？**  
A: 実質的にありません。コレクションはメモリが許す限り多くのカレンダーを保持できますが、パフォーマンスのためにリストは管理しやすい範囲に保ってください。

**Q: カレンダーへの変更はそれを使用しているタスクに自動的に反映されますか？**  
A: はい — カレンダーにリンクされたタスクは、プロジェクトを保存した後に更新された作業時間を反映します。

---

**最終更新日:** 2026-04-13  
**テスト環境:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}