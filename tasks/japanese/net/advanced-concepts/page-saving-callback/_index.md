---
date: 2026-03-16
description: Aspose.Tasks for .NETでページ保存コールバックを実装する方法を学び、マルチページ文書の出力ストリームをカスタマイズして処理できるようにします。
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksでページ保存コールバックを実装する
url: /ja/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でページ保存コールバックを実装する

## はじめに

このチュートリアルでは、.NET 用 Aspose.Tasks で **ページ保存コールバックを実装する** 方法を学びます。この強力な機能を使用すると、マルチページ ドキュメントの各ページを任意のストリームに出力でき、出力の保存方法や後続処理を完全にコントロールできます。

## クイック回答
- **ページ保存コールバックは何をするものですか？** 各レンダリングされたページを個別のストリームにキャプチャし、個別に処理できるようにします。  
- **どの形式にエクスポートできますか？** `ImageSaveOptions` がサポートする任意の形式、例: PNG、JPEG、PDF。  
- **ライセンスは必要ですか？** 本番環境で使用する場合は有効な Aspose.Tasks ライセンスが必要です。  
- **.NET Core でも使用できますか？** はい、Aspose.Tasks は .NET Core および .NET 5/6+ をフルサポートしています。  
- **コールバックはスレッドセーフですか？** コールバックはレンダリングを実行するスレッド上で呼び出されるため、通常のスレッド安全性の規則が適用されます。

## **ページ保存コールバックを実装する** とは？
**ページ保存コールバック** パターンは、Aspose.Tasks の保存パイプラインにカスタムロジックを差し込む手段です。ファイルに直接書き込む代わりに、各ページごとに `Stream` オブジェクトが渡されるため、メモリ上に保持したり、クラウドストレージへアップロードしたり、追加処理を施したりできます。

## コールバックで PNG としてプロジェクトをエクスポートする理由
プロジェクトを PNG でエクスポートすると、各ガントチャートページのラスタ画像が得られ、レポートやメール、Web ページへの埋め込みに最適です。コールバックを使用すれば、ディスクに一時ファイルを作成せずに、各ページを個別の `MemoryStream` に保持できます。

## 前提条件

1. **C# の知識** – クラス、インターフェイス、ストリームの基本が分かっていること。  
2. **Aspose.Tasks for .NET** – [こちら](https://releases.aspose.com/tasks/net/) からダウンロードしてインストール。  
3. **IDE** – Visual Studio、Rider、または任意の .NET 対応エディタ。

## 名前空間のインポート

まず、必要な名前空間をインポートします:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## 手順 1: Project オブジェクトの作成

既存の MPP ファイルを `Project` インスタンスにロードします:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## 手順 2: Image Save Options の設定

PNG 出力用に `ImageSaveOptions` を設定し、カスタムコールバックを添付します:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **プロのコツ:** `RenderToSinglePage = false` を設定すると、各ガントチャートページが個別にレンダリングされ、コールバックが別々のストリームを受け取れるようになります。

## 手順 3: コールバック付きでプロジェクトを保存

実際のストリームはコールバックが提供するため、`Save` メソッドには `Stream.Null` を渡します:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## 手順 4: 保存されたページストリームの処理

保存処理が完了すると、コールバックは `MemoryStream` オブジェクトのコレクション（ページごとに 1 つ）を保持しています。これらを列挙して処理できます:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## 手順 5: カスタムページ保存コールバックの実装

`IPageSavingCallback` を実装した sealed クラスを作成します。このクラスは各ページのストリームを取得し、後で使用できるようにリストに格納します。

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## よくある落とし穴とトラブルシューティング

| 問題 | 原因 | 解決策 |
|------|------|--------|
| **ページが返ってこない** | `RenderToSinglePage` が `true` のまま | `RenderToSinglePage = false` に設定し、ページを個別に生成 |
| **ストリームが空** | `KeepStreamOpen` を `true` にしたまま後で破棄しない | デフォルトの `false` のままにし、コールバックにストリーム閉鎖を任せる |
| **メモリ不足エラー** | 非常に大きなプロジェクトで高解像度 PNG が多数生成される | ストリームを 1 つずつ処理するか、VM のメモリ上限を増やす |

## FAQ

**Q1: Aspose.Tasks のページ保存コールバックとは何ですか？**  
A: マルチページ ドキュメントの各ページ保存プロセスをインターセプトし、そのページ用のカスタム `Stream` を提供できる機能です。

**Q2: このコールバックで保存形式を変えることはできますか？**  
A: はい。`SaveFileFormat` を変更すれば、PNG、JPEG、PDF、SVG など任意の形式にエクスポートできます。

**Q3: Aspose.Tasks は .NET Core と互換性がありますか？**  
A: 完全に対応しています。.NET Core、.NET 5、.NET 6 をサポートしています。

**Q4: ページ保存中にエラーが発生した場合はどう対処すべきですか？**  
A: コールバック内部を try/catch で囲み、例外をログに記録します。`OnFinish` メソッドは最終的なクリーンアップに適しています。

**Q5: Aspose.Tasks の追加リソースやサポートはどこで得られますか？**  
A: [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) で質問でき、[こちら](https://reference.aspose.com/tasks/net/) のドキュメントや、[Aspose.Tasks 公式サイト](https://purchase.aspose.com/buy) で機能やライセンス情報を確認できます。

---

**最終更新日:** 2026-03-16  
**テスト環境:** Aspose.Tasks 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}