---
title: 更新されたリソース データを Aspose.Tasks に書き込む
linktitle: 更新されたリソース データを Aspose.Tasks に書き込む
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して MS Project ファイル内のリソース データを簡単に更新する方法を学びます。
weight: 21
url: /ja/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 更新されたリソース データを Aspose.Tasks に書き込む

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project リソース データを更新する方法を説明します。 Aspose.Tasks は、システムに Microsoft Project をインストールしなくても Microsoft Project ファイルを操作できる強力な Java API です。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. Java Development Kit (JDK) がシステムにインストールされています。
2.  Java ライブラリの Aspose.Tasks。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
3. Java プログラミングの基本的な知識。

## パッケージのインポート

まず、Java コードで Aspose.Tasks を操作するために必要なパッケージをインポートする必要があります。次のインポート ステートメントを Java ファイルに追加します。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## ステップ 1: データ ディレクトリを設定する

データ ファイルが配置されるディレクトリを定義します。

```java
String dataDir = "Your Data Directory";
```

## ステップ 2: 入力ファイルと出力ファイルを指定する

入力 MS Project ファイルとその結果として更新されるファイルのパスを定義します。

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; //更新する 1 つの RSC を含むテスト ファイル
String resultFile = dataDir + "OutputMPP.mpp"; //テストプロジェクトを書き込むファイル
```

## ステップ 3: プロジェクトをロードする

 MS Project ファイルを`Project`物体：

```java
Project project = new Project(file);
```

## ステップ 4: リソースを追加して属性を設定する

新しいリソースをプロジェクトに追加し、標準レート、超過勤務レート、グループなどの属性を設定します。

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## ステップ 5: プロジェクトを保存する

更新されたプロジェクトを、変更されたリソース データとともに保存します。

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 結論

このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project リソース データを更新する方法を説明しました。これらの手順に従うことで、MS Project ファイル内のリソース情報をプログラムで効率的に操作できます。

## よくある質問

### Q1: Aspose.Tasks for Java を使用して、同じプロジェクト内の複数のリソースを更新できますか?

A1: はい、複数のリソースを反復処理し、それに応じて属性を設定することで、複数のリソースを更新できます。

### Q2: Aspose.Tasks は MS Project 以外のファイル形式をサポートしていますか?

A2: はい、Aspose.Tasks は XML、MPP などを含むさまざまなファイル形式をサポートしています。

### Q3: Aspose.Tasks は Java のさまざまなバージョンと互換性がありますか?

A3: Aspose.Tasks は Java バージョン 6 以降と互換性があります。

### Q4: Aspose.Tasks を使用して MS Project ファイルに対して他の操作を実行できますか?

A4: はい、タスク、リソース、カレンダーの読み取り、書き込み、操作など、幅広い操作を実行できます。

### Q5: Aspose.Tasks に関する追加のヘルプやサポートはどこで見つけられますか?

 A5: をご覧いただけます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートやご質問がございましたら。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
