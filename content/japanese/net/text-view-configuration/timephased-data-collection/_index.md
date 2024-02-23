---
title: Aspose.Tasks でタイムスケール データ収集をマスターする
linktitle: Aspose.Tasks でのタイムスケール データの収集
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でタイムスケール データの収集を探索します。ステップバイステップガイド、よくある質問など。今すぐプロジェクト管理能力を強化してください。
type: docs
weight: 15
url: /ja/net/text-view-configuration/timephased-data-collection/
---
## 導入
Aspose.Tasks を使用して、.NET アプリケーションでタイムスケール データの力を活用したいと考えていますか?これ以上探さない！この包括的なガイドでは、Aspose.Tasks for .NET を使用してタイムスケール データを収集するプロセスを説明し、この強力なライブラリを最大限に活用できるようにします。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.Tasks for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[Aspose.Tasks .NET ドキュメント](https://reference.aspose.com/tasks/net/).
2. .NET 開発環境: 動作する .NET 開発環境がセットアップされていることを確認してください。
3. ドキュメント ディレクトリ: コード スニペット内のプレースホルダー「ドキュメント ディレクトリ」をドキュメント ディレクトリへのパスに置き換えます。
## 名前空間のインポート
.NET プロジェクトで、Aspose.Tasks 機能を利用するために必要な名前空間をインポートすることから始めます。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. プロジェクトとリソースを作成する
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. プロジェクトにタスクを追加する
```csharp
var task = project.RootTask.Children.Add("Task 1");
//タスクのプロパティを設定します...
var task2 = project.RootTask.Children.Add("Task 2");
//タスク 2 のプロパティを設定します...
```
## 3. リソースをタスクに割り当てる
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
//割り当てプロパティを設定します...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//割り当て 2 のプロパティを設定します...
```
## 4. タイムスケールデータの操作
```csharp
//輪郭のある作業輪郭を設定する
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
//タイムスケール データ収集が読み取り専用かどうかを確認する
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
//生成されたタイムスケール データをクリアする
assignment.TimephasedData.Clear();
//タイムスケール データの作成と追加
var td = new TimephasedData
{
    //タイムスケール データのプロパティを設定します...
};
assignment.TimephasedData.Add(td);
//タイムスケール データのリストを追加する
var list = new List<TimephasedData>();
//タイムスケール データ項目をリストにさらに追加します...
assignment.TimephasedData.AddRange(list);
//タイムスケール データをタイプと日付範囲でフィルター処理します
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
//フィルタリングされたタイムスケール データを印刷します...
```
## 5. タイムスケールデータの操作
```csharp
//間違ったタイムスケール データ項目を追加して削除する
var td4 = new TimephasedData
{
    //間違ったタイムスケール データ プロパティを設定します...
};
assignment.TimephasedData.Add(td4);
//間違ったタイムスケール データ項目を削除する
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
//すべてのタイムスケール項目を反復処理する
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    //タイムスケール項目の詳細を印刷...
}
```
## 6. タイムスケール データを別の割り当てにコピーする
```csharp
//タイムスケール データを別の割り当てにコピーする
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
//コレクションを単純なリストに変換する
List<TimephasedData> tds = assignment.TimephasedData.ToList();
//タイムスケール データ項目を 1 つずつ削除します
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## 結論
結論として、このチュートリアルでは、Aspose.Tasks for .NET を使用してタイムスケール データを収集する詳細なチュートリアルを提供しました。これらの手順に従うことで、この機能をプロジェクトにシームレスに統合でき、効果的な時間追跡とリソース管理が可能になります。
## よくある質問
### Aspose.Tasks for .NET を他のプロジェクト管理ツールと併用できますか?
はい。Aspose.Tasks for .NET は、一般的なプロジェクト管理ツールと連携するように設計されており、さまざまなファイル形式をサポートしています。
### Aspose.Tasks で管理できるリソースとタスクの数に制限はありますか?
Aspose.Tasks はさまざまなサイズのプロジェクトを処理し、リソースとタスクの数に厳密な制限はありません。
### Aspose.Tasks for .NET に関連する問題やクエリのサポートを受けるにはどうすればよいですか?
サポートについては、次のサイトにアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティとつながり、支援を受けることができます。
### Aspose.Tasks for .NET を購入する前に試すことはできますか?
はい、Aspose.Tasks for .NET の機能を調べるには、[無料トライアル](https://releases.aspose.com/).
### Aspose.Tasks for .NET のライセンスはどこで購入できますか?
 Aspose.Tasks for .NET のライセンスを購入できます。[ここ](https://purchase.aspose.com/buy).