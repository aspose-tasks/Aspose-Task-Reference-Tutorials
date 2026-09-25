---
date: 2026-09-25
description: Aspose.Tasks for Java を使用して MS Project ファイルから通貨コードを取得する方法を学びましょう – Java
  開発者が必要とする通貨コードを素早く取得する方法です。
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Aspose.Tasks で通貨コードを管理する
og_description: Aspose.Tasks を使用して MS Project ファイルから Java の通貨コードを取得します。このガイドでは、プロジェクトの読み取り方法、ISO
  通貨識別子の抽出方法、そして Java アプリケーションへの適用方法を示します。
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: MS Project から Java の通貨コードを取得する
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Aspose.Tasks を使用して MS Project から Java の通貨コードを取得する
url: /ja/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project から Aspose.Tasks を使用して通貨コード（Java）を取得する

## はじめに
このチュートリアルでは、Aspose.Tasks Java API を使用して MS Project ファイルから **通貨コード（Java）を取得する方法** を学びます。マルチ通貨の財務レポートを作成したり、異なる地域のプロジェクトを統合したり、下流システムで正しい通貨記号を表示したりする必要がある場合でも、以下の手順で環境設定から ISO 通貨識別子を返すワンライン呼び出しまでを案内します。ガイドの最後までに、サポートされている任意の Project ファイル形式をロードし、`USD`、`EUR`、`GBP` などの3文字通貨コードを抽出できるようになります。

## クイック回答
- **API の機能は何ですか？** MS Project ファイルを読み取り、通貨コードなどのプロパティを公開します。  
- **使用言語は何ですか？** Java、Aspose.Tasks for Java ライブラリを介して。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **コードをワンラインで取得できますか？** はい—`prj.get(Prj.CURRENCY_CODE)` は通貨コード文字列を即座に返します。  
- **すべての Project バージョンと互換性がありますか？** Aspose.Tasks はレガシー MPP、XML、XER ファイルを含む 20 以上の入力形式をサポートしています。

## MS Project ファイルの読み取りとは？
MS Project ファイルを読み取ることは、プログラムで *.mpp*（または XML や XER などのサポートされている他の形式）を開き、その内部データ構造にアクセスすることを意味します。これらの構造にはタスク、リソース、カレンダー、コストテーブル、財務設定が含まれます。ファイルを解析することで Microsoft Project を起動せずに情報を抽出でき、自動レポート作成、移行、統合ワークフローを実現します。

## なぜ Aspose.Tasks を使用して MS Project ファイルを読み取るのか？
Aspose.Tasks は純粋な Java ソリューションを提供し、COM インターロップやローカルの Microsoft Project インストールの必要性を排除します。20 以上のファイル形式をサポートし、数千のタスクを持つプロジェクトでも 100 MB 未満のメモリで処理でき、豊富なオブジェクトモデルを提供します。`Prj.CURRENCY_CODE` のような定数に直接アクセスできるため、通貨情報を即座かつ確実に取得できます。

## 前提条件
コードに入る前に、以下が揃っていることを確認してください：

### Java Development Kit (JDK) がインストールされていること
JDK 11 以降の最新版が必要です。公式 Oracle サイトからダウンロードしてください: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)。

### Aspose.Tasks for Java ライブラリ
最新の Aspose.Tasks for Java バイナリを取得し、プロジェクトのクラスパスに追加してください。完全なドキュメントとダウンロードリンクは [here](https://reference.aspose.com/tasks/java/) にあります。

## パッケージのインポート
`Project` クラスと `Prj` 定数は `com.aspose.tasks` 名前空間にあります。Java ソースファイルの先頭でインポートしてください：

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## ステップバイステップ ガイド

### 手順 1: データディレクトリの設定
*.mpp* ファイルが格納されているフォルダーを定義します。実行環境に合わせてパスを調整し、ランタイムがプロジェクトファイルを見つけられるようにしてください。

```java
String dataDir = "Your Data Directory";
```

### 手順 2: プロジェクトファイルのロード
`Project` クラスは Aspose.Tasks のトップレベルオブジェクトで、単一の MS Project ファイルをメモリ上に表現します。インスタンスを作成するとファイルが読み込まれ、クエリ可能なインメモリモデルが構築されます。

```java
Project prj = new Project(dataDir + "project.mpp");
```

### 手順 3: 通貨コードの取得
`Prj.CURRENCY_CODE` 定数は ISO 通貨識別子を格納するプロパティを示します。`prj.get(Prj.CURRENCY_CODE)` を呼び出すと、1 回の操作で3文字コードが返されます。

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
出力は、プロジェクトで設定されている 3 文字の ISO 通貨コード（例: `USD`、`EUR`、`GBP`）になります。

### 手順 4: Java で通貨コードを取得する方法（追加コンテキスト）
プロジェクトをロードし、`prj.get(Prj.CURRENCY_CODE)` を呼び出して結果を `String` に格納します。その後、この値を通貨識別子を必要とする任意の金融サービス、レポートエンジン、UI コンポーネントに渡すことができます。

### 手順 5: （オプション）通貨コードの使用
典型的な下流シナリオは次のとおりです：

- **レポート生成** – コスト列の前にコードを付加します（`USD 1,200`）。  
- **API 統合** – 通貨パラメータを要求する決済ゲートウェイに ISO コードを送信します。  
- **データ統合** – ポートフォリオレベルの分析のために、通貨別に複数のプロジェクトをグループ化します。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|-------|--------|-----|
| **Null 出力** | プロジェクトファイルで通貨が定義されていない（デフォルトは空）。 | 読み込む前に Microsoft Project で通貨を設定するか、`prj.set(Prj.CURRENCY_CODE, "USD");` で割り当ててください。 |
| **ファイルが見つかりません** | `dataDir` パスが間違っています。 | パスを確認し、ファイル名が正確に一致していること（大文字小文字も含む）を確認してください。 |
| **サポートされていないファイルバージョン** | 非常に古いまたは破損した *.mpp* ファイル。 | 最新の Aspose.Tasks バージョンにアップグレードするか、まず Microsoft Project でファイルを新しい形式に変換してください。 |

## よくある質問

**Q: Aspose.Tasks は複雑なプロジェクト構造を処理できますか？**  
A: はい、API は階層化されたタスク、リソースプール、カスタムフィールド、カレンダーを制限なく読み取ります。

**Q: Aspose.Tasks はさまざまなバージョンの MS Project ファイルと互換性がありますか？**  
A: もちろんです。Project 98 から最新の Office リリースまで、MPP、XML、XER などの形式をサポートしています。

**Q: Aspose.Tasks はドキュメントとサポートを提供していますか？**  
A: 完全な API リファレンス、コード例、専用のテクニカルサポートが Aspose のウェブサイトで利用可能です。

**Q: 購入前に Aspose.Tasks を試すことはできますか？**  
A: 無料トライアルが提供されており、通貨コード抽出を含むすべての機能を評価できます。

**Q: 評価用の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは [website](https://purchase.aspose.com/temporary-license/) から入手可能です。

---

**最終更新日:** 2026-09-25  
**テスト環境:** Aspose.Tasks for Java（最新バージョン）  
**作者:** Aspose

## 関連チュートリアル

- [Project Properties Java – Aspose.Tasks でメタデータを読み取る](/tasks/java/project-properties/)
- [Aspose.Tasks for Java を使用して Microsoft Project からプロジェクト情報を読み取る方法](/tasks/java/project-properties/read-project-info/)
- [Aspose.Tasks で MS Project のアウトラインコードを取得する](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}