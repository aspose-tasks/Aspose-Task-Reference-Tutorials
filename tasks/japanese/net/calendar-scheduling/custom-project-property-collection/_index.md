---
date: 2026-10-15
description: Aspose.Tasks for .NET でカスタム プロパティを追加し、カスタム プロジェクト プロパティを管理する方法を学び、プロジェクト
  メタデータの制御を強化しましょう。
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Aspose.Tasks におけるカスタム プロジェクト プロパティ コレクションの管理
og_description: Aspose.Tasks for .NET を使用してプロジェクト ファイルにカスタム プロパティを追加します。このガイドでは、カスタム
  プロパティの管理方法、読み取り方法、ブール値や文字列値を効率的に追加する方法を示します。
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Aspose.Tasks .NET API を使用してプロジェクトにカスタム プロパティを追加する
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Aspose.Tasks for .NET でカスタム プロパティを追加する方法
url: /ja/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NETでカスタムプロパティを追加する方法

## はじめに

カスタムプロパティのサポートを追加すると、組み込みフィールドではカバーできないプロジェクト固有のメタデータを保存できます。このチュートリアルでは **カスタムプロパティを追加** し、取得し、Aspose.Tasks for .NET を使用してカスタムプロパティコレクション全体を管理する方法を学びます。最後には、ビジネスルールに合わせた Boolean、DateTime、Double、String の値でプロジェクトファイルをカスタマイズできるようになります。

## クイック回答
- **Boolean カスタムプロパティを追加できますか？** はい – `CustomPropertyType.Boolean` を使用します。  
- **サポートされているカスタムプロパティのタイプは何種類ですか？** 4 種類: Boolean、DateTime、Double、String。  
- **カスタムプロパティコレクションは読み取り専用ですか？** プロジェクトが読み取り専用のソースからロードされた場合、読み取り専用になることがあります。  
- **この機能を使用するのにライセンスが必要ですか？** 評価には一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **対応している .NET バージョンはどれですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## カスタムプロパティとは？

カスタムプロパティは、Project オブジェクトに添付できるユーザー定義のメタデータフィールドです。「リスクレベル」や「顧客 ID」など、標準の MS‑Project フィールドでカバーできない追加情報を保存できます。

## Aspose.Tasksでカスタムプロパティを追加する理由

Aspose.Tasks は **50 以上の入出力フォーマット** をサポートし、**最大 10,000 タスク** のプロジェクトをメモリ全体にロードせずに処理できます。カスタムプロパティを追加すると、ビジネスに重要なデータをプロジェクトファイルに直接埋め込めるため、外部データベースが不要になり、データがプロジェクトと共に移動します。

## 前提条件

- Visual Studio（任意の最新エディション）がワークステーションにインストールされていること。  
- Aspose.Tasks for .NET – 上記の[ダウンロードリンク](https://releases.aspose.com/tasks/net/)からダウンロードしてください。  
- C# の構文と .NET プロジェクト構造に基本的に慣れていること。

## 名前空間のインポート

以下の名前空間により、コアプロジェクトモデルとカスタムプロパティ API にアクセスできます。

```csharp
using Aspose.Tasks;
using System;


```

## Aspose.Tasksでカスタムプロパティを追加する方法

カスタムプロパティを追加するには、まずプロジェクトをロードし、`CustomProperty` オブジェクトを作成して名前、タイプ、値を設定し、最後にプロジェクトの `CustomProperties` コレクションに追加します。この操作によりメタデータがプロジェクトファイルに直接埋め込まれ、`project.Save(...)` を呼び出すと変更が保存されます。

`CustomProperty` はプロジェクトに添付された単一のユーザー定義フィールドを表します。

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### 手順 1: プロジェクトの初期化

`Project` は Aspose.Tasks でプロジェクトファイルを表す主要クラスです。

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### 手順 2: カスタムプロパティコレクションの準備状態を確認

`CustomProperties` はプロジェクトのすべてのカスタムプロパティオブジェクトを保持するコレクションです。

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### 手順 3: カスタムプロパティを追加

`Add` メソッドは新しいカスタムプロパティをプロジェクトのコレクションに挿入します。

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### 手順 4: カスタムプロパティにアクセス

`CustomProperties` コレクションは IEnumerable を実装しており、各 `CustomProperty` を反復処理できます。

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### 手順 5: カスタムプロパティの値を取得

`Get` メソッドは名前でカスタムプロパティの値を返します。

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### 手順 6: カスタムプロパティ名を列挙

`Names` プロパティはコレクション内のすべてのカスタムプロパティ名のリストを提供します。

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### 手順 7: カスタムプロパティを削除またはクリア

`Remove` メソッドは特定のプロパティを削除し、`Clear` はコレクション全体を空にします。

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## よくある落とし穴とトラブルシューティング

- **読み取り専用コレクション** – `project.CustomProperties.IsReadOnly` が `true` を返す場合、ソースファイルが排他読み取りで開かれていないか確認するか、編集前に書き込み可能な場所へコピーしてください。  
- **型の不一致** – 宣言された `CustomPropertyType` と一致しない値を割り当てると `ArgumentException` がスローされます。必ず正しい `Type` を設定した後に `Value` を設定してください。  
- **変更の保存** – プロパティを追加または削除した後は `project.Save("output.mpp")` を呼び出して変更を永続化してください。呼び出さないと変更はメモリ内に留まります。

## よくある質問

**Q: Aspose.Tasks for .NET を使用して、任意のデータ型のカスタムプロパティをプロジェクトに追加できますか？**  
A: はい、Boolean、DateTime、Double、String の各タイプをサポートするカスタムプロパティを追加できます。

**Q: Aspose.Tasks for .NET でカスタムプロパティ名を列挙することは可能ですか？**  
A: もちろん可能です。`Names` プロパティを使用してカスタムプロパティ名を列挙できます。

**Q: プロジェクトから特定のカスタムプロパティを削除するにはどうすればよいですか？**  
A: `Remove` メソッドにプロパティ名を渡すことで削除できます。

**Q: Aspose.Tasks for .NET は一時ライセンスをサポートしていますか？**  
A: はい、評価目的で Aspose のウェブサイトから一時ライセンスを取得できます。

**Q: Aspose.Tasks for .NET に関するサポートや追加の支援はどこで受けられますか？**  
A: 任意の質問や支援については Aspose.Tasks フォーラム [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) をご利用ください。

---

**最終更新日:** 2026-10-15  
**テスト対象:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks for .NETで組み込みプロジェクトプロパティを読み取る方法](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Aspose.TasksでMS Project属性コレクションを管理する](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks カスタムフィールドタイプ – カレンダーとスケジューリング](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}