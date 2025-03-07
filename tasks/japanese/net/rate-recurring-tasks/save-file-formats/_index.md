---
title: MS プロジェクト ファイルをさまざまな形式で Aspose.Tasks に保存する
linktitle: Aspose.Tasks でのさまざまな形式でのファイルの保存
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project ファイルをさまざまな形式で保存する方法を学びます。効率的なプロジェクト管理のための簡単なステップ。
weight: 17
url: /ja/net/rate-recurring-tasks/save-file-formats/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS プロジェクト ファイルをさまざまな形式で Aspose.Tasks に保存する

## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project ファイルをさまざまな形式で保存する方法を説明します。 Aspose.Tasks は、開発者がプロジェクト ファイルをプログラムで操作および管理できるようにする強力な API です。
## 前提条件
始める前に、以下のものがあることを確認してください。
1.  Aspose.Tasks for .NET:Aspose.Tasks for .NET をダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
2. 開発環境: Visual Studio などの .NET 開発環境をセットアップします。
3. C# の基本的な理解: C# プログラミング言語に精通していると役立ちます。

## 名前空間のインポート
必要な名前空間を C# ファイルの先頭にインポートしてください。
```csharp

using Aspose.Tasks.Saving;
```
## ステップ 1: プロジェクト オブジェクトを作成する
まず、Project オブジェクトを作成し、Microsoft Project ファイルをロードします。
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## ステップ 2: プロジェクトを CSV 形式で保存する
それでは、プロジェクトを CSV 形式で保存してみましょう。 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## ステップ 3: 他の形式を調べる
Aspose.Tasks は、XML、PDF、XLSX など、プロジェクト ファイルを保存するためのさまざまな形式をサポートしています。単に変更するだけで、これらの形式を調べることができます。`SaveFileFormat`のパラメータ`Save`方法。
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
次の手順に従うと、Aspose.Tasks for .NET を使用して Microsoft Project ファイルをさまざまな形式で簡単に保存できます。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project ファイルをさまざまな形式で保存する方法を学びました。 Aspose.Tasks は、プロジェクト ファイルをプログラムで操作するプロセスを簡素化し、開発者に柔軟性と効率性を提供します。
## よくある質問
### Q: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか?
A: Aspose.Tasks は、Microsoft Project 2003 XML、Microsoft Project 2007 MPP、および Microsoft Project 2010 MPP 形式をサポートしています。
### Q: 購入する前に Aspose.Tasks を試すことはできますか?
 A: はい、以下から無料トライアルをダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks のサポートを受けるにはどうすればよいですか?
A: Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks では一時ライセンスを利用できますか?
 A: はい、一時ライセンスは評価目的で利用できます。 1つ入手できます[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks の価格はいくらですか?
 A: 価格情報は、Aspose.Tasks 購入ページで確認できます。[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
