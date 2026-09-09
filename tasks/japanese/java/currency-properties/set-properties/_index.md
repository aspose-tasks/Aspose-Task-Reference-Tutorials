---
date: 2026-09-09
description: Aspose.Tasks の Java プロジェクトで通貨記号を変更する方法を学び、通貨コードを設定し、記号を調整し、Microsoft
  Project ファイル向けにカスタム形式を適用する方法をご紹介します。
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Aspose.Tasks プロジェクトで通貨プロパティを設定する
og_description: Java を使用して Aspose.Tasks の通貨記号を変更する方法。ステップバイステップの手順、前提条件、プロジェクトコストの書式設定をカスタマイズするためのヒントをご紹介します。
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Aspose.Tasks の通貨記号を変更する方法 – Java ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Aspose.Tasks プロジェクトで通貨記号を変更する方法 – Java ガイド
url: /ja/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasksで通貨記号を変更する方法 – Java ガイド

## はじめに
このチュートリアルでは、Aspose.Tasks Java API を使用して Microsoft Project ファイルの **通貨記号を変更する方法** を学びます。海外クライアント向けのレポート作成、複数地域の予算統合、または単に会社の会計基準に合わせる必要がある場合でも、通貨記号を調整することで、すべてのコスト関連フィールドに正しい通貨記号が表示されます。本ガイドでは、開発環境の設定から新規または既存のプロジェクトファイルに変更を永続化するまで、すべての手順を説明します。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Tasks for Java.  
- **通貨記号を変更できますか？** はい – `Prj.CURRENCY_SYMBOL` を設定し、`CurrencySymbolPositionType` を選択します。  
- **サポートされているファイル形式は何ですか？** XML、MPP、その他多数は `SaveFileFormat` でサポートされています。  
- **開発にライセンスは必要ですか？** 無料トライアルでテストは可能ですが、本番環境ではライセンスが必要です。  
- **実装にどれくらい時間がかかりますか？** 基本的なセットアップで約5〜10分です。

## Aspose.Tasks を使用して Java で通貨記号を変更する方法
対象のプロジェクトをロード（または新規作成）し、目的の通貨プロパティを設定してファイルを保存します。操作は 3 つの API 呼び出しで構成されます：`Project` オブジェクトを作成またはロードし、通貨コード、記号、位置を割り当て、最後に `project.save` を呼び出します。このアプローチは新規プロジェクトでも既存ファイルでも、Microsoft Project がインストールされていなくても機能します。

## なぜ Aspose.Tasks を使って通貨を変更するのか
Aspose.Tasks は **30 以上の通貨関連プロパティに対するフル API カバレッジ** を提供し、コード、記号、小数桁、位置を一元管理できます。ライブラリは数百ページに及ぶ Project ファイルを典型的なサーバハードウェアで 1 秒未満で処理し、Windows、Linux、macOS で追加の依存関係なしに動作します。

## 前提条件
開始する前に、以下を確認してください。

1. **Java Development Kit (JDK) 8 以上** – API は少なくとも JDK 8 が必要です。  
2. **Aspose.Tasks for Java** – 最新の JAR は [Aspose.Tasks ダウンロードページ](https://releases.aspose.com/tasks/java/) から取得してください。  
3. **IDE** – Eclipse、IntelliJ IDEA、または Java をサポートする任意のエディタ。  
4. **書き込み可能なフォルダー** – 生成されたプロジェクトファイルを保存する場所。

## パッケージのインポート
以下のクラスはプロジェクトプロパティ、ファイル操作、通貨設定へのアクセスを提供します。

`Project` – メモリ内の Microsoft Project ファイルを表します。  
`Prj` – 通貨フィールドを含むすべてのプロジェクトレベルプロパティの定数を保持します。  
`CurrencySymbolPositionType` – 通貨記号の位置（金額の前または後）を列挙します。  

これらのインポートは、コードがプロジェクトを操作できるようになる前に必須です。

## 手順ガイド

### 手順 1: データディレクトリを定義する
ソースファイルを保持し、出力を書き込むフォルダーを選択します。ディレクトリが存在し、Java プロセスに書き込み権限があることを確認してください。

### 手順 2: 新しいプロジェクト インスタンスを作成する
`Project` クラスは Aspose.Tasks のトップレベルオブジェクトで、メモリ内の単一の Project ファイルを表します。インスタンス化すると、設定可能な空のプロジェクトが作成されます。

### 手順 3: 通貨プロパティを設定する
ここで通貨コード、小数桁数、記号自体、記号の位置を設定します。

- **通貨コード** – `AUD` や `USD` のような 3 文字の ISO 4217 コード。  
- **小数桁数** – 多くの通貨で通常 2 桁。  
- **通貨記号** – 金額と共に表示される文字または文字列、例：`$` や `€`。  
- **記号の位置** – `CurrencySymbolPositionType.Before` は金額の前に記号を配置し、`After` は後に配置します。  

これらの設定は、プロジェクト内のすべてのコスト関連フィールド（リソース料金、タスク予算など）に影響します。

> **プロのコツ:** 既存ファイルの通貨を変更する必要がある場合は、上記設定を適用する前に `new Project("file.mpp")` でロードしてください。

### 手順 4: 更新されたプロジェクトを保存する
目的の形式でプロジェクトをディスクに書き込みます。XML 形式は人間が読め、`SaveFileFormat.MPP` は Microsoft Project との完全な互換性を保持します。

### 手順 5: 成功を確認する
短いメッセージやログエントリを出力して、エラーなく処理が完了したことを確認します。これは自動化パイプラインで特に有用です。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| **`project.save` での `NullPointerException`** | `dataDir` が有効なパスでないか、書き込み権限がありません。 | ディレクトリが存在し、Java プロセスに書き込み権限があることを確認してください。 |
| **通貨記号が表示されない** | ロケールに対して記号の位置が誤って設定されています。 | 記号が金額の前に来るべき場合は `CurrencySymbolPositionType.Before` を使用してください。 |
| **プロジェクトファイルが MS Project で開かない** | 互換性のない設定で古い形式で保存しています。 | 最新の MS Project バージョンと完全に互換性を持たせるために `SaveFileFormat.MPP` で保存してください。 |

## FAQ

**Q: Aspose.Tasks を使用して単一プロジェクト内で複数の通貨を設定できますか？**  
A: はい、プロジェクトレベルの通貨を定義した後、個々のリソースやタスクのコストフィールドを変更することで、異なる通貨設定を割り当てることができます。

**Q: Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: はい、Project 2000 から最新リリースまでの MPP ファイル、XML やその他の交換フォーマットをサポートしています。

**Q: Aspose.Tasks はカスタム通貨フォーマットをサポートしていますか？**  
A: はい、カスタム記号、小数桁数、位置を定義でき、これらの設定は保存されたファイルに保持されます。

**Q: Aspose.Tasks を他の Java フレームワークと統合できますか？**  
A: もちろんです。API は純粋な Java で実装されているため、Spring、Hibernate、Maven、Gradle などのエコシステムとシームレスに連携できます。

**Q: 追加のヘルプやサンプルはどこで見つけられますか？**  
A: [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) を訪れるか、公式ドキュメントで詳細な API リファレンスをご確認ください。

## 結論
これで、Java を使用して Aspose.Tasks プロジェクトの **通貨記号を変更する方法**、通貨コードの設定、小数桁数の調整、カスタム記号の適用方法がわかりました。これらの機能により、ロケール固有のコストレポートを生成し、プロジェクト予算を地域の会計基準に合わせ、Microsoft Project ファイルをグローバルチーム間で一貫させることができます。

---

**最終更新日:** 2026-09-09  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## 関連チュートリアル

- [java プロジェクト プロパティ – Aspose.Tasks for Java を使用して MPP から通貨記号を抽出](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks プロジェクトで Java の通貨プロパティを読む](/tasks/java/currency-properties/read-properties/)
- [Aspose.Tasks で Java の通貨コードを管理](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}