---
title: Aspose.Tasks の計算モード
linktitle: Aspose.Tasks の計算モード
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET で計算モードを効果的に管理し、プロジェクトのスケジュールとタスクの依存関係を合理化する方法を学びます。
type: docs
weight: 29
url: /ja/net/advanced-features/calculation-mode/
---
## 導入

Aspose.Tasks for .NET は、開発者が .NET アプリケーションで Microsoft Project ファイルをプログラム的に操作できるようにする強力な API です。プロジェクト ファイルを操作する際の重要な側面の 1 つは、タスクとプロジェクト スケジュールの計算方法と更新方法を決定する計算モードの管理です。このチュートリアルでは、Aspose.Tasks for .NET でサポートされているさまざまな計算モードを詳しく説明し、それらを効果的に使用する方法を示します。

## 前提条件

始める前に、次のものが揃っていることを確認してください。

1. Visual Studio: Visual Studio がシステムにインストールされていることを確認してください。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. C# プログラミングの基本的な理解: C# プログラミングの概念を理解します。

## 名前空間のインポート

Aspose.Tasks for .NET の使用を開始する前に、必要な名前空間をインポートしましょう。

```csharp
using Aspose.Tasks;
using System;


```

## 自動計算モードの適用

### ステップ 1: 新しいプロジェクト インスタンスを作成する

新しいものを初期化する`Project`オブジェクトを作成し、そのオブジェクトを設定します`CalculationMode`財産を`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### ステップ 2: プロジェクトの開始日を設定し、タスクを追加する

プロジェクトの開始日を定義し、それにタスクを追加します。

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### ステップ 3: タスクをリンクする

タスク間の依存関係を確立します。

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### ステップ 4: 再計算された日付を確認する

日付が自動的に再計算されているかどうかを確認します。

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
//必要に応じて検証を追加します
```

## 手動計算モードの適用

### ステップ 1: 新しいプロジェクト インスタンスを作成する

新しいものを初期化する`Project`オブジェクトを作成し、そのオブジェクトを設定します`CalculationMode`財産を`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### ステップ 2: プロジェクトの開始日を設定し、タスクを追加する

プロジェクトの開始日を定義し、それにタスクを追加します。

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### ステップ 3: タスクのプロパティを確認する

タスクのプロパティが手動モードで正しく設定されているかどうかを確認します。

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
//必要に応じて検証を追加します
```

### ステップ 4: タスクをリンクし、日付を確認する

タスクをリンクし、日付が再計算されていないか確認してください。

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## なし計算モードを適用する

### ステップ 1: 新しいプロジェクト インスタンスを作成する

新しいものを初期化する`Project`オブジェクトを作成し、そのオブジェクトを設定します`CalculationMode`財産を`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### ステップ 2: 新しいタスクを追加する

新しいタスクをプロジェクトに追加します。

```csharp
var task = project.RootTask.Children.Add("Task");
```

### ステップ 3: タスクのプロパティを確認する

タスクのプロパティが自動的に計算されていないか確認してください。

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
//必要に応じて検証を追加します
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET で利用可能な計算モードを調べ、それらを実際のシナリオに適用する方法を学びました。自動、手動、または計算なしモードが必要な場合でも、Aspose.Tasks はプロジェクトの要件に合わせた柔軟性を提供します。

## よくある質問

### Q1: 実行時に計算モードを動的に変更できますか?

A1: はい、実行中の任意の時点でプロジェクトの計算モードを変更できます。`CalculationMode`財産。

### Q2: Aspose.Tasks は Microsoft Project 以外のプロジェクト管理ファイル形式をサポートしていますか?

A2: Aspose.Tasks は主に Microsoft Project ファイル形式に焦点を当てていますが、Primavera P6 XML、Primavera DB、Asta Powerproject XML などの他の形式もサポートしています。

### Q3: Aspose.Tasks は小規模プロジェクトとエンタープライズ レベルのプロジェクトの両方に適していますか?

A3：もちろんです！ Aspose.Tasks は、包括的な機能と堅牢な API により、小規模プロジェクトとエンタープライズ レベルのプロジェクトの両方のニーズに応えるように設計されています。

### Q4: Aspose.Tasks を他の .NET ライブラリおよびフレームワークと統合できますか?

A4: はい、Aspose.Tasks を他の .NET ライブラリおよびフレームワークとシームレスに統合して、アプリケーションの機能を強化できます。

### Q5: Aspose.Tasks ユーザーが利用できるコミュニティ フォーラムまたはサポート チャネルはありますか?

 A5: はい、ご覧いただけます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティのサポートとディスカッションのために。