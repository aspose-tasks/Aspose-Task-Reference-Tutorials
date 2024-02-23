---
title: Aspose.Tasks for .NET を使用して WBS コード マスクをマスターする
linktitle: Aspose.Tasks の WBS コード マスクのコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用してプロジェクト管理を強化します。この包括的なチュートリアルでは、WBS コード マスクを簡単に作成、管理、転送する方法を学びます。
type: docs
weight: 15
url: /ja/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## 導入
プロジェクト管理のダイナミックな世界では、タスクを効率的に整理することが非常に重要です。 Aspose.Tasks for .NET は、プロジェクトの作業分解構造 (WBS) コードを簡単に管理するための強力なソリューションを提供します。このチュートリアルでは、WBS コード マスクのコレクションを詳しく調べ、Aspose.Tasks for .NET を使用して実装および操作する方法を検討します。
## 前提条件
このコーディング作業に着手する前に、次の前提条件が満たされていることを確認してください。
- C# プログラミング言語に関する実践的な知識。
-  Aspose.Tasks for .NET が開発環境にインストールされています。そうでない場合は、ダウンロードしてください[ここ](https://releases.aspose.com/tasks/net/).
- Visual Studio のようなコード エディターにより、シームレスなコーディング エクスペリエンスが実現します。
## 名前空間のインポート
まず、必要な名前空間をインポートしましょう。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. プロジェクトと WBS コード定義の初期化
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. WBS コードマスクを定義する
既存のコード マスクをすべてクリアし、新しいコード マスクを追加します。
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. コードマスク情報の表示
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. プロジェクトにタスクを追加する
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. タスク情報の取得
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. コードマスクの操作
コードマスクを削除し、削除されていることを確認します。
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. コードマスクを別のプロジェクトにコピーする
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. 別のプロジェクトのコードマスクを表示する
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. 他のプロジェクトにタスクを追加する
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. 他のプロジェクトの WBS コードを表示する
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 結論
Aspose.Tasks for .NET を使用すると、WBS コードの管理が簡単なタスクになります。このチュートリアルでは、WBS コード マスクの作成、操作、転送について説明し、プロジェクト管理エクスペリエンスを向上させるための包括的なガイドを提供します。
## よくある質問
### Q: Aspose.Tasks for .NET を他のプログラミング言語で使用できますか?
A: Aspose.Tasks は主に .NET 言語をサポートしていますが、他の言語との相互運用性オプションを検討することもできます。
### Q: Aspose.Tasks for .NET の試用版はありますか?
 A: はい、試用版をダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET に関するヘルプを求めたり、問題を報告するにはどうすればよいですか?
A: にアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートとディスカッションのため。
### Q: プロジェクト管理における WBS コードの目的は何ですか?
A: WBS コードは、プロジェクト タスクを階層的に整理および構造化するのに役立ち、プロジェクト計画への体系的なアプローチを提供します。
### Q: Aspose.Tasks for .NET で WBS コードの形式をカスタマイズできますか?
A: もちろん、Aspose.Tasks for .NET を使用すると、WBS コードの形式と構造を完全に制御できます。