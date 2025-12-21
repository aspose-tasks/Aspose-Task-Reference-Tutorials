---
date: 2025-12-21
description: JavaでMPPファイルからSVGを作成し、Aspose.Tasksライブラリを使用してプロジェクトをSVGとして保存する方法を学びます。コード例付きのステップバイステップガイド。
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して Java で MPP から SVG を作成する方法
url: /ja/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java で MPP から SVG を作成する方法

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用して **MPP ファイルから SVG を作成**する方法を学びます。Microsoft Project（MPP）ファイルをスケーラブルベクターグラフィックス（SVG）に変換すると、解像度に依存しない高品質な図を Web ページ、レポート、ダッシュボードに直接埋め込むことができます。必要なセットアップ手順を示し、正確なコード例を提示し、各ステップを解説するので、**プロジェクトを SVG として保存**する処理を自分のアプリケーションに自信を持って組み込めます。

## クイック回答
- **「MPP から SVG を作成する」とは何ですか？**  
  Microsoft Project ファイル（.mpp）を SVG 画像に変換し、ブラウザ上で品質を失うことなく表示できるようにします。  
- **変換を担当するライブラリはどれですか？**  
  Aspose.Tasks for Java が、1 行の `save` メソッドで変換を実行します。  
- **ライセンスは必要ですか？**  
  商用利用には一時ライセンスが必要です。無料トライアルも利用可能です。  
- **前提条件は何ですか？**  
  Java JDK 8 以上と Aspose.Tasks for Java の JAR が必要です。  
- **変換にかかる時間は？**  
  標準的なプロジェクトファイルであれば、通常 1 秒未満です。

## 「MPP から SVG を作成する」とは？
MPP ファイルから SVG を作成するとは、プロジェクトスケジュールの視覚的表現（タスク、タイムライン、リソースなど）を Scalable Vector Graphics 形式にエクスポートすることです。SVG は XML ベースで軽量、かつ高解像度ディスプレイでも完璧に拡大縮小できます。

## Aspose.Tasks を使ってプロジェクトを SVG として保存するメリット
- **Microsoft Project のインストール不要** – ライブラリ単体で動作します。  
- **完全な忠実度** – チャート、ガントバー、マイルストーンのスタイルがそのまま保持されます。  
- **クロスプラットフォーム** – Windows、Linux、macOS でコードを実行可能です。  
- **簡単統合** – 1 行の API 呼び出しで既存の Java パイプラインに自然に組み込めます。

## 前提条件
- **Java Development Kit (JDK)** – バージョン 8 以上。Oracle の公式サイトからダウンロードしてください。  
- **Aspose.Tasks for Java** – 公式ダウンロードページ **[here](https://releases.aspose.com/tasks/java/)** から取得してください。  

## パッケージのインポート
まず、必要なクラスをインポートします。インポートブロックは変更しません。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 手順 1: データディレクトリの定義
ソースの MPP ファイルがある場所と、SVG を出力する場所を指定します。

```java
String dataDir = "Your Data Directory";
```

> **プロのコツ:** `FileNotFoundException` を回避するため、絶対パスまたはプロジェクトのリソースフォルダーに対する相対パスを使用してください。

## 手順 2: MPP ファイルの読み込み
既存の Microsoft Project ファイルをロードして `Project` インスタンスを作成します。

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

この行は、先ほど定義したフォルダーから *HomeMovePlan.mpp* を読み込みます。

## 手順 3: プロジェクトを SVG として保存
次に、**プロジェクトを SVG として保存**するための 1 行コマンドを実行します。

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

このメソッドは `project5.svg` を同じディレクトリに書き出します。生成された SVG は最新のブラウザで開くことができ、HTML に直接埋め込むことも可能です。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| **ファイルが見つからない** | `dataDir` パスが誤っている | ディレクトリ文字列が区切り文字（`/` または `\\`）で終わっているか確認してください。 |
| **SVG が空白になる** | ビューがロードされていない | 保存前に MPP ファイルにガントチャートビューが含まれていることを確認してください。 |
| **ライセンス例外** | 有効なライセンスが適用されていない | `save` を呼び出す前に `License.setLicense("path/to/license.xml")` で一時ライセンスを設定してください。 |

## FAQ

**Q: Aspose.Tasks for Java はすべてのバージョンの Microsoft Project ファイルに対応していますか？**  
A: はい、MPP、MPT、XML 形式の古いバージョンから最新リリースまでサポートしています。

**Q: SVG 出力の外観をカスタマイズできますか？**  
A: もちろんです。`SvgOptions` を使用してフォント、色、レイアウトオプションを設定し、`save` 前に適用できます。

**Q: 商用利用にはライセンスが必要ですか？**  
A: はい、製品版での使用には有効なライセンスが必要です。**[here](https://purchase.aspose.com/temporary-license/)** から一時ライセンスを取得できます。

**Q: 購入前に Aspose.Tasks for Java を試すことはできますか？**  
A: はい、無料トライアルが **[here](https://purchase.aspose.com/buy)** で利用可能です。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
A: コミュニティフォーラム **[here](https://forum.aspose.com/c/tasks/15)** で質問やフィードバックを投稿できます。

## 結論
これで Java で **MPP ファイルから SVG を作成**し、Aspose.Tasks を使って **プロジェクトを SVG として保存**する方法が分かりました。この機能を活用すれば、Web ポータルやレポートダッシュボード、スケーラブルなグラフィックが必要なあらゆる場所にリッチなプロジェクトビジュアライゼーションを組み込めます。`SvgOptions` で出力を微調整し、開発ツールキットに強力な武器を加えてください。

---

**最終更新日:** 2025-12-21  
**テスト環境:** Aspose.Tasks for Java 24.10  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}