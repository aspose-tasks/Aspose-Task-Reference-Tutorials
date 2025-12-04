---
date: 2025-12-04
description: Aspose.Tasks Java プロジェクトで通貨を設定する方法、通貨や通貨記号の変更方法を学びましょう。Microsoft Project
  ファイルを簡単に操作できます。
language: ja
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks プロジェクトで通貨を設定する方法 – Java ガイド
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks プロジェクトで通貨を設定する方法 – Java ガイド

## Introduction
このチュートリアルでは、Aspose.Tasks Java API を使用して Microsoft Project ファイルの **通貨を設定する方法** を学びます。国際チーム向けに *通貨を変更* したり、Java で *通貨記号* を調整したりする必要がある場合でも、以下の手順で分かりやすくコード例とともに実装できます。

## Quick Answers
- **必要なライブラリは？** Aspose.Tasks for Java。  
- **通貨記号は変更できる？** はい – `CurrencySymbolPositionType` と `Prj.CURRENCY_SYMBOL` を使用します。  
- **サポートされているファイル形式は？** XML、MPP、その他多数は `SaveFileFormat` で指定可能です。  
- **開発にライセンスは必要？** テスト用の無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **実装にかかる時間は？** 基本的な設定で約 5‑10 分です。

## What is “currency” in a Project file?
Project の通貨は、コスト値の表示方法（コード（例: `AUD`）、小数点桁数、記号（`$`）および記号の位置）を定義します。これらのプロパティを設定することで、リソース単価、タスク予算などのすべてのコスト関連フィールドが、対象ユーザーに適した通貨形式で表示されます。

## Why use Aspose.Tasks to change currency?
- **Microsoft Project のインストール不要** – 任意のサーバー上でファイルを操作可能。  
- **完全な API カバレッジ** – 通貨関連フィールドはすべて `Prj` 定数で取得・設定可能。  
- **クロスプラットフォーム** – Windows、Linux、macOS で任意の Java 対応 IDE から利用可能。  
- **高性能** – 大規模なプロジェクトファイルも高速かつ安定して処理。

## Prerequisites
開始する前に以下を用意してください。

1. **Java Development Kit (JDK)** – バージョン 8 以上。  
2. **Aspose.Tasks for Java** – 最新の JAR を [Aspose.Tasks ダウンロードページ](https://releases.aspose.com/tasks/java/) から取得。  
3. **IDE** – Eclipse、IntelliJ IDEA、またはお好みのエディタ。  
4. **書き込み可能なフォルダー** – 生成されたプロジェクトファイルを保存する場所。

## Import Packages
まず、プロジェクトプロパティやファイル操作に必要なクラスをインポートします。

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
ソースファイルが格納され、出力が書き込まれるフォルダーを指定します。

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
新しい `Project` オブジェクトをインスタンス化します。このオブジェクトはメモリ上の Microsoft Project ファイルを表します。

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
ここで **通貨を設定する方法** として、コード、桁数、記号、記号の位置などを指定します。

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **プロのコツ:** 既存プロジェクトの **通貨を変更** したい場合は、`new Project("file.mpp")` でファイルをロードしてから上記設定を適用してください。

### Step 4: Save the Updated Project
プロジェクトを希望の形式でディスクに保存します。この例では XML 形式を使用していますが、`SaveFileFormat.MPP` も選択可能です。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
エラーなく完了したことを示すメッセージを出力します。

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` が有効なパスでない、または書き込み権限がない。 | ディレクトリが存在し、Java プロセスに書き込み権限があることを確認してください。 |
| **Currency symbol not showing** | ロケールに対して記号位置が誤って設定されている。 | 金額の前に記号を表示したい場合は `CurrencySymbolPositionType.Before` を使用してください。 |
| **Project file does not open in MS Project** | 古い形式で保存され、互換性のない設定が含まれている。 | 最新の MS Project と完全互換にするため、`SaveFileFormat.MPP` で保存してください。 |

## Frequently Asked Questions

**Q: Aspose.Tasks で単一プロジェクトに複数通貨を設定できますか？**  
A: はい、リソースまたはタスク単位で通貨プロパティを設定することで、1 つのプロジェクト内で複数通貨を扱えます。

**Q: Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルに対応していますか？**  
A: 完全に対応しています。Project 2000 から最新バージョンまでの MPP ファイルはもちろん、XML など他形式もサポートしています。

**Q: カスタム通貨フォーマットはサポートされていますか？**  
A: はい、記号、少数桁数、位置を自由に定義でき、地域固有の要件に合わせられます。

**Q: Aspose.Tasks を他の Java ライブラリやフレームワークと統合できますか？**  
A: もちろんです。純粋な Java API なので、Spring、Hibernate、Maven、Gradle などとシームレスに連携できます。

**Q: Aspose.Tasks の追加サポートや支援はどこで受けられますか？**  
A: コミュニティ支援は [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) で、詳細な API リファレンスは公式ドキュメントをご参照ください。

## Conclusion
これで **通貨を設定する方法**、**通貨値を変更する方法**、そして **Java スタイルで通貨記号を変更する方法** を Aspose.Tasks for Java を使ってマスターしました。これらの機能により、グローバルチーム向けにコストデータを調整し、ロケール固有のレポートを生成し、国境を越えてプロジェクトファイルの一貫性を保つことができます。

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}