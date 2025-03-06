---
title: Aspose.Tasks を使用した MS Project Server の管理
linktitle: Aspose.Tasks を使用した Project Server の管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して、シームレスな MS Project Server 管理を実現します。プロジェクトのタスクを簡単に自動化します。
type: docs
weight: 23
url: /ja/net/project-management-integration/project-server-management/
---
## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用した MS Project Server の管理について詳しく説明します。 Aspose.Tasks は、開発者がプログラムで Microsoft Project ファイルを操作できるようにする強力なライブラリであり、プロジェクト データのシームレスな統合と操作を可能にします。
## 前提条件
Aspose.Tasks を使用した MS Project Server の管理に入る前に、次の前提条件が設定されていることを確認してください。
1. Microsoft Project Server: 管理者権限、または少なくともプロジェクトを作成および管理する権限を持っている Microsoft Project Server インスタンスにアクセスする必要があります。
2.  Aspose.Tasks for .NET ライブラリ: Aspose.Tasks for .NET ライブラリをダウンロードしてインストールしていることを確認してください。からダウンロードできます。[Webサイト](https://releases.aspose.com/tasks/net/).
3. 資格情報: MS Project Server インスタンスでの認証に必要な資格情報を取得します。通常、これにはユーザー名とパスワードが含まれます。
## 名前空間のインポート
開始する前に、C# コードに必要な名前空間がインポートされていることを確認してください。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## ステップ 1: 認証資格情報をセットアップする
まず、MS Project Server インスタンスに接続するための認証資格情報を設定する必要があります。これには、ドメイン アドレス、ユーザー名、パスワードが含まれます。
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## ステップ 2: プロジェクトをロードする
次に、Aspose.Tasks を使用して管理する MS Project ファイルを読み込みます。
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## ステップ 3: Project Server Manager を作成する
インスタンス化する`ProjectServerManager`以前に定義された資格情報を使用してオブジェクトを作成します。
```csharp
var manager = new ProjectServerManager(credentials);
```
## ステップ 4: 保存オプションを定義する
プロジェクトに特定の保存オプションを定義します。たとえば、操作のタイムアウトを設定できます。
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## ステップ 5: プロジェクトの作成または更新
最後に、MS Project Server 上でプロジェクトを作成または更新します。
```csharp
manager.CreateNewProject(project, options);
```
おめでとう！ Aspose.Tasks for .NET を使用して MS Project Server を正常に管理できました。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project Server をプログラムで管理する方法を検討しました。提供されている手順を使用すると、Aspose.Tasks を .NET アプリケーションにシームレスに統合して、MS Project Server 上のプロジェクト管理タスクを自動化できます。
## よくある質問
### Q: Aspose.Tasks は Microsoft Project Server のすべてのバージョンと互換性がありますか?
A: Aspose.Tasks は、さまざまなバージョンの Microsoft Project Server との統合をサポートしており、さまざまな環境間での互換性を確保しています。
### Q: Aspose.Tasks を使用してプロジェクトに対して一括操作を実行できますか?
A: はい、Aspose.Tasks を使用すると、MS Project Server 上でプロジェクトの作成、更新、削除などの一括操作を実行できます。
### Q: Aspose.Tasks はプロジェクトのスケジュール設定とリソース管理のサポートを提供しますか?
A: もちろん、Aspose.Tasks はプロジェクトのスケジューリング、リソース割り当て、タスク管理機能の包括的なサポートを提供します。
### Q: Aspose.Tasks を使用してレポート タスクを自動化することはできますか?
A: はい、Aspose.Tasks を使用すると、プロジェクト データに基づいてカスタム レポートの生成を自動化でき、効率的なプロジェクトの監視と分析が容易になります。
### Q: Aspose.Tasks を購入する前に試してみることはできますか?
 A: はい、から無料トライアルにアクセスして、Aspose.Tasks の機能を調べることができます。[Webサイト](https://purchase.aspose.com/temporary-license/).