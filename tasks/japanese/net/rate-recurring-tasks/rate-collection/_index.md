---
title: Aspose.Tasks で MS プロジェクトのレートをマスターする
linktitle: Aspose.Tasks のレートのコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project ファイルのレートを管理する方法を学びます。効果的なリソース管理のためのステップバイステップのチュートリアル。
weight: 11
url: /ja/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で MS プロジェクトのレートをマスターする

## 導入
Aspose.Tasks for .NET を使用して MS Project でレートを管理するチュートリアルへようこそ。このガイドでは、Aspose.Tasks を使用して MS Project ファイル内のレートを操作するプロセスについて説明します。経験豊富な開発者であっても、.NET 開発を始めたばかりであっても、このチュートリアルでは、プロジェクト内でレートを効果的に処理するための手順を段階的に説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
### 1. Visual Studioのインストール
システムに Visual Studio がインストールされていることを確認してください。まだダウンロードしていない場合は、Web サイトからダウンロードできます。
### 2. .NET 用の Aspose.Tasks
 Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/tasks/net/).
### 3. C# と .NET の基礎知識
このチュートリアルで提供されるコード例をより深く理解するには、C# プログラミング言語と .NET Framework の基本をよく理解してください。
## 名前空間のインポート
C# プロジェクトで、Aspose.Tasks 機能を使用するために必要な名前空間をインポートします。
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
ここで、各例を複数のステップに分けてみましょう。
## ステップ 1: MS プロジェクト ファイルをロードする
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
ここでは、新しいものを作成します`Project`既存の MS Project ファイルをロードしてオブジェクトを作成します。
## ステップ 2: リソースを追加し、作業量と料金を設定する
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
新しいリソースをプロジェクトに追加し、そのタイプを作業、作業量、標準レートとして設定します。
## ステップ 3: リソースに料金を追加する
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
開始日と終了日、標準料金、料金形式を指定して料金をリソースに追加します。
## ステップ 4: 料金情報を印刷する
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
このステップでは、リソースに関連付けられた料金に関する情報を出力します。
## ステップ 5: 料金を更新する
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
特定のレートの終了日を更新します。
## ステップ 6: 料金を削除する
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
このステップでは、特定のタイプのレートをすべて削除します。
## ステップ 7: 残りのレートを反復処理する
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
最後に、削除後の残りのレートを繰り返します。
## 結論
結論として、このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project ファイルのレートを管理するための包括的なガイドを提供しました。このチュートリアルで概説されている段階的な手順に従うことで、プロジェクト内でレートを効率的に処理し、正確なリソース管理を確保できます。
## よくある質問
### Q: Aspose.Tasks for .NET を他のプロジェクト管理ソフトウェアと一緒に使用できますか?
A: はい、Aspose.Tasks for .NET は、MS Project、Primavera などを含むさまざまなプロジェクト管理ソフトウェアとの統合をサポートしています。
### Q: Aspose.Tasks for .NET は、MS Project ファイルのさまざまなバージョンと互換性がありますか?
A: もちろん、Aspose.Tasks for .NET はさまざまなバージョンの MS Project ファイルの操作をサポートしており、柔軟性と互換性を確保しています。
### Q: Aspose.Tasks for .NET はドキュメントとサポートを提供しますか?
 A: はい、Aspose.Tasks で包括的なドキュメントを見つけたり、サポート フォーラムにアクセスしたりできます。[Webサイト](https://reference.aspose.com/tasks/net/).
### Q: 購入する前に Aspose.Tasks for .NET を試すことはできますか?
A: はい、Aspose.Tasks for .NET の無料トライアルを利用して、その機能と要件との互換性を評価できます。
### Q: Aspose.Tasks for .NET のライセンスはどのように購入できますか?
 A: Aspose.Tasks for .NET のライセンスは、[Webサイト](https://purchase.aspose.com/temporary-license/)、ニーズに合わせた柔軟なライセンス オプションを提供します。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
