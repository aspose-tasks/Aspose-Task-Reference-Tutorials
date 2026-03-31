---
date: 2026-03-21
description: Aspose.Tasks for .NETでプロジェクトを画像として保存する際の画像エクスポート方法と、BitmapInvalidSizeExceptionの対処方法を学びます。プロジェクトを画像として保存する手順と、PNG形式でエクスポートする手順が含まれています。
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 画像のエクスポート方法と無効サイズ例外の処理
url: /ja/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 画像のエクスポート方法 – Aspose.Tasks における Bitmap の無効サイズ例外の処理

このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project ファイルから **画像をエクスポートする方法** を学び、さらにプロセス中に発生する可能性のある `BitmapInvalidSizeException` の捕捉方法について解説します。プロジェクトを画像としてエクスポートすることは、レポート ダッシュボード、ドキュメント、またはスケジュールのビジュアル スナップショットを共有する際に一般的な要件です。このガイドの最後までに、**プロジェクトを画像として保存** できるようになり、**PNG 形式でプロジェクトをエクスポート** する際の予期せぬクラッシュを防げます。

## Quick Answers
- **画像をエクスポートするときに発生し得る例外は何ですか？** `BitmapInvalidSizeException`  
- **サンプルで使用されている形式はどれですか？** PNG (`SaveFileFormat.Png`)  
- **特別なライセンスは必要ですか？** 本番環境で使用するには有効な Aspose.Tasks ライセンスが必要です。  
- **タイムスケールを変更できますか？** はい – タイムスケール単位（分、時間、日など）を設定できます。  
- **コードは .NET Core と互換性がありますか？** 完全に対応しています – 同じ API が .NET Framework と .NET Core の両方で動作します。

## What is the BitmapInvalidSizeException?
`BitmapInvalidSizeException` は、画像用に計算されたビットマップの寸法がサポート範囲外（例: 幅または高さが 0、または内部制限を超える）である場合にスローされます。これは通常、タイムスケールやビュー設定により画像が大きすぎる、または小さすぎる場合に発生します。

## Why export a project as an image?
- **ビジュアル レポーティング** – Gantt チャートを PDF、Word 文書、Web ページに埋め込めます。  
- **クロスプラットフォーム共有** – PNG ファイルは Microsoft Project がなくても任意のデバイスで閲覧可能です。  
- **パフォーマンス** – 画像はフルプロジェクト ファイルに比べて軽量で、プレビューが高速です。

## Prerequisites
1. C# と .NET 開発の基本知識。  
2. Aspose.Tasks for .NET がインストール済み（NuGet パッケージ `Aspose.Tasks`）。  
3. サンプルの Microsoft Project ファイル（例: `Blank2010.mpp`）。  

## Import Namespaces
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Step‑by‑Step Guide

### Step 1: Initialize the Project and Choose a View
まず、`Project` インスタンスを作成し、レンダリングしたいビューを選択します（ここでは最初の Gantt チャート ビューを使用します）。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Step 2: Configure Image Save Options (Export Project to PNG)
目的の画像形式を設定し、ビューで定義されたタイムスケールを Aspose.Tasks に使用させます。

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Step 3: Adjust the Timescale Unit (Control Image Size)
タイムスケールを変更するとビットマップの寸法が変わります。この例では **minutes** を使用して画像サイズを抑えています。

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Step 4: Attempt to Save the Project as an Image
この行が実際の **save project as image** 操作を実行します。

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Step 5: Catch and Handle the BitmapInvalidSizeException
`try / catch` ブロックで保存呼び出しをラップし、ビットマップ サイズが無効な場合にアプリケーションが適切に対処できるようにします。

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Common Issues and Solutions
| Issue | Cause | Solution |
|-------|-------|----------|
| タイムスケール調整後も例外がスローされる | タイムスケールが依然としてビットマップを大きくしすぎている | `view.MiddleTimescaleTier.Count` を減らすか、より粗い `TimescaleUnit`（例: Hours）に切り替える |
| 出力ファイルが空になる | ファイル パスが正しくない、または書き込み権限がない | `DataDir` が書き込み可能なフォルダーを指しているか確認し、形式を変更した場合は拡張子が `.png` であることを確認 |
| 画像品質が低い | デフォルト DPI が低い可能性がある | `options.DpiX` と `options.DpiY` を高い値（例: 300）に設定 |

## Frequently Asked Questions

**Q: What causes the BitmapInvalidSizeException in Aspose.Tasks?**  
A: 計算されたビットマップ寸法が無効になると発生します。主にタイムスケールが画像を大きすぎる、または幅/高さが 0 になる場合です。

**Q: Can I customize the timescale when exporting an image?**  
A: はい。チュートリアルに示したように、`view.MiddleTimescaleTier.Unit` と `Count` を変更して調整できます。

**Q: Does Aspose.Tasks support other image formats besides PNG?**  
A: もちろんです。`SaveFileFormat` には JPEG、BMP、GIF、TIFF も含まれます。`ImageSaveOptions` の列挙値を変更するだけです。

**Q: Is a license required for exporting images in a production environment?**  
A: 必要です。評価モードでも動作しますが、商用ライセンスを取得すれば評価制限が解除され、フルサポートが受けられます。

**Q: How can I improve the quality of the exported PNG?**  
A: DPI 設定（`options.DpiX` と `options.DpiY`）を上げるか、ビューのタイムスケールを調整してビットマップを大きくすると品質が向上します。

## Conclusion
上記の手順に従うことで、**画像をエクスポートする方法** と **プロジェクトを画像として保存** する方法、そして `BitmapInvalidSizeException` を優雅に処理する方法が習得できました。これらのテクニックにより、レポート パイプラインがより堅牢になり、さまざまなプロジェクト サイズやタイムスケールに対してビジュアル エクスポートが確実に機能します。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose