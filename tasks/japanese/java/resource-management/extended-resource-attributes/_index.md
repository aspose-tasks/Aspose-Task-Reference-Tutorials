---
date: 2026-01-13
description: Aspose.Tasks for Java を使用して、カスタム属性の作成、Microsoft Project ファイルの読み込み、Java
  で数値を設定し、プロジェクトを XML として保存する方法を学びます。
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して MS Project でカスタム属性を作成する方法
url: /ja/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project で Aspose.Tasks を使用してカスタム属性を作成する方法

## Introduction
このチュートリアルでは、**Aspose.Tasks for Java** を使用して Microsoft Project ファイルのリソースに対するカスタム属性の作成方法を学びます。Microsoft Project ファイルの読み込み、数値属性の定義、値の設定、そして XML としてプロジェクトを保存する手順を順に解説します。最後まで実践できるサンプルが得られ、独自のプロジェクト管理ソリューションに応用できます。

## Quick Answers
- **“カスタム属性” とは何ですか？**  
  ユーザーが定義するフィールドで、リソースやタスクに対して余分な情報（例: 年齢、スキルレベル）を保存できます。  
- **どのライブラリがこれを扱いますか？**  
  Aspose.Tasks for Java が、カスタム属性の作成・管理用のフルエント API を提供します。  
- **ライセンスは必要ですか？**  
  評価用の無料一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **数値を設定できますか？**  
  はい – `setNumericValue` に `BigDecimal`（例: `30.5345`）を渡して設定します。  
- **プロジェクトはどのように保存しますか？**  
  変更後のファイルは `SaveFileFormat.Xml` を使用して XML として保存できます。

## What is a Custom Attribute?
**カスタム属性**（拡張属性とも呼ばれます）は、Microsoft Project のリソースやタスクに追加できる列です。組み込みフィールドではカバーできない情報（従業員の年齢、認定レベル、ビジネス固有の指標など）を取得するために使用します。

## Why Create a Custom Attribute in MS Project?
- **組織のニーズに合わせてプロジェクトデータをカスタマイズ**  
- **高度なレポート作成を可能にする**（後でクエリできる値を保存）  
- **複数プロジェクト間で一貫性を維持**（同じ属性定義をプログラムで適用）

## Prerequisites
開始する前に以下を用意してください。

1. **Java 開発環境** – JDK 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java** – 最新バージョンを [here](https://releases.aspose.com/tasks/java/) からダウンロード。  
3. **IDE** – Eclipse、IntelliJ IDEA、または任意の Java 対応 IDE。

## Step‑by‑Step Guide

### Import Packages
まず、必要な Aspose.Tasks クラスをインポートします。これらはプロジェクト、リソース、拡張属性の操作に必須です。

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Step 1: Define Data Directory
ソースのプロジェクトファイルがあるフォルダーと、出力先フォルダーを設定します。

```java
String dataDir = "Your Data Directory";
```

### Step 2: Load Microsoft Project File
既存ファイルを読み込んで `Project` インスタンスを作成します。これが **Microsoft プロジェクトファイルのロード** 手順で、ファイル内容全体にアクセスできるようになります。

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Step 3: Define the Custom Attribute
数値属性 **Age** を新規定義します。API は定義が既に存在するか確認し、存在しなければ作成します。

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Step 4: Set Numeric Value in Java
特定のリソース用に属性インスタンスを作成し、`setNumericValue` で数値を設定します。これが **set numeric value java** の実例です。

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Step 5: Add Resource and Attach the Custom Attribute
新しいリソース **R1** を追加し、先ほど作成したカスタム属性を紐付けます。

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Step 6: Save Project as XML
変更を永続化するためにプロジェクトを保存します。これは **save project as xml** 手順で、更新されたファイルをクリーンな XML 形式で出力します。

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Step 7: Display Result
処理がエラーなく完了したことを示すメッセージを出力します。

```java
System.out.println("Process completed Successfully");
```

これらの手順を実行することで、**カスタム属性の作成**、Microsoft Project ファイルの読み込み、Java での数値設定、そして XML 形式での保存が完了します。

## Common Pitfalls & Tips
- **属性 ID の競合**: 新規定義を作成する前に必ず `getById` で既存を確認し、重複 ID を防止してください。  
- **精度の取り扱い**: `BigDecimal` は小数点以下の精度を保持します。正確な値が必要な場合は `float` や `double` の使用を避けましょう。  
- **ファイルパス**: 絶対パスを使用するか、IDE の作業ディレクトリを適切に設定して `FileNotFoundException` を回避してください。

## Frequently Asked Questions

**Q: タスクにもカスタム属性を作成できますか？**  
A: はい – 属性定義時に `ExtendedAttributeTask` を使用すればタスク向けのカスタム属性が作れます。

**Q: 複数のカスタム属性を一度に追加できますか？**  
A: 可能です。属性ごとに `ExtendedAttributeDefinition` オブジェクトを作成し、目的のリソースやタスクに紐付けます。

**Q: プロジェクトはどの形式で保存できますか？**  
A: Aspose.Tasks は XML、MPP、PDF、HTML など多数の形式をサポートしています。本例では `SaveFileFormat.Xml` を使用しました。

**Q: 開発ビルドでも Aspose.Tasks のライセンスは必要ですか？**  
A: 評価用の一時ライセンスで十分です。本番環境ではフルライセンスが必須です。

**Q: 後でカスタム属性の値を取得するには？**  
A: `resource.getExtendedAttributes()` で属性コレクションを取得し、`getNumericValue()` や `getTextValue()` で個々の値を読み取れます。

## Conclusion
Aspose.Tasks for Java を使って Microsoft Project に **カスタム属性** を作成する手順は、プロジェクトの読み込み → 属性定義 → 値設定 → リソースへの紐付け → ファイル保存、という流れでシンプルです。この方法により、プロジェクトデータモデルをプログラムで拡張でき、レポートの充実や業務プロセスとの統合が容易になります。

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}