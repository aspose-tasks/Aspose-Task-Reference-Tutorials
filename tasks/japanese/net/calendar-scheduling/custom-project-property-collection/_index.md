---
title: Aspose.Tasks でのカスタム プロジェクト プロパティ コレクションの管理
linktitle: Aspose.Tasks でのカスタム プロジェクト プロパティ コレクションの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でカスタム プロジェクト プロパティを効果的に管理し、プロジェクト管理エクスペリエンスを向上させる方法を学びます。
weight: 24
url: /ja/net/calendar-scheduling/custom-project-property-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でのカスタム プロジェクト プロパティ コレクションの管理

## 導入

Aspose.Tasks for .NET を使用してプロジェクト管理エクスペリエンスを強化する準備はできていますか?カスタム プロジェクト プロパティの管理はプロジェクト管理の重要な側面であり、プロジェクトの要件に合わせた特定のメタデータを追加できるようになります。このチュートリアルでは、Aspose.Tasks for .NET を使用してカスタム プロジェクト プロパティ コレクションを効果的に操作する方法について詳しく説明します。

## 前提条件

続行する前に、次の前提条件が設定されていることを確認してください。

1. Visual Studio 環境: Visual Studio をシステムにインストールします。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET を次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/).
3. C# の基本知識: C# プログラミング言語の基本を理解します。

## 名前空間のインポート

まず、Aspose.Tasks for .NET を使用するために必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System;


```

包括的な理解のためにサンプル コードを複数のステップに分割してみましょう。

## ステップ 1: プロジェクトを初期化する

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

このステップでは、Aspose.Tasks を使用して新しいプロジェクトを初期化します。

## ステップ 2: カスタム プロパティ収集の準備状況を確認する

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

このコードは、カスタム プロパティ コレクションが読み取り専用かどうかをチェックします。

## ステップ 3: カスタム プロパティを追加する

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

ここでは、Boolean、DateTime、Double、および String 型をサポートするカスタム プロパティをプロジェクトに追加します。

## ステップ 4: カスタム プロパティにアクセスする

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

このループにより、カスタム プロパティを反復処理し、そのタイプ、名前、および値を表示できます。

## ステップ 5: カスタム プロパティ値を取得する

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

このコードは、「カスタム名」という名前の特定のカスタム プロパティの値を取得します。

## ステップ 6: カスタム プロパティ名を反復処理する

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

ここでは、カスタム プロパティの名前を反復処理して表示します。

## ステップ 7: カスタム プロパティを削除またはクリアする

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

特定のカスタム プロパティを名前で削除したり、コレクション全体をクリアしたりできます。

## 結論

Aspose.Tasks for .NET のカスタム プロジェクト プロパティ コレクションをマスターすると、プロジェクトのメタデータを効率的に管理できるようになります。このステップバイステップ ガイドに従うことで、カスタム プロパティをプロジェクト管理ワークフローにシームレスに統合し、組織化と効率性を向上させることができます。

## よくある質問

### Q1: Aspose.Tasks for .NET を使用して、任意のデータ型のカスタム プロパティをプロジェクトに追加できますか?

A1: はい、Boolean、DateTime、Double、String 型をサポートするカスタム プロパティを追加できます。

### Q2: Aspose.Tasks for .NET でカスタム プロパティ名を反復処理することは可能ですか?

 A2: もちろん、次のコマンドを使用してカスタム プロパティ名を反復処理できます。`Names`財産。

### Q3: プロジェクトから特定のカスタム プロパティを削除するにはどうすればよいですか?

 A3: カスタム プロパティを名前で削除するには、`Remove`方法。

### Q4: Aspose.Tasks for .NET は一時ライセンスをサポートしていますか?

A4: はい、評価目的で Aspose Web サイトから一時ライセンスを取得できます。

### Q5: Aspose.Tasks for .NET に関するサポートやさらなる支援はどこで入手できますか?

 A5: Aspose.Tasks フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tasks/15)ご質問やサポートがございましたら。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
