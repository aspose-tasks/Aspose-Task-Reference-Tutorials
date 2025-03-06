---
title: Aspose.TasksでMSプロジェクトをJPEGとして変換する
linktitle: Aspose.Tasks にプロジェクトを JPEG として保存
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して Microsoft Project ファイルを JPEG 画像に簡単に変換する方法を学びます。生産性を向上させます。
weight: 20
url: /ja/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TasksでMSプロジェクトをJPEGとして変換する

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project ファイルを JPEG 画像として保存する方法を説明します。これは、プロジェクトの視覚化を共有したり、プロジェクト データをレポートやプレゼンテーションに統合したりする場合に特に役立ちます。
## 前提条件
始める前に、以下のものがあることを確認してください。
1.  Java 開発キット (JDK): システムに Java がインストールされていることを確認してください。最新バージョンをダウンロードしてインストールできます。[Java Web サイト](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java: 次の手順に従って、Aspose.Tasks for Java をダウンロードしてセットアップします。[ドキュメンテーション](https://reference.aspose.com/tasks/java/).

## パッケージのインポート
まず、必要なパッケージを Java ファイルにインポートします。
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## ステップ 1: データ ディレクトリを定義する
MS Project ファイルが配置されているデータ ディレクトリへのパスを設定します。
```java
String dataDir = "Your Data Directory";
```
## ステップ 2: MS プロジェクト ファイルをロードする
Aspose.Tasks を使用して MS Project ファイルを読み込みます。
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## ステップ 3: JPEG 品質を構成する (オプション)
 JPEG品質を調整したい場合は、`ImageSaveOptions`クラス。品質の範囲は 0 ～ 100 です。
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // JPEG品質を50に設定します
```
## ステップ 4: プロジェクトを JPEG として保存する
MS Project ファイルを JPEG 画像として保存します。
```java
project.save(dataDir + "image_out.jpeg", options);
```

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project ファイルを JPEG 画像として保存する方法を学習しました。この機能により、プロジェクト データを簡単に共有し、さまざまなドキュメントやプレゼンテーションに統合することができます。
## よくある質問
### Q: JPEG画像の画質を調整できますか?
 A: はい、次を使用して品質を調整できます。`setJpegQuality()`メソッド。範囲は 0 ～ 100 です。
### Q: JPEG 品質を指定しない場合はどうなりますか?
A: 品質を指定しない場合は、デフォルトの品質が使用されます。
### Q: Aspose.Tasks for Java は無料で使用できますか?
 A: Aspose.Tasks for Java は商用ライブラリですが、無料トライアルでその機能を試すことができます。訪問[無料お試しページ](https://releases.aspose.com/)詳細については。
### Q: Aspose.Tasks for Java のサポートはどこで入手できますか?
A: Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks の一時ライセンスを購入できますか?
 A: はい、次から一時ライセンスを購入できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
