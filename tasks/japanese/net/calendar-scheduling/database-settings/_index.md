---
title: Aspose.Tasks のデータベース設定
linktitle: Aspose.Tasks のデータベース設定
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Primavera データベースからプロジェクトをインポートする方法を学びます。この包括的なチュートリアルで段階的なガイダンスを取得してください。
weight: 29
url: /ja/net/calendar-scheduling/database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のデータベース設定

## 導入

Aspose.Tasks for .NET は、開発者が .NET アプリケーションで Microsoft Project ファイルを操作できるようにする強力なライブラリです。このチュートリアルでは、Aspose.Tasks を使用して Primavera データベースからプロジェクトをインポートすることに焦点を当てます。

## 前提条件

始める前に、以下のものがあることを確認してください。

- C# プログラミング言語の基本的な知識。
- Visual Studio がシステムにインストールされている。
-  Aspose.Tasks for .NET ライブラリがインストールされています。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
- Primavera データベースへのアクセスと、必要な権限。

## 名前空間のインポート

まず、必要な名前空間を C# プロジェクトにインポートする必要があります。これらの名前空間は、Aspose.Tasks for .NET を操作するために必要なクラスとメソッドへのアクセスを提供します。

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

ここで、提供されたサンプル コードを複数のステップに分割してみましょう。

## ステップ 1: 接続文字列を定義する

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

このステップでは、Primavera データベースに接続するための接続文字列を定義します。必ず交換してください`DataDir`データベースファイルが置かれているディレクトリに置き換えます。

## ステップ 2: データベース設定の作成

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

ここでは、次のインスタンスを作成します。`PrimaveraDbSettings`クラスに接続し、接続文字列とプロジェクト ID をパラメーターとして渡します。要件に応じてプロジェクト ID を調整します。

## ステップ 3: プロバイダーの不変名を設定する

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

プロバイダーの不変名を指定します。この例では SQLite を使用していますが、データベース プロバイダーに基づいて変更できます。

## ステップ 4: プロジェクトをロードする

```csharp
var project = new Project(settings);
```

新しいを作成します`Project`オブジェクトを作成し、データベース設定をパラメータとして渡します。

## ステップ 5: プロジェクトを保存する

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

最後に、指定したファイル形式でプロジェクトを目的の場所に保存します。

## 結論

このチュートリアルでは、Aspose.Tasks for .NET を使用して Primavera データベースからプロジェクトをインポートする方法を学びました。提供された手順に従うことで、プロジェクトのインポート機能を .NET アプリケーションにシームレスに統合できます。

## よくある質問

### Q1: Aspose.Tasks for .NET を使用して、さまざまなデータベース プロバイダーからプロジェクトをインポートできますか?

A1: はい、接続文字列とプロバイダーの不変名を適宜調整することで、さまざまなデータベース プロバイダーからプロジェクトをインポートできます。

### Q2: Aspose.Tasks for .NET に利用できる無料トライアルはありますか?

 A2: はい、Aspose.Tasks for .NET の無料トライアルを次のサイトから入手できます。[ここ](https://releases.aspose.com/).

### Q3: Aspose.Tasks for .NET のドキュメントはどこで見つけられますか?

 A3: ドキュメントは見つかります。[ここ](https://reference.aspose.com/tasks/net/).

### Q4: Aspose.Tasks for .NET のサポートを受けるにはどうすればよいですか?

 A4: Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).

### Q5: Aspose.Tasks for .NET を使用するには一時ライセンスが必要ですか?

 A5: ライブラリの全機能を評価したい場合は、次のサイトから一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
