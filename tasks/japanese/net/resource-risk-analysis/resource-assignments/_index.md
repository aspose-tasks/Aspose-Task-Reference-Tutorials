---
title: Aspose.Tasks での MS プロジェクトのリソース割り当ての処理
linktitle: Aspose.Tasks でのリソース割り当ての処理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project のリソース割り当てを効率的に処理する方法を学びます。この包括的なガイドは、開発者向けに段階的なガイダンスを提供します。
weight: 11
url: /ja/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での MS プロジェクトのリソース割り当ての処理

## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project のリソース割り当てを効率的に処理する方法を詳しく説明します。 Aspose.Tasks は、開発者が Microsoft Project ファイルをプログラムで操作できるようにする強力な API です。これらの手順に従うことで、.NET アプリケーション内でリソースの割り当てを効果的に管理する方法を学習できます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

## 名前空間のインポート
まず、.NET プロジェクトで Aspose.Tasks 機能を利用するために必要な名前空間をインポートする必要があります。これも：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
次に、Aspose.Tasks を使用して MS Project のリソース割り当てを処理する方法を包括的に理解するために、提供された例を複数のステップに分解してみましょう。
## ステップ 1: プロジェクトとカレンダーの設定をセットアップする
まず、新しいプロジェクト インスタンスを作成し、プロジェクトのカレンダー設定をセットアップします。
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## ステップ 2: プロジェクトにタスクを追加する
次に、新しいタスクをプロジェクトのルート タスクに追加します。
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## ステップ 3: リソース割り当てを作成し、タイムスケール データを生成する
ここで、タスクの新しいリソース割り当てを作成し、タイムスケール データを生成します。
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## ステップ 4: タスクを分割する
開始日と終了日を指定して、タスクを複数の部分に分割します。
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## ステップ 5: 作業輪郭を設定する
割り当ての作業輪郭タイプを設定します。
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## ステップ 6: プロジェクトを保存する
最後に、変更を加えたプロジェクト ファイルを保存します。
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## 結論
結論として、Aspose.Tasks for .NET を使用して Microsoft Project のリソース割り当てを処理するのは簡単なプロセスです。このチュートリアルで概説されている手順に従うことで、.NET アプリケーション内でリソースの割り当てを効率的に管理できます。
## よくある質問
### Aspose.Tasks は複雑なプロジェクト構造を処理できますか?
はい、Aspose.Tasks は、複雑なプロジェクト構造を効率的に処理するための包括的な機能を提供します。
### Aspose.Tasks は Microsoft Project のさまざまなバージョンと互換性がありますか?
はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project をサポートしており、さまざまな環境間での互換性を確保しています。
### 特定の要件に基づいてリソースの割り当てをカスタマイズできますか?
確かに、Aspose.Tasks は、特定のプロジェクトのニーズを満たすリソース割り当ての広範なカスタマイズ オプションを提供します。
### Aspose.Tasks はプロジェクト データの他の形式へのエクスポートをサポートしていますか?
はい、Aspose.Tasks を使用すると、プロジェクト データを XML、PDF、HTML などのさまざまな形式にエクスポートできます。
### Aspose.Tasks ユーザーはテクニカル サポートを利用できますか?
はい、Aspose はフォーラムやその他のチャネルを通じて専用のテクニカル サポートを提供し、ユーザーの質問や問題をサポートします。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
