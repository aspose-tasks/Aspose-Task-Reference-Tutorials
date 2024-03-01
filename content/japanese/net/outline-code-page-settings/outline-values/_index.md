---
title: Aspose.Tasks を使用して MS プロジェクトのアウトライン値をマスターする
linktitle: Aspose.Tasks でのアウトライン値の管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project のアウトライン値を効率的に管理する方法を学びます。プロジェクトのアウトラインを簡単にカスタマイズします。
type: docs
weight: 16
url: /ja/net/outline-code-page-settings/outline-values/
---
## 導入
このチュートリアルでは、.NET 用の Aspose.Tasks ライブラリを使用して Microsoft Project のアウトライン値を管理する方法を説明します。 Aspose.Tasks を使用すると、アウトライン コードを簡単に操作し、新しいアウトライン値を作成し、要件に応じてプロジェクト アウトラインをカスタマイズできます。
## 前提条件
始める前に、次のものが揃っていることを確認してください。
1.  Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
2. 開発環境: Visual Studio など、.NET Framework との互換性のある開発環境がセットアップされていることを確認してください。
3. C# プログラミングの基本的な理解: C# を使用して Aspose.Tasks ライブラリを操作するため、C# プログラミング言語の基本を理解してください。

## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    
```
## ステップ 1: プロジェクト ファイルをロードする
```csharp
//ドキュメントディレクトリへのパス。
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
この手順では、新しい Project オブジェクトを初期化し、指定されたディレクトリから Microsoft Project ファイルを読み込みます。
## ステップ 2: アウトライン コード定義を定義する
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
ここでは、2 つのOutlineCodeDefinition オブジェクトを定義し、プロジェクトのOutlineCodes コレクションに追加します。
## ステップ 3: アウトライン マスクを定義する
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
このステップでは、アウトライン コード定義のアウトラインマスクを設定します。
## ステップ 4: アウトライン値を作成する
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
このステップでは、2 つのOutlineValue オブジェクトを作成し、値、値 ID、タイプ、説明、折りたたみステータスなどのプロパティを設定します。

## 結論
Aspose.Tasks for .NET を使用した MS Project のアウトライン値の管理は、提供されている機能を利用して簡単に行うことができます。このチュートリアルで概説されている手順に従うことで、アウトライン コードと値を効率的に操作して、ニーズに応じてプロジェクト アウトラインをカスタマイズできます。
## よくある質問
### Q: Aspose.Tasks を他の .NET フレームワークで使用できますか?
A: はい、Aspose.Tasks はさまざまな .NET フレームワークと互換性があり、開発環境の柔軟性を確保します。
### Q: Aspose.Tasks の試用版はありますか?
 A: はい、Aspose.Tasks の無料試用版にアクセスできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks のサポートを受けるにはどうすればよいですか?
 A: サポートと支援が必要な場合は、Aspose.Tasks フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks の一時ライセンスを購入できますか?
A: はい、Aspose.Tasks の一時ライセンスを次のサイトから購入できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks の詳細なドキュメントはどこで見つけられますか?
 A: 入手可能な包括的なドキュメントを参照できます。[ここ](https://reference.aspose.com/tasks/net/).