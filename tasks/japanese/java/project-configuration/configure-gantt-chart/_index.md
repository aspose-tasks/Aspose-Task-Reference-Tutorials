---
title: Aspose.Tasks プロジェクトでガント チャート ビューを構成する
linktitle: Aspose.Tasks プロジェクトでガント チャート ビューを構成する
second_title: Aspose.Tasks Java API
description: Java を使用して Aspose.Tasks でガント MS プロジェクト チャート ビューを構成する方法を学びます。プロジェクトをカスタマイズし、ガント チャートで段階的に視覚化します。
weight: 10
url: /ja/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks プロジェクトでガント チャート ビューを構成する

## 導入
このチュートリアルでは、Java を使用して Aspose.Tasks プロジェクトでガント MS プロジェクト チャート ビューを構成する方法を学習します。 Aspose.Tasks は、Microsoft Project ファイルをプログラムで操作できるようにする強力な Java API です。これらの手順に従うことで、プロジェクトの要件に応じてガント チャート ビューをカスタマイズできるようになります。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java 開発キット (JDK): システムに Java がインストールされていることを確認してください。
2.  Aspose.Tasks ライブラリ: Aspose.Tasks ライブラリをダウンロードしてインストールします。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
3. 統合開発環境 (IDE): 任意の IDE を選択します。このチュートリアルでは IntelliJ IDEA を使用しますが、使い慣れた任意の IDE を使用できます。
## パッケージのインポート
まず、Java プロジェクトで Aspose.Tasks を操作するために必要なパッケージをインポートする必要があります。次のインポート ステートメントを Java ファイルに追加します。
```java
import com.aspose.tasks.*;
```
ここで、ガント MS プロジェクト チャート ビューを構成するプロセスを段階的に説明します。
## ステップ 1: データ ディレクトリを設定する
```java
String dataDir = "Your Data Directory";
```
交換する`"Your Data Directory"`プロジェクト データ ディレクトリへのパスを置き換えます。
## ステップ 2: プロジェクト ファイルをロードする
```java
Project project = new Project(dataDir + "project.mpp");
```
プロジェクト ファイルをロードします (`project.mpp`この例では)`Project` Aspose.Tasks のクラス。
## ステップ 3: 新しいアクティビティを追加する
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
を使用してプロジェクト内に新しいタスクを作成します。`Task`クラスを作成し、ルートタスクの子に追加します。
## ステップ 4: カスタム属性を定義する
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
を使用して新しいカスタム属性を定義します。`ExtendedAttributeDefinition`クラスを作成し、プロジェクトの拡張属性に追加します。
## ステップ 5: カスタム属性をタスクに追加する
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
を使用して、作成されたタスクにカスタム属性を追加します。`createExtendedAttribute`方法。
## ステップ 6: テーブルをカスタマイズする
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
指定した幅、タイトル、配置を使用してテキスト属性フィールドを追加して、テーブルをカスタマイズします。
## ステップ 7: プロジェクトを保存する
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
設定したガント MS プロジェクト チャート ビューでプロジェクトを保存します。作成されたファイルは Microsoft Project 2010 で開くことができます。
## 結論
おめでとう！ Java を使用して、Aspose.Tasks プロジェクトでガント MS プロジェクト チャート ビューを正常に構成しました。プロジェクト属性をカスタマイズし、プロジェクトのニーズに応じてガント チャートで視覚化できるようになりました。
## よくある質問
### Q: Aspose.Tasks を他のプログラミング言語で使用できますか?
A: はい、Aspose.Tasks は .NET、Java、C などの複数のプログラミング言語で利用できます。++.
### Q: Aspose.Tasks に利用できる無料トライアルはありますか?
 A: はい、以下から無料トライアルをダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks のサポートはどこで見つけられますか?
A: サポートを見つけたり、質問したりできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks のライセンスを購入するにはどうすればよいですか?
 A: ライセンスは以下から購入できます。[ここ](https://purchase.aspose.com/buy).
### Q: テスト目的には一時ライセンスが必要ですか?
 A: はい、次から一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
