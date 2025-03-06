---
title: Aspose.Tasks の利用可能期間のコレクション
linktitle: Aspose.Tasks の利用可能期間のコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でリソースの利用可能期間を管理する方法を学習します。このステップバイステップのチュートリアルでは、有効期間の追加、更新、削除について説明し、効果的なプロジェクト リソースの計画を確実にします。
weight: 18
url: /ja/net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks の利用可能期間のコレクション

## 導入

このチュートリアルでは、Aspose.Tasks for .NET でリソースの利用可能期間コレクションを操作する方法を説明します。利用可能期間の管理はプロジェクト管理にとって重要であり、プロジェクト内のタスクにリソースがいつ利用できるかを定義できるようになります。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. Visual Studio: システムに Visual Studio がインストールされていることを確認します。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. 基本的な理解: C# および .NET Framework に関する知識。

## 名前空間のインポート

まず、必要な名前空間をプロジェクトにインポートする必要があります。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

サンプルコードを複数のステップに分けて、各部分を理解してみましょう。

## ステップ 1: プロジェクトとリソースを初期化する

```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

ここでは、プロジェクト ファイルをロードし、その ID によって特定のリソースを取得しています。

## ステップ 2: 既存の利用可能期間をクリアする

```csharp
resource.AvailabilityPeriods.Clear();
```

リソースに関連付けられている既存の利用可能期間はすべてクリアされます。

## ステップ 3: 利用可能期間を追加する

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

利用可能な期間のコレクションを繰り返し処理し、それらをリソースに追加します。

## ステップ 4: 新しい利用可能期間を挿入する

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

2013 年の新しい利用可能期間を作成し、コレクションに挿入します。

## ステップ 5: 利用可能期間を表示する

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

リソースに関連付けられた各利用可能期間の数と詳細が出力されます。

## ステップ 6: 利用可能期間を別のリソースにコピーする

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

利用可能期間をあるリソースから別のリソースにコピーします。

## ステップ 7: 利用可能期間の更新と削除

```csharp
//特定の期間の利用可能なユニットを更新する
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

//特定の期間を削除する
otherResource.AvailabilityPeriods.Remove(period2013);
```

ある期間で使用可能なユニットを更新し、コレクションから特定の期間を削除します。

## 結論

このチュートリアルでは、Aspose.Tasks for .NET で利用可能期間コレクションを操作する方法を学習しました。リソースの可用性を管理することは、効果的なプロジェクトの計画と実行に不可欠です。

## よくある質問

### Q1: 利用可能な期間にカスタム フィールドを追加できますか?

A1: いいえ、Aspose.Tasks for .NET の利用可能期間はカスタム フィールドをサポートしていません。

### Q2: 利用可能期間は特定のタスクに関連付けられていますか?

A2: いいえ、利用可能期間はリソースに関連付けられており、一般的にタスクに利用できる時期を定義します。

### Q3: 外部ソースから利用可能期間をインポートできますか?

A3: はい、Aspose.Tasks for .NET API を使用して、さまざまなデータ ソースから利用可能期間をインポートできます。

### Q4: 重複する利用可能期間はどのように処理すればよいですか?

A4: Aspose.Tasks for .NET には、重複する期間を処理するための組み込みメカニズムが提供されていません。このようなシナリオを管理するには、カスタム ロジックの実装が必要になる場合があります。

### Q5: リソースが持つことができる利用可能期間の数に制限はありますか?

A5: リソースが持つことができる利用可能期間の数に事前定義された制限はありませんが、期間が多数になるとパフォーマンスが低下する可能性があります。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
