---
title: Aspose.Tasks のタスクに拡張属性を追加する
linktitle: Aspose.Tasks のタスクに拡張属性を追加する
second_title: Aspose.Tasks Java API
description: 拡張属性を使用して Microsoft Project ファイルをカスタマイズする際の Aspose.Tasks Java の機能を探索します。プロジェクト管理機能を簡単に強化します。
weight: 11
url: /ja/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のタスクに拡張属性を追加する

## 導入
プロジェクト管理機能を強化することは、効率的なタスク追跡とリソース管理にとって非常に重要です。 Aspose.Tasks for Java は、Java 開発者が Microsoft Project ファイルをシームレスに操作するための強力なソリューションを提供します。このチュートリアルでは、Aspose.Tasks for Java を使用してタスクに拡張属性を追加し、特定の要件に応じてプロジェクト データをカスタマイズおよび整理できるようにする方法を説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
- Java プログラミングの基本的な知識。
-  Aspose.Tasks for Java ライブラリがインストールされています。からダウンロードできます。[Webサイト](https://releases.aspose.com/tasks/java/).
- システムにインストールされている Java 統合開発環境 (IDE)。
## パッケージのインポート
Java プロジェクトで、Aspose.Tasks 機能にアクセスするために必要なパッケージをインポートします。
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
ここで、各例を複数のステップに分けてみましょう。
## 1. プレーンテキスト属性の追加
1. ドキュメント ディレクトリのパスを設定します。
```java
String dataDir = "Your Document Directory";
```
2. 新しいプロジェクトを作成します。
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Text1 タイプの拡張属性定義を作成します。
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. プロジェクトの拡張属性コレクションに定義を追加します。
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. プロジェクトにタスクを追加します。
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. 属性定義から拡張属性を作成します。
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. 生成された拡張属性に値を割り当てます。
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. 拡張属性をタスクに追加します。
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. プロジェクトを保存します。
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. ルックアップオプションを使用したテキスト属性の追加
上記と同じ手順に従い、Text1 を Text2 に置き換え、ルックアップ値をカスタマイズします。
## 3. ルックアップオプションを使用して期間属性を追加する
上記と同じ手順に従い、Text1 をDuration2 に置き換え、ルックアップ値をカスタマイズします。
## 結論
このステップバイステップ ガイドに従うことで、Aspose.Tasks for Java を利用して Microsoft Project ファイル内のタスクに拡張属性を追加する方法を学習しました。このカスタマイズにより、プロジェクト管理アプローチをカスタマイズできるようになり、柔軟性と効率が向上します。
## よくある質問
### Q: Aspose.Tasks for Java を他の Java ライブラリと一緒に使用できますか?
A: はい、Aspose.Tasks for Java は Java プロジェクトにシームレスに統合でき、他の Java ライブラリとうまく連携します。
### Q: Aspose.Tasks for Java は大規模なプロジェクト管理アプリケーションに適していますか?
A: 確かに、Aspose.Tasks for Java は、大規模なアプリケーションを含むさまざまなサイズのプロジェクトを処理できるように設計されています。
### Q: Aspose.Tasks for Java を商用プロジェクトで使用する場合に、ライセンスに関する考慮事項はありますか?
 A: はい、に提供されているライセンス情報を必ず確認してください。[Aspose.Task の Web サイト](https://purchase.aspose.com/buy).
### Q: Aspose.Tasks for Java に関するサポートや支援を受けるにはどうすればよいですか?
 A: にアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティのサポートとディスカッションのために。
### Q: 購入する前に Aspose.Tasks for Java を試すことはできますか?
 A: はい、無料試用版にアクセスできます。[ここ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
