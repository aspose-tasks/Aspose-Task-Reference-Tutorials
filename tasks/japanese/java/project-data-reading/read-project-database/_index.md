---
title: Aspose.Tasks での MS Project データベースからのプロジェクト データの読み取り
linktitle: Aspose.Tasks で Microsoft Project データベースからプロジェクト データを読み取る
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して Microsoft Project データベースからプロジェクト データを読み取る方法を学習します。コード例を含むステップバイステップのガイド。
weight: 12
url: /ja/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での MS Project データベースからのプロジェクト データの読み取り

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project データベースからプロジェクト データを読み取る方法を説明します。 Aspose.Tasks は、開発者が Microsoft Project をインストールしなくても Microsoft Project ドキュメントを操作できるようにする強力な Java API です。このガイドで概説されている手順に従うことで、データベースからプロジェクト データを効率的に抽出し、目的の形式で保存する方法を学びます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java プログラミングの基本的な知識。
2. Java Development Kit (JDK) がシステムにインストールされています。
3. Aspose.Tasks for Java ライブラリがダウンロードされ、プロジェクトに構成されます。

## パッケージのインポート
まず、必要なパッケージをインポートします。
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
## ステップ 1: データベース接続をセットアップする
まず、Microsoft Project データベースへの接続を設定する必要があります。これには、データベース URL、サーバー名、ポート番号、データベース名、ユーザー名、およびパスワードの指定が含まれます。
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## ステップ 2: JDBC ドライバーを追加する
次に、JDBC ドライバーをプロジェクトに追加する必要があります。このドライバーは、Java アプリケーションと Microsoft SQL Server データベース間の通信を容易にします。
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## ステップ 3: プロジェクト データを読み取る
ここで、`Project`オブジェクトを作成し、以前に定義した設定を使用してデータベースからプロジェクト データをロードします。
```java
Project project = new Project(settings);
```
## ステップ 4: プロジェクト データを保存する
最後にプロジェクトデータを任意の形式で保存します。この例では、XML ファイルとして保存します。
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
おめでとう！ Aspose.Tasks for Java を使用して、Microsoft Project データベースからプロジェクト データを正常に読み取ることができました。

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project データベースからプロジェクト データを読み取るプロセスについて説明しました。概要を示した手順に従うことで、プロジェクト情報をシームレスに抽出し、要件に応じて操作できます。 Aspose.Tasks は Microsoft Project ドキュメントの処理を簡素化し、効率的なデータの抽出と操作を可能にします。
## よくある質問
### Q: Aspose.Tasks を使用して、Microsoft Project 以外のデータベースからプロジェクト データを読み取ることはできますか?
A: はい、Aspose.Tasks は、XML ファイル、Primavera、Microsoft Project データベースなど、さまざまなソースからのプロジェクト データの読み取りをサポートしています。
### Q: Aspose.Tasks は Microsoft Project のさまざまなバージョンと互換性がありますか?
A: はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project で動作するように設計されており、互換性とシームレスな統合が保証されています。
### Q: プロジェクト データを保存する前に操作できますか?
A: もちろん、Aspose.Tasks は、タスクの追加、リソースの更新、プロジェクト プロパティの設定など、プロジェクト データを操作するための幅広い機能を提供します。
### Q: Aspose.Tasks は複数の出力形式をサポートしていますか?
A: はい、Aspose.Tasks は、XML、PDF、HTML、PNG や JPEG などの画像形式など、さまざまな出力形式をサポートしています。
### Q: Aspose.Tasks に関するさらなるサポートや支援はどこで入手できますか?
 A: 追加のサポートや支援が必要な場合は、Aspose.Tasks フォーラムにアクセスするか、Web サイトで入手可能なドキュメントを参照してください。[ここ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
