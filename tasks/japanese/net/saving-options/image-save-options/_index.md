---
title: Aspose.Tasks の画像保存 MS プロジェクト オプション
linktitle: Aspose.Tasks の画像保存オプション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project のオプションを画像として保存する方法を学びます。シームレスな統合については、ステップバイステップのガイドに従ってください。
weight: 11
url: /ja/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks の画像保存 MS プロジェクト オプション


## 導入
ソフトウェア開発の世界では、プロジェクト タスクを効率的に処理することが、プロジェクト管理を成功させるために非常に重要です。 Aspose.Tasks for .NET は、Microsoft Project ファイルを扱う開発者に強力なソリューションを提供し、.NET アプリケーション内でプロジェクト タスクをシームレスに操作、変換、管理できるようにします。
## 前提条件
Aspose.Tasks for .NET を使用して MS Project オプションをイメージとして保存する前に、次の前提条件が満たされていることを確認してください。
### 1. Aspose.Tasks for .NET をインストールする
まず、Aspose.Tasks for .NET を開発環境にインストールする必要があります。ライブラリはからダウンロードできます。[Webサイト](https://releases.aspose.com/tasks/net/)提供されるインストール手順に従ってください。
### 2. ライセンスの取得 (オプション)
 Aspose.Tasks for .NET は評価モードではライセンスなしで使用できますが、すべての機能を使用し、評価の制限を解除するにはライセンスを取得することをお勧めします。からライセンスを取得できます。[購入ページ](https://purchase.aspose.com/buy)または、[仮免許](https://purchase.aspose.com/temporary-license/)テスト目的のため。
### 3. C# および .NET 開発の基礎知識
例に従って、Aspose.Tasks の機能をアプリケーションに効果的に統合するには、C# プログラミング言語と .NET Framework の基本を理解する必要があります。
## 名前空間のインポート
Aspose.Tasks for .NET を使用して MS Project オプションを画像として保存する前に、必要な名前空間を C# プロジェクトにインポートしていることを確認してください。
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## ステップ 1: ドキュメント ディレクトリ パスを設定する
ドキュメント用に指定されたディレクトリがあることを確認し、それに応じてパスを設定します。
```csharp
String DataDir = "Your Document Directory";
```
## ステップ 2: MS プロジェクト ファイルをロードする
新しいものを初期化する`Project` MS Project ファイルをロードしてオブジェクトを作成します。
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## ステップ 3: 画像保存オプションを定義する
のインスタンスを作成します`ImageSaveOptions`必要な設定を指定します。
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## ステップ 4: 保存するページを指定する
必要に応じて、保存するページを指定します。この例では、ページ 2 を追加します。
```csharp
options.Pages.Add(2);
```
## ステップ 5: 画像を保存する
最後に、指定したオプションを使用して、選択したページを画像として保存します。
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## 結論
Aspose.Tasks for .NET は、MS Project ファイルを操作するプロセスを簡素化し、開発者がプロジェクト タスクを簡単に操作できるようにします。このチュートリアルで概説されている手順に従うことで、MS Project のオプションを .NET アプリケーション内に画像として効率的に保存できます。
## よくある質問
### Q1: ライセンスなしで Aspose.Tasks for .NET を使用できますか?
A: はい、評価モードではライセンスなしで Aspose.Tasks for .NET を使用できます。ただし、全機能のライセンスを取得し、評価制限を解除することをお勧めします。
### Q2: テスト用の一時ライセンスを取得するにはどうすればよいですか?
 A: テスト目的の一時ライセンスは、[一時ライセンスのページ](https://purchase.aspose.com/temporary-license/).
### Q3: Aspose.Tasks for .NET は他の .NET フレームワークと互換性がありますか?
A: はい、Aspose.Tasks for .NET は、.NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。
### Q4: 画像保存オプションをさらにカスタマイズできますか?
A: はい、ページ サイズ、解像度、出力形式の調整など、特定の要件に応じて画像保存オプションをカスタマイズできます。
### Q5: Aspose.Tasks for .NET のサポートはどこで見つけられますか?
 A: Aspose.Tasks for .NET のサポートと支援については、[フォーラム](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
