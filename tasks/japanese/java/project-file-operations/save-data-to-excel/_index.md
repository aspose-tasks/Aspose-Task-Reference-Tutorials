---
title: Aspose.Tasks で MS プロジェクト データを Excel に保存する
linktitle: Aspose.Tasks でデータを Excel に保存する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して Microsoft Project データを Excel ファイルに保存する方法を学びます。 Java 開発者にとって簡単な統合。
weight: 19
url: /ja/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で MS プロジェクト データを Excel に保存する

## 導入
Aspose.Tasks for Java は、開発者がプログラムで Microsoft Project ファイルを操作できるようにする強力なライブラリです。このチュートリアルでは、プロジェクト ファイルから Excel ファイルにデータを保存するプロセスを段階的に説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java Development Kit (JDK): システムに Java がインストールされていることを確認してください。最新バージョンの JDK を Oracle Web サイトからダウンロードしてインストールできます。
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリを次の場所からダウンロードします。[ダウンロードリンク](https://releases.aspose.com/tasks/java/)それを Java プロジェクトに含めます。

## パッケージのインポート
まず、Aspose.Tasks を操作するために必要なパッケージを Java コードにインポートする必要があります。
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

提供された例を複数のステップに分けてみましょう。
## ステップ 1: データ ディレクトリ パスを定義する
```java
String dataDir = "Your Data Directory";
```
交換する`"Your Data Directory"`プロジェクト ファイルが配置されているデータ ディレクトリへのパスを置き換えます。
## ステップ 2: プロジェクト ファイルをロードする
```java
Project project = new Project(dataDir + "project5.mpp");
```
このコード行は、指定されたデータ ディレクトリから「project5.mpp」という名前のプロジェクト ファイルを読み込みます。
## ステップ 3: プロジェクトを XLSX として保存する
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
ここで、`save`メソッドは、ロードされたプロジェクト ファイルを「project1.xlsx」という名前の Excel ファイルとして同じデータ ディレクトリに保存するために使用されます。を指定します。`SaveFileFormat.Xlsx`パラメータを使用してXLSX形式で保存します。

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project ファイルから Excel ファイルにデータを保存する方法を学習しました。提供された手順に従うことで、この機能を Java アプリケーションにシームレスに統合できます。
## よくある質問
### Aspose.Tasks for Java を使用してプロジェクト データをプログラムで操作できますか?
はい、Aspose.Tasks for Java は、プロジェクト ファイルの読み取り、書き込み、変更など、プロジェクト データを操作するための広範な機能を提供します。
### Aspose.Tasks for Java に利用できる無料トライアルはありますか?
はい、Aspose.Tasks for Java の無料試用版を次からダウンロードできます。[ここ](https://releases.aspose.com/).
### Aspose.Tasks for Java のドキュメントはどこで見つけられますか?
Aspose.Tasks for Java のドキュメントを見つけることができます。[ここ](https://reference.aspose.com/tasks/java/).
### Aspose.Tasks for Java に関連する問題やクエリのサポートを受けるにはどうすればよいですか?
 Aspose.Tasks フォーラムにアクセスしてサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for Java の一時ライセンスを購入できますか?
はい、次から一時ライセンスを購入できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
