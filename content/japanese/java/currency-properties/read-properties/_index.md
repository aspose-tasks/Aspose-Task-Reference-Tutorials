---
title: Aspose.Tasks プロジェクトの通貨プロパティの読み取り
linktitle: Aspose.Tasks プロジェクトの通貨プロパティの読み取り
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して MS Project ファイルから通貨情報を抽出する方法を学びます。ステップバイステップのガイドが提供されます。
type: docs
weight: 10
url: /ja/java/currency-properties/read-properties/
---
## 導入
このチュートリアルでは、Aspose.Tasks for Java を利用して Microsoft Project ファイルから通貨プロパティを読み取る方法を学びます。 Aspose.Tasks は、開発者が Microsoft Project をインストールしなくても Microsoft Project ドキュメントを操作できるようにする強力な Java API です。以下に概説する手順に従うことで、通貨関連の情報を簡単に抽出できるようになります。
## 前提条件
このチュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。
2.  Aspose.Tasks for Java JAR: Aspose.Tasks for Java ライブラリを次からダウンロードします。[ここ](https://releases.aspose.com/tasks/java/)それを Java プロジェクトに含めます。
## パッケージのインポート
まず、必要なパッケージを Java クラスにインポートします。
```java
import com.aspose.tasks.*;
```
## ステップ 1: プロジェクト ディレクトリを設定する
まず、Microsoft Project ファイルが配置されるプロジェクト ディレクトリを設定します。このディレクトリ パスは次のように定義できます。
```java
String dataDir = "Your Data Directory";
```
交換する`"Your Data Directory"`プロジェクト ディレクトリへの実際のパスを置き換えます。
## ステップ 2: プロジェクト リーダー インスタンスを作成する
インスタンス化する`Project`Microsoft Project ファイルへのパスを指定してオブジェクトを作成します。
```java
Project project = new Project(dataDir + "project.mpp");
```
必ず交換してください`"project.mpp"` MS Project ファイルの名前に置き換えます。
## ステップ 3: 通貨プロパティの表示
プロジェクト ファイルから通貨プロパティを取得して表示します。
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
このコード セグメントは、通貨コード、数字、記号、記号の位置などの情報を MS Project ファイルから取得し、コンソールに出力します。
## ステップ 4: プロセスの完了
最後に、プロセスが正常に完了したことを示すメッセージを出力します。
```java
System.out.println("Process completed Successfully");
```
## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project ファイルから通貨プロパティを読み取る方法を検討しました。概要を示した手順に従うことで、プロジェクト ファイルから通貨関連の情報をプログラムで簡単に抽出でき、Java アプリケーションへのシームレスな統合が可能になります。
## よくある質問
### Q: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか?
A: Aspose.Tasks は、MS Project 2003-2021 によって生成された MPP ファイルを含む、さまざまなバージョンの Microsoft Project をサポートしています。
### Q: Aspose.Tasks を使用して通貨プロパティを変更できますか?
A: はい、Aspose.Tasks を使用すると、MS Project ファイル内の通貨プロパティをプログラムで読み取り、変更することができます。
### Q: Aspose.Tasks は商用利用に適していますか?
 A: はい、Aspose.Tasks はプロ向けに設計された商用ライブラリです。ライセンスを購入できます[ここ](https://purchase.aspose.com/buy).
### Q: Aspose.Tasks には無料トライアルが提供されていますか?
 A: はい、Aspose.Tasks の無料トライアルを利用できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks に関するヘルプやサポートはどこに問い合わせればよいですか?
 A: Aspose.Tasks フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tasks/15)サポートやご質問がございましたら。