---
date: 2026-03-24
description: .NETでAspose.Tasks Layout Builderを使用したメモリ不足時の処理とプロジェクト画像の保存方法を学びます。コード例付きのステップバイステップガイド。
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks Layout Builder（C#）でのメモリ不足時の対処
url: /ja/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Layout Builder を使用したメモリ不足の処理

## はじめに

メモリ不足の処理は、大規模なプロジェクト ファイルを扱う信頼性の高い .NET アプリケーションを構築する上で重要な要素です。Aspose.Tasks Layout Builder で可視化を生成すると、特に複雑なガント チャートでメモリ関連の例外がすぐに発生することがあります。本チュートリアルでは、**メモリ例外の処理**、**ガント ビューのカスタマイズ**、そして **プロジェクト画像の安全な保存** の方法を順を追って解説し、巨大なスケジュールでもアプリケーションが応答し続けるようにします。

## クイック回答
- **メモリ不足の処理とは？** 大量データを処理する際にメモリ使用量を管理し、`OutOfMemoryException` 系のエラーを捕捉すること。
- **どの API が役立つか？** .NET 用 Aspose.Tasks Layout Builder。
- **典型的なシナリオは？** 高解像度のガント チャートを PNG にレンダリングすること。
- **必要な前提条件は？** Aspose.Tasks がインストールされた .NET (Framework 4.5+ または .NET 6)。
- **エラーはどう捕捉するか？** `ApsLayoutBuilderOutOfMemoryException` および関連例外用に `try…catch` ブロックを使用します。

## 前提条件

コードに入る前に、以下を確認してください。

1. **C# の基礎** – 標準的な C# 構文に慣れていること。
2. **Aspose.Tasks for .NET** がインストール済み。まだ追加していない場合は、[here](https://releases.aspose.com/tasks/net/) からダウンロードしてください。
3. **IDE** – Visual Studio（または C# 拡張機能付き VS Code）でサンプルをコンパイル・実行できる環境。

## 名前空間のインポート

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## ステップバイステップ ガイド

### ステップ 1: プロジェクトのロード

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

この行は **Blank2010.mpp** を `Project` インスタンスに読み込み、可視化の準備を行います。

### ステップ 2: ガントチャートビューのカスタマイズ

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

ここでは中間および下部のタイムスケール層を調整して **ガント ビューをカスタマイズ** します。これらの層を変更すると、一度にレンダリングされるデータ量が減少し、メモリ圧迫の緩和に役立ちます。

### ステップ 3: 画像保存オプションの構成

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` は Aspose.Tasks にチャートの描画方法を指示します。出力形式は PNG を選択し、先ほどカスタマイズしたタイムスケールをビューにバインドします。

### ステップ 4: プロジェクトを画像として保存

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

`Save` 呼び出しは、上記で定義したオプションを使用して **プロジェクト画像を保存** します。プロジェクトが非常に大きい場合、ここがメモリ不足が顕在化しやすいポイントです。

### ステップ 5: 例外の処理

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

`ApsLayoutBuilderOutOfMemoryException` を捕捉することで、**メモリ例外を優雅に処理** し、アプリケーションがクラッシュする代わりに明確なメッセージを提供できます。2 番目の catch は、巨大チャートのレンダリング時に発生し得るビットマップサイズの問題に対処します。

## 一般的な問題と解決策

| 問題 | 発生原因 | 対策 |
|------|----------|------|
| **OutOfMemoryException** | 非常に高解像度の画像をレンダリングすると、プロセスが割り当て可能な RAM を超えてしまう。 | 画像サイズを縮小する、タイムスケール層を簡素化する、またはチャートを複数の画像に分割する。 |
| **BitmapInvalidSizeException** | 要求されたビットマップサイズがプラットフォームの最大値を超えている。 | `ImageSaveOptions` で幅・高さを制限するか、セグメント単位でレンダリングする。 |
| **Slow performance** | 大規模プロジェクト ファイルの処理に多くの時間がかかる。 | レンダリング前に `project.Set(Prj.SaveToCache, true)` を有効化するか、バックグラウンド スレッドで実行する。 |

## FAQ

### Q1: Aspose.Tasks for .NET とは何ですか？

A1: Aspose.Tasks for .NET は、.NET アプリケーションからプログラム的に Microsoft Project ファイルを操作できる強力な API です。

### Q2: Aspose.Tasks の一時ライセンスはどこで取得できますか？

A2: [このリンク](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

### Q3: Aspose.Tasks は大規模プロジェクト ファイルの処理に適していますか？

A3: はい、Aspose.Tasks は大規模プロジェクト ファイルを効率的に扱う機能と最適化を提供しますが、開発者は依然としてメモリ管理戦略を検討する必要があります。

### Q4: Aspose.Tasks でガントチャートの外観をカスタマイズできますか？

A4: もちろんです！Aspose.Tasks は、要件に合わせてガントチャートの外観やレイアウトを細かくカスタマイズする豊富な機能を提供します。

### Q5: Aspose.Tasks のサポートやヘルプはどこで得られますか？

A5: [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) でヘルプやサポートを受けられ、コミュニティとも交流できます。

## よくある質問

**Q: プロジェクト画像を保存する際のメモリ使用量を減らすには？**  
A: 画像解像度を下げる、タイムスケールの範囲を制限する、またはチャートを複数の小さなセグメントに分割して保存します。

**Q: 画像を直接 Web 応答にストリーム送信できますか？**  
A: はい、`project.Save(stream, options)` を使用してストリームを書き込み、HTTP 応答に送信できます。

**Q: Aspose.Tasks は .NET Core および .NET 5/6 をサポートしていますか？**  
A: ライブラリは .NET Core、.NET 5、.NET 6 と完全に互換性があります。

**Q: 最適化後もメモリ不足エラーが発生した場合はどうすべきですか？**  
A: より多くの RAM を搭載したマシンで処理するか、レンダリングをバックグラウンド サービスにオフロードすることを検討してください。

**Q: ガントチャートを PNG 以外の形式でエクスポートできますか？**  
A: はい、`ImageSaveOptions` は JPEG、BMP、TIFF もサポートしています。

---

**最終更新日:** 2026-03-24  
**テスト環境:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}