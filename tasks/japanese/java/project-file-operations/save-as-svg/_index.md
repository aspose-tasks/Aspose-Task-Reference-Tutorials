---
date: 2026-03-27
description: Aspose.Tasks を使用して Java で MPP を SVG にエクスポートする方法を学びましょう。ステップバイステップのガイド、コード例、そしてプロジェクトをすばやく
  SVG として保存するためのヒントをご紹介します。
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して Java で MPP を SVG にエクスポートする方法
url: /ja/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでMPPをSVGにエクスポートする方法

## Export MPP to SVG – はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用して **export MPP to SVG** ファイルの作成方法を学びます。Microsoft Project (MPP) ファイルを Scalable Vector Graphics (SVG) 画像に変換すると、高品質で解像度に依存しない図をウェブページ、レポート、ダッシュボードに直接埋め込むことができます。必要なセットアップを順に説明し、必要なコードを正確に示し、各ステップを解説するので、独自のアプリケーションで自信を持って **save project as SVG** ができるようになります。

## クイック回答
- **“export MPP to SVG” とは何ですか？**  
  Microsoft Project ファイル (.mpp) を SVG 画像に変換し、品質の低下なしに任意のブラウザで表示できるようにします。  
- **どのライブラリが変換を処理しますか？**  
  Aspose.Tasks for Java は、変換を実行する単一行の `save` メソッドを提供します。  
- **ライセンスは必要ですか？**  
  商用利用には一時ライセンスが必要です。無料トライアルも利用可能です。  
- **前提条件は何ですか？**  
  Java JDK 8 以上と Aspose.Tasks for Java の JAR。  
- **変換にかかる時間はどれくらいですか？**  
  標準的なプロジェクトファイルでは、通常 1 秒未満です。

## “export MPP to SVG” とは何か
MPP を SVG にエクスポートするとは、プロジェクトスケジュールの視覚的表現（タスク、タイムライン、リソース）を取得し、SVG ファイルとして書き出すことを意味します。SVG は XML ベースで軽量、かつ高解像度ディスプレイでも完璧にスケーリングします。

## Aspose.Tasks で MPP を SVG にエクスポートする理由
- **Microsoft Project のインストールは不要** – ライブラリは単独で動作します。  
- **フルフィデリティ** – チャート、ガントバー、マイルストーンのスタイルがそのまま保持されます。  
- **クロスプラットフォーム** – Windows、Linux、macOS でコードを実行できます。  
- **ワンライン API** – 1 回の呼び出しでプロジェクトを SVG として保存でき、既存の Java パイプラインに自然に組み込めます。

## 前提条件
- **Java Development Kit (JDK)** – バージョン 8 以上。Oracle のウェブサイトからダウンロードしてください。  
- **Aspose.Tasks for Java** – 公式ダウンロードページ **[here](https://releases.aspose.com/tasks/java/)** からライブラリを取得してください。  

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
ソース MPP ファイルの場所と SVG が書き込まれる場所を指定します。

```java
String dataDir = "Your Data Directory";
```

> **プロのコツ:** `FileNotFoundException` を回避するために、絶対パスまたはプロジェクトの resources フォルダーに対する相対パスを使用してください。

## 手順 2: MPP ファイルのロード
`Project` インスタンスを作成し、既存の Microsoft Project ファイルをロードします。

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

この行は、先ほど定義したフォルダーから *HomeMovePlan.mpp* を読み取ります。

## 手順 3: プロジェクトを SVG として保存
これで、単一のコマンドで **export MPP to SVG** が可能です。

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

このメソッドは `project5.svg` を同じディレクトリに書き込みます。生成された SVG は、最新のブラウザーで開くことも、HTML に直接埋め込むこともできます。

## 一般的な使用例
- **Project dashboards** – クライアントに Microsoft Project のインストールを要求せず、ウェブポータルにライブのガントチャートを埋め込めます。  
- **Automated reporting** – PDF や HTML レポート用に SVG 画像をリアルタイムで生成します。  
- **Cross‑team collaboration** – ブラウザーだけで閲覧できるステークホルダーと視覚的スケジュールを共有します。  

## 一般的な問題と解決策
| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** | `dataDir` パスが正しくありません | ディレクトリ文字列が区切り文字（`/` または `\\`）で終わっているか確認してください。 |
| **Blank SVG output** | ビューなしでプロジェクトがロードされた | 保存前に MPP ファイルにガントチャートビューが含まれていることを確認してください。 |
| **License exception** | 有効なライセンスが適用されていません | `save` を呼び出す前に `License.setLicense("path/to/license.xml")` を使用して一時ライセンスを適用してください。 |

## よくある質問

**Q: Aspose.Tasks for Java はすべてのバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: はい、古いバージョンから最新の Project リリースまで、MPP、MPT、XML 形式をサポートしています。

**Q: SVG 出力の外観をカスタマイズできますか？**  
A: もちろんです。`save` を呼び出す前に `SvgOptions` を使用してフォント、色、レイアウトオプションを設定できます。

**Q: Aspose.Tasks for Java は商用利用にライセンスが必要ですか？**  
A: はい、製品環境では有効なライセンスが必要です。**[here](https://purchase.aspose.com/temporary-license/)** から一時ライセンスを取得できます。

**Q: 購入前に Aspose.Tasks for Java を試すことはできますか？**  
A: はい、無料トライアルが **[here](https://purchase.aspose.com/buy)** で利用可能です。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
A: コミュニティフォーラム **[here](https://forum.aspose.com/c/tasks/15)** を訪れて質問やフィードバックを共有してください。

## 結論
これで、Java で **export MPP to SVG** を行い、Aspose.Tasks を使用して効率的に **save project as SVG** できるようになりました。この機能により、豊富なプロジェクト可視化をウェブポータル、レポートダッシュボード、またはスケーラブルなグラフィックが必要なあらゆる場所に統合できます。`SvgOptions` を試して出力を微調整すれば、開発ツールキットに強力なツールが加わります。

---

**最終更新日:** 2026-03-27  
**テスト環境:** Aspose.Tasks for Java 24.10  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}