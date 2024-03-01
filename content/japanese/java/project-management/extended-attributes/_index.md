---
title: Aspose.Tasks プロジェクトの拡張属性を処理する
linktitle: Aspose.Tasks プロジェクトの拡張属性を処理する
second_title: Aspose.Tasks Java API
description: Java を使用して Aspose.Tasks プロジェクトの拡張属性を効率的に処理する方法を学びます。効果的なプロジェクト管理のためのステップバイステップのガイド。
type: docs
weight: 13
url: /ja/java/project-management/extended-attributes/
---
## 導入
プロジェクト管理における拡張属性の管理は、プロジェクト データをカスタマイズおよび強化するために重要です。 Aspose.Tasks for Java は、MS Project ファイルの拡張属性を効率的に処理するための強力なツールを提供します。このチュートリアルでは、プロセスを段階的にガイドし、各概念を完全に理解できるようにします。
## 前提条件
このチュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
1. Java プログラミングの基本的な知識。
2. JDK (Java Development Kit) がシステムにインストールされていること。
3. Aspose.Tasks for Java ライブラリがダウンロードされ、Java プロジェクトにセットアップされます。
## パッケージのインポート
まず、開始するために必要なパッケージをインポートしましょう。
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## ステップ 1: データ ディレクトリを定義する
```java
String dataDir = "Your Data Directory";
```
必ず交換してください`"Your Data Directory"`プロジェクトのデータ ディレクトリへのパスを置き換えます。
## ステップ 2: プロジェクト ファイルをロードする
```java
Project prj = new Project(dataDir + "project5.mpp");
```
この行は、という名前のプロジェクト ファイルをロードします。`"project5.mpp"`.
## ステップ 3: 拡張属性定義にアクセスする
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
ここでは、プロジェクトから拡張属性定義のコレクションを取得します。
## ステップ 4: 拡張属性定義を作成する
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
このコード セグメントは、カスタム フィールド タイプを次のように指定して、タスクの拡張属性定義を作成します。`Start`属性名は次のようになります`"Start 7"`.
## ステップ 5: プロジェクトに定義を追加する
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
新しく作成した拡張属性定義をプロジェクトと属性定義のコレクションの両方に追加します。
## ステップ 6: タスクと拡張属性にアクセスする
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
ここでは、プロジェクトとそれに関連付けられた拡張属性からタスクを取得します。
## ステップ 7: 拡張属性インスタンスの作成
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
このステップでは、以前に定義された属性定義に基づいて拡張属性のインスタンスを作成します。
## ステップ 8: 属性値を設定する
```java
Date date = new Date();
ea.setDateValue(date);
```
拡張属性の値、この場合は日付値を設定します。
## ステップ 9: タスクに属性を追加する
```java
eas.add(ea);
```
最後に、タスクに拡張属性を追加します。
## ステップ 10: プロジェクトを保存する
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
この行は、追加された拡張属性を持つ変更されたプロジェクトを XML ファイルに保存します。
## 結論
このチュートリアルでは、Java を使用して Aspose.Tasks プロジェクトの拡張属性を処理する方法を学習しました。これらの手順に従うことで、カスタム プロジェクト データを効率的に管理し、プロジェクト管理機能を強化できます。
## よくある質問
### Q: Aspose.Tasks を他のプログラミング言語で使用できますか?
A: はい、Aspose.Tasks は Java、.NET、C などの複数のプログラミング言語をサポートしています。++.
### Q: Aspose.Tasks に利用できる無料トライアルはありますか?
A: はい、Aspose.Tasks Web サイトから無料トライアルをダウンロードできます。
### Q: 拡張属性タイプをカスタマイズできますか?
A: もちろん、Aspose.Tasks を使用すると、プロジェクトのニーズに合わせたカスタム拡張属性タイプを定義できます。
### Q: Aspose.Tasks ドキュメントにアクセスするにはどうすればよいですか?
 A: Aspose.Tasks Web サイトで包括的なドキュメントを見つけることができます。[ドキュメンテーション](https://reference.aspose.com/tasks/java/).
### Q: Aspose.Tasks ユーザーはテクニカル サポートを利用できますか?
 A: はい、Aspose.Tasks フォーラムを通じてテクニカル サポートにアクセスできます。[Webサイト](https://forum.aspose.com/c/tasks/15).