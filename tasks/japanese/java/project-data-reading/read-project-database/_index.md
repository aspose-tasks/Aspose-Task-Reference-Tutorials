---
date: 2026-10-31
description: Aspose.Tasks for Java を使用してプロジェクトを PDF として保存し、Microsoft Project データベースを読み取る方法を学びます。また、Project
  Server への接続、プロジェクトの HTML への変換、XML へのエクスポートも解説します。
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Aspose.Tasks における Microsoft Project データベースからのプロジェクト データの読み取り
og_description: Aspose.Tasks for Java を使用してプロジェクトを PDF として保存し、Microsoft Project データベースを読み取ります。Project
  Server への接続方法や、HTML、XML、CSV へのエクスポート方法を学びます。
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Aspose.Tasks for Java を使用してプロジェクトを PDF として保存し、Microsoft Project データベースを読み取る
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Aspose.Tasks for Java を使用してプロジェクトを PDF として保存し、Microsoft Project データベースを読み取る
url: /ja/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用してプロジェクトを PDF として保存し、Microsoft Project データベースを読み取る

## 概要
このチュートリアルでは、Microsoft Project Server から **Microsoft Project データベースを直接読み取り**、そして Aspose.Tasks Java API を使用して **プロジェクトを PDF として保存** する方法を紹介します。印刷可能なレポートの生成、レガシーデータの移行、またはカスタムポータルへのプロジェクト情報埋め込みが必要な場合でも、本ガイドは JDBC 接続の設定から PDF、XML、HTML へのエクスポートまで、すべての手順を案内します。最後まで実施すれば、Microsoft Project をインストールせずに任意の Java サーバー上で動作する本番環境向けソリューションが手に入ります。

## クイック回答
- **Aspose.Tasks は何をしますか？** Microsoft Project ファイルとデータベースを読み取り、書き込み、操作するための純粋な Java API を提供します。  
- **Microsoft Project をインストールする必要がありますか？** いいえ、Aspose.Tasks は Microsoft Project とは独立して動作します。  
- **サポートされているデータベースの種類は何ですか？** Microsoft SQL Server、Project Server のバックエンドです。  
- **他の形式へエクスポートできますか？** はい—PDF、XML、HTML、CSV、PNG、JPEG など多数です。  
- **主な前提条件は何ですか？** JDK 8 以降、Aspose.Tasks for Java ライブラリ、SQL Server JDBC ドライバー、そして有効な Project Server の認証情報です。

## 「Microsoft Project データベースを読み取る」とは何ですか？
Microsoft Project データベースを読み取ることは、Project Server の SQL Server リポジトリに接続し、保存されたプロジェクトデータを抽出して、Aspose.Tasks が操作できる `Project` オブジェクトにロードすることを意味します。このアプローチは、自動レポート作成、データ移行、またはカスタム分析に最適です。

## なぜ Aspose.Tasks for Java を使用するのですか？
Aspose.Tasks for Java は、デスクトップアプリケーションを必要とせずに Microsoft Project データを操作でき、任意のプラットフォームで動作する純粋な Java ソリューションを提供します。タスク、リソース、カレンダー、カスタムフィールドの包括的なオブジェクトモデルを提供し、大規模なエンタープライズプロジェクトも効率的に処理できるため、自動レポート作成、移行、統合シナリオに最適です。

- **Microsoft Project への依存なし** – 任意のサーバーや CI 環境で実行可能です。  
- **リッチなオブジェクトモデル** – タスク、リソース、割り当て、カレンダー、カスタムフィールドにプログラムからアクセスできます。  
- **複数のエクスポートオプション** – Aspose.Tasks は **20 以上のファイル形式** へのエクスポートをサポートし、PDF、XML、HTML、CSV、PNG、JPEG などを単一の API 呼び出しで出力できます。  
- **高性能** – ライブラリは **最大 10,000 タスク** を含むプロジェクトを 1 分未満で処理でき、データをストリーミングしてファイル全体をメモリに読み込むことを回避します。

## 前提条件
1. 動作する Java 開発環境 (JDK 8 以上)。  
2. Aspose.Tasks for Java ライブラリをプロジェクトのクラスパスに追加する。  
3. Project Server の SQL データベースに接続するための認証情報 (サーバー名、ポート、データベース名、ユーザー名、パスワード)。  
4. Microsoft JDBC Driver for SQL Server (例: `sqljdbc4.jar`)。

## パッケージのインポート
まず、必要なクラスをインポートします。リストには Aspose.Tasks のコアクラスと標準的な Java ユーティリティが含まれています。

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Project Server への接続方法
信頼できる接続を確立することは、プロジェクトデータを読み取るための基盤です。SQL Server インスタンスが Java ホストから到達可能であり、使用するログインに Project Server スキーマ上の **SELECT** 権限があることを確認してください。また、ネットワーク遅延を確認し、必要な SSL 設定を構成して安全な通信を確保する必要があります。

## ステップ 1: データベース接続の設定
`MspDbSettings` クラスは、Microsoft Project Server データベースにアクセスするために必要な JDBC 接続情報をカプセル化します。JDBC 接続文字列を保持する `MspDbSettings` インスタンスを作成します。プレースホルダーの値を実際のサーバー詳細に置き換えてください。

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **プロのヒント:** 接続文字列はハードコーディングせず、セキュアな設定ファイルまたは環境変数に保存してください。

## ステップ 2: JDBC ドライバーの追加
Microsoft SQL Server JDBC ドライバーを実行時にロードし、JVM がデータベースと通信できるようにします。

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **警告:** ドライバーのバージョンが SQL Server のバージョンと一致していることを確認してください。互換性のないドライバーを使用すると接続に失敗する可能性があります。

## ステップ 3: プロジェクトデータの読み取り
`Project` クラスは、メモリにロードされた Microsoft Project ファイルを表し、タスク、リソース、割り当てを公開します。`MspDbSettings` を渡して `Project` オブジェクトをインスタンス化します。Aspose.Tasks はデータベースからプロジェクトデータを自動的に取得します。

```java
Project project = new Project(settings);
```

この時点で `project` オブジェクトを調査でき、タスクやリソースの一覧表示や必要に応じたフィールドの変更が可能です。

## ステップ 4: プロジェクトを PDF として保存
`SaveFileFormat` 列挙型は `Project.save` メソッドの出力形式を定義します（PDF、XML、HTML など）。ロードしたプロジェクトを任意のファイル形式にエクスポートします。以下の例はプロジェクトを **PDF** として保存し、印刷可能なレポートに最適です。`SaveFileFormat` 列挙型を変更すれば **XML にエクスポート** または **HTML に変換** も可能です。

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

XML が好みの場合は、`SaveFileFormat.Pdf` を `SaveFileFormat.Xml` に置き換えるだけです。HTML 出力の場合は `SaveFileFormat.Html` を使用してください。

## 一般的な問題と解決策
| Issue | Typical cause | Fix |
|-------|---------------|-----|
| **接続タイムアウト** | サーバー/ポートが間違っている、またはファイアウォールがブロックしている | サーバーアドレスを確認し、ポート 1433 を開放し、シンプルな JDBC テストプログラムで接続をテストしてください。 |
| **認証エラー** | ユーザー名/パスワードが無効、または SQL Server が SQL 認証用に設定されていない | 有効な SQL ログインを使用するか、サーバーで混合モード認証を有効にしてください。 |
| **ドライバーが見つからない** | JDBC jar がクラスパスにない | `addJDBCDriver` が正しい `.jar` ファイルを指していること、パスが二重バックスラッシュ (`\\`) を使用していることを確認してください。 |
| **ロード後にプロジェクトが空** | Project Server のテーブルを読む権限が不足している | ログインに Project Server データベーススキーマへの SELECT 権限を付与してください。 |

## よくある質問

**Q: Aspose.Tasks は Microsoft Project 以外のデータベースからプロジェクトデータを読み取ることができますか？**  
A: はい、Aspose.Tasks は XML ファイル、Primavera データベース、その他の標準的なプロジェクト形式からの読み取りをサポートしています。

**Q: Aspose.Tasks はさまざまなバージョンの Microsoft Project と互換性がありますか？**  
A: はい、ライブラリは Microsoft Project 2007 から最新の 2024 リリースまで対応しており、バージョン間のシームレスな統合を実現します。

**Q: 保存する前にプロジェクトデータを操作できますか？**  
A: もちろんです。リッチな API を使用して、タスク、リソース、カスタムフィールドの追加、更新、削除が可能です。

**Q: Aspose.Tasks は複数の出力形式をサポートしていますか？**  
A: はい、PDF、XML、HTML、CSV、PNG、JPEG など、合計で 20 以上の形式でプロジェクトを保存できます。

**Q: Aspose.Tasks のさらなるサポートや支援はどこで得られますか？**  
A: 追加のサポートが必要な場合は、Aspose.Tasks フォーラムをご覧になるか、ウェブサイト上のドキュメントをご参照ください。 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

## 結論
このステップバイステップガイドに従うことで、**Microsoft Project データベースを読み取り**、**プロジェクトを PDF として保存**し、Aspose.Tasks for Java を使用して他の形式へエクスポートする方法が分かります。このアプローチにより、Microsoft Project への依存がなくなり、自動レポート作成が効率化され、強力なカスタム統合への道が開かれます。

---

**最終更新日:** 2026-10-31  
**テスト環境:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**作成者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks でプロジェクトを PDF として保存する方法 – エクスポートガイド](/tasks/java/project-file-operations/save-as-pdf/)
- [プロジェクトを PDF として保存 – Aspose.Tasks for Java でタスクシートをレンダリング](/tasks/java/task-properties/render-task-sheet/)
- [プロジェクトを PDF にエクスポートし、Aspose.Tasks でタスクリストとフッター間のギャップを縮小](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}