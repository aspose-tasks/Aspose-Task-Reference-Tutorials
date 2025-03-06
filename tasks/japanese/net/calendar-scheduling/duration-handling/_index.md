---
title: Aspose.Tasks での期間の処理
linktitle: Aspose.Tasks での期間の処理
second_title: Aspose.Tasks .NET API
description: ステップバイステップのチュートリアルで、Aspose.Tasks for .NET で期間を効果的に処理する方法を学びます。
weight: 30
url: /ja/net/calendar-scheduling/duration-handling/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での期間の処理

## 導入

プロジェクト管理アプリケーションでは、期間を効果的に処理することが重要です。 Aspose.Tasks for .NET は、期間を効率的に管理するための堅牢な機能を提供します。このチュートリアルでは、Aspose.Tasks for .NET を使用した期間処理のさまざまな側面を検討します。

## 前提条件

チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。

1. C# の基本知識: 例を理解して実装するには、C# プログラミング言語に精通していることが不可欠です。
2. Visual Studio: Visual Studio IDE をインストールして、.NET アプリケーションを作成および実行します。
3.  Aspose.Tasks for .NET: Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).

## 名前空間のインポート

まず、Aspose.Tasks 機能を使用するために必要な名前空間をインポートしましょう。

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

各例をステップバイステップのガイド形式で複数のステップに分けてみましょう。

## タスクの期間の更新

### ステップ 1: プロジェクト ファイルをロードする

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### ステップ 2: タスクと期間を取得する

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### ステップ 3: 更新期間

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### ステップ 4: 更新された期間を表示する

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## タスクの期間を減算する

### ステップ 1: プロジェクト ファイルをロードする

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### ステップ 2: タスクと期間を取得する

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### ステップ 3: 期間を減算する

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### ステップ 4: 更新された期間を表示する

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## 期間を TimeSpan に変換する

### ステップ 1: プロジェクト ファイルをロードする

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### ステップ 2: タスクと期間を取得する

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### ステップ 3: 期間を TimeSpan に変換する

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## 期間を文字列に変換する

### ステップ 1: プロジェクト ファイルをロードする

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### ステップ 2: タスクと期間を取得する

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### ステップ 3: 期間を文字列に変換する

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET での期間処理のさまざまな側面について説明しました。プロジェクト管理を成功させるには、期間を理解し効果的に管理することが不可欠です。 Aspose.Tasks は、.NET アプリケーションでの期間管理タスクを簡素化するための包括的な機能を提供します。

## よくある質問

### Q1: Aspose.Tasks for .NET とは何ですか?

A1: Aspose.Tasks for .NET は、.NET アプリケーションで Microsoft Project ファイルを操作するための強力なライブラリです。

### Q2: Aspose.Tasks は複雑なプロジェクト構造を処理できますか?

A2: はい、Aspose.Tasks は複雑なプロジェクト構造を簡単に処理でき、操作用の広範な API を提供します。

### Q3: Aspose.Tasks for .NET は .NET Core と互換性がありますか?

A3: はい、Aspose.Tasks for .NET は .NET Core と互換性があるため、クロスプラットフォーム アプリケーションで使用できます。

### Q4: Aspose.Tasks は Microsoft Project ファイルの読み取りと書き込みをサポートしていますか?

A4: はい、Aspose.Tasks は、MPP、XML、MPX などのさまざまな形式の Microsoft Project ファイルの読み取りと書き込みをサポートしています。

### Q5: Aspose.Tasks for .NET の試用版はありますか?

A5: はい、Aspose.Tasks for .NET の無料トライアルを次のサイトから入手できます。[ここ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
