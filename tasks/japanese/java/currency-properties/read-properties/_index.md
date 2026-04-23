---
date: 2026-02-07
description: Aspose.Tasks for Java を使用して、MS Project ファイルから通貨プロパティ（Java）を読み取り、通貨シンボル（Java）を抽出する方法を学びます。ステップバイステップのガイドに従って、通貨コード、シンボル、桁数、位置をプログラムで抽出しましょう。
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks プロジェクトで Java の通貨プロパティを読み取る
url: /ja/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks プロジェクトで Java の通貨プロパティを読み取る

## Introduction
このチュートリアルでは、Aspose.Tasks for Java API を使用して Microsoft Project ファイルから **read currency properties java** を読み取ります。Aspose.Tasks を使用すれば、Microsoft Project をインストールせずに .mpp ファイルを操作できるため、レポートの自動化、データ移行、または Java ベースのエンタープライズ アプリケーションへの統合に最適です。本ガイドの最後までに、プロジェクト ファイルから通貨コード、シンボル、小数桁数、シンボルの位置を直接抽出できるようになります。

## Quick Answers
- **「read currency properties java」とは何ですか？**  
  Java コードを使用して MS Project ファイルから通貨に関するメタデータ（コード、シンボル、桁数、位置）を取得することを指します。  
- **試すのにライセンスは必要ですか？**  
  Aspose.Tasks の無料トライアルは利用可能です。商用利用には商用ライセンスが必要です。  
- **必要な JDK バージョンは？**  
  Java 8 以上。  
- **読み取った後に通貨設定を変更できますか？**  
  はい、Aspose.Tasks は通貨プロパティの読み取りと書き込みの両方をサポートしています。  
- **すべての .mpp バージョンと互換性がありますか？**  
  API は Microsoft Project 2003‑2021 で作成されたファイルをサポートしています。

## What is read currency properties java?
Java で通貨プロパティを読み取るとは、Microsoft Project ファイル内で金額の表示方法を定義するプロジェクト レベルの設定にアクセスすることです。これらの設定には、ISO 通貨コード（例: **USD**）、シンボル（**$**）、小数桁数、シンボルが金額の前に来るか後に来るかが含まれます。

## Why read currency properties java with Aspose.Tasks?
- **Microsoft Project のインストール不要** – API は Java をサポートする任意のプラットフォームで動作します。  
- **高速なインプロセス抽出** – 大量のプロジェクト ファイルをバッチ処理するのに最適です。  
- **フルコントロール** – 取得した値をカスタム レポートに組み込んだり、ERP システムに統合したりできます。  
- **クロスバージョン対応** – Project 2003 から最新の 2021 リリースまでの .mpp ファイルで動作します。

## Prerequisites
開始する前に以下を用意してください。

1. **Java Development Kit (JDK)** – Java 8 以上がインストールされ、`PATH` に設定されていること。  
2. **Aspose.Tasks for Java JAR** – 最新ライブラリを [here](https://releases.aspose.com/tasks/java/) からダウンロードし、プロジェクトのクラスパスに追加します。  

## Import Packages
プロジェクト操作に必要な Aspose.Tasks 名前空間をインポートします。

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
分析対象の `.mpp` ファイルが格納されているフォルダーを定義します。パスを変数に保持しておくとコードの再利用性が向上します。

```java
String dataDir = "Your Data Directory";
```

*`"Your Data Directory"` を `project.mpp` が存在するフォルダーへの絶対パスまたは相対パスに置き換えてください。*

## Step 2: Create a Project Reader Instance
Microsoft Project ファイルを `Project` オブジェクトにロードします。このオブジェクトを通じて、通貨設定を含むすべてのプロジェクト プロパティにアクセスできます。

```java
Project project = new Project(dataDir + "project.mpp");
```

*ファイル名が異なる場合は `"project.mpp"` を該当の名前に変更してください。*

## Step 3: Display Currency Properties
`Prj` 列挙体を使用して各通貨属性を取得し、コンソールに出力します。API はオブジェクトを返すので、文字列に変換して表示できます。

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**表示例:**  
- **Currency Code** – `USD`、`EUR`、`JPY` などの ISO‑4217 コード。  
- **Currency Digits** – 多くの通貨で `2`、日本円の場合は `0`。  
- **Currency Symbol** – レポートに表示される文字（`$`、`€`、`¥`）。  
- **Currency Symbol Position** – `0` は金額の **前**、`1` は **後** を表します。

## How to extract currency symbol java?
シンボルだけが必要な場合は `Prj.CURRENCY_SYMBOL` プロパティに注目してください。同じ `project.get(...)` 呼び出しでシンボルを取得でき、変数に保存したりログに記録したり、別サービスへ渡したりできます。これは、金融ダッシュボードやローカライズされた UI コンポーネントで **extract currency symbol java** が必要なときに特に有用です。

## Step 4: Process Completion
抽出が正常に完了したことを示すメッセージを出力します。バッチ ジョブの一部としてコードを実行する場合に便利です。

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` パスが間違っている、またはファイル名が誤記されている。 | ディレクトリ文字列を確認し、指定場所に `.mpp` ファイルが存在することを確認してください。 |
| **NullPointerException on `project.get(...)`** | プロジェクト ファイルに通貨情報が含まれていない（稀）か、プロパティキーが間違っている。 | 読み取る前に `project.contains(Prj.CURRENCY_CODE)` で存在をチェックしてください。 |
| **LicenseException** | 本番環境で有効な Aspose.Tasks ライセンスが設定されていない。 | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` を `Project` オブジェクト作成前に実行してください。 |

## Frequently Asked Questions

**Q: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか？**  
A: Aspose.Tasks は Microsoft Project 2003‑2021 で生成された .mpp ファイルをサポートしており、古い形式から最新形式まで対応しています。

**Q: Aspose.Tasks で通貨プロパティを変更できますか？**  
A: はい、通貨設定の読み取りと書き込みの両方が可能です。例: `project.set(Prj.CURRENCY_CODE, "EUR");` としてからプロジェクトを保存してください。

**Q: Aspose.Tasks は商用利用に適していますか？**  
A: もちろんです。商用ライセンスは [here](https://purchase.aspose.com/buy) から購入できます。

**Q: 無料トライアルはありますか？**  
A: はい、完全機能のトライアル版が [here](https://releases.aspose.com/) から入手可能です。

**Q: Aspose.Tasks のサポートやヘルプはどこで受けられますか？**  
A: 公式フォーラムが最適です – [here](https://forum.aspose.com/c/tasks/15) からアクセスしてください。

## Additional FAQ (AI‑Optimized)

**Q: Java で通貨シンボルだけをプログラム的に抽出する方法は？**  
A: `project.get(Prj.CURRENCY_SYMBOL)` を呼び出し、結果を `String` にキャストすれば、プロジェクト ファイルで使用されている正確なシンボルが取得できます。

**Q: パスワード保護された .mpp ファイルから通貨プロパティを読み取れますか？**  
A: はい。パスワードを受け取る `Project` コンストラクタのオーバーロードを使用してファイルをロードし、上記と同様にプロパティを取得してください。

**Q: 多数のプロジェクト ファイルを処理する際のパフォーマンスは？**  
A: Aspose.Tasks はインプロセスで動作し、標準的な .mpp ファイルは数ミリ秒で読み取れます。大量処理の場合は、可能な限り同一の `Project` インスタンスを再利用すると効果的です。

## Conclusion
これで **read currency properties java** と **extract currency symbol java** を Aspose.Tasks for Java を使って MS Project ファイルから取得する方法を習得しました。この機能により、Microsoft Project に依存せずに通貨メタデータをカスタム レポート、財務分析、統合パイプラインに組み込むことが可能になります。プロパティの変更や他のプロジェクト属性との組み合わせなど、さまざまなシナリオで自由に試してみてください。

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}