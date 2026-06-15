---
date: 2026-06-15
description: Aspose.Tasks for Java を使用して MS Project ファイルのコストを管理する方法を学びます。MPP ファイルの読み込みや
  actual cost work と budgeted cost schedule の取得方法を含みます。
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Aspose.Tasks でリソースコストを処理する
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java を使用した MS Project のコスト管理方法
url: /ja/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用した MS Project のコスト管理方法

## はじめに

プロジェクト予算の管理はすべてのプロジェクトマネージャーにとって重要な責務であり、**コスト管理の方法**を効果的に行うかどうかがプロジェクトの成功を左右します。Aspose.Tasks for Java を使用すれば、Microsoft Project ファイルをプログラムから操作でき、.mpp ファイルを手動で開くことなくリソースのコストデータを読み書きできます。このチュートリアルでは、MPP ファイルの読み込み、実績コスト作業の確認、各リソースの予算コストスケジュールの抽出をステップバイステップで解説します。

## クイック回答
- **Aspose.Tasks for Java は何をしますか？** Microsoft Project ファイル（.mpp）を Microsoft Project がインストールされていなくても読み書きできます。  
- **MPP ファイルはどうやってロードしますか？** `new Project("path/to/file.mpp")` を使用します – API がメモリ上でファイルを解析します。  
- **利用できるコストフィールドはどれですか？** 実績コスト作業 (ACWP)、予定コスト作業スケジュール (BCWS)、実績コスト作業 (BCWP)。  
- **開発用にライセンスは必要ですか？** テスト用の無料一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされている Java バージョンは？** Java 8 以降、Java 17 LTS も含みます。

## MS Project のコストを管理するには？

`new Project("yourFile.mpp")` でプロジェクトをロードし、各 `Resource` オブジェクトを反復処理して ACWP、BCWS、BCWP などのコスト関連プロパティを取得します。Aspose.Tasks は内部のコスト値をプロジェクトの通貨に自動変換するため、取得した値をそのまま表示または保存できます。この方法により手作業のスプレッドシート計算が不要になり、すべてのプロジェクトレポートでデータの一貫性が保証されます。

## 前提条件

1. Java プログラミングの基本的な理解。  
2. Aspose.Tasks for Java ライブラリをプロジェクトに追加（Maven/Gradle または手動 JAR）。  
3. 分析対象の Microsoft Project ファイル（`.mpp`）へのアクセス。

## パッケージのインポート

`Project` と `Resource` クラスはプロジェクトデータを操作するエントリーポイントです。

`Project` クラスは Aspose.Tasks のトップレベルオブジェクトで、単一の Microsoft Project ファイルをメモリ上で表します。  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## 手順 1: データディレクトリを定義する

まず、`.mpp` ファイルが格納されているフォルダーを指定します。このパスは絶対パスでも、アプリケーションの作業ディレクトリに対する相対パスでも構いません。

```text
```java
String dataDir = "Your Data Directory";
```
```

## 手順 2: MS Project ファイルをロードする

`Project` がファイルを読み込み、クエリ可能なオブジェクトモデルを構築します。API は Microsoft Project がインストールされていなくてもファイルを解析し、30 以上の入力形式をサポートします。

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## 手順 3: リソースを反復処理する

`Resource` オブジェクトは人員、機器、材料など予算を消費する要素を表します。`project.getResources()` コレクションをループして各リソースにアクセスできます。

```text
```java
for (Resource res : prj.getResources()) {
```
```

## 手順 4: リソース名とコストを確認する

各リソースについて、名前が定義されていることを確認した上でコストフィールドを取得します。`getActualCost()` メソッドは **実績コスト作業** (ACWP) を返し、`getBudgetedCost()` は **予算コストスケジュール** (BCWS/BCWP) を返します。

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## なぜ Aspose.Tasks for Java を使用して MPP ファイルをロードするのか？

Aspose.Tasks は **30 以上のファイル形式**（`.mpp`、`.xml`、`.xlsx` など）をサポートし、**最大 10,000 タスク** のプロジェクトを 200 MB 未満の RAM で処理できます。ライブラリはすべての計算をサーバー側で実行するため、Microsoft Project のライセンスが不要です。

## よくある問題と解決策

- **リソース名が null の場合:** 古いファイルにはプレースホルダーリソースが含まれることがあります。コストプロパティにアクセスする前に必ず `resource.getName() != null` を確認してください。  
- **大容量ファイルでメモリ圧迫が発生する場合:** `LoadOptions` はロードするプロジェクトデータを指定できる設定クラスです。`project.setLoadOptions(LoadOptions.setLoadResourceData(false))` を使用して必要なデータだけをロードし、後で必要に応じて有効化します。  
- **通貨の不一致:** API はプロジェクトの通貨設定を尊重しますが、`project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` で上書き可能です。`CostRateTableType` はタスクに適用できるさまざまなコストレートテーブルを列挙します。

## よくある質問

**Q: Aspose.Tasks for Java は複雑なプロジェクト構造を扱えますか？**  
A: はい、入れ子になったサマリタスク、複数のリソースカレンダー、カスタムフィールドをすべてサポートし、すべての対応 Project バージョンで利用可能です。

**Q: Microsoft Project のさまざまなバージョンのファイルに対応していますか？**  
A: 完全に対応しています。Microsoft Project 2000 から最新の 2023 形式までのファイルを読み書きできます。

**Q: Aspose.Tasks for Java を他の Java ライブラリと統合できますか？**  
A: はい、API は標準的な Java オブジェクトを返すため、ロギングフレームワーク、ORM ツール、レポーティングライブラリなどとのシームレスな統合が可能です。

**Q: Aspose.Tasks for Java はカスタマーサポートを提供していますか？**  
A: Aspose は専用フォーラム、詳細なドキュメント、ライセンスユーザー向けの迅速なメールサポートを提供しています。

**Q: Aspose.Tasks for Java の無料トライアルはありますか？**  
A: Aspose のウェブサイトから 30 日間の評価ライセンスをダウンロードでき、すべての機能を無料で試すことができます。

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## 関連チュートリアル

- [コスト差異の計算と割り当てコストの管理方法](/tasks/java/resource-assignments/assignment-cost/)
- [タスクの予算、作業、コスト管理](/tasks/java/task-properties/task-budget-work-cost/)
- [Aspose.Tasks for Java でプロジェクトにリソースを追加する](/tasks/java/resource-management/create-resources/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}