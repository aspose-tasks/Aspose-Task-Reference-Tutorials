---
date: 2026-09-30
description: Aspose.Tasks for Java を使用してタスクの拡張属性を作成する方法を学びましょう。カスタムタスクフィールドを追加するための、業界トップクラスの
  Java プロジェクト管理ライブラリです。
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Aspose.Tasks Java を使用してタスクの拡張属性を作成する方法
og_description: Aspose.Tasks for Java を使用してタスクの拡張属性を作成する方法を学びましょう。カスタムタスクフィールドを追加するための、業界トップクラスの
  Java プロジェクト管理ライブラリです。
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Aspose.Tasks Java を使用してタスクの拡張属性を作成する方法
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Aspose.Tasks Java を使用してタスクの拡張属性を作成する方法
url: /ja/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Java を使用したタスク拡張属性の作成方法

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project ファイル内に **create task extended attribute** を作成する方法を学びます。カスタム フィールドを追加することで、組み込み列ではカバーできないプロジェクト固有のデータを取得でき、レポートやリソース計画をより細かく制御できます。ガイドの最後までに、任意のタスクにプレーンテキスト、ルックアップ対応、期間属性を追加できるようになります。

## クイック回答
- **What does “extended attribute” mean?** カスタム フィールドで、タスク、リソース、または割り当てに対して定義し、付与できるものです。  
- **Which library adds this capability?** Aspose.Tasks for Java、Java のプロジェクト管理ライブラリです。  
- **Do I need a license to try it?** はい – Aspose のウェブサイトから 30 日間の無料トライアルが利用可能です。  
- **Can I add lookup values?** もちろんです。テキストまたは期間フィールドに対して許可された値のリストを提供できます。  
- **Is the API compatible with Java 8 and later?** はい、Java 8 以降に対応しており、主要な OS すべてで動作します。

## タスク拡張属性とは何ですか？
タスク拡張属性は、プロジェクト ファイル内の各タスクに対して追加情報を格納するユーザー定義列です。組み込みフィールドと同様に機能しますが、テキスト、数値、日付、期間など、必要な任意のデータ型を保持できます。

## なぜ Aspose.Tasks for Java を使用するのですか？
Aspose.Tasks は **50 以上のファイル形式** をサポートし、**10,000 件以上のタスク** を持つプロジェクトを Microsoft Project をインストールせずに処理できます。このライブラリは完全にオフラインで動作し、データプライバシーとエンタープライズ規模のソリューション向けに決定的なパフォーマンスを保証します。

## 前提条件
- 基本的な Java プログラミングの知識。  
- Aspose.Tasks for Java ライブラリがインストールされていること。[website](https://releases.aspose.com/tasks/java/) からダウンロードできます。  
- Java IDE（IntelliJ IDEA、Eclipse、または VS Code）がマシンに設定されていること。

## パッケージのインポート
`import` 文により、`Project`、`ExtendedAttributeDefinition`、`ExtendedAttribute` など、必要なコア クラスにアクセスできます。

`Project` は Microsoft Project ファイルを表し、読み取り、変更、保存のメソッドを提供します。  
`ExtendedAttributeDefinition` はタスク、リソース、または割り当てに付与できるカスタム フィールドを定義します。  
`ExtendedAttribute` は定義のインスタンスで、特定のエンティティの実際の値を保持します。

## タスクにプレーンテキストの拡張属性を追加する方法
プレーンテキストの拡張属性を追加するには、まずプロジェクトをロードし、Text 型の定義を作成してプロジェクトのコレクションに追加し、タスクを作成し、定義から属性をインスタンス化し、テキスト値を設定してタスクに付与し、最後にプロジェクトを保存します。

### 1. ドキュメント ディレクトリ パスを設定
ソース ファイルと出力ファイルの保存場所を指定します。

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. 新しいプロジェクトを作成
`Project` オブジェクトをインスタンス化し、必要に応じて既存の .mpp ファイルをロードします。

```java
String dataDir = "Your Document Directory";
```

### 3. Text1 タイプの拡張属性定義を作成
カスタム フィールドを “Text1” という名前のプレーンテキスト列として定義します。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. 定義をプロジェクトの拡張属性コレクションに追加
プロジェクトが認識できるように新しい定義を登録します。

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. プロジェクトにタスクを追加
カスタム フィールドを受け取るタスクを作成します。

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. 属性定義から拡張属性を作成
特定のタスクにバインドできるインスタンスを生成します。

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. 生成した拡張属性に値を割り当て
保存したい実際のテキストを設定します。例: “Design Review”。

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. 拡張属性をタスクに追加
属性インスタンスをタスクの `ExtendedAttributes` コレクションに付与します。

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. プロジェクトを保存
更新されたプロジェクトを希望の形式でディスクに書き戻します。

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## ルックアップ オプション付きのテキスト属性を追加する方法
ルックアップ付きのテキスト属性を追加する場合、プレーンテキスト属性と同じ手順を踏みますが、定義を追加する前に `LookupValues` コレクションに許可された文字列を設定します。これらの値は Microsoft Project のドロップダウン リストとして表示され、データの一貫性が保たれます。

## ルックアップ オプション付きの期間属性を追加する方法
ルックアップ付きの期間属性を追加するには、定義作成時に `Text1` タイプを `Duration2` に置き換え、`LookupValues` コレクションに “1 day”、 “2 days” などの期間文字列を設定します。定義がプロジェクトに追加された後、属性インスタンスを作成し、期間値を設定してタスクに付与し、ファイルを保存します。

## 一般的な問題とトラブルシューティング
- **Lookup values not appearing** – `project.getExtendedAttributes().add(definition)` を呼び出す *前に* 各ルックアップ エントリを `LookupValues` コレクションに追加していることを確認してください。  
- **Attribute value not saved** – 値を設定した *後に* `ExtendedAttribute` インスタンスをタスクに追加していることを確認してください。  
- **File size grows unexpectedly** – 非常に大規模なプロジェクトを扱う場合、インクリメンタル保存を有効にするために `project.setSaveOptions(new ProjectSaveOptions())` の呼び出しを検討してください。

## よくある質問

**Q: Can I use Aspose.Tasks for Java with other Java libraries?**  
A: はい、Aspose.Tasks for Java は Spring、Hibernate、Apache POI など、あらゆる Java エコシステムとスムーズに統合できます。

**Q: Is Aspose.Tasks for Java suitable for large‑scale project management applications?**  
A: もちろんです。このライブラリは数千タスク規模のプロジェクトを処理できるよう設計されており、メモリ使用量を抑えるストリーミングもサポートしています。

**Q: Are there any licensing considerations for using Aspose.Tasks for Java in a commercial project?**  
A: はい、有効な商用ライセンスが必要です。詳細は [Aspose.Tasks website](https://purchase.aspose.com/buy) で確認できます。

**Q: How can I get support or assistance with Aspose.Tasks for Java?**  
A: コミュニティサポートは [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) をご覧いただくか、Aspose アカウントからサポートチケットを開いてください。

**Q: Can I try Aspose.Tasks for Java before purchasing?**  
A: はい、[Aspose.Tasks free trial](https://releases.aspose.com/) ページから無料トライアル版にアクセスできます。

**最終更新日:** 2026-09-30  
**テスト環境:** Aspose.Tasks for Java 24.10  
**作者:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## 関連チュートリアル

- [Java プロジェクト管理におけるカスタム列と拡張属性](/tasks/java/project-management/extended-attributes/)
- [Aspose.Tasks for Java で拡張タスク属性を読む](/tasks/java/task-properties/extended-task-attributes/)
- [プロジェクト aspose.tasks の作成方法 – 新しいタスク属性の設定](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}