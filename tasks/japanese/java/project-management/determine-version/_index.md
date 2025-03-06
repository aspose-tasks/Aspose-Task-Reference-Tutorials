---
title: Aspose.Tasks を使用して MS プロジェクトのバージョンを確認する
linktitle: Aspose.Tasks を使用してプロジェクトのバージョンを確認する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してプログラムで MS Project ファイルのバージョンを確認する方法を学びます。コード例を含むステップバイステップのガイド。
weight: 12
url: /ja/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用して MS プロジェクトのバージョンを確認する

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project ファイルのバージョンを確認する方法を段階的に説明します。 Aspose.Tasks は、開発者が Microsoft Project をインストールしなくても Microsoft Project ファイルを操作できるようにする強力な Java API です。
## 前提条件
始める前に、以下のものがあることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。
2.  Aspose.Tasks for Java JAR ファイル: Aspose.Tasks for Java ライブラリを次の場所からダウンロードします。[Webサイト](https://releases.aspose.com/tasks/java/)それを Java プロジェクトに追加します。
3. MS プロジェクト ファイル: テスト用の MS プロジェクト ファイル (XML 形式) を準備します。

## パッケージのインポート
コードに入る前に、必要なパッケージをインポートしましょう。
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## ステップ 1: プロジェクトをセットアップする
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Data Directory";
```
交換する`"Your Data Directory"`MS Project ファイルを含むディレクトリへのパスを置き換えます。
## ステップ 2: プロジェクトをロードする
```java
Project project = new Project(dataDir + "input.xml");
```
交換する`"input.xml"` MS Project ファイルの名前に置き換えます。
## ステップ 3: プロジェクトのバージョンを決定する
```java
//プロジェクトのバージョンプロパティを表示する
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
このコード スニペットは、MS Project ファイルのバージョンと最終保存日を取得して出力します。
## ステップ 4: 結果の表示
```java
//変換結果を表示します。
System.out.println("Process completed Successfully");
```
この行はプロセスの完了を示します。

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project ファイルのバージョンを確認する方法を学習しました。ステップバイステップのガイドに従うことで、手間をかけずに Java アプリケーションで MS Project ファイルを効率的に操作できます。

## よくある質問
### Q: Aspose.Tasks を他のプログラミング言語で使用できますか?
A: はい、Aspose.Tasks は .NET、Java、C などの複数のプログラミング言語をサポートしています。++.
### Q: Aspose.Tasks は大規模プロジェクトに適していますか?
A: 確かに、Aspose.Tasks は、あらゆる規模のプロジェクトを簡単に処理できるように設計されています。
### Q: Aspose.Tasks を使用してプロジェクト データをカスタマイズできますか?
A: はい、Aspose.Tasks を使用すると、プロジェクト データの操作、タスク、リソースの変更などを行うことができます。
### Q: Aspose.Tasks には Microsoft Project のインストールが必要ですか?
A: いいえ、Aspose.Tasks は独立して動作するため、Microsoft Project をインストールする必要はありません。
### Q: Aspose.Tasks のテクニカル サポートは利用できますか?
 A: はい、次の Aspose.Tasks フォーラムから技術サポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
