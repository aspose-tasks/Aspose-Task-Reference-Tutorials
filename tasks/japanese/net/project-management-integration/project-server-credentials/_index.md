---
title: Aspose.Tasks での MS Project Server 資格情報の管理
linktitle: Aspose.Tasks での Project Server 資格情報の管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project Server の資格情報をシームレスに管理する方法を学びます。プロジェクト管理の効率を高めます。
weight: 22
url: /ja/net/project-management-integration/project-server-credentials/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での MS Project Server 資格情報の管理

## 導入
プロジェクト管理の分野では、効果的な調整とシームレスなコミュニケーションがプロジェクトを成功させるために極めて重要です。 Aspose.Tasks for .NET は、Microsoft Project Server の資格情報を管理するための包括的なソリューションを提供し、ユーザーがプロジェクト データに安全にアクセスして操作できるようにします。このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project Server の資格情報を管理するプロセスを詳しく説明し、ユーザーがスムーズに操作できるように各ステップをガイドします。
## 前提条件
Aspose.Tasks for .NET を使用して MS Project Server 資格情報を管理する作業を開始する前に、次の前提条件が満たされていることを確認してください。
### 1. Aspose.Tasks for .NET のインストール
まず、提供されているから Aspose.Tasks for .NET をダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/)。インストール手順に従って、ライブラリを .NET 環境にシームレスに統合します。
### 2. アクセス認証情報
MS Project Server へのアクセスに必要な資格情報を収集します。これには、Project Server に関連付けられた SharePoint ドメイン アドレス、ユーザー名、パスワードが含まれます。

## 名前空間のインポート
.NET プロジェクトで、Aspose.Tasks for .NET が提供する機能を効率的に利用するために必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## ステップ 1: ドキュメント ディレクトリ パスを定義する
```csharp
String DataDir = "Your Document Directory";
```
## ステップ 2: SharePoint ドメイン アドレス、ユーザー名、およびパスワードを設定する
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## ステップ 3: Project Server 資格情報を作成する
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## ステップ 4: プロジェクト ファイルをロードする
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## 手順 5: Project Server Manager を初期化する
```csharp
var manager = new ProjectServerManager(credentials);
```
## ステップ 6: 新しいプロジェクトを作成する
```csharp
manager.CreateNewProject(newProject);
```
## ステップ 7: プロジェクト リストの取得
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## ステップ 8: プロジェクト リストを反復処理する
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## 結論
MS Project Server の資格情報を効果的に管理することは、プロジェクト管理を合理化するために最も重要です。 Aspose.Tasks for .NET は、堅牢な機能セットを提供することでこのプロセスを簡素化します。このチュートリアルで概説されているステップバイステップのガイドに従うことで、ユーザーは Aspose.Tasks for .NET をプロジェクトにシームレスに統合し、プロジェクト データへの安全なアクセスと操作を確保できます。
## よくある質問
### Q: Aspose.Tasks for .NET は、Microsoft Project Server のすべてのバージョンと互換性がありますか?
A: Aspose.Tasks for .NET は、さまざまなバージョンの Microsoft Project Server と互換性があるように設計されており、ユーザーの多用途性と柔軟性を保証します。
### Q: Aspose.Tasks for .NET を既存の .NET プロジェクトに統合できますか?
A: はい、Aspose.Tasks for .NET は既存の .NET プロジェクトにシームレスに統合でき、効率的なプロジェクト管理機能を促進します。
### Q: Aspose.Tasks for .NET はプロジェクト リソースへのアクセスをサポートしていますか?
A: もちろん、Aspose.Tasks for .NET は、プロジェクト リソースへのアクセスと操作に対する包括的なサポートを提供し、プロジェクト管理の効率を高めます。
### Q: Aspose.Tasks for .NET で利用できるライセンス オプションはありますか?
A: はい、Aspose.Tasks for .NET は、試用目的の一時ライセンスや商用利用の完全ライセンスなど、柔軟なライセンス オプションを提供しています。
### Q: Aspose.Tasks for .NET に関するサポートやサポートはどこに問い合わせればよいですか?
 A: Aspose.Tasks for .NET に関する問い合わせやサポートが必要な場合は、次のサポート フォーラムにアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).## 完全なソース コード
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
