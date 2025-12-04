---
date: 2025-12-04
description: Aspose.Tasks for Java を使用して、MS Project ファイルから通貨プロパティ（Java）を読み取る方法を学びましょう。ステップバイステップのガイドに従って、通貨コード、シンボル、桁数、位置をプログラムで抽出します。
language: ja
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks プロジェクトで Java を使用して通貨プロパティを読み取る
url: /java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks プロジェクトで Java の通貨プロパティを読み取る

## Introduction
このチュートリアルでは、Aspose.Tasks for Java API を使用して Microsoft Project ファイルから **read currency properties java** を取得します。Aspose.Tasks を使えば、Microsoft Project をインストールせずに .mpp ファイルを操作できるため、レポートの自動化、データ移行、または Java ベースのエンタープライズアプリケーションへの統合に最適です。本ガイドの最後までに、プロジェクトファイルから通貨コード、シンボル、小数桁数、シンボルの位置を直接抽出できるようになります。

## Quick Answers
- **“read currency properties java” とは何ですか？**  
  Java コードを使用して MS Project ファイルから通貨に関するメタデータ（コード、シンボル、桁数、位置）を取得することを指します。  
- **試すのにライセンスは必要ですか？**  
  Aspose.Tasks の無料トライアルは利用可能です。商用利用には製品ライセンスが必要です。  
- **必要な JDK バージョンは？**  
  Java 8 以上。  
- **読み取った後に通貨設定を変更できますか？**  
  はい、Aspose.Tasks は通貨プロパティの読み取りと書き込みの両方をサポートしています。  
- **すべての .mpp バージョンと互換性がありますか？**  
  API は Microsoft Project 2003‑2021 で作成されたファイルをサポートします。

## What is read currency properties java?
Java で通貨プロパティを読み取るとは、Microsoft Project ファイル内で金額の表示方法を定義するプロジェクトレベルの設定にアクセスすることです。これらの設定には ISO 通貨コード（例: **USD**）、シンボル（**$**）、小数桁数、シンボルが金額の前に来るか後に来るかが含まれます。

## Why read currency properties java with Aspose.Tasks?
- **Microsoft Project のインストール不要** – API は Java が動作する任意のプラットフォームで利用可能です。  
- **高速なインプロセス抽出** – 大量のプロジェクトファイルをバッチ処理するのに最適です。  
- **フルコントロール** – 取得した値をカスタムレポートに組み込んだり、ERP システムと統合したりできます。  
- **バージョン横断サポート** – Project 2003 から最新の 2021 版までの .mpp ファイルで動作します。

## Prerequisites
開始する前に以下を用意してください。

1. **Java Development Kit (JDK)** – Java 8 以上がインストールされ、`PATH` に設定されていること。  
2. **Aspose.Tasks for Java JAR** – 最新ライブラリを [here](https://releases.aspose.com/tasks/java/) からダウンロードし、プロジェクトのクラスパスに追加します。## Import Packages
プロジェクト操作に必要な Aspose.Tasks 名前空間をインポートします。

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
分析対象の `.mpp` ファイルが格納されているフォルダーを定義します。パスを変数に保持しておくとコードの再利用性が高まります。

```java
String dataDir = "Your Data Directory";
```

*`"Your Data Directory"` を、`project.mpp` が存在するフォルダーへの絶対パスまたは相対パスに置き換えてください。*

## Step 2: Create a Project Reader Instance
Microsoft Project ファイルを `Project` オブジェクトにロードします。このオブジェクトを通じて、通貨設定を含むすべてのプロジェクトプロパティにアクセスできます。

```java
Project project = new Project(dataDir + "project.mpp");
```

*ファイル名が異なる場合は、`"project.mpp"` を該当の名前に変更してください。*

## Step 3: Display Currency Properties
`Prj` 列挙体を使用して各通貨属性を取得し、コンソールに出力します。API はオブジェクトを返すので、文字列に変換して表示できます。

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**出力例:**  
- **Currency Code** – `USD`、`EUR`、`JPY` などの ISO‑4217 コード。  
- **Currency Digits** – 多くの通貨で `2`、日本円の場合は `0`。  
- **Currency Symbol** – レポートに表示される文字 (`$`、`€`、`¥`)。  
- **Currency Symbol Position** – 金額の **前** が `0`、**後** が `1`。

## Step 4: Process Completion
抽出が正常に完了したことを示すメッセージを出力します。バッチジョブの一部としてコードを実行する際に便利です。

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` パスが間違っている、またはファイル名が誤記されている。 | ディレクトリ文字列を確認し、指定場所に `.mpp` ファイルが存在することを確認してください。 |
| **NullPointerException on `project.get(...)`** | プロジェクトファイルに通貨情報が含まれていない（稀）か、プロパティキーが間違っている。 | 読み取る前に `project.contains(Prj.CURRENCY_CODE)` で存在をチェックしてください。 |
| **LicenseException** | 本番環境で有効な Aspose.Tasks ライセンスが設定されていない。 | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` を `Project` オブジェクト作成前に実行してライセンスを適用してください。 |

## Frequently Asked Questions

**Q: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか？**  
A: Aspose.Tasks は Microsoft Project 2003‑2021 で生成された .mpp ファイルをサポートしており、古い形式から最新形式までカバーしています。

**Q: Aspose.Tasks で通貨プロパティを変更できますか？**  
A: はい、通貨設定の読み取りと書き込みの両方が可能です。例: `project.set(Prj.CURRENCY_CODE, "EUR");` の後にプロジェクトを保存してください。

**Q: Aspose.Tasks は商用利用に適していますか？**  
A: もちろんです。商用ライブラリであり、ライセンスは [here](https://purchase.aspose.com/buy) から購入できます。

**Q: Aspose.Tasks の無料トライアルはありますか？**  
A: はい、完全機能のトライアルが [here](https://releases.aspose.com/) から入手可能です。

**Q: Aspose.Tasks のサポートやヘルプはどこで受けられますか？**  
A: 公式フォーラムが最適です – [here](https://forum.aspose.com/c/tasks/15) からアクセスしてください。

## Conclusion
これで **read currency properties java** を Aspose.Tasks for Java を使用して MS Project ファイルから取得する方法を学びました。この機能により、Microsoft Project に依存せずに通貨メタデータをカスタムレポートや財務分析、統合パイプラインに組み込むことができます。プロパティの変更や他のプロジェクト属性との組み合わせを試して、よりリッチなソリューションを構築してみてください。

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}