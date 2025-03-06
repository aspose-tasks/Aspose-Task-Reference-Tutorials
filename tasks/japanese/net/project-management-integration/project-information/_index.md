---
title: Aspose.Tasks で MS プロジェクト情報を抽出する
linktitle: Aspose.Tasks でのプロジェクト情報の抽出
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project 情報を簡単に抽出する方法を学びます。包括的なチュートリアルをご覧ください。
weight: 20
url: /ja/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で MS プロジェクト情報を抽出する

## 導入
Aspose.Tasks for .NET を使用して Microsoft Project ファイルから情報を効率的に抽出したいと考えていますか?このチュートリアルでは、プロセスを段階的に説明します。ただし、実装の詳細に入る前に、必要なものがすべて揃っていることを確認してください。
## 前提条件
始める前に、以下のものがあることを確認してください。
### 1. .NET 用の Aspose.Tasks
 Aspose.Tasks for .NET ライブラリがインストールされていることを確認してください。まだダウンロードしていない場合は、からダウンロードできます。[Aspose.Tasks for .NET Web サイト](https://releases.aspose.com/tasks/net/).
### 2. SharePoint の資格情報
MS Project ファイルが保存されている SharePoint にアクセスするには、資格情報が必要です。次の情報があることを確認してください。
- SharePoint ドメイン アドレス
- ユーザー名
- パスワード
## 名前空間のインポート
前提条件を整理したら、必要な名前空間をプロジェクトにインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
ここで、MS Project 情報を抽出するプロセスを複数のステップに分けてみましょう。
## ステップ 1: 認証情報を入力する
まず、Project Server にアクセスするための SharePoint 資格情報を指定する必要があります。
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 手順 2: Project Server Manager を初期化する
次に、`ProjectServerManager`提供された認証情報を持つインスタンス。
```csharp
var reader = new ProjectServerManager(credentials);
```
## ステップ 3: プロジェクト リストの取得
これで、Project Server からプロジェクトのリストを取得できるようになりました。
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## ステップ 4: プロジェクト情報を印刷する
最後に、プロジェクトのリストを繰り返し処理し、その情報を出力します。
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## 結論
おめでとう！ Aspose.Tasks for .NET を使用して MS Project 情報を抽出する方法を学習しました。この知識があれば、この機能を .NET アプリケーションにシームレスに統合できるようになります。
## よくある質問
### Q1: Aspose.Tasks for .NET は Microsoft Project のどのバージョンでも使用できますか?
A: はい、Aspose.Tasks for .NET は、2003、2007、2010、2013、2016、2019 などのさまざまなバージョンの Microsoft Project をサポートしています。
### Q2: Aspose.Tasks for .NET は Windows プラットフォームと Linux プラットフォームの両方と互換性がありますか?
A: はい、Aspose.Tasks for .NET は Windows と Linux の両方のプラットフォームと互換性があり、さまざまな開発環境に多用途に使用できます。
### Q3: Aspose.Tasks for .NET を使用してタスクの依存関係を抽出できますか?
A: もちろんです！ Aspose.Tasks for .NET は、基本的なプロジェクト情報だけでなく、タスクの依存関係やその他の複雑な詳細情報も抽出する堅牢な機能を提供します。
### Q4: Aspose.Tasks for .NET はテクニカル サポートを提供しますか?
 A: はい、Aspose.Tasks for .NET のテクニカル サポートは、[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)、ここで質問したり、専門家に支援を求めることができます。
### Q5: Aspose.Tasks for .NET を購入する前に試すことはできますか?
 A：確かに！ Aspose.Tasks for .NET の無料トライアルは、[リリースページ](https://releases.aspose.com/)を使用すると、購入を決定する前にその機能を調べることができます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
