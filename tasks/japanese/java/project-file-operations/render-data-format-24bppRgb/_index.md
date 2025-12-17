---
date: 2025-12-17
description: Aspose.Tasks for Java を使用して、プロジェクトを画像として保存し、画像の解像度を変更する方法を学びましょう。このステップバイステップガイドでは、24bppRgb
  フォーマットで MS Project データをレンダリングする方法を示します。
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用した 24bppRgb 形式でプロジェクトを画像として保存
url: /ja/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクトを画像として保存 – 24bppRgb 形式（Aspose.Tasks 使用）

## Introduction
このチュートリアルでは、Aspose.Tasks for Java を使用して **save project as image** を 24bppRgb ピクセル形式で保存する方法を学びます。MS Project のデータを画像にレンダリングすることは、スケジュールのビジュアルスナップショットを共有したり、レポートにタイムラインを埋め込んだり、プロジェクトポータル用のサムネイルを生成したりする際に便利です。また、品質要件に合わせて **change image resolution java** を行う方法も紹介します。

## Quick Answers
- **プロジェクトを画像としてレンダリングできますか？** はい、Aspose.Tasks を使用すると、プロジェクトを TIFF、PNG、JPEG などの形式で保存できます。  
- **どのピクセル形式が最も高い色深度を提供しますか？** `Format24bppRgb` は真のカラー（24 ビット）画像を提供します。  
- **画像の解像度はどう調整しますか？** `ImageSaveOptions` の `setHorizontalResolution` と `setVerticalResolution` を使用します。  
- **本番環境でライセンスが必要ですか？** 評価版以外で使用する場合は商用ライセンスが必要です。  
- **すべての Java バージョンと互換性がありますか？** Java 8 以降で動作します。

## What is “save project as image”?
プロジェクトを画像として保存すると、Microsoft Project ファイル（`.mpp`）のビジュアル表現がラスタ形式（例：TIFF）に変換されます。生成されたファイルはブラウザで表示したり、ドキュメントに挿入したり、元の Project アプリケーションがなくても印刷したりできます。

## Why use the 24bppRgb format?
24bppRgb ピクセル形式は、各ピクセルを赤・緑・青それぞれ 8 ビットで保存し、アルファチャンネルなしで真のカラー品質を提供します。色忠実度が重要な高解像度レポートに最適で、32 ビット形式に比べてファイルサイズも適度に抑えられます。

## Prerequisites
開始する前に、以下を用意してください。

1. **Java Development Kit (JDK)** – JDK 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java** – [here](https://releases.aspose.com/tasks/java/) からダウンロードしてインストール。  
3. **Basic Java knowledge** – Java の構文やプロジェクト設定に慣れていると、コードスニペットの理解がスムーズです。

## Import Packages
まず、必要な Aspose.Tasks クラスを Java プロジェクトにインポートします。

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` を、`.mpp` ファイルが存在する絶対パスに置き換えてください。

### Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
この行は Microsoft Project ファイル（`project.mpp`）を読み取り、Aspose.Tasks が操作できる `Project` オブジェクトを作成します。

### Step 3: Configure Image Save Options
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
ここでは出力形式を TIFF に設定し、**72 dpi** の解像度を指定します（必要に応じて値を変更できます – ここが **change image resolution java** の箇所です）。さらに、真のカラー出力のために 24bppRgb ピクセル形式を選択しています。

### Step 4: Save Project Data as Image
```java
project.save(dataDir + "resFile.tif", options);
```
`save` メソッドは、上記で定義したオプションを使用してレンダリングされた画像を `resFile.tif` に書き込みます。

## Common Issues and Solutions
| 問題 | 原因 | 対策 |
|------|------|------|
| **Blank image output** | プロジェクトビューが空の場合があります。 | 保存前に `project.setDefaultView(ViewType.Gantt);` を呼び出してください。 |
| **Low‑quality image** | 解像度が低すぎます。 | `setHorizontalResolution` と `setVerticalResolution` を増やします（例：150 dpi）。 |
| **Unsupported pixel format** | 古い Aspose.Tasks バージョンを使用しています。 | 最新の Aspose.Tasks for Java リリースにアップグレードしてください。 |

## Conclusion
これで、Aspose.Tasks for Java を使用して 24bppRgb 形式で **save project as image** し、解像度を調整する方法が分かりました。この手法により、プロジェクトスケジュールの鮮明で色忠実度の高いビジュアル表現を、共有、レポート作成、アーカイブなどさまざまな用途で生成できます。

## FAQ's
### Q: 他の画像形式でもプロジェクトデータをレンダリングできますか？
A: はい、Aspose.Tasks は PNG、JPEG、BMP などのさまざまな画像形式へのレンダリングをサポートしています。  
### Q: Aspose.Tasks は異なるバージョンの MS Project と互換性がありますか？
A: はい、Aspose.Tasks は 2003、2007、2010、2013、2016 など複数の MS Project バージョンをサポートしています。  
### Q: レンダリング画像の解像度やピクセル形式をカスタマイズできますか？
A: はい、Aspose.Tasks を使用して要件に合わせて解像度やピクセル形式をカスタマイズできます。  
### Q: 商用利用には Aspose.Tasks のライセンスが必要ですか？
A: はい、商用利用にはライセンスの購入が必要です。テスト目的の一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。  
### Q: Aspose.Tasks のサポートはどこで受けられますか？
A: Aspose.Tasks のサポートは [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) で受けられます。

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}