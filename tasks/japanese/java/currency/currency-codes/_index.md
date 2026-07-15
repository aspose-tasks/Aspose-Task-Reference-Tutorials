---
date: 2026-02-10
description: Aspose.Tasks for Java を使用して MS Project ファイルから通貨コードを取得する方法を学びましょう – Java
  開発者が必要とする通貨コードをすばやく取得できます。
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して MS Project から通貨を取得する方法
url: /ja/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用して MS Project から通貨を取得する方法

## はじめに
ようこそ！このチュートリアルでは、Aspose.Tasks Java API を使用して MS Project ファイルから **通貨コードを取得する方法** を学びます。マルチ通貨の財務レポートを作成したり、異なる地域のプロジェクトを統合したり、下流処理のために正しい通貨記号が必要な場合でも、本ガイドは環境設定からプログラムで通貨コードを抽出するまでのすべての手順を案内します。最後まで読めば、MS Project ファイルの読み取りに慣れ、**get currency code java** 呼び出しを使用して ISO 通貨識別子を取得できるようになります。

## クイック回答
- **API は何をしますか？** MS Project ファイルを読み取り、通貨コードなどのプロパティを公開します。  
- **使用言語は何ですか？** Java、Aspose.Tasks for Java ライブラリを使用します。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **1 行でコードを取得できますか？** はい、`prj.get(Prj.CURRENCY_CODE)` が通貨コード文字列を返します。  
- **すべての Project バージョンと互換性がありますか？** Aspose.Tasks は古い MPP 形式と新しい XML、XER 形式の両方をサポートします。

## **read ms project file** とは何ですか？
MS Project ファイルを読むことは、プログラムで *.mpp*（または他のサポート形式）プロジェクトドキュメントを開き、タスク、リソース、カレンダー、財務設定などのデータ構造にアクセスすることを意味し、Microsoft Project を手動で操作する必要はありません。

## Aspose.Tasks を使用して **read msproject** ファイルを読む理由は？
- **フルフォーマットサポート** – Project 98 から最新の Office リリースまでのファイルで動作します。  
- **COM や Office のインストール不要** – 純粋な Java で、サーバーサイドの自動化に最適です。  
- **リッチな API** – `Prj.CURRENCY_CODE` などのプロパティに直接アクセスでき、**how to retrieve currency** 情報を即座に取得できます。  
- **パフォーマンス** – 軽量なパースで、多数のプロジェクトをバッチ処理するのに最適です。

## 前提条件
コードに入る前に、以下が揃っていることを確認してください：

### Java Development Kit (JDK) がインストール済み
最近の JDK がマシンにインストールされていることを確認してください。最新の JDK バージョンは [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) からダウンロードしてインストールできます。

### Aspose.Tasks for Java ライブラリ
Aspose.Tasks for Java ライブラリをダウンロードして設定してください。詳細なドキュメントと最新のバイナリは [here](https://reference.aspose.com/tasks/java/) で入手できます。

## パッケージのインポート
まずは、Java プロジェクトで必要なパッケージをインポートしましょう：

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## ステップバイステップガイド

### 手順 1: データディレクトリの設定
*.mpp* ファイルが格納されているフォルダーを定義します。環境に合わせてパスを調整してください。

```java
String dataDir = "Your Data Directory";
```

### 手順 2: プロジェクトファイルのロード
`Project` インスタンスを作成し、MS Project ファイルをロードします。ここで **read msproject** データがメモリに読み込まれます。

```java
Project prj = new Project(dataDir + "project.mpp");
```

### 手順 3: 通貨コードの取得
プロジェクトがロードされたので、単一の呼び出しで **how to retrieve currency** 情報を取得できます。これは **get currency code java** の使用例です。

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
出力は、プロジェクトで設定されている 3 文字の ISO 通貨コード（例: `USD`、`EUR`、`GBP`）になります。

### 手順 4: Java で通貨コードを取得する方法（追加情報）
後で使用するために値を保存したい場合は、単に変数に代入してください：

*追加のコードブロックは不要です* – `prj.get(Prj.CURRENCY_CODE)` が返す文字列を保持し、任意の金融サービス、レポートエンジン、UI コンポーネントに渡すだけです。

### 手順 5: （オプション）通貨コードの使用
取得したコードを他の場所で使用したい場合があります。たとえば、カスタムレポートでコスト値をフォーマットしたり、金融 API に渡したりします。典型的なシナリオは次のとおりです：

- **レポート生成** – コスト列の前にコードを付加します（`USD 1,200`）。  
- **API 統合** – 通貨識別子が必要な決済ゲートウェイに ISO コードを送信します。  
- **データ統合** – ポートフォリオ分析のために、通貨別に複数のプロジェクトをグループ化します。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|-------|--------|-----|
| **Null output** | プロジェクトファイルで通貨が定義されていません（デフォルトは空）。 | Microsoft Project で通貨を設定するか、読み込む前に `prj.set(Prj.CURRENCY_CODE, "USD");` で設定してください。 |
| **File not found** | `dataDir` パスが正しくありません。 | パスを確認し、ファイル名が正確に一致していること（大文字小文字も含む）を確認してください。 |
| **Unsupported file version** | 非常に古いまたは破損した *.mpp* ファイルです。 | 最新の Aspose.Tasks バージョンを使用するか、まず Microsoft Project でファイルを新しい形式に変換してください。 |

## よくある質問

**Q: Aspose.Tasks は複雑なプロジェクト構造を扱えますか？**  
A: はい、API はマルチレベルのタスク階層、リソースプール、カスタムフィールドを問題なく読み取り・操作できます。

**Q: Aspose.Tasks はさまざまなバージョンの MS Project ファイルと互換性がありますか？**  
A: もちろんです。MPP、XML、XER など、さまざまな Microsoft Project リリースのフォーマットをサポートしています。

**Q: Aspose.Tasks はドキュメントやサポートを提供していますか？**  
A: 詳細なドキュメント、コード例、専用サポートが Aspose のウェブサイトで利用可能です。

**Q: 購入前に Aspose.Tasks を試すことはできますか？**  
A: 無料トライアルが提供されており、通貨コードの読み取りを含むすべての機能を評価できます。

**Q: Aspose.Tasks の一時ライセンスはどこで取得できますか？**  
A: 短期評価用の一時ライセンスは [website](https://purchase.aspose.com/temporary-license/) から取得できます。

**最終更新日:** 2026-02-10  
**テスト環境:** Aspose.Tasks for Java（最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}