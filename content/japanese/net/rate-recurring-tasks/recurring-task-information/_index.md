---
title: Aspose.Tasks での定期的なタスク情報の抽出
linktitle: Aspose.Tasks での定期的なタスク情報の抽出
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project ファイルから定期的なタスク情報を抽出する方法を学びます。 .NET 開発者向けの簡単な統合。
type: docs
weight: 13
url: /ja/net/rate-recurring-tasks/recurring-task-information/
---
## 導入
Aspose.Tasks for .NET は、開発者が .NET アプリケーションで Microsoft Project ファイルを操作できるようにする強力なライブラリです。このチュートリアルでは、Aspose.Tasks を使用して MS Project ファイルから定期的なタスク情報を抽出する方法を説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. C# プログラミング言語の基本的な理解。
2. Visual Studio がシステムにインストールされている。
3.  Aspose.Tasks for .NET ライブラリがインストールされています。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    
```
ここで、例を複数のステップに分けてみましょう。
## ステップ 1: プロジェクト ファイルのパスを設定する
```csharp
String DataDir = "Your Document Directory";
```
交換する`"Your Document Directory"`MS Project ファイルへのパスを置き換えます。
## ステップ 2: MS Project ファイルをロードする
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
この行は新しいものを初期化します`Project`パスで指定された MS Project ファイルをロードしてオブジェクトを取得します。
## ステップ 3: タスクの定期的な情報を読み取る
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    //定期的なタスク情報にアクセスして表示する
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    //必要に応じて他の定期的なタスク情報を表示し続けます
}
```
このループはプロジェクト内のすべてのタスクを繰り返し、各タスクに関連付けられた繰り返し情報があるかどうかを確認します。存在する場合、開始日、期間、終了日など、定期的なタスクのさまざまなプロパティが取得されて表示されます。
## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project ファイルから定期的なタスク情報を抽出する方法を学習しました。この知識があれば、この機能を .NET アプリケーションに統合して、定期的なタスクをより効率的に処理できるようになります。
## よくある質問
### Q: Aspose.Tasks for .NET を使用して定期的なタスク情報を変更できますか?
A: はい、提供されている API を使用して、定期的なタスクの情報をプログラムで変更できます。
### Q: Aspose.Tasks は MS Project 以外のプロジェクト ファイル形式をサポートしていますか?
A: はい、Aspose.Tasks は MPP、XML、CSV などのさまざまなプロジェクト ファイル形式をサポートしています。
### Q: Aspose.Tasks for .NET に利用できる無料トライアルはありますか?
 A: はい、以下から無料トライアルをダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET のドキュメントはどこで見つけられますか?
 A: ドキュメントは見つかります。[ここ](https://reference.aspose.com/tasks/net/).
### Q: Aspose.Tasks for .NET のテクニカル サポートを受けるにはどうすればよいですか?
A: Aspose.Tasks フォーラムから技術サポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).