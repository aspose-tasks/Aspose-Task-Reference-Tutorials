---
date: 2026-06-10
description: Javaで拡張属性を作成し、Microsoft Projectファイルを読み込み、数値を設定し、Aspose.Tasks for Javaを使用してプロジェクトをXMLとして保存する方法を学びます。
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Aspose.Tasksで拡張リソース属性を扱う
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: JavaでAspose.Tasksを使用して拡張属性を作成する方法
url: /ja/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java と Aspose.Tasks で拡張属性を作成する方法

## はじめに
このハンズオンガイドでは、Aspose.Tasks を使用して Microsoft Project ファイル用に **create extended attribute in Java** を作成します。既存のプロジェクトの読み込み、新しい数値属性の定義、リソースへの値の割り当て、最後に変更を XML ファイルとして永続化する手順を順に説明します。最後まで読むと、任意の Java ベースのプロジェクト管理ソリューションに組み込める再利用可能なコードパターンが手に入ります。

## クイック回答
- **拡張属性とは何ですか？**  
  ユーザー定義フィールド（例: Age、Skill Level）で、リソースやタスクの追加データを保存します。  
- **どの API が作成しますか？**  
  Aspose.Tasks for Java はカスタム属性を定義および管理するための `ExtendedAttributeDefinition` クラスを提供します。  
- **ライセンスは必要ですか？**  
  開発には一時的な評価ライセンスで動作しますが、本番環境での展開にはフルライセンスが必要です。  
- **数値を保存できますか？**  
  はい – 正確な小数値を割り当てるには `setNumericValue(BigDecimal)` を使用します。  
- **変更を永続化するにはどうすればよいですか？**  
  `project.save("output.xml", SaveFileFormat.Xml)` を呼び出して、更新されたプロジェクトを XML 形式で書き出します。

## カスタム属性とは何ですか？
**custom attribute**（拡張属性とも呼ばれる）は、Microsoft Project のリソースやタスクに追加できる列です。従来のフィールドではカバーできないデータ、例えば従業員の年齢、認定レベル、またはビジネス固有の指標などを取得できます。

## Java で拡張属性を作成する理由は？
Java で拡張属性を作成すると、プログラムでプロジェクトデータを拡張でき、ファイル間の一貫性を確保し、自動レポートを可能にします。属性を一度定義すれば、手動入力なしで多数のリソースやタスクに適用でき、時間の節約とエラーの削減につながります。

- **組織に合わせたデータ** – 手動の Excel 回避策なしで、重要な指標を保存できます。  
- **よりリッチなレポートを実現** – 後でダッシュボードや分析のためにカスタムフィールドをクエリできます。  
- **一貫性の維持** – プログラムで同じ定義を数十のプロジェクトに適用し、人為的エラーを排除します。  
- **パフォーマンス検証済み** – Aspose.Tasks は、製品ベンチマークによると、最大 10,000 タスクと 5,000 リソースのプロジェクトを、ファイル全体をメモリにロードせずに処理します。

## 前提条件
1. **Java Development Kit** – JDK 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java** – 最新リリースを [here](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **IDE** – Eclipse、IntelliJ IDEA、または任意の Java 対応開発環境。  

## Java で拡張属性を作成する方法は？
プロジェクトをロードし、属性を定義し、リソースに付与し、ファイルを保存します – すべて数ステップで実行できます。以下のセクションでは、各ステップを簡潔に説明し、実際のコードが入るプレースホルダーを示します。

### ステップバイステップ ガイド

#### パッケージのインポート
`Project`、`ExtendedAttributeDefinition`、`ExtendedAttributeResource` および関連クラスは `com.aspose.tasks` 名前空間にあります。これらを Java ファイルの先頭でインポートします。

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

#### ステップ 1: データディレクトリの定義
`Paths` は、プラットフォームに依存しない方法でファイルシステムパスを取得するメソッドを提供するユーティリティクラスです。

```java
String dataDir = "Your Data Directory";
```

#### ステップ 2: Microsoft Project ファイルのロード
`Project` は、メモリ内の Microsoft Project ファイルを表し、その内容への読み書きアクセスを可能にします。

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### ステップ 3: カスタム属性の定義
`ExtendedAttributeDefinition` は、リソースやタスクに付与できる新しいカスタムフィールドのスキーマを定義します。

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### ステップ 4: Java で数値を設定
`ExtendedAttributeResource` は、特定のリソースインスタンスに対するカスタム属性の値を保持します。

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### ステップ 5: リソースを追加しカスタム属性を付与
`Resource` は、人物、機器、または資材などのプロジェクトリソースをモデル化します。

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### ステップ 6: プロジェクトを XML として保存
`SaveFileFormat` は、XML を含むプロジェクト保存時にサポートされる出力形式を列挙します。

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### ステップ 7: 結果の表示
`System.out.println` は、標準コンソール出力にテキスト行を出力します。

```java
System.out.println("Process completed Successfully");
```

## よくある落とし穴とヒント
- **属性 ID の競合:** 新しい定義を作成する前に必ず `project.getExtendedAttributes().getById(id)` を呼び出し、重複した識別子を防ぎます。  
- **精度の取り扱い:** 正確な数値には `float`/`double` より `BigDecimal` を使用することを推奨します。これによりレポートでの丸め誤差を回避できます。  
- **ファイルパスの信頼性:** `Paths.get(...).toAbsolutePath()` を使用するか、IDE の作業ディレクトリを設定して `FileNotFoundException` を防止してください。  

## よくある質問

**Q: タスク用にもカスタム属性を作成できますか？**  
A: はい – 属性スキーマを定義する際に `ExtendedAttributeResource` の代わりに `ExtendedAttributeTask` を使用します。

**Q: 複数のカスタム属性を一度に追加できますか？**  
A: もちろんです。各属性ごとに別々の `ExtendedAttributeDefinition` オブジェクトを作成し、目的のリソースやタスクに付与します。

**Q: プロジェクトはどの形式で保存できますか？**  
A: Aspose.Tasks は XML、MPP、PDF、HTML など 30 以上の形式をサポートしています。この例では `SaveFileFormat.Xml` を使用しました。

**Q: 開発ビルドにライセンスは必要ですか？**  
A: テストには一時的な評価ライセンスで十分です。実稼働環境ではフル商用ライセンスが必要です。

**Q: 後でカスタム属性の値を読み取るにはどうすればよいですか？**  
A: `resource.getExtendedAttributes()` を呼び出してコレクションを反復処理し、`getNumericValue()` または `getTextValue()` で保存された値を取得します。

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## 関連チュートリアル

- [リソースの作成方法 – Aspose.Tasks for Java によるリソース管理](/tasks/java/resource-management/)
- [カスタムフィールドの作成 – 拡張属性の処理](/tasks/java/project-management/extended-attributes/)
- [プロジェクトの作成方法 – Aspose.Tasks で新しいタスク属性を設定](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}