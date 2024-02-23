---
title: MS Project をマスターする Aspose.Tasks の保存オプション
linktitle: Aspose.Tasks の一般的な保存オプション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project ファイルを効率的に保存する方法を学びます。プロジェクトに合わせて出力オプションを簡単にカスタマイズできます。
type: docs
weight: 17
url: /ja/net/saving-options/general-save-options/
---
## 導入
Aspose.Tasks for .NET は、Microsoft Project ファイルをプログラムで操作するための強力な機能を提供します。このチュートリアルでは、Aspose.Tasks が提供するさまざまなオプションを使用して MS Project ファイルを保存する複雑な手順を詳しく説明します。具体的には、Aspose.Tasks で使用できる一般的な保存オプションに焦点を当て、特定の要件に合わせて出力を調整できるようにします。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET を次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/).
2. .NET Framework の基本的な理解: .NET プログラミングの概念に精通していると有益です。

## 名前空間のインポート
コードに入る前に、必要な名前空間を必ずインポートしてください。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## ステップ 1: プロジェクト ファイルをロードする
まず、Aspose.Tasks を使用して MS Project ファイルをロードする必要があります。
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## ステップ 2: 保存オプションを定義する
要件に応じて保存オプションを定義します。この例では、`Spreadsheet2003SaveOptions`、
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## ステップ 3: ビューの列をカスタマイズする
ガント チャート、リソース ビュー、割り当てビューなどのビュー列をカスタマイズできます。それぞれに列を追加する方法は次のとおりです。
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## ステップ 4: オプションを指定してプロジェクトを保存する
最後に、指定したオプションを使用してプロジェクトを保存します。
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 結論
Aspose.Tasks for .NET を使用して一般的な MS Project 保存オプションをマスターすると、プロジェクトのニーズに応じて出力形式を効率的にカスタマイズできるようになります。
## よくある質問
### Q: Aspose.Tasks は、MS Project ファイルのさまざまなバージョンと互換性がありますか?
A: はい、Aspose.Tasks はさまざまなバージョンの MS Project ファイルをサポートしており、さまざまな環境間での互換性を確保しています。
### Q: 購入する前に Aspose.Tasks を試すことはできますか?
 A: はい、無料トライアルを利用して Aspose.Tasks を探索できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks のドキュメントはどこで見つけられますか?
A: 詳細なドキュメントが見つかります。[ここ](https://reference.aspose.com/tasks/net/)、Aspose.Tasks 機能の使用に関する包括的なガイダンスを提供します。
### Q: Aspose.Tasks の一時ライセンスを取得するにはどうすればよいですか?
 A: 一時ライセンスは評価目的で使用できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks 関連のクエリのサポートはどこに問い合わせればよいですか?
 A: Aspose.Tasks コミュニティ フォーラムに参加できます。[ここ](https://forum.aspose.com/c/tasks/15)専門家や開発者仲間からの支援が得られます。