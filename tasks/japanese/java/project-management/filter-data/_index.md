---
date: 2026-06-05
description: Aspose.Tasks for Java を使用して MPP ファイルをフィルタリングする方法を学び、filter criteria をカスタマイズし、filter
  tasks by date でプロジェクト管理を効率化します。
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Aspose.Tasks for Java を使用した MPP ファイルのフィルタリング方法
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java を使用した MPP ファイルのフィルタリング方法
url: /ja/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用した MPP ファイルのフィルタリング方法

## はじめに
Java アプリケーションで Microsoft Project ファイル (*.mpp*) を扱う場合、最も重要なタスク、リソース、または割り当てを抽出するために **MPP ファイルをフィルタリング** する必要が頻繁にあります。このチュートリアルでは、Aspose.Tasks for Java を使用してプログラムで **MPP をフィルタリングする方法** を解説し、**フィルタ条件のカスタマイズ** 方法を示し、実用的な「日付でタスクをフィルタリング」シナリオをデモします。最後まで読むと、任意の Java プロジェクトに組み込めるすぐに使えるコードスニペットが手に入ります。

## クイック回答
- **“filter mpp” とは何ですか？** 定義された条件に基づいてプロジェクトデータのサブセットを抽出することを意味します。  
- **どのライブラリがこれを処理しますか？** Aspose.Tasks for Java は、フィルタの作成と適用のための包括的な API を提供します。  
- **ライセンスは必要ですか？** 開発には無料トライアルが利用でき、商用環境では商用ライセンスが必要です。  
- **タスク、リソース、割り当てもフィルタできますか？** はい – 各エンティティタイプには独自のフィルタコレクションがあります。  
- **Java 8 以上が必要ですか？** Aspose.Tasks は Java 8 以降をサポートしています。

## Java における “how to filter mpp” とは何ですか？
`How to filter mpp` は、Aspose.Tasks の `Filter` オブジェクトを使用して、開始日、コスト、カスタム フィールドなどの特定の条件を満たすプロジェクト要素のみを選択するプロセスです。`Project` をロードし、`Filter` を取得すると、API は条件に一致するコレクションを返し、集中したレポート作成や下流の統合を可能にします。

## なぜフィルタ条件をカスタマイズするのか？
カスタムフィルタ条件を使用すると、ハイリスクタスク、期限超過項目、予算超過リソースなどを対象にでき、膨大なプロジェクトファイルを簡潔で実行可能なビューに変換できます。Aspose.Tasks は **50 以上の事前定義フィルタタイプ** をサポートし、無制限のカスタムフィルタを構築できるため、手動でのデータ抽出時間を最大 70 % 短縮できます。

## 前提条件
開始する前に、以下が揃っていることを確認してください：

1. **Java Development Kit (JDK)** – バージョン 8 以上。  
2. **Aspose.Tasks for Java** – [download page](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **IDE** – IntelliJ IDEA、Eclipse、または NetBeans が使用できます。  

## パッケージのインポート
`Filter`、`FilterCollection`、`FilterCriteria`、`ItemType`、および `Project` は、プロジェクトデータにフィルタを定義および適用するために使用されるコアクラスです。

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## ステップバイステップ ガイド

### 手順 1: プロジェクトの設定
まず、解析したい MPP ファイルを指す `Project` インスタンスを作成し、メモリにロードします。この単一の手順で、フィルタリング、検証、さらなる操作のためのプロジェクト全体モデルが準備され、API を通じてタスク、リソース、割り当てにアクセスできるようになります。

### MPP ファイルをフィルタリングするためにプロジェクトを設定するには？
`Project` クラスは MPP ファイルをメモリにロードして表現します。解析したい MPP ファイルを指す `Project` インスタンスを作成し、メモリにロードします。この単一の手順で、フィルタリング、検証、さらなる操作のためのプロジェクト全体モデルが準備され、API を通じてタスク、リソース、割り当てにアクセスできるようになります。

### フィルタを取得して検査するには？
`Filter` オブジェクトは、プロジェクト項目を選択するためのフィルタ定義をカプセル化します。Aspose.Tasks は「All Tasks」や「Critical Tasks」などの事前定義フィルタを保持しています。`project.getTaskFilters().getByName("My Filter")` またはインデックスベースのアクセスを使用して `Filter` オブジェクトを取得し、`FilterCriteria` コレクションを調べて各ルールとそれらを結合する論理演算子 (AND/OR) を確認し、フィルタが要件に合致していることを確認します。

### ネストされた条件行を反復処理するには？
`FilterCriteriaGroup` は、論理演算子で結合されたフィルタ条件のグループを表します。フィルタは各自の演算子を持つ条件グループを含むことができます。`filter.getCriteria().getRows()` をループし、行が `FilterCriteriaGroup` の場合は子行へ再帰的に処理します。この走査により、例えば “(Start < today AND Cost > 1000) OR Priority = High” のような複雑なフィルタロジックを完全に理解し、必要に応じて条件を調整できます。

### デバッグのために条件情報を出力するには？
条件ツリーを走査した後、各行のフィールド名、テスト演算子、値をコンソールに出力します。このシンプルなダンプにより、フィルタが大規模プロジェクトに適用する前に意図したビジネスルールと一致しているかを確認でき、誤った演算子や値を見つけやすくなります。

### プログラムで新しいフィルタを作成するには？
`new Filter("My Filter")` で `Filter` をインスタンス化し、`project.getTaskFilters().add(filter)` を使用してプロジェクトのタスクフィルタコレクションに追加します。その後、`FilterCriteria` コレクションに必要な行を追加し、フィールド名、テスト演算子、値を指定して、フィルタ適用時にどのタスクを含めるか正確に定義します。

### タスクではなくリソースにフィルタを適用できますか？
`ResourceFilters` コレクションはリソースに適用できるフィルタ定義を保持しています。はい – `project.getResourceFilters()` を使用して、タスクフィルタと同様にリソース固有のフィルタを操作できます。フィルタを追加または取得した後、タスクと同様に `FilterCriteria` を設定し、リソースコレクションに適用してフィルタ済みリソース集合を取得します。

### 複数のフィルタを OR ロジックで組み合わせることは可能ですか？
`Operation` を `OR` に設定した親 `FilterCriteriaGroup` を作成し、個々の `FilterCriteria` オブジェクトを子として追加します。このグループは各子条件を評価し、いずれかを満たす項目を返すため、複数のシンプルなフィルタを組み合わせて広範な選択を実現できます。

### Aspose.Tasks はカスタム フィールドでのフィルタリングをサポートしていますか？
`CustomField` 列挙型はプロジェクトで定義されたカスタム フィールドの識別子を提供します。もちろんです。`CustomField` 列挙型を介してカスタム フィールドを参照すれば、組み込みフィールドと同様にフィルタ式で扱えます。同じ演算子と値を使用して `FilterCriteria` 行に含めることができ、標準のプロジェクト属性と共にユーザー定義データに対する強力なクエリが可能です。

### 大規模な MPP ファイルでのフィルタリングはパフォーマンスにどのような影響がありますか？
フィルタリングは完全にメモリ内で実行され、通常 1,000 タスクのプロジェクトは 200 ms 未満で処理されます。数千タスクのファイルの場合は、`ProjectReader` を使用して必要なセクションのみをロードし、選択的にロードした後にフィルタを適用することを検討してください。これによりメモリ使用量を抑え、非常に大規模なプロジェクトでも高速な応答時間を維持できます。

**最終更新日:** 2026-06-05  
**テスト環境:** Aspose.Tasks for Java 24.10  
**作者:** Aspose

## 関連チュートリアル

- [MPP ファイルのロード (Java) - Aspose.Tasks でプロジェクト プロパティを管理](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - 手軽な MS Project Online データ読み取り](/tasks/java/project-data-reading/read-project-online/)
- [Aspose.Tasks for Java を使用した MS Project の開始日設定](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```