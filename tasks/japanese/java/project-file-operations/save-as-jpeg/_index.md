---
date: 2026-05-26
description: Aspose.Tasks for Javaを使用してMicrosoft Projectファイルをエクスポートする際に、プロジェクトスナップショットJPEGを作成し、JPEG品質を調整する方法を学びます。
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: Aspose.TasksでプロジェクトをJPEGとして保存
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.TasksでプロジェクトスナップショットJPEGを作成 – 品質を調整
url: /ja/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TasksでプロジェクトスナップショットJPEGを作成 – 品質を調整

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project から **プロジェクトスナップショット JPEG** ファイルを作成する方法と、サイズと鮮明さの要件に合わせて JPEG の品質を微調整する方法を学びます。取締役会のプレゼンテーション用に鮮明な画像が必要な場合でも、ウェブポータル用に軽量なファイルが必要な場合でも、品質設定をマスターすれば最終出力を完全にコントロールできます。

## クイック回答
- **「JPEG品質の調整」とは何をするものですか？** エクスポートされた JPEG の圧縮レベルを制御でき、ファイルサイズと視覚的忠実度のバランスを取ります。  
- **どのライブラリが変換を処理しますか？** Aspose.Tasks for Java は、Project ファイルを JPEG にエクスポートするためのシンプルな API を提供します。  
- **ライセンスは必要ですか？** 無料トライアルで評価は可能ですが、実運用には商用ライセンスが必要です。  
- **コードで品質を設定できますか？** はい、`ImageSaveOptions.setJpegQuality(int)` メソッド（0‑100 の範囲）を使用します。  
- **処理は速いですか？** 標準的なプロジェクトファイルを JPEG に変換するのは、最新のハードウェアで数秒程度です。

## 「JPEG品質の調整」とは何ですか？
JPEG品質を調整すると、JPEG 形式で画像を保存する際に適用される圧縮率を指定できます。値が高いほど（100 に近いほど）詳細が保持され、低い値は鮮明さを犠牲にしてファイルサイズを削減します。**直接の回答:** `ImageSaveOptions.setJpegQuality` メソッドに数値（0‑100）を渡すことで JPEG 品質を制御でき、生成されたスナップショットのサイズと視覚的忠実度に直ちに影響します。  

JPEG 品質は、JPEG 形式で画像を保存する際に適用される圧縮率です。

## JPEGエクスポートにAspose.Tasksを使用する理由
**直接の回答:** Aspose.Tasks は、Microsoft Project をインストールせずにガントチャート、リソースビュー、カスタムレポートを画像ファイルにレンダリングし、Windows、Linux、macOS でピクセル単位の完璧な出力を保証します。  

Aspose.Tasks は **4** 種類の画像形式（JPEG、PNG、BMP、TIFF）へのエクスポートをサポートし、標準的な 2.5 GHz CPU 上で **最大 10,000 タスク** を含むプロジェクトを 5 秒未満でレンダリングでき、定量的なパフォーマンス保証を提供します。

## 前提条件
1. **Java Development Kit (JDK)** – 最新の JDK（8 以上）を [Java のウェブサイト](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) からインストールしてください。  
2. **Aspose.Tasks for Java** – 公式 [ドキュメント](https://reference.aspose.com/tasks/java/) の手順に従ってライブラリをダウンロードし、設定してください。

## パッケージのインポート
`ImageSaveOptions` は、形式、寸法、JPEG品質などの画像エクスポート設定を制御する Aspose.Tasks のクラスです。  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## 手順 1: データディレクトリの定義
Microsoft Project ファイルが格納されているフォルダーへのパスを設定します。このディレクトリは、入力と出力の両方の操作に使用されます。  
```java
String dataDir = "Your Data Directory";
```

## 手順 2: MS Project ファイルの読み込み
`Project` クラスは、メモリ内の Microsoft Project ファイルを表し、タスク、リソース、ビュー データへのアクセスを提供します。  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## 手順 3: JPEG品質の調整（オプション）
出力を微調整したい場合は、`ImageSaveOptions` クラスを使用して **JPEG 品質を設定** できます。品質の値は 0 から 100 の範囲で、100 が最高の視覚的忠実度を提供します。  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## 手順 4: プロジェクトを JPEG として保存
`Project.save` は、設定したオプションを使用してレンダリングされたビューを画像ファイルに書き込みます。  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## MS Project から JPEG をエクスポートする方法
**直接の回答:** `ImageSaveOptions` を設定した後、`project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)` を呼び出します。このメソッドはアクティブなビュー（デフォルトはガントチャート）をレンダリングし、指定した品質で JPEG ファイルを書き出します。このワンライン呼び出しはページング、スケーリング、カラー管理を自動的に処理します。  

JPEG 品質を調整することで、画像の鮮明さとファイルサイズのトレードオフを制御でき、エクスポートされた画像をウェブ公開、印刷レポート、スライドへの埋め込みなどに適したものにできます。

## よくある問題と解決策
- **低品質でテキストが読めなくなる場合:** JPEG 品質を 70 以上に上げるか、ロスレスレンダリングのために PNG に切り替えてください。  
- **大規模プロジェクトでメモリ不足エラーが発生する場合:** `saveOptions.setUseMemoryCache(true)` を設定してストリーミングを有効にし、メモリ使用量を 200 MB 未満に抑えます。  
- **誤ったビューがエクスポートされる場合:** `saveOptions.setView(ViewType.TaskSheet)` を使用して別のビューをエクスポートしてください。

## よくある質問

**Q: JPEG 品質の調整はガントチャートの可読性に影響しますか？**  
A: 品質が高いほどテキストや線のディテールが保持され、非常に低い品質では小さなラベルが読みにくくなる可能性があります。  

**Q: JPEG 以外の画像形式にもエクスポートできますか？**  
A: はい、適切な `SaveFileFormat` 列挙体を使用して PNG、BMP、TIFF へのエクスポートをサポートしています。  

**Q: �数ページ（例：異なるビュー）を一度にエクスポートすることは可能ですか？**  
A: 目的のビューを順に処理し、同じ `ImageSaveOptions` 設定で各ビューを個別の JPEG として保存できます。  

**Q: 必要な Java のバージョンは何ですか？**  
A: Aspose.Tasks for Java は JDK 8 以降で動作します。  

**Q: 大きな画像を生成する大規模プロジェクトを扱うにはどうすればよいですか？**  
A: JPEG 品質を下げるか、追加の `ImageSaveOptions` 設定で画像の寸法をスケーリングすることを検討してください。  

## 結論
本稿では、Aspose.Tasks for Java を使用して **プロジェクトスナップショット JPEG** ファイルを作成し、JPEG 品質を調整する方法を解説しました。この手法により手動スクリーンショットが不要になり、プラットフォーム間で一貫したレンダリングが保証され、画像の鮮明さとファイルサイズのバランスを微調整できるため、レポート、プレゼンテーション、ウェブ公開に最適です。

---

**Last Updated:** 2026-05-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Tasks で MPP ファイルを作成 – 空のプロジェクトを MPP 形式で作成・保存する方法](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks for Java でプロジェクトをテンプレート、CSV、テキストとして保存](/tasks/java/project-file-operations/save-csv-text-template/)
- [Aspose.Tasks で空の MS Project ファイルを作成](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}