---
title: Aspose.Tasks での MS プロジェクト グループ基準の操作
linktitle: Aspose.Tasks のグループ基準
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks を使用して .NET で MS Project ファイルをプログラム的に操作する方法を調べます。タスク グループと基準情報のステップバイステップの例を取得します。
type: docs
weight: 27
url: /ja/net/tasks-project-management/group-criteria/
---
## 導入
Aspose.Tasks for .NET は、.NET アプリケーションでの Microsoft Project ファイルの操作を容易にする強力な API です。プロジェクト管理ソフトウェアを開発している場合でも、プロジェクト データをプログラムで操作する必要がある場合でも、Aspose.Tasks はニーズを満たす包括的な機能セットを提供します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
### 1. C# および .NET Framework の知識
このチュートリアルで提供される例を理解して実装するには、C# プログラミング言語と .NET Framework に精通していることが不可欠です。
### 2. Aspose.Tasks for .NET のインストール
開発環境に Aspose.Tasks for .NET がインストールされていることを確認してください。ライブラリはからダウンロードできます[ここ](https://releases.aspose.com/tasks/net/)提供されるインストール手順に従ってください。
### 3. 統合開発環境（IDE）
C# コードを作成して実行するために、Visual Studio などの IDE をシステムにインストールします。

## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ステップ 1: Microsoft Project ファイルをロードする
まず、Microsoft Project ファイルへのパスを指定します。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
交換する`"Your Document Directory"`プロジェクト ファイルへのパスを置き換えます。
## ステップ 2: タスク グループ情報を取得する
次に、プロジェクト内のタスク グループに関する情報を取得します。
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
このコード スニペットは、タスク グループの合計数を出力し、2 番目のタスク グループ、その名前、および保持する条件の数を取得します。
## ステップ 3: タスクグループの基準情報を取得する
ここで、タスク グループ内の特定の基準の詳細を詳しく見てみましょう。
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
このセグメントには、インデックス、フィールド、グループ化情報、セルの色、フォントの色、グループ間隔、開始点などの基準のさまざまなプロパティが表示されます。
## ステップ 4: Criterion のフォント情報を取得する
最後に、基準のフォント関連の詳細を取得します。
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
このステップでは、フォント名、サイズ、スタイル、および基準が昇順または降順のどちらでソートされているかを出力します。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して、Microsoft Project ファイルからタスク グループと条件に関する情報を取得する方法を検討しました。ステップバイステップのガイドに従うことで、.NET アプリケーションでプログラムによってプロジェクト データを効率的に操作できます。
## よくある質問
### Aspose.Tasks は大きな Microsoft Project ファイルを処理できますか?
Aspose.Tasks は、大規模なプロジェクト ファイルを効率的に処理できるように最適化されており、高いパフォーマンスと信頼性を保証します。
### Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか?
はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project をサポートし、さまざまなファイル形式間の互換性を確保します。
### Aspose.Tasks を使用してプロジェクト データを操作できますか?
確かに、Aspose.Tasks は、タスク、リソース、カレンダーなどを含むプロジェクト データを操作するための広範な機能を提供します。
### Aspose.Tasks はさまざまな .NET プラットフォームのサポートを提供しますか?
はい、Aspose.Tasks は、.NET Framework、.NET Core、.NET Standard を含む複数の .NET プラットフォームをサポートしています。
### 支援を求めることができる Aspose.Tasks のコミュニティ フォーラムはありますか?
はい、次の場所にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)質問したり、知識を共有したり、他のユーザーと共同作業したりするため。