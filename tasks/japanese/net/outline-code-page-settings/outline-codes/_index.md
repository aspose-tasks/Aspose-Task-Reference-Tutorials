---
title: Aspose.Tasks for .NET でプロジェクト アウトライン コードを管理する
linktitle: Aspose.Tasks でのアウトライン コードの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project のアウトライン コードを管理する方法を学びます。プロジェクトの組織を簡単に簡素化します。
weight: 10
url: /ja/net/outline-code-page-settings/outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET でプロジェクト アウトライン コードを管理する

## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project のアウトライン コードを管理する方法を説明します。アウトライン コードは、ユーザーが特定の基準に従ってタスクを分類および整理できるようにする Microsoft Project のカスタム フィールドです。 Aspose.Tasks は、これらのアウトライン コードをプログラム的に読み取り、操作するプロセスを簡素化します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1.  Aspose.Tasks for .NET ライブラリ: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/tasks/net/).
2. 開発環境: Visual Studio などの .NET プログラミングに適した開発環境をセットアップします。
3. C# の基礎知識: C# プログラミング言語に精通していると、コード例を理解するのに役立ちます。

## 名前空間のインポート
まず、必要な名前空間を C# プロジェクトにインポートする必要があります。これにより、Aspose.Tasks ライブラリによって提供されるクラスとメソッドにアクセスできるようになります。
1. Visual Studio を開く: Visual Studio IDE を起動します。
2. 新しいプロジェクトを作成する: 新しい C# プロジェクトを開始するか、Aspose.Tasks を使用する既存のプロジェクトを開きます。
3. Aspose.Tasks 参照の追加: ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択し、「Aspose.Tasks」を検索して、最新バージョンをインストールします。
4. Aspose.Tasks 名前空間のインポート: C# ファイルの先頭に、次の using ディレクティブを追加します。
```csharp
using Aspose.Tasks;
using System;

```
## ステップ 1: ドキュメント ディレクトリを定義する
まず、MS Project ファイルを含むディレクトリへのパスを設定します。
```csharp
String DataDir = "Your Document Directory";
```
交換する`"Your Document Directory"`プロジェクト ファイルへの実際のパスを置き換えます。
## ステップ 2: プロジェクト ファイルをロードする
新しいインスタンスを作成する`Project` MS Project ファイルをロードしてオブジェクトを作成します。
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
これにより、指定されたファイルでプロジェクト オブジェクトが初期化されます。
## ステップ 3: アウトライン コードを読む
プロジェクト内のすべてのタスクを反復処理し、そのアウトライン コードを取得します。
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
このコード スニペットは各タスクをループし、アウトライン コードがあるかどうかを確認し、タスクに関連付けられた各アウトライン コードのフィールド ID、値 GUID、値 ID などの詳細を出力します。

## 結論
結論として、Aspose.Tasks for .NET は、Microsoft Project のアウトライン コードをプログラムで管理するための強力な機能を提供します。このチュートリアルで概説されている手順に従うと、C# を使用して MS Project ファイル内のアウトライン コードを効率的に読み取り、操作できます。
## よくある質問
### Q: Aspose.Tasks を使用してアウトライン コードを変更できますか?
A: はい、Aspose.Tasks for .NET を使用して、アウトライン コードをプログラムで変更できます。タスクのアウトライン コードにアクセスし、必要に応じて値を更新するだけです。
### Q: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか?
A: Aspose.Tasks は、2003、2007、2010、2013、2016、2019 などの幅広い Microsoft Project バージョンをサポートしています。
### Q: Aspose.Tasks を商用利用するにはライセンスが必要ですか?
A: はい、Aspose.Tasks の商用利用には有効なライセンスが必要です。ライセンスは、Aspose Web サイトから取得できます。
### Q: 購入する前に Aspose.Tasks を試すことはできますか?
A: はい、Aspose.Tasks の無料試用版を Web サイトからダウンロードして、その機能を評価できます。
### Q: Aspose.Tasks のサポートはどこで入手できますか?
 A: 次のフォーラムにアクセスすると、Aspose.Tasks のサポートを受けることができます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).## 完全なソース コード
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
