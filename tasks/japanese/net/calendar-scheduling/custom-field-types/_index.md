---
date: 2026-07-19
description: ステップバイステップのコード、前提条件、FAQ とともに、Aspose.Tasks for .NET でカスタム フィールド タイプを追加する方法を学びましょう。
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Aspose.Tasks のカスタム フィールド タイプ
og_description: Aspose.Tasks for .NET でカスタム フィールド タイプを追加する方法を学びます。このステップバイステップ ガイドに従って、拡張属性を効率的に作成、定義、使用しましょう。
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Aspose.Tasks for .NET でカスタム フィールド タイプを追加する方法
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Aspose.Tasks for .NET でカスタム フィールド タイプを追加する方法
url: /ja/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasksでカスタムフィールドタイプを追加する方法

## はじめに

このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project ファイルに **カスタムフィールド** タイプを追加する方法を紹介します。カスタムフィールドを使用すると、リスクスコア、部門コード、カスタムメモなどの追加情報をタスク、リソース、またはプロジェクト自体に直接保存できます。環境設定から定義、追加、カスタムテキストフィールドの検証まで、全工程を順に解説します。

## クイック回答
- **カスタムフィールドとは何ですか？** タスク/リソース上でテキスト、数値、日付、またはフラグを保持できるユーザー定義の列です。  
- **カスタムフィールドを定義するクラスはどれですか？** `ExtendedAttributeDefinition`。  
- **既存のプロジェクトにカスタムフィールドを追加できますか？** はい — プロジェクトをロードし、定義を作成してからコレクションに追加します。  
- **Aspose.Tasks のライセンスは必要ですか？** 本番環境ではライセンスが必要です。評価目的では無料トライアルが利用できます。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## Aspose.Tasks の「カスタムフィールドを追加する方法」とは？

**カスタムフィールドを追加する方法** は、`ExtendedAttributeDefinition` を作成し、プロジェクトの `ExtendedAttributes` コレクションに添付するプロセスを指します。これにより、標準の Project スキーマに含まれない追加メタデータを保存できます。タスク、リソース、またはプロジェクト自体に使用でき、リスクレベル、部門コード、カスタムメモなど、デフォルトフィールドに存在しない情報を取得できます。

## プロジェクト管理でカスタムフィールドを使用する理由

Aspose.Tasks は **50 以上の組み込み拡張属性タイプ** をサポートし、ファイルサイズに大きな影響を与えることなく **任意の数のカスタムフィールド** を定義できます。カスタムフィールドを使用すると、次のことが可能です。  
これらのフィールドは Microsoft Project の追加列として表示され、数式、レポート、フィルタで参照できます。プロジェクトファイル内に保存され、ファイルと共に移動するため、下流のツールでもカスタムデータが保持されます。

## 前提条件

### 1. Visual Studio のインストール
Visual Studio（2019 以降）がマシンにインストールされていることを確認してください。Microsoft のウェブサイトからダウンロードできます。

### 2. Aspose.Tasks for .NET
プロジェクトに Aspose.Tasks の NuGet パッケージを追加します。最新バージョンは [here](https://releases.aspose.com/tasks/net/) からダウンロードしてください。

### 3. 基本的な C# の知識
C# の構文、クラス、および .NET プロジェクト構造に慣れている必要があります。

## 名前空間のインポート

`Project`、`ExtendedAttributeDefinition`、および関連する列挙型は `Aspose.Tasks` 名前空間にあります。ファイルの先頭でインポートしてください。

`Aspose.Tasks` 名前空間は Microsoft Project ファイルを扱うためのすべてのコア型を提供します。

```csharp

```

## プロジェクトにカスタムフィールドを追加する方法？

既存のプロジェクトをロードし、カスタムフィールド定義を作成して、プロジェクトの拡張属性コレクションに追加します—すべて3つの簡潔な手順で行います。このパターンはタスク、リソース、プロジェクト自体に適用でき、ファイルを保存したときにカスタムフィールドが永続化されることを保証します。

### 手順 1: Project オブジェクトの作成
`Project` は Aspose.Tasks のトップレベルオブジェクトで、メモリ内の単一の Project ファイルを表します。インスタンス化するとファイルがロードされ、タスク、リソース、拡張属性にアクセスできるようになります。

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### 手順 2: カスタムフィールドの定義
`ExtendedAttributeDefinition` は新しい列を表します。この例では、タスク用の **Text** タイプのカスタムフィールドを作成し、エイリアスを “MyText” に設定します。`ExtendedAttributeTask.Text1` 列挙値は、Aspose.Tasks が値をどこに保存するかを示します。

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### 手順 3: カスタムフィールド定義をプロジェクトに追加
プロジェクトの `ExtendedAttributes` コレクションはすべてのカスタムフィールド定義を保持します。定義を追加することで、プロジェクト内のすべてのタスクで使用できるようになります。

```csharp
project.ExtendedAttributes.Add(definition);
```

## よくある問題と解決策
- **フィールドが MS Project の UI に表示されない** – `Alias` プロパティを設定してください。MS Project はエイリアスを列ヘッダーとして表示します。  
- **保存時に例外がスローされる** – プロジェクトファイルが読み取り専用でないこと、そして有効なライセンスがあることを確認してください。  
- **リロード後にカスタムフィールドの値が失われる** – タスクに値を割り当てた後、`project.Save("output.mpp")` を呼び出すことを確認してください。

## よくある質問

**Q: Aspose.Tasks を他の .NET フレームワークで使用できますか？**  
A: はい、Aspose.Tasks は .NET Framework、.NET Core、.NET 5/6/7 で動作します。

**Q: Aspose.Tasks はエンタープライズレベルのアプリケーションに適していますか？**  
A: 完全に適しています。**最大 10,000 タスク** のプロジェクト処理をサポートし、マルチスレッドサーバー環境でも実行可能です。

**Q: Aspose.Tasks は複数のプロジェクトファイル形式をサポートしていますか？**  
A: はい — Aspose.Tasks は MPP、XML、HTML、CSV 形式の読み書きが可能で、**すべての主要な Microsoft Project バージョン** をカバーします。

**Q: Aspose.Tasks でリソースデータを操作できますか？**  
A: はい、リソースの追加、更新、削除が可能で、カスタムフィールドを割り当てることもできます。

**Q: Aspose.Tasks ユーザー向けのコミュニティフォーラムはありますか？**  
A: はい、[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) にアクセスして他のユーザーと交流し、Aspose チームからサポートを受けられます。

---

**最終更新日:** 2026-07-19  
**テスト環境:** Aspose.Tasks 24.12 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Tasks での MS Project 拡張属性定義のマスター](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Aspose.Tasks を使用した MS Project 拡張属性の操作](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Aspose.Tasks のフィールドヘルパーと MS Project の統合](/tasks/net/tasks-project-management/field-helper/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}