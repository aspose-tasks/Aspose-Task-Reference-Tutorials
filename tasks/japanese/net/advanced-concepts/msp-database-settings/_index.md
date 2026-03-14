---
date: 2026-03-14
description: Aspose.Tasks を使用して Microsoft Project データベースのデータベース スキーマを指定する方法と、プロジェクト
  データを .NET アプリケーションにインポートする方法を学びましょう。
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks を使用した Project DB のデータベーススキーマを指定する
url: /ja/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks における Microsoft Project データベースの設定

## はじめに

.NET アプリケーションで Aspose.Tasks を使用して Microsoft Project データベースを扱う場合、**データベース スキーマを指定**し、**プロジェクト データをシームレスにインポート**するための必要な設定を構成する必要があります。このチュートリアルでは、接続詳細の**設定方法**、**.NET 接続文字列の作成**、そして最終的に**MPP としてプロジェクトを保存**する手順をステップ バイ ステップで解説します。

## クイック アンサー
- **主な目的は何ですか？** データベース スキーマを指定し、Project データベースを .NET アプリにインポートすることです。  
- **必要なライブラリは？** Aspose.Tasks for .NET。  
- **Project Server への接続方法は？** 正しい SQL 接続文字列を作成し、`MspDbSettings` を使用します。  
- **生成されるファイル形式は？** `SaveFileFormat.Mpp` で保存された MPP ファイル。  
- **スキーマ名は変更できますか？** はい、`MspDbSettings` の `Schema` プロパティで設定できます。

## Project DB のデータベース スキーマを指定する方法

多くのエンタープライズ環境では、Project Server データベースがカスタム スキーマ（例: `dbo`、`psdata`）の下に配置されています。スキーマを明示的に設定することで、Aspose.Tasks が正しいテーブルを参照でき、実行時エラーを防ぎ、正確なデータ インポートが保証されます。

## 前提条件

開始する前に、以下を用意してください。

1. Aspose.Tasks for .NET: [こちら](https://releases.aspose.com/tasks/net/) から Aspose.Tasks ライブラリをダウンロードしてインストールします。  
2. Microsoft Project データベースへのアクセス権: インポート元となる Microsoft Project データベースへのアクセスが必要です。  

## 名前空間のインポート

まず、プロジェクトに必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 手順 1: 接続文字列の作成

Microsoft Project データベースへの接続文字列を構築します。ここで **.NET 接続文字列を作成**し、**Project Server への接続方法**も定義します。

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **プロのコツ:** `DataSource` と `InitialCatalog` の値を必ず確認してください。サーバーのアドレスと公開されているデータベース名と一致している必要があります。

## 手順 2: MspDbSettings の構成

`MspDbSettings` のインスタンスを作成し、接続文字列を渡したうえで `Schema` プロパティを設定して **データベース スキーマを指定**します。これにより Aspose.Tasks がどのスキーマをクエリするかが決まります。

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

ここでは、読み込む対象プロジェクトを特定するプロジェクト GUID も提供しています。

## 手順 3: プロジェクト データの読み込み

設定済みの `MspDbSettings` を使用して `Project` オブジェクトをインスタンス化します。このステップで **データベースからプロジェクトをインポート**する処理が実行され、.NET オブジェクトにデータが格納されます。

```csharp
var project = new Project(settings);
```

## 手順 4: プロジェクト データの保存

最後に、読み込んだプロジェクトをディスク上の MPP ファイルとして永続化します。これにより **MPP としてプロジェクトを保存**する Aspose.Tasks API の使用例が示されます。

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

コードを実行すると、`ImportProjectDataFromDatabase_out.mpp` ファイルが出力ディレクトリに作成され、Microsoft Project で開くことができます。

## 結論

本チュートリアルでは、Microsoft Project データベースの **データベース スキーマを指定**し、**接続を構成**し、**プロジェクト データをインポート**し、**MPP として保存**する手順を Aspose.Tasks for .NET を用いて学びました。これらの手順により、Project Server のデータをカスタム アプリケーションにシームレスに統合でき、堅牢なプロジェクト管理ソリューションの構築が可能になります。

## よくある質問

### Q1: 異なるバージョンの Microsoft Project データベースでも Aspose.Tasks を使用できますか？
A1: はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project データベースをサポートしており、統合の柔軟性を提供します。

### Q2: データベース接続の問題をトラブルシューティングするには？
A2: 接続文字列が正しい資格情報とデータベース情報で構成されていることを確認してください。また、[Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) のドキュメントやサポートも参照できます。

### Q3: Aspose.Tasks のトライアル版はありますか？
A3: はい、[こちら](https://releases.aspose.com/) から無料トライアル版を入手できます。

### Q4: データベース操作用のスキーマをカスタマイズできますか？
A4: はい、`MspDbSettings` オブジェクトの `Schema` プロパティでデータベース構造に合わせたスキーマを指定できます。

### Q5: Aspose.Tasks の詳細なドキュメントはどこで確認できますか？
A5: 詳細な機能解説は、包括的なドキュメント [こちら](https://reference.aspose.com/tasks/net/) をご覧ください。

**Q: この方法は Azure SQL データベースでも動作しますか？**  
A: もちろんです。`DataSource` を Azure のサーバー名に変更し、TLS/SSL 設定が有効になっていることを確認してください。

**Q: 大規模な Project データベースでタイムアウトが発生した場合は？**  
A: 接続文字列の `ConnectTimeout` 値を増やし、必要に応じてバッチ単位でプロジェクトをロードすることを検討してください。

---

**最終更新日:** 2026-03-14  
**テスト環境:** Aspose.Tasks 24.12 for .NET  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}