---
title: Aspose.Tasks を使用したプロジェクト データのマスタリング
linktitle: Aspose.Tasks でのプロジェクト データの操作
second_title: Aspose.Tasks .NET API
description: .NET で Aspose.Tasks を使用して Microsoft Project データを操作する方法を学びます。タスクの作成、リソースの追加、プロジェクトの保存が簡単に行えます。
weight: 16
url: /ja/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用したプロジェクト データのマスタリング

## 導入
このチュートリアルでは、.NET 用の Aspose.Tasks ライブラリを使用して Microsoft Project データを操作する方法を説明します。 Aspose.Tasks は、タスクの作成、リソースの追加、プロパティの設定、さまざまな形式でのプロジェクトの保存など、プロジェクト ファイルを操作するための強力な機能を提供します。
## 前提条件
始める前に、次のものが揃っていることを確認してください。
1.  Aspose.Tasks ライブラリのインストール: 以下から Aspose.Tasks ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
2. 開発環境: .NET 開発環境がセットアップされていることを確認してください。
3. C# の基礎知識: C# プログラミング言語に精通していると役立ちます。

## 名前空間のインポート
Aspose.Tasks を使用する前に、必要な名前空間をプロジェクトにインポートします。
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## ステップ 1: プロジェクト オブジェクトを初期化する
```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project();
```
この行は、`Project` Microsoft Project ファイルを表すクラス。
## ステップ 2: プロジェクトのプロパティを設定する
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
これらの行は、作業形式やタスク作成モードなどのプロジェクトのプロパティを設定する方法を示しています。
## ステップ 3: タスクの追加
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
ここでは、「タスク 1」という名前の新しいタスクがプロジェクトのルート タスクに追加されます。
## ステップ 4: タスクのプロパティを設定する
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
これらの行は、「タスク 1」の開始日、期間、終了日を設定します。
## ステップ 5: リソースの追加
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
このパートでは、作業リソースをプロジェクトに追加する方法を説明します。
## ステップ 6: リソースをタスクに割り当てる
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
これらの行は、以前に追加した時間リソースを、特定の開始日、作業日、終了日を指定して「タスク 1」に割り当てる方法を示しています。
## ステップ 7: プロジェクトの保存
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
最後に、プロジェクトは Microsoft Project XML ファイル形式で保存されます。

## 結論
このチュートリアルでは、.NET の Aspose.Tasks ライブラリを使用して Microsoft Project データを操作する方法を学習しました。ステップバイステップのガイドに従うことで、プロジェクト ファイルの操作、タスクやリソースの追加、タスクへのリソースの割り当て、プロジェクトをさまざまな形式で保存することができます。
## よくある質問
### Q: Aspose.Tasks は複雑なプロジェクト構造を処理できますか?
A: はい、Aspose.Tasks は複雑なプロジェクト構造を包括的にサポートし、タスク、リソース、割り当てを効率的に管理できるようにします。
### Q: Aspose.Tasks は Microsoft Project のさまざまなバージョンと互換性がありますか?
A: Aspose.Tasks は、Microsoft Project の幅広いバージョンをサポートしており、さまざまな環境間での互換性を確保しています。
### Q: Aspose.Tasks を他の .NET ライブラリと統合できますか?
A: もちろん、Aspose.Tasks は他の .NET ライブラリとシームレスに統合され、開発プロジェクトに柔軟性をもたらします。
### Q: Aspose.Tasks はプロジェクト スケジューリング アルゴリズムのサポートを提供しますか?
A: はい、Aspose.Tasks には、プロジェクトのタイムラインとリソース使用率の最適化に役立つ高度なスケジュール アルゴリズムが含まれています。
### Q: Aspose.Tasks ユーザー向けのコミュニティ フォーラムはありますか?
 A: はい、役立つリソースを見つけたり、他の Aspose.Tasks ユーザーと交流したりできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
