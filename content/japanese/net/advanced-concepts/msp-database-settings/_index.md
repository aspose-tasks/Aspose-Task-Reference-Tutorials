---
title: Aspose.Tasks での Microsoft Project データベースの設定
linktitle: Aspose.Tasks での Microsoft Project データベースの設定
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks を使用して Microsoft Project データベース設定を構成し、.NET アプリケーションにシームレスに統合する方法を学びます。
type: docs
weight: 19
url: /ja/net/advanced-concepts/msp-database-settings/
---
## 導入

Aspose.Tasks を使用して .NET アプリケーションで Microsoft Project データベースを操作している場合は、プロジェクト データをシームレスにインポートするために必要な設定を構成する必要があります。このチュートリアルでは、プロセスを段階的に説明します。

## 前提条件

始める前に、以下のものがあることを確認してください。

1.  Aspose.Tasks for .NET: Aspose.Tasks ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
2. Microsoft Project データベースへのアクセス: データをインポートするには、Microsoft Project データベースにアクセスできる必要があります。

## 名前空間のインポート

まず、必要な名前空間をプロジェクトにインポートしていることを確認してください。

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## ステップ 1: 接続文字列を作成する

Microsoft Project データベースへの接続文字列を作成します。以下に例を示します。

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

プレースホルダーの値を実際のデータベースの資格情報に置き換えてください。

## ステップ 2: MspDbSettings を構成する

のインスタンスを作成します`MspDbSettings`そして、プロジェクト GUID とともに接続文字列を指定します。

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## ステップ 3: プロジェクト データをロードする

インスタンス化する`Project`構成された設定を使用してオブジェクトを作成します。

```csharp
var project = new Project(settings);
```

## ステップ 4: プロジェクト データを保存する

ロードしたプロジェクト データをファイルに保存します。

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project データベースにアクセスするための設定を構成する方法を学習しました。これらの手順に従うことで、プロジェクト データをアプリケーションにシームレスにインポートでき、効率的なプロジェクト管理が容易になります。

## よくある質問

### Q1: Aspose.Tasks をさまざまなバージョンの Microsoft Project データベースで使用できますか?

A1: はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project データベースをサポートしているため、統合が柔軟に行えます。

### Q2: データベースの接続問題をトラブルシューティングするにはどうすればよいですか?

A2: 接続文字列が適切な資格情報とデータベースの詳細で正しく構成されていることを確認してください。ドキュメントを参照したり、サポートを求めたりすることもできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).

### Q3: Aspose.Tasks の試用版はありますか?

 A3: はい、以下から無料試用版にアクセスできます。[ここ](https://releases.aspose.com/).

### Q4: データベース対話用のスキーマをカスタマイズできますか?

 A4: はい、スキーマを指定できます。`MspDbSettings`データベース構造に従ってオブジェクトを作成します。

### Q5: Aspose.Tasks の使用に関する詳細なドキュメントはどこで入手できますか?

 A5: 包括的なドキュメントを参照できます。[ここ](https://reference.aspose.com/tasks/net/) Aspose.Tasks 機能の詳細については、こちらをご覧ください。