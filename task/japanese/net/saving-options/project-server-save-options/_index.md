---
title: Aspose.Tasks のサーバー保存 MS プロジェクト オプション
linktitle: Project Server の Aspose.Tasks の保存オプション
second_title: Aspose.Tasks .NET API
description: Project Server 統合を使用して、Aspose.Tasks の Microsoft Project オプションを保存する方法を学習します。プロジェクト管理ワークフローを強化します。
type: docs
weight: 16
url: /ja/net/saving-options/project-server-save-options/
---
## 導入
このチュートリアルでは、Project Server を使用して Aspose.Tasks の Microsoft Project オプションを保存する方法について詳しく説明します。 Aspose.Tasks は、開発者がプログラムで Microsoft Project ファイルを操作できるようにする強力な .NET API です。 Project Server の機能を活用することで、Aspose.Tasks をプロジェクト管理ワークフローにシームレスに統合できます。このチュートリアルでは、プロセスを段階的に説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET を次の場所からインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/).
   
2. Project Server へのアクセス: アクセス資格情報と Project Server インスタンスの URL が必要です。お持ちでない場合は、以下から無料トライアル版を入手できます。[ここ](https://releases.aspose.com/).
3. Microsoft Project ファイル: Aspose.Tasks を使用して、保存する Microsoft Project ファイル (.mpp) を準備します。

## 名前空間のインポート
まず、必要な名前空間をプロジェクトにインポートする必要があります。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## ステップ 1: プロジェクトと資格情報を初期化する
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
必ず交換してください`"Your Document Directory"`, `URL`, `Domain`, `UserName`、 そして`Password`実際の価値観に合わせて。
## ステップ 2: Project Server Manager を作成する
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## ステップ 3: 保存オプションを定義する
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
を調整します。`ProjectGuid`, `ProjectName`, `Timeout`、 そして`PollingInterval`あなたの要件に従って。
## ステップ 4: プロジェクトをサーバーに保存する
```csharp
manager.CreateNewProject(project, options);
```
これにより、指定されたオプションを使用してプロジェクトが Project Server に保存されます。

## 結論
このチュートリアルでは、Project Server 統合を使用して Aspose.Tasks の Microsoft Project オプションを保存する方法を学習しました。これらの手順に従うことで、Aspose.Tasks をプロジェクト管理ワークフローにシームレスに組み込むことができ、効率と生産性が向上します。
## よくある質問
### Q: Aspose.Tasks をさまざまなバージョンの Microsoft Project で使用できますか?
A: はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project をサポートしており、さまざまな環境間での互換性を確保しています。
### Q: Aspose.Tasks の試用版はありますか?
 A: はい、Aspose.Tasks の無料試用版を次のサイトから入手できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks はマルチスレッドをサポートしていますか?
A: はい、Aspose.Tasks はスレッドセーフになるように設計されており、プロジェクト データへの同時アクセスが可能です。
### Q: Project Server 統合を使用する場合、保存オプションをカスタマイズできますか?
A: はい、要件に合わせて、プロジェクト名、タイムアウト、ポーリング間隔などの保存オプションを調整できます。
### Q: Aspose.Tasks のサポートはどこで見つけられますか?
 A: 次のサイトでサポートと支援を見つけることができます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).