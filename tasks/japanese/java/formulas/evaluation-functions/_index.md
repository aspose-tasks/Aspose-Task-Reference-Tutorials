---
date: 2026-10-10
description: Aspose.Tasks で拡張属性を追加し、評価関数を使用し、この Java プロジェクト管理ライブラリでプロジェクトレポートを生成する方法を学びます。
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Aspose.Tasks の数式で評価関数をサポート
og_description: Aspose.Tasks で拡張属性を追加し、評価関数を使用し、この Java プロジェクト管理ライブラリでプロジェクトレポートを生成する方法を学びます。
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Aspose.Tasks の数式で拡張属性を追加する方法
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Aspose.Tasks の数式で拡張属性を追加する方法
url: /ja/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks の数式で拡張属性を追加する方法

## はじめに
Aspose.Tasks for Java は **Java プロジェクト管理ライブラリ** で、Java で `Project` オブジェクトを作成し、コード内で直接 Microsoft Project の関数を評価することでプロジェクトレポートを生成できます。これらの数式を埋め込むことで、複雑な計算を実行し、カスタムレポートを生成し、開発環境を離れることなくプロジェクト分析を自動化できます。このチュートリアルでは、プロジェクトオブジェクトの作成、拡張属性の追加、評価関数を使用して **add custom field task** データを追加する手順を解説します。

## クイック回答
- **“create project object java” は何を意味しますか？** プログラムから操作できるインメモリの `Project` インスタンスを作成します。  
- **どのライブラリが必要ですか？** Aspose.Tasks for Java（公式サイトからダウンロード）。  
- **ライセンスは必要ですか？** 本番環境で使用するには一時的または完全な Aspose.Tasks ライセンスが必要です。無料トライアルも利用可能です。  
- **カスタムフィールドは使用できますか？** はい。タスクに **add extended attribute** を追加してカスタムフィールドとして扱うことができます。  
- **すべての Project ファイル形式と互換性がありますか？** Aspose.Tasks は主要な 3 つの形式（MPP、MPT、XML）と、50 以上の追加入出力形式に対応しています。

## 前提条件
1. **Java 開発環境** – JDK 8+ と IntelliJ IDEA や Eclipse などの IDE。  
2. **Aspose.Tasks for Java ライブラリ** – [Aspose.Tasks for Java ダウンロードページ](https://releases.aspose.com/tasks/java/) からダウンロードし、ライブラリを組み込んでください。

## パッケージのインポート
Java クラスに Aspose.Tasks の名前空間を追加して、プロジェクト、タスク、拡張属性を操作できるようにします。

```java
import com.aspose.tasks.*;
```

## プロジェクトレポートの生成 – create project object java
`Project` クラスは、メモリ内の Microsoft Project ファイルを表し、タスク、リソース、カスタムデータを公開します。このクラスのインスタンス化により、定義するすべてのプロジェクト要素のコンテナが得られます。

```java
Project project = new Project();
```

上記の行は **creates project object java** を作成し、空の状態でカスタマイズの準備ができています。

## 拡張属性の追加方法
`ExtendedAttributeDefinition` クラスは、タスクに付与できるカスタムフィールドを定義します。拡張属性を追加するには、タイプ `Number` のこのクラスのインスタンスを作成し、“Sine” のようなエイリアスを割り当て、プロジェクトの `ExtendedAttributes` コレクションに追加し、カスタムフィールドが必要な各タスクにリンクします。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

ここではタイプ `Number` の **add extended attribute** を “Sine” という名前で作成し、タスクに関連付けています。

## プロジェクトに拡張属性を追加する
属性定義をプロジェクトに登録し、すべてのタスクが参照できるようにします。

```java
project.getExtendedAttributes().add(attr);
```

## 新しいタスクの作成
`Task` はプロジェクト内の作業項目を表し、カスタムフィールドを含めることができます。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## プロジェクトにカスタムフィールドタスクを追加する
先に定義した拡張属性を新しく作成したタスクにリンクし、タスクに数式や計算で使用できるカスタム “Sine” フィールドを付与します。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

これでタスクは数式や計算で使用できるカスタム “Sine” フィールドを保持します。これがプログラムで **add custom field task** データを追加する方法でもあります。

## 評価関数を使用する理由
評価関数を使用すると、ネイティブな Microsoft Project の数式（例: `Sin([Start])`）を Aspose.Tasks に直接埋め込むことができ、外部処理なしでオンザフライ計算が可能になります。これにより、すべてのプロジェクトロジックが一元化され、データ同期エラーが減少し、レポート生成が高速化します。Aspose.Tasks は 100 以上の MS Project 関数の評価をサポートし、Java 内で包括的な計算エンジンを提供します。

## 一般的な問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **Formula returns `NaN`** | カスタムフィールドの型が期待される数値型と一致しているか確認してください。 |
| **Extended attribute not visible** | タスクを作成する **前に** 属性定義がプロジェクトに追加されていることを確認してください。 |
| **License exception** | 一時的または完全な **Aspose.Tasks ライセンス** をインストールしてください。トライアルモードでは一部機能が制限される場合があります。 |
| **Missing temporary license** | Aspose のウェブサイトから **temporary Aspose ライセンス** を取得してください。 |

## よくある質問

**Q: Aspose.Tasks for Java は複雑な MS Project の数式を処理できますか？**  
A: はい、Aspose.Tasks for Java は幅広い MS Project 関数の評価をサポートしており、Java アプリケーション内で複雑な計算が可能です。

**Q: Aspose.Tasks for Java はさまざまなバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: はい、Aspose.Tasks for Java は MPP、MPT、XML 形式を含むさまざまなバージョンの Microsoft Project ファイルをサポートしています。

**Q: 購入前に Aspose.Tasks for Java を試すことはできますか？**  
A: はい、ウェブサイトの [Aspose.Tasks for Java 購入ページ](https://purchase.aspose.com/buy) から無料トライアル版をダウンロードできます。

**Q: Aspose.Tasks for Java のサポートはどのように受けられますか？**  
A: Aspose.Tasks コミュニティフォーラム [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15) からサポートを受けられます。

**Q: Aspose.Tasks for Java 用の一時ライセンスはありますか？**  
A: はい、テスト目的で使用できる一時ライセンスを Aspose のウェブサイトの [Aspose temporary license page](https://purchase.aspose.com/temporary-license/) から取得できます。

## 結論
これらの手順に従うことで、**create project object**、**add extended attribute** の方法と、評価関数を活用して **generate project report** を自動的に生成する方法を学びました。この基盤を拡張して、より高度なプロジェクト分析、カスタムダッシュボード、または自動スケジューリングツールを構築できます—すべて Aspose.Tasks for Java が提供します。

---

**最終更新日:** 2026-10-10  
**テスト環境:** Aspose.Tasks for Java 24.10  
**作者:** Aspose

## 関連チュートリアル

- [Java プロジェクト管理におけるカスタム列と拡張属性](/tasks/java/project-management/extended-attributes/)
- [Aspose.Tasks for Java で拡張タスク属性を読み取る](/tasks/java/task-properties/extended-task-attributes/)
- [Aspose.Tasks for Java の使用方法 – リソース割り当てに拡張属性を追加](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}