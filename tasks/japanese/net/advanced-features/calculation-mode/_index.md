---
date: 2026-03-24
description: Aspose.Tasks for .NETで計算モードの設定方法を学びます。自動、手動、なしの計算モードを取り上げ、タスクの依存関係を管理します。
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: .NET 用 Aspose.Tasks の計算モードの設定方法
url: /ja/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET の計算モードの設定方法

## はじめに

Aspose.Tasks for .NET は、Microsoft Project ファイルをプログラムから操作できる強力な API です。最も重要な設定のひとつが **計算モード** で、タスクの日付やプロジェクトスケジュールがどのように更新されるかを制御します。このチュートリアルでは **計算モードの設定方法** を学び、**自動計算モード**、**手動計算モード**、**None 計算モード** を確認し、これらのオプションが **タスクの依存関係の管理**、**プロジェクト開始日の作成**、**タスクの完了‑開始関係のリンク** にどのように影響するかを見ていきます。

## クイック回答
- **計算モードとは何ですか？** タスクの日付が自動的、手動的、または全く再計算されないかを決定します。  
- **なぜ手動計算モードを使用するのですか？** スケジュールの更新タイミングを完全に制御でき、大量更新時に便利です。  
- **デフォルトのモードはどれですか？** 自動計算モードで、変更後に日付が即座に更新されます。  
- **実行時にモードを変更できますか？** はい、`Project` オブジェクトの `CalculationMode` プロパティを設定するだけです。  
- **ライセンスは必要ですか？** 本番環境で使用するには有効な Aspose.Tasks ライセンスが必要です。

## Aspose.Tasks における「計算設定」とは何ですか？

計算モードの設定は、`Project.CalculationMode` プロパティに列挙値を割り当てるだけで完了します。列挙体は `Automatic`、`Manual`、`None` の 3 つのオプションを提供します。どのモードを選択するかは、即時更新が必要か、バッチ処理が必要か、または完全に制御したいかというワークフロー次第です。

## 前提条件

開始する前に、以下を用意してください。

1. **Visual Studio** – 任意の最新バージョン（2019、2022、またはそれ以降）。  
2. **Aspose.Tasks for .NET** – ライブラリを [here](https://releases.aspose.com/tasks/net/) からダウンロードしてインストールします。  
3. **Basic C# knowledge** – コンソールアプリケーションの作成や NuGet パッケージの使用に慣れている必要があります。

## 名前空間のインポート

Aspose.Tasks for .NET を使用する前に、必要な名前空間をインポートしましょう。

```csharp
using Aspose.Tasks;
using System;
```

## 計算モードの設定方法

以下に各計算モードのステップバイステップ例を示します。コードブロックは元のチュートリアルと同一です。説明文だけを拡充しています。

### 自動計算モードの適用

自動モードはタスクやリンクを変更するたびに日付を即座に再計算します。

#### 手順 1: 新しい Project インスタンスの作成

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### 手順 2: プロジェクト開始日を設定し、タスクを追加

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### 手順 3: タスクをリンク（完了‑開始）

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### 手順 4: 再計算された日付を確認

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### 手動計算モードの適用

手動モードは自動更新を無効にし、再計算を明示的に呼び出すまで変更をバッチ処理できます。

#### 手順 1: 新しい Project インスタンスの作成

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### 手順 2: プロジェクト開始日を設定し、タスクを追加

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### 手順 3: タスクプロパティを確認

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### 手順 4: タスクをリンクし、日付を確認（自動再計算なし）

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### None 計算モードの適用

None モードはすべての内部計算をオフにします。スケジュール変更なしでデータの読み取りやエクスポートだけを行いたい場合に使用します。

#### 手順 1: 新しい Project インスタンスの作成

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### 手順 2: 新しいタスクを追加

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### 手順 3: タスクプロパティを確認（自動 ID 付与なし）

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## よくある問題と解決策

| 問題 | 発生理由 | 対策 |
|------|----------|------|
| タスクをリンクした後に日付が更新されない | プロジェクトが **Manual** または **None** モードになっている | `project.CalculationMode = CalculationMode.Automatic` と設定するか、`project.Calculate()` を手動で呼び出す |
| タスク ID が 0 のままになる | **None** モードでは ID が生成されないため | **Automatic** または **Manual** モードに切り替えて再計算する |
| `ArgumentException` が発生してリンクできない | **Manual** モードで再計算せずに、前タスクの開始日が後タスクより遅れている | 正しい開始日を設定するか、リンク追加後に再計算する |

## よくある質問

**Q1: 実行時にモードを動的に変更できますか？**  
A1: はい、コードの任意の位置で `CalculationMode` プロパティを変更でき、即時更新が必要な場合は `project.Calculate()` を呼び出します。

**Q2: Aspose.Tasks は Microsoft Project 以外のプロジェクト管理ファイル形式をサポートしていますか？**  
A2: Aspose.Tasks は主に Microsoft Project 形式に焦点を当てていますが、Primavera P6 XML、Primavera DB、Asta Powerproject XML もサポートしています。

**Q3: Aspose.Tasks は小規模プロジェクトとエンタープライズ規模のプロジェクトの両方に適していますか？**  
A3: もちろんです。シンプルなタスクリストから複雑な多フェーズのエンタープライズスケジュールまで、API はスケーラブルに対応します。

**Q4: Aspose.Tasks を他の .NET ライブラリやフレームワークと統合できますか？**  
A4: はい、Aspose.Tasks は ASP.NET、WPF、Xamarin、その他任意の .NET テクノロジーと組み合わせて、リッチなプロジェクト管理ソリューションを構築できます。

**Q5: Aspose.Tasks ユーザー向けのコミュニティフォーラムやサポートチャネルはありますか？**  
A5: はい、[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) でコミュニティサポートやディスカッションが利用できます。

**最終更新日:** 2026-03-24  
**テスト環境:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}