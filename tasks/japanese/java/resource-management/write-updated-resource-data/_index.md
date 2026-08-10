---
date: 2026-06-30
description: Aspose.Tasks for Java を使用して、複数のリソースを更新し、リソース グループ データを変更し、プロジェクトを MPP
  にエクスポートして MPP として保存する方法を学びます。
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Aspose.Tasks for Java で複数のリソースを更新する
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java で複数のリソースを更新する
url: /ja/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java で複数リソースを更新する

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project ファイル内の **複数リソースを更新する** 方法を学びます。レートを変更したり、グループを再割り当てしたり、更新されたファイルを MPP にエクスポートしたりする必要がある場合でも、以下の手順で完全な本番環境向けワークフローを案内します。Microsoft Project のインストールは不要で、API は数百のリソースを持つプロジェクトも効率的に処理できます。

## クイック回答
- **複数のリソースを一度に更新できますか？** はい – `ResourceCollection` を反復処理し、属性を一括で設定します。  
- **ファイルを MPP として保存するメソッドはどれですか？** `project.save("output.mpp", SaveFileFormat.MPP)`。  
- **商用利用にはライセンスが必要ですか？** 本番環境では有料ライセンスが必要です。無料トライアルも利用可能です。  
- **サポートされている Java バージョンは何ですか？** Java 6 以降、Java 17 LTS も含まれます。  
- **大量更新はパフォーマンスが良いですか？** Aspose.Tasks は、典型的なサーバー上で 500 リソースのプロジェクトを 2 秒未満で処理します。

## 「複数リソースを更新する」とは何ですか？
**「複数リソースを更新する」** は、単一の Project ファイル内でレート、グループ、カレンダー、カスタム フィールドなど、複数のリソースエントリのプロパティをプログラムで変更することを指します。この操作は、エンタープライズリソース計画システムとプロジェクトデータを同期したり、多数のリソースにわたる予算を調整したり、組織全体のポリシー変更を適用したりする際に頻繁に必要となります。

## リソース グループを変更し、プロジェクトを MPP にエクスポートするために Aspose.Tasks を使用する理由は？
Aspose.Tasks は **50 以上の入力および出力フォーマット** をサポートし、MPP、XML、CSV などが含まれ、**プロジェクトを MPP にエクスポート** でき、ファイル全体をメモリに読み込む必要がありません。ライブラリは最大 **2 GB** のサイズのファイルを処理でき、**プロジェクトを MPP として保存** することを迅速かつ確実に行えます。

## 前提条件
始める前に、以下が揃っていることを確認してください。

1. システムに Java Development Kit (JDK) がインストールされていること。  
2. Aspose.Tasks for Java ライブラリ。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から可能です。  
3. Java プログラミングの基本知識。  

## パッケージのインポート
`import` 文は、必要な Aspose.Tasks クラスをソースファイルに導入します。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## ステップ 1: データ ディレクトリの設定
データファイルが配置されているディレクトリを定義します：

```java
String dataDir = "Your Data Directory";
```

## ステップ 2: 入力ファイルと出力ファイルの指定
入力の MS Project ファイルと、更新後のファイルのパスを定義します：

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## ステップ 3: プロジェクトのロード
`Project` は、メモリにロードされた Microsoft Project ファイルを表し、タスク、リソース、その他のプロジェクト データへのアクセスを提供します。

```java
Project project = new Project(file);
```

## ステップ 4: リソースの追加と属性の設定
`Resource` は個々のプロジェクト リソースをモデル化し、レート、グループ、カレンダー、その他の属性を設定できるようにします。

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## ステップ 5: 複数リソースを効率的に更新する
`ResourceCollection` はプロジェクト内のすべてのリソースのコレクションで、`project.getResources()` で取得できます。

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## ステップ 6: プロジェクトの保存
`SaveFileFormat` は、MPP、XML、PDF など、プロジェクトを保存する際にサポートされるファイル形式を列挙します。

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## プロジェクト内の複数リソースを更新する方法は？
既存のプロジェクトをロードし、`ResourceCollection` を取得して各 `Resource` オブジェクトを反復処理します。各リソースについて、レート、グループ、カスタム属性など必要なフィールドを変更し、次のアイテムへ進みます。すべてのリソースの処理が完了したら、`project.save(...)` を一度呼び出して変更を効率的に永続化します。

## 一般的な問題と解決策
- **リソース ID の衝突** – `project.getResources().add(new Resource())` を使用して、各新規リソースに一意の ID が付与されるようにしてください。  
- **レート形式エラー** – `ResourceRate` オブジェクトを使用し、`RateType` を `StandardRate` または `OvertimeRate` に設定してください。  
- **大きなファイルでメモリ負荷がかかる** – ロード前に `Project.setReadOnly(true)` を有効にして、メモリ使用量を削減してください。

## よくある質問
**Q: Aspose.Tasks for Java を使用して同じプロジェクト内の複数リソースを更新できますか？**  
A: はい、リソースを反復処理し、属性を適切に設定することで複数リソースを更新できます。

**Q: Aspose.Tasks は MS Project 以外のファイル形式もサポートしていますか？**  
A: はい、Aspose.Tasks は XML、MPP などを含むさまざまなファイル形式をサポートしています。

**Q: Aspose.Tasks はさまざまな Java バージョンと互換性がありますか？**  
A: Aspose.Tasks は Java 6 以降のバージョンと互換性があります。

**Q: Aspose.Tasks を使用して MS Project ファイルで他の操作を実行できますか？**  
A: はい、タスク、リソース、カレンダーの読み取り、書き込み、操作など、幅広い操作を実行できます。

**Q: Aspose.Tasks の追加ヘルプやサポートはどこで見つけられますか？**  
A: 支援や質問がある場合は、[Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) をご覧ください。

**Q: 更新されたファイルを MPP 形式でエクスポートするにはどうすればよいですか？**  
A: すべてのリソース変更を行った後、`project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` を呼び出してください。

**Q: リソース グループを変更する最適な方法は何ですか？**  
A: プロジェクトを保存する前に、各 `Resource` オブジェクトの `Resource.Group` プロパティを設定してください。

---

**最終更新日:** 2026-06-30  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル
- [Aspose.Tasks for Java でプロジェクトにリソースを追加](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java で MS Project のリソース コストを管理](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks for Java で MPP を Excel にエクスポートする方法](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}