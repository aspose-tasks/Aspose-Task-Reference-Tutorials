---
title: Aspose.Tasks でリソースのタイムスケール データを読み取る
linktitle: Aspose.Tasks でリソースのタイムスケール データを読み取る
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して MS Project リソースからタイムスケール データを抽出する方法を学びます。ステップバイステップのチュートリアル。
type: docs
weight: 15
url: /ja/java/resource-management/read-timephased-data/
---
## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project リソースのタイムスケール データを読み取るプロセスを説明します。このライブラリは、Microsoft Project ファイルをプログラムで管理するための強力な機能を提供します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。からダウンロードできます。[Webサイト](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)インストール手順に従ってください。
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリを次の場所からダウンロードします。[ダウンロードページ](https://releases.aspose.com/tasks/java/)ドキュメントに記載されているインストール手順に従ってください。

## パッケージのインポート
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## ステップ 1: データ ディレクトリを設定する
まず、MS Project ファイルが配置されるディレクトリを定義します。
```java
String dataDir = "Your Data Directory";
```
## ステップ 2: MS プロジェクト テンプレート ファイルを読み取る
MS Project テンプレート ファイルの名前を指定します。
```java
String fileName = "ResourceTimephasedData.mpp";
```
## ステップ 3: 入力ファイルをプロジェクトとして読み取る
Aspose.Tasks を使用して入力ファイルを読み取り、Project オブジェクトとして読み込みます。
```java
Project project = new Project(dataDir + fileName);
```
## ステップ 4: ID でリソースを取得する
一意の識別子 (ID) を使用して、プロジェクトから目的のリソースを取得します。
```java
Resource resource = project.getResources().getByUid(1);
```
## ステップ 5: リソース作業のタイムスケール データを印刷する
リソース作業のタイムスケール データを出力します。
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## ステップ 6: リソース コストのタイムスケール データを出力する
リソース コストのタイムスケール データを出力します。
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project リソースのタイムスケール データを読み取る方法を学習しました。これらの手順に従うことで、プログラムによってプロジェクト ファイルから貴重な情報を効率的に抽出できます。
## よくある質問
### Aspose.Tasks は Microsoft Project 以外の他の種類のプロジェクト ファイルを処理できますか?
はい、Aspose.Tasks は、MPP、XML、CSV などのさまざまなファイル形式をサポートしています。
### Aspose.Tasks はさまざまな Java 開発環境と互換性がありますか?
はい、Aspose.Tasks はすべての主要な Java IDE およびフレームワークと互換性があります。
### Aspose.Tasks を使用してプロジェクト データを操作できますか?
確かに、Aspose.Tasks は、プロジェクト データを作成、変更、分析するための広範な API を提供します。
### Aspose.Tasks はエンタープライズレベルのプロジェクトに適していますか?
はい。Aspose.Tasks は、その信頼性と拡張性によりエンタープライズ環境で広く使用されています。
### Aspose.Tasks の使用中に問題が発生した場合、どこでサポートを見つけられますか?
訪問できます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティとサポートチームからの支援が必要です。