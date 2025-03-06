---
title: Aspose.Tasks で MS プロジェクト属性コレクションを管理する
linktitle: Aspose.Tasks での拡張属性コレクションの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project の拡張属性を効率的に管理する方法を学びます。ステップバイステップのガイダンスに従って、タスクの属性をシームレスに操作します。
weight: 12
url: /ja/net/tasks-project-management/extended-attribute-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で MS プロジェクト属性コレクションを管理する

## 導入
Aspose.Tasks for .NET を使用して MS Project の拡張属性を効率的に管理したいと考えていますか?このチュートリアルでは、プロセスを段階的に説明します。飛び込んでみましょう！
## 前提条件
始める前に、以下のものがあることを確認してください。
1. Visual Studio: システムに Visual Studio をインストールします。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET をダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. C# の基本知識: C# プログラミング言語の基本を理解します。

## 名前空間のインポート
まず、必要な名前空間をプロジェクトにインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    
```
## ステップ 1: プロジェクト ファイルをロードする
まず、次のコード スニペットを使用して MS Project ファイルを読み込みます。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## ステップ 2: タスクと拡張属性にアクセスする
特定のタスクとその拡張属性にアクセスします。
```csharp
var task = project.RootTask.Children.GetById(1);
```
## ステップ 3: 拡張属性をクリアする
必要に応じて、既存の拡張属性をクリアします。
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## ステップ 4: 拡張属性定義を作成する
新しい拡張属性の定義を作成します。
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## ステップ 5: タスク拡張属性を反復処理する
タスクの拡張属性を反復処理します。
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## ステップ 6: 拡張属性を追加する
新しい拡張属性をタスクに追加します。
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## ステップ 7: 拡張属性を使用する
必要に応じて、拡張属性に対する操作を実行します。
## ステップ 8: 拡張属性を削除する
拡張属性をインデックスまたは条件によって削除します。
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## ステップ 9: 属性を別のタスクにコピーする
同じまたは異なるプロジェクト内の別のタスクに属性をコピーします。
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## 結論
MS Project の拡張属性コレクションの管理は、Aspose.Tasks for .NET を使用してシームレスになります。このチュートリアルで概説されている手順に従うことで、拡張属性を効率的に処理し、プロジェクト管理機能を強化できます。
## よくある質問
### Q: 複数のプロジェクトにわたって拡張属性を操作できますか?
A: はい、Aspose.Tasks for .NET を使用して、異なるプロジェクトのタスク間で拡張属性をコピーできます。
### Q: タスクごとの拡張属性の数に制限はありますか?
A: Aspose.Tasks for .NET では、タスクごとの拡張属性の数に固有の制限はありません。
### Q: カスタム拡張属性フィールドを作成できますか?
A: もちろんです！ Aspose.Tasks for .NET を使用すると、プロジェクトの要件に合わせたカスタム拡張属性フィールドを定義できます。
### Q: Aspose.Tasks for .NET は、さまざまなバージョンの MS Project ファイルの読み取りと書き込みをサポートしていますか?
A: はい、Aspose.Tasks for .NET は、さまざまなバージョンの MS Project ファイル形式をサポートしています。
### Q: Aspose.Tasks for .NET の試用版はありますか?
 A: はい、以下から無料トライアルをダウンロードできます。[ここ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
