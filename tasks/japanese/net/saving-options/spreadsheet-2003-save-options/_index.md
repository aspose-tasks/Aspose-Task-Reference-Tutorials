---
title: MS Project とスプレッドシート 2003 の Aspose.Tasks オプション
linktitle: スプレッドシート 2003 Aspose.Tasks の保存オプション
second_title: Aspose.Tasks .NET API
description: マスター スプレッドシート 2003 Aspose.Tasks for .NET を使用して MS プロジェクト オプションを保存します。 MS Project ファイルをプログラムでシームレスにカスタマイズして保存します。
weight: 19
url: /ja/net/saving-options/spreadsheet-2003-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project とスプレッドシート 2003 の Aspose.Tasks オプション

## 導入
このチュートリアルでは、Aspose.Tasks for .NET を活用して Spreadsheet 2003 Save MS Project オプションを利用する方法について詳しく説明します。この強力なツールにより、.NET 環境での MS Project ファイルのシームレスな操作とカスタマイズが可能になります。プロセスを段階的に見てみましょう。
## 前提条件
このチュートリアルを開始する前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/).
2. C# プログラミングに精通していること: このチュートリアルで説明する概念を理解するには、C# プログラミング言語の基本的な理解が必要です。

## 名前空間のインポート
まず、必要な名前空間を C# プロジェクトにインポートします。
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
これらの名前空間は、スプレッドシート 2003 形式を使用して MS Project ファイルを保存し、表示オプションをカスタマイズするために必要な機能へのアクセスを提供します。
## ステップ 1: プロジェクトをロードする
まず、Aspose.Tasks を使用して MS Project ファイルをロードします。
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
交換する`"Your Document Directory"`MS Project ファイルが配置されている実際のディレクトリ パスに置き換えます。
## ステップ 2: 保存オプションを定義する
のインスタンスを作成して、スプレッドシート 2003 の保存オプションを定義します。`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## ステップ 3: ビューの列をカスタマイズする
ガント チャート、リソース ビュー、および割り当てビューのビュー列をカスタマイズします。
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
これらの手順により、カスタム列がそれぞれのビューに追加され、MS Project ファイルの視覚化および分析機能が強化されます。
## ステップ 4: プロジェクトを保存する
最後に、指定したオプションを使用してプロジェクトを保存します。
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
このコマンドは、変更されたプロジェクトをスプレッドシート 2003 形式とカスタマイズされたビュー列で保存します。

## 結論
Aspose.Tasks for .NET、特に Spreadsheet 2003 Save MS Project オプションを利用すると、開発者は MS Project ファイルをプログラムで効率的に管理およびカスタマイズできるようになります。このチュートリアルで概説されているステップバイステップのガイドに従うことで、これらの機能を .NET アプリケーションにシームレスに統合し、生産性と柔軟性を向上させることができます。

## よくある質問
### Q: Aspose.Tasks for .NET は Web アプリケーションとデスクトップ アプリケーションの両方で使用できますか?
A: はい、Aspose.Tasks for .NET は Web アプリケーションとデスクトップ アプリケーションの両方にシームレスに統合でき、プラットフォーム間で一貫した機能を提供します。
### Q: Aspose.Tasks for .NET の試用版はありますか?
A: はい、Aspose.Tasks for .NET の無料トライアルにアクセスできます。[Webサイト](https://releases.aspose.com/)を使用すると、購入する前にその機能を調べることができます。
### Q: Aspose.Tasks for .NET を使用してビュー列をカスタマイズする場合に制限はありますか?
A: Aspose.Tasks for .NET は、最小限の制限付きで、ビュー列の広範なカスタマイズ オプションを提供します。ただし、複雑なカスタマイズには、ライブラリに関する高度な知識が必要になる場合があります。
### Q: Aspose.Tasks for .NET の使用中に問題が発生した場合、サポートを求めることはできますか?
 A: もちろんです！ Aspose.Tasks フォーラムで包括的なサポートとリソースを見つけることができます。[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15)では、専門家やコミュニティのメンバーが、直面する可能性のある質問や課題の解決を支援します。
### Q: Aspose.Tasks for .NET の一時ライセンスを取得するにはどうすればよいですか?
 A: Aspose.Tasks for .NET の一時ライセンスは、[購入ページ](https://purchase.aspose.com/temporary-license/)を使用すると、ライブラリの全機能を評価できます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
