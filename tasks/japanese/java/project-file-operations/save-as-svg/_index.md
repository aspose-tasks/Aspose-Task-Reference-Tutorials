---
title: JavaでMSプロジェクトをSVGに変換する
linktitle: Aspose.Tasks に SVG として保存
second_title: Aspose.Tasks Java API
description: Aspose.Tasks ライブラリを使用して、Microsoft Project ファイルを Java の SVG として保存する方法を学びます。コード例を含むステップバイステップのガイド。
weight: 18
url: /ja/java/project-file-operations/save-as-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでMSプロジェクトをSVGに変換する

## 導入
Aspose.Tasks for Java は、プロジェクト管理ファイルを操作するための強力なライブラリであり、開発者がプロジェクト データを操作し、さまざまな操作を実行し、レポートを効率的に生成できるようにします。このチュートリアルでは、Aspose.Tasks for Java を使用してプロジェクトを SVG として保存する方法を説明します。 SVG (Scalable Vector Graphics) は、Web 上でベクター グラフィックを表示するために広く使用されている形式で、スケーラビリティと高品質のレンダリングを提供します。
## 前提条件
始める前に、以下のものがあることを確認してください。
### Java開発環境
システムに Java Development Kit (JDK) がインストールされていることを確認してください。 JDK は Oracle Web サイトからダウンロードしてインストールできます。
### Java ライブラリの Aspose.Tasks
 Web サイトから Aspose.Tasks for Java ライブラリをダウンロードしてインストールします。ダウンロードリンクは提供されているドキュメントにあります。[ここ](https://releases.aspose.com/tasks/java/).

## パッケージのインポート
まず、Aspose.Tasks 機能を使用するために必要なパッケージを Java プログラムにインポートする必要があります。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

ここで、提供された例を複数のステップに分解してみましょう。
## ステップ 2: データ ディレクトリを定義する
```java
String dataDir = "Your Data Directory";
```
交換する`"Your Data Directory"`プロジェクト ファイルが配置されているディレクトリへのパスを置き換えます。
## ステップ 3: プロジェクト ファイルをロードする
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
このステップでは、指定されたデータ ディレクトリから「HomeMovePlan.mpp」という名前のプロジェクト ファイルを読み込みます。
## ステップ 4: SVG として保存する
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
この手順では、読み込んだプロジェクトを「project5.svg」という名前で SVG 形式で指定したデータ ディレクトリに保存します。

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用してプロジェクトを SVG として保存する方法を学習しました。提供された手順に従うことで、プロジェクト ファイルを SVG 形式に効率的に変換でき、Web ベースのアプリケーションや視覚化ツールとのシームレスな統合が可能になります。
## よくある質問
### Aspose.Tasks for Java は、Microsoft Project ファイルのすべてのバージョンと互換性がありますか?
はい、Aspose.Tasks for Java は、MPP、MPT、XML 形式など、さまざまなバージョンの Microsoft Project ファイルをサポートしています。
### SVG 出力の外観をカスタマイズできますか?
はい、フォント、色、レイアウト構成などのパラメーターを調整することで、SVG 出力の外観をカスタマイズできます。
### Aspose.Tasks for Java を商用利用するにはライセンスが必要ですか?
はい、Aspose.Tasks for Java を商用利用するには有効なライセンスが必要です。 Webサイトからライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### 購入する前に Aspose.Tasks for Java を試すことはできますか?
はい、Web サイトから Aspose.Tasks for Java の無料トライアルをリクエストできます。[ここ](https://purchase.aspose.com/buy)その機能と能力を評価します。
### Aspose.Tasks for Java のサポートはどこで入手できますか?
フォーラムにアクセスすると、Aspose.Tasks for Java のサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15)で質問したり、コミュニティと交流したりできます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
