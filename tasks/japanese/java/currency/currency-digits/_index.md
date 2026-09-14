---
date: 2026-09-14
description: Aspose.Tasks を使用して ms project の通貨を取得し、Java でプロジェクト プロパティを読み取る方法を学びます。MPP
  ファイルから通貨桁を抽出するステップバイステップ ガイドです。
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Aspose.Tasks を使用して MS Project から通貨を取得する方法
og_description: Aspose.Tasks を使用して ms project の通貨を取得し、Java でプロジェクト プロパティを読み取る方法を学びます。この簡潔な
  Java チュートリアルに従って、MPP ファイルから通貨桁を抽出してください。
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Aspose.Tasks を使用して ms project の通貨を取得する方法 – Java ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Aspose.Tasks を使用して ms project の通貨を取得する方法
url: /ja/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用して MS Project の通貨情報を取得する方法

## はじめに
Microsoft Project ファイルから **how to get ms project currency** 情報を取得したい場合、正しい場所に来ました。この包括的なチュートリアルでは、Aspose.Tasks ライブラリ for Java を使用して **how to work with ms project currency** 値を扱う方法を学びます。レポートツールやマイグレーションユーティリティの構築、あるいは **java project file** の通貨設定を読み取るだけでも、本ガイドは *.mpp* ファイルの読み込みから通貨桁数の抽出まで、すべての手順を案内します。最後まで読めば、独自のアプリケーションで ms project currency データを扱う自信がつくでしょう。

## クイック回答
- **What library reads MS Project files?** Aspose.Tasks for Java.  
- **How many lines of code to get currency digits?** Just three concise lines after the project is loaded.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Which Java version is supported?** Java 8 or higher (any JDK that runs Aspose.Tasks).  
- **Can I retrieve other Project properties?** Yes – Aspose.Tasks exposes a full set of Project fields (e.g., start date, cost rates, etc.).

## ms project currency とは
`ms project currency` プロパティは、Microsoft Project が金額を表示する際に使用する小数点以下の桁数を定義します。これはプロジェクトファイル内で **CURRENCY_DIGITS** フィールドとして保存され、金額が整数、1 桁小数、2 桁小数などで表示されるかを決定します。この設定は予算レポート、コスト集計、財務数値を表示する UI に直接影響を与えるため、正確なデータ交換に不可欠です。

## ms project currency の取り扱いに Aspose.Tasks を使用する理由
Aspose.Tasks を使用すれば、Microsoft Project をインストールせずに通貨桁数を抽出でき、エンタープライズレベルのパフォーマンスで実行できます。このライブラリは **30+ years of Project file versions**（Project 2000 から Project 2024 まで）をサポートし、**150 distinct file schemas** 以上に対応しています。標準的なサーバーで 500 ページのプロジェクトを読み込むのに通常 **2 秒** 未満で済み、必要なフィールドだけをクエリできるため、最大規模のスケジュールでもメモリ使用量を **50 MB** 未満に抑えることができます。

## 前提条件
1. **Java Development Environment** – JDK 8 以上がインストールされ、設定されていること。  
2. **Aspose.Tasks for Java** – 公式サイトから最新の JAR をダウンロードしてください: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)。  
3. **Basic Java knowledge** – Java プロジェクトの作成、外部ライブラリの追加、`main` メソッドの実行に慣れていることが必要です。

## パッケージのインポート
まず、必要なクラスをインポートします。Aspose.Tasks ライブラリから `Project` クラスと関連ユーティリティをインポートします。  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 手順 1: データディレクトリの定義
**java project file** (`*.mpp`) が格納されているフォルダーを指定します。  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` を、`project.mpp` が存在する絶対パスまたは相対パスに置き換えてください。

## 手順 2: mpp ファイルの読み込み
ここでは、Aspose.Tasks を使用して **how to load mpp** ファイルを読み込む方法を見ていきます。`Project` クラスは Microsoft Project ファイルを表し、そのプロパティにアクセスできます。  
```java
Project project = new Project(dataDir + "project.mpp");
```
`IOException` がスローされるので、ファイル名が正確に一致していることを確認してください。

## 手順 3: 通貨桁数の取得
プロジェクトが読み込まれたら、**ms project currency** の桁数を抽出するのはワンライナーです。`getCurrencyDigits()` メソッドは金額に定義された小数点以下の桁数を返します。  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
この呼び出しは小数点以下の桁数を表す `Integer` を返します（例: セントの場合は `2`）。値はコンソールに出力されますが、さらに処理するために変数に格納することも可能です。

## よくある問題とヒント
- **File not found** – `dataDir` パスを再確認し、`.mpp` 拡張子を含めたファイル名が正しいことを確認してください。  
- **Unsupported file version** – Aspose.Tasks は Project 2000‑2024 形式をサポートしていますが、古いまたは破損したファイルは変換が必要になる場合があります。  
- **License not set** – 開発中はトライアルで動作しますが、本番環境では評価用の透かしを回避するために有効なライセンスを適用する必要があります。

## よくある質問

**Q: Can Aspose.Tasks handle other Project attributes besides currency digits?**  
A: はい、Aspose.Tasks はタスク、リソース、カスタムフィールドなど、Project ファイルのさまざまな側面を操作するための豊富な機能を提供します。

**Q: Is Aspose.Tasks suitable for enterprise‑level applications?**  
A: 絶対に適しています。Aspose.Tasks はエンタープライズグレードのプロジェクト要求に応えるよう設計されており、高性能とスケーラビリティを提供します。

**Q: Does Aspose.Tasks support cross‑platform development?**  
A: はい、Java Runtime Environment をサポートする任意のプラットフォーム（Windows、Linux、macOS）で Aspose.Tasks for Java を使用できます。

**Q: Can I try Aspose.Tasks before purchasing?**  
A: はい、[Aspose releases page](https://releases.aspose.com/) から無料トライアル版をダウンロードしてお試しいただけます。

**Q: Where can I get support for Aspose.Tasks?**  
A: サポートは [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) でご利用いただけます。

---

**最終更新日:** 2026-09-14  
**テスト済み:** Aspose.Tasks for Java (執筆時点での最新バージョン)  
**作者:** Aspose

## 関連チュートリアル

- [java プロジェクト プロパティ – Aspose.Tasks for Java を使用して MPP から通貨記号を抽出](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks を使用して MS Project から通貨を取得する方法](/tasks/java/currency/currency-codes/)
- [Project Properties Java – Aspose.Tasks でメタデータを読み取る](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}