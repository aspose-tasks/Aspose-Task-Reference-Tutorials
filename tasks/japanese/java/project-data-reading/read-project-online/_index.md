---
title: Aspose.Tasks を使用した簡単な MS Project オンライン データ読み取り
linktitle: Aspose.Tasks でのプロジェクト オンライン データの読み取り
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して Microsoft Project Online データを簡単に読み取る方法を学びます。プロジェクト管理能力を強化します。
weight: 13
url: /ja/java/project-data-reading/read-project-online/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用した簡単な MS Project オンライン データ読み取り

## 導入
プロジェクト管理の分野では、Microsoft Project Online データを効率的に処理することは、業務を合理化するために非常に重要です。 Aspose.Tasks for Java は、そのようなデータを簡単に読み取るための堅牢なソリューションを提供します。このチュートリアルでは、Aspose.Tasks を活用して MS Project Online データにシームレスにアクセスして操作する方法について詳しく説明します。
## 前提条件
このチュートリアルに入る前に、次のものが揃っていることを確認してください。
1. Java Development Kit (JDK): Java プログラムをコンパイルして実行するには、JDK をインストールします。
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks ライブラリをダウンロードして、Java プロジェクトに組み込みます。から入手できます[ここ](https://releases.aspose.com/tasks/java/).
3. Microsoft Project Online アカウント: MS Project Online データにアクセスするための有効な資格情報を取得します。
4. SharePoint ドメイン アドレス: MS Project Online データが存在する SharePoint ドメイン アドレス。
5. ユーザー名とパスワード: MS Project Online へのアクセスを認証するための資格情報。
## パッケージのインポート
Java プロジェクトで、シームレスな統合に必要な Aspose.Tasks パッケージをインポートします。
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## ステップ 1: SharePoint ドメイン アドレス、ユーザー名、およびパスワードを設定する
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
交換する`"https://contoso.sharepoint.com"` SharePoint ドメイン アドレスを使用して、`"admin@contoso.onmicrosoft.com"`ユーザー名と`"MyPassword"`あなたのパスワードと一緒に。
## 手順 2: Project Server の資格情報を使用して認証する
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
作成する`ProjectServerCredentials`SharePoint ドメイン アドレス、ユーザー名、およびパスワードを含むオブジェクト。次に初期化します`ProjectServerManager`これらの資格情報を使用して。
## ステップ 3: プロジェクトリストを取得して情報を表示する
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
から取得したプロジェクト リストを反復処理します。`reader.getProjectList()`名前、作成日、最終保存日などのプロジェクトの詳細を表示します。
## ステップ 4: 個々のプロジェクトをロードしてリソース数を出力する
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
プロジェクトごとに、次を使用してロードします。`reader.getProject(p.getId())`プロジェクト名と関連するリソースの数を出力します。

## 結論
Aspose.Tasks for Java は、MS Project Online データを読み取るプロセスを簡素化し、開発者にプロジェクト管理タスクを合理化する強力なツールセットを提供します。このチュートリアルに従うことで、Aspose.Tasks を Java アプリケーションに効率的に統合して、プロジェクト データに簡単にアクセスして操作することができます。
## よくある質問
### Q: Aspose.Tasks for Java を使用して MS Project Online データを変更できますか?
A: はい、Aspose.Tasks は、MS Project Online データをプログラム的に読み取るだけでなく変更するための広範な機能を提供します。
### Q: Aspose.Tasks は他のプロジェクト管理ファイル形式をサポートしていますか?
A: もちろん、Aspose.Tasks は MPP、XML などを含むさまざまなファイル形式をサポートしており、さまざまなプロジェクト管理システムとの互換性を確保しています。
### Q: Aspose.Tasks for Java に利用できる無料トライアルはありますか?
 A: はい、次のサイトから無料トライアルを利用できます。[ここ](https://releases.aspose.com/) Aspose.Tasks の特徴と機能を探索します。
### Q: Aspose.Tasks for Java の包括的なドキュメントはどこで見つけられますか?
 A: 詳細なドキュメントを参照してください。[ここ](https://reference.aspose.com/tasks/java/)Java プロジェクトで Aspose.Tasks を利用するための包括的なガイダンスを参照してください。
### Q: Aspose.Tasks for Java ではどのようなサポート オプションが利用できますか?
 A: 問題が発生した場合、または質問がある場合は、Aspose.Tasks コミュニティ フォーラムから支援を求めることができます。[ここ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
