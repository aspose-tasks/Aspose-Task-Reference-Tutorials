---
title: Aspose.Tasks で MS プロジェクトのアウトライン コードを取得する
linktitle: Aspose.Tasks でアウトライン コードを取得する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してプログラムで Microsoft Project アウトライン コードを取得する方法を学びます。プロジェクト管理能力を強化します。
weight: 15
url: /ja/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で MS プロジェクトのアウトライン コードを取得する

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project のアウトライン コードを取得する方法を学習します。 MS Project のアウトライン コードは、プロジェクトのタスク、リソース、割り当てを分類および整理するための構造化された方法を提供します。 Aspose.Tasks は、開発者が Microsoft Project ファイルをプログラムで操作および管理できるようにする強力な Java ライブラリです。
## 前提条件
始める前に、次の前提条件が設定されていることを確認してください。
### 1. Java開発環境
システムに Java Development Kit (JDK) がインストールされていることを確認してください。 JDK は Oracle Web サイトからダウンロードしてインストールできます。
### 2. Aspose.Tasks ライブラリ
Aspose.Tasks ライブラリをダウンロードして Java プロジェクトに組み込みます。ライブラリはからダウンロードできます。[Aspose.Tasks for Java ダウンロード ページ](https://releases.aspose.com/tasks/java/).
## パッケージのインポート
まず、Java コードの Aspose.Tasks から必要なパッケージをインポートします。
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
ここで、提供されたサンプル コードを複数のステップに分割してみましょう。
## ステップ 1: プロジェクトをロードする
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
このステップでは、Microsoft Project ファイルを`Project`指定されたファイル名を使用してオブジェクトを作成します。
## ステップ 2: アウトライン コードを取得する
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
プロジェクト内の各アウトライン コード定義を繰り返し処理します。
## ステップ 3: アウトライン コードのプロパティにアクセスする
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
エイリアス、フィールド ID、フィールド名などのアウトライン コード定義のさまざまなプロパティを取得して出力します。
## ステップ 4: エンタープライズ カスタム コードを確認する
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
アウトライン コードがエンタープライズ カスタム コードであるかどうかを確認し、それに応じて結果を出力します。
## ステップ 5: アウトライン コード マスクを表示する
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
アウトライン コードに関連付けられた各マスクを反復処理し、そのレベルとマスク値を出力します。
## ステップ 6: アウトライン コード値を表示する
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
各アウトライン コード値を反復処理し、その説明、値 ID、値、およびタイプを出力します。
## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project のアウトライン コードを取得する方法を学習しました。提供された手順に従うことで、Java アプリケーションのアウトライン コードに効果的にアクセスして操作し、高度なプロジェクト管理機能を有効にすることができます。
## よくある質問
### Q1: Aspose.Tasks for Java を使用して、プロジェクト ファイル内のアウトライン コードを変更できますか?
A: はい、Aspose.Tasks for Java は、MS Project ファイル内のアウトライン コードをプログラム的に変更するための API を提供します。
### Q2: Aspose.Tasks for Java の試用版はありますか?
 A: はい、Aspose.Tasks for Java の無料試用版を次のサイトからダウンロードできます。[Aspose.Task の Web サイト](https://releases.aspose.com/).
### Q3: Aspose.Tasks for Java のテクニカル サポートを受けるにはどうすればよいですか?
 A: テクニカル サポートを受けるには、次のサイトにアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)そこにクエリを投稿します。
### Q4: Aspose.Tasks for Java の一時ライセンスを購入できますか?
 A: はい、Aspose.Tasks for Java の一時ライセンスを次のサイトから購入できます。[購入ページ](https://purchase.aspose.com/temporary-license/).
### Q5: Aspose.Tasks for Java の完全なドキュメントはどこで見つけられますか?
 A: を参照してください。[ドキュメンテーション](https://reference.aspose.com/tasks/java/)Aspose.Tasks for Java の使用方法の詳細については、「Aspose.Tasks for Java」を参照してください。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
