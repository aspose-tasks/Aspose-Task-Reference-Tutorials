---
title: Aspose.Tasks 式での評価関数のサポート
linktitle: Aspose.Tasks 式での評価関数のサポート
second_title: Aspose.Tasks Java API
description: Java を使用して Aspose.Tasks 式で MS Project 関数の評価をサポートする方法を学びます。 Aspose.Tasks を使用して生産性を向上させます。
weight: 10
url: /ja/java/formulas/evaluation-functions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 式での評価関数のサポート


## 導入
Aspose.Tasks for Java は、開発者が Microsoft Project ファイルをプログラムで操作できるようにする強力なライブラリです。その重要な機能の 1 つは、Aspose.Tasks 式内での MS Project 関数の評価をサポートする機能です。この機能により、ユーザーは Java アプリケーション内で直接複雑な計算と分析を実行できるようになります。
## 前提条件
MS Project 関数を Aspose.Tasks 式に統合する作業を開始する前に、次のものが揃っていることを確認してください。
1. Java 開発環境: Java が、IntelliJ IDEA や Eclipse などの Java 開発用の互換性のある IDE とともにシステムにインストールされていることを確認してください。
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリをダウンロードして、Java プロジェクトに組み込みます。からダウンロードできます。[Aspose.Tasks for Java のダウンロード ページ](https://releases.aspose.com/tasks/java/).
## パッケージのインポート
まず、Aspose.Tasks 機能を利用するために必要なパッケージを Java クラスにインポートします。
```java
import com.aspose.tasks.*;
```

## ステップ 1: 新しいプロジェクト オブジェクトを作成する
まず、新規作成します`Project`操作するオブジェクト:
```java
Project project = new Project();
```
これにより、新しい空のプロジェクトが初期化されます。
## ステップ 2: タスクの拡張属性を定義する
次に、タスクの拡張属性を定義します。この属性は、タスクに関連付けられたカスタム データを保持します。
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
ここでは、次のタイプの拡張属性を作成します。`Number`タスクの名前は「Sine」です。
## ステップ 3: 拡張属性をプロジェクトに追加する
拡張属性の定義をプロジェクトの拡張属性のリストに追加します。
```java
project.getExtendedAttributes().add(attr);
```
これにより、カスタム属性がプロジェクトに追加されます。
## ステップ 4: 新しいタスクを作成する
次に、プロジェクト内に新しいタスクを作成しましょう。
```java
Task task = project.getRootTask().getChildren().add("Task");
```
これにより、「Task」という名前の新しいタスクがプロジェクトに追加されます。
## ステップ 5: 拡張属性をタスクに関連付ける
前に作成した拡張属性をタスクに関連付けます。
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
これにより、「Sine」拡張属性がタスクに関連付けられます。

## 結論
結論として、MS Project 関数を Java の Aspose.Tasks 式に統合するのは簡単なプロセスです。指定された手順に従うことで、Aspose.Tasks for Java の強力な機能を効果的に利用して、Microsoft Project ファイルをプログラムで操作および分析できます。
## よくある質問
### Q: Aspose.Tasks for Java は複雑な MS Project 式を処理できますか?
A: はい、Aspose.Tasks for Java は幅広い MS Project 関数の評価をサポートしており、Java アプリケーション内で複雑な計算を行うことができます。
### Q: Aspose.Tasks for Java は、さまざまなバージョンの Microsoft Project ファイルと互換性がありますか?
A: はい、Aspose.Tasks for Java は、MPP、MPT、XML 形式など、さまざまなバージョンの Microsoft Project ファイルをサポートしています。
### Q: 購入する前に Aspose.Tasks for Java を試すことはできますか?
 A: はい、Aspose.Tasks for Java の無料試用版を Web サイトからダウンロードできます。[ここ](https://purchase.aspose.com/buy).
### Q: Aspose.Tasks for Java のサポートを受けるにはどうすればよいですか?
A: Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks for Java で利用できる一時ライセンスはありますか?
 A: はい、Aspose Web サイトからテスト目的の一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
