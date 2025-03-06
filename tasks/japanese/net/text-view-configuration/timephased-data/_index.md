---
title: Aspose.Tasks for .NET を使用したタイムスケール データ処理のマスター
linktitle: Aspose.Tasks でのタイムスケール データの処理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を探索して、タイムスケール データを簡単に処理し、プロジェクト計画を強化し、リソース管理を最適化します。 #アスポーズ #タスク #MSプロジェクト
weight: 14
url: /ja/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET を使用したタイムスケール データ処理のマスター

## 導入
プロジェクト管理の世界では、時間配分されたデータを効果的に処理することは、リソースの割り当て、コストの見積もり、プロジェクト全体の計画にとって非常に重要です。 Aspose.Tasks for .NET は、カスタムのタイムスケール データをシームレスに操作するための強力なソリューションを提供します。このチュートリアルでは、Aspose.Tasks を使用してタイムスケール データを処理するプロセスを説明し、プロジェクト内のリソース管理を最適化できるようにします。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- プロジェクト管理の概念についての基本的な理解。
-  Aspose.Tasks for .NET がインストールされました。ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
- 提供されたサンプルを実装するためのコード エディター (Visual Studio など)。
## 名前空間のインポート
.NET プロジェクトでは、Aspose.Tasks 機能を利用するために必要な名前空間をインポートしてください。コード ファイルの先頭に次の行を追加します。
```csharp
    using Aspose.Tasks;
    using System;
    
```
ここで、提供された例を複数のステップに分割して、Aspose.Tasks を使用してタイムスケール データを処理する方法を説明します。
## ステップ 1: プロジェクトをセットアップする
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
ここでは、新しいプロジェクトを初期化し、その計算モードを設定します。
## ステップ 2: リソースとタスクを定義する
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
作業リソースとコスト リソース、およびタスクを作成して、プロジェクト構造をシミュレートします。
## ステップ 3: リソースをタスクに割り当てる
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
作業リソースとコストリソースをタスクに割り当てます。
## ステップ 4: カスタムのタイムスケール データを追加する
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
//costAssignment の同様の手順
costAssignment.TimephasedData.Clear();
```
作業とコストの両方の割り当てにタイムスケールのカスタム データを追加します。
## ステップ 5: タイムスケール データを表示する
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        //各タイムスケール データ エントリに関する関連情報を表示する
    }
}
```
最後に、各割り当てのタイムスケール データを表示します。
#
## 結論
Aspose.Tasks でタイムスケール データを効果的に処理すると、詳細なプロジェクト計画とリソース管理の新たな可能性が広がります。このステップバイステップのガイドに従うことで、プロジェクトの特定のニーズを満たすためにタイムスケール データを操作する方法を学びました。
## よくある質問
### Aspose.Tasks for .NET を他のプロジェクト管理ツールと併用できますか?
Aspose.Tasks は主に .NET 開発用に設計されています。ただし、その機能はさまざまなプロジェクト管理ツールを補完できます。
### Aspose.Tasks for .NET に利用できる無料トライアルはありますか?
はい、無料トライアルを試すことができます[ここ](https://releases.aspose.com/).
### Aspose.Tasks for .NET のサポートを受けるにはどうすればよいですか?
訪問[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティサポートのために。
### 一時ライセンスとは何ですか?どうすれば取得できますか?
一時ライセンスについて学ぶ[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Tasks for .NET のドキュメントはどこで見つけられますか?
総合的なものを参照してください[ドキュメンテーション](https://reference.aspose.com/tasks/net/)詳細については。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
