---
date: 2026-08-24
description: Aspose.Tasks for Java を使用して MS Project にリソースを追加し、標準レートやその他のリソースプロパティを設定し、リソースを効率的に管理する方法を学びます。
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Aspose.Tasks でリソースプロパティを設定する
og_description: Aspose.Tasks for Java を使用して MS Project のリソースを追加し、標準レートを設定します。この簡潔なガイドで前提条件、ステップバイステップのコード、トラブルシューティングを学びましょう。
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Aspose.Tasks (Java) で MS Project のリソースを追加し、レートを設定する
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Aspose.Tasks を使用して MS Project のリソースを追加する方法
url: /ja/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasksでリソース ms プロジェクトを追加し、レートを設定

## はじめに
Microsoft Project ファイルの読み書きが必要な Java アプリケーションを開発している場合、**adding a resource ms project** とその標準レートの設定は日常的ですが重要な作業です。このガイドでは `Project` オブジェクトの作成方法、リソースの追加方法、そして Aspose.Tasks for Java を使用して標準レートと残業レートの両方を設定する方法を示します。最後まで読むと、Microsoft Project をインストールせずにコスト計算を自動化し、プロジェクトスケジュールを最新の状態に保つことができるようになります。

## クイック回答
- **Project ファイルを表すクラスは何ですか？** `Project`
- **新しいリソースを追加する呼び出しはどれですか？** `project.getResources().add()`
- **標準レートはどのように設定しますか？** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **本番環境でライセンスは必要ですか？** はい、有効な Aspose.Tasks ライセンスをロードする必要があります。
- **サポートされている Java バージョンはどれですか？** Java 8 以降 (Java 17+ 推奨)。

## 「標準レートの設定」とは何ですか？
*set standard rate* 操作はリソースにデフォルトの時間単価を割り当てます。このレートはプロジェクトマネージャーが労働費用を計算し、コストレポートを生成し、予算を予測する際に使用され、プロジェクトライフサイクル全体で各リソースが実施する作業の期待価格を反映したコスト計算が行われます。

## なぜ Aspose.Tasks でレートを設定するのか？
Aspose.Tasks は **50 以上の入力および出力フォーマット** を処理でき、MPP、MPX、XML、Primavera ファイルなどを含み、ファイル全体をメモリにロードせずに数百ページに及ぶプロジェクトを扱えます。これにより、Windows、Linux、macOS サーバー上で高スループットのバッチ処理が可能となり、一般的な自動化シナリオで手作業を最大 90 % 削減できます。

## 前提条件
開始する前に、以下の項目が準備できていることを確認してください。

### Java 開発環境のセットアップ
1. JDK 8 以降をインストールします。[Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) からダウンロードできます。  
2. IntelliJ IDEA、Eclipse、NetBeans などの IDE を選択し、Java 開発用に設定します。

### Aspose.Tasks for Java のインストール
1. 最新の Aspose.Tasks for Java パッケージを [download page](https://releases.aspose.com/tasks/java/) からダウンロードします。  
2. JAR ファイルをプロジェクトのクラスパスに追加するか、製品ドキュメントに示されているように Maven/Gradle の依存関係を宣言します。

## パッケージのインポート
必要な Aspose.Tasks のコアクラスをインポートします。この手順により、後で使用する `Project`、`Resource`、`Rsc` 型にアクセスできるようになります。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## ステップ 1: プロジェクトオブジェクトの作成
`Project` クラスは、メモリ内で MS Project ファイル全体を表す最上位オブジェクトです。インスタンス化すると、タスク、リソース、その他のデータを追加できる空のプロジェクトが作成されます。

```java
Project project = new Project();
```

## ステップ 2: リソースの追加 (add resource ms project)
`Resource` クラスは、人物、機器、材料など単一のプロジェクトリソースをモデル化します。`project.getResources().add()` でリソースを追加すると、プロパティ設定の準備ができた非 null の `Resource` インスタンスが返されます。

```java
Resource rsc = project.getResources().add("Rsc");
```

## ステップ 3: リソースプロパティの設定 (how to set rates)
`Rsc` 列挙型には `STANDARD_RATE` や `OVERTIME_RATE` などのリソースフィールド用定数が含まれています。  
適切な `Rsc` 列挙値を使用して `Resource` オブジェクトの `set` を呼び出すことで、標準レートと残業レートを設定します。レートは金額の精度を保つために `BigDecimal` として保存されます。

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## 一般的な問題と解決策
| 問題 | 発生理由 | 対策 |
|-------|----------------|-----|
| `NullPointerException` when calling `set` | リソースが正しく追加されていません。 | `project.getResources().add()` が非 null の `Resource` を返すことを確認してください。 |
| Rates appear as 0 in the saved file | `int` を使用し、`BigDecimal` を使用していないため。 | 金額には常に `BigDecimal.valueOf()` を使用してください。 |
| License not found | `Project` 作成前にライセンスファイルがロードされていません。 | プログラム開始時にライセンスをロードします (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`)。 |

## 結論
これで、**add resource ms project** の方法、`Project` オブジェクトの作成方法、そして Aspose.Tasks for Java を使用した **標準レートと残業レートの設定** が分かりました。この機能により、コスト計算を自動化し、カスタムレポートを生成し、任意の Java アプリケーションから MS Project のリソースを完全に管理できるようになります。

## よくある質問
**Q: Aspose.Tasks for Java は複雑な MS Project ファイルを処理できますか？**  
A: はい、数千のタスクやリソースを含む大規模ファイルを含む、すべての主要な Project フォーマットをサポートし、データ損失なくすべてのフィールドを保持します。

**Q: 無料トライアルは利用可能ですか？**  
A: はい、[Aspose.Tasks free trial page](https://releases.aspose.com/) から Aspose.Tasks for Java の無料トライアルにアクセスできます。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
A: [support forum](https://forum.aspose.com/c/tasks/15) で支援を求めることができます。

**Q: 評価用の一時ライセンスはどのように取得できますか？**  
A: [temporary license page](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

**Q: 正式ライセンスはどこで購入できますか？**  
A: [purchase page](https://purchase.aspose.com/buy) からフルライセンスを購入してください。

---

**最終更新日:** 2026-08-24  
**テスト環境:** Aspose.Tasks for Java 24.12 (執筆時点での最新)  
**作者:** Aspose

## 関連チュートリアル

- [リソースの作成方法 – Aspose.Tasks for Java によるリソース管理](/tasks/java/resource-management/)
- [Aspose.Tasks for Java でプロジェクトにリソースを追加する](/tasks/java/resource-management/create-resources/)
- [プロジェクトにリソースを追加し、Aspose.Tasks でレベリング遅延プロパティを処理する方法](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}