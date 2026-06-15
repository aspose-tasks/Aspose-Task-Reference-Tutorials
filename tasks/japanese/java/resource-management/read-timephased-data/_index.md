---
date: 2026-06-15
description: Aspose.Tasks for Java を使用して MS Project のリソースから時間分割データを抽出する方法を学びます。ID
  でリソースを取得するステップバイステップガイド。
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Aspose.Tasks でリソースの時間分割データを読み取る
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks でリソースの時間分割データを読み取る – ID でリソースを取得
url: /ja/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のリソースの時間別データを読み取る

## はじめに
このチュートリアルでは、**how to get resource by id** を学び、Aspose.Tasks for Java を使用してリソースの時間別データを読み取ります。プロジェクトフォルダーの設定から作業およびコストの時間別値の出力まで、各ステップを順に解説するので、Microsoft Project ファイルからプログラムで貴重なスケジューリング情報を抽出できます。Aspose.Tasks for Java は、Microsoft Project をインストールせずに Microsoft Project ファイルの作成、読み取り、変更、変換を可能にする包括的な API で、幅広いプロジェクト管理機能とフォーマットに対応しています。

## クイック回答
- **“get resource by id” は何をしますか？** `Project` から一意の識別子を使用して特定の `Resource` オブジェクトを取得します。  
- **どのライブラリが時間別データを処理しますか？** Aspose.Tasks for Java が `Resource.getTimephasedData` API を提供します。  
- **ライセンスは必要ですか？** 開発用途は無料トライアルで動作しますが、製品環境では商用ライセンスが必要です。  
- **大規模プロジェクトを読み取れますか？** はい。Aspose.Tasks はファイル全体をメモリに読み込まずに、最大 10,000 タスクのファイルを処理できます。  
- **必要な Java バージョンは？** Java 8 以上で、主要な JDK とすべて互換性があります。

## “get resource by id” とは何ですか？
`get resource by id` は、ロード済みの `Project` からリソースの数値 ID を使って `Resource` インスタンスを取得するメソッド呼び出しです。この操作により、割り当て、カレンダー、カスタム フィールドなどの詳細プロパティへ正確にアクセスでき、特定リソースに関連する時間別作業やコスト データの抽出に不可欠です。

## 時間別データに Aspose.Tasks を使用する理由
Aspose.Tasks は **50 以上の入力・出力フォーマット**（MPP、XML、CSV など）をサポートし、マルチイヤーのスケジュールにわたるリソースの時間別作業・コスト値を低メモリで抽出できます。API はデフォルトで 15 分間隔のデータを返し、レポートやカスタム分析に細かなインサイトを提供します。

## 前提条件
開始する前に、以下の前提条件を満たしていることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。[ウェブサイト](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)からダウンロードし、インストール手順に従ってください。  
2. Aspose.Tasks for Java Library: [ダウンロードページ](https://releases.aspose.com/tasks/java/)から Aspose.Tasks for Java ライブラリを取得し、ドキュメントに記載のインストール手順に従ってください。

## パッケージのインポート
最初のステップは、必要な Aspose.Tasks クラスを Java ソース ファイルにインポートすることです。

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## 手順 1: データディレクトリの設定
まず、MS Project ファイルが格納されているディレクトリを定義します。データ フォルダーをソースコードと分離しておくと、プロジェクトの保守性が向上します。

```java
String dataDir = "Your Data Directory";
```

## 手順 2: MS Project テンプレートファイルの読み取り
MS Project テンプレート ファイル名を指定します。テンプレートを使用することで、異なるプロジェクト間で列設定を統一できます。

```java
String fileName = "ResourceTimephasedData.mpp";
```

## 手順 3: 入力ファイルを Project として読み込む
`Project` クラスは Aspose.Tasks のコア オブジェクトで、Microsoft Project ファイルをメモリ上に表現します。ファイルをロードすると、タスク、リソース、スケジュールへプログラムからアクセスできるようになります。

```java
Project project = new Project(dataDir + fileName);
```

## 手順 4: ID でリソースを取得する
特定のリソースを取得するには、`getResources().getById(id)` メソッドを呼び出します。これがキーワードで参照されている正確な操作です。

```java
Resource resource = project.getResources().getByUid(1);
```

## 手順 5: リソース作業の時間別データを出力する
`Resource` オブジェクトを取得したら、`resource.getTimephasedData(ResourceTimephasedDataType.Work)` を呼び出して、時間ごとの作業割り当てを取得できます。返されるコレクションは `TimephasedData` オブジェクトを含み、各間隔の開始日、終了日、作業量が格納されています。

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## 手順 6: リソースコストの時間別データを出力する
同様に、`resource.getTimephasedData(ResourceTimephasedDataType.Cost)` は同じ時間間隔で分割されたコスト情報を返します。予算策定やコスト追跡レポートに役立ちます。

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## 1 行でリソースを ID で取得する方法
プロジェクトをロードした後、`project.getResources().getById(5)` を呼び出します—**5** を必要なリソース ID に置き換えてください。この単一呼び出しで `Resource` オブジェクトが返され、その後で時間別データ、割り当て、カスタム フィールドなどを問い合わせられます。リソースは内部でインデックス化されているため、メソッドは O(1) 時間で実行されます。

## よくある問題と解決策
- **Resource not found** – プロジェクト ファイルにその ID が存在することを確認してください。ID は 1 から始まり、リソースごとに一意です。  
- **Empty timephased data** – リソースに作業またはコストの割り当てがあるか確認してください。割り当てがない場合、コレクションは空になります。  
- **Large file performance** – 500 MB を超えるプロジェクトでは、`Project.setLoadOptions(LoadOptions.fromFile(...))` を使用して遅延ロードを有効にしてください。

## よくある質問

**Q: Aspose.Tasks は Microsoft Project 以外のプロジェクト ファイルも扱えますか？**  
A: はい。Aspose.Tasks は MPP、XML、CSV など複数のフォーマットをサポートし、異なる標準間での読み書きが可能です。

**Q: Aspose.Tasks はさまざまな Java 開発環境に対応していますか？**  
A: もちろんです。主要な IDE（IntelliJ IDEA、Eclipse、NetBeans）やビルド ツール（Maven、Gradle）で動作します。

**Q: Aspose.Tasks でプロジェクト データを操作できますか？**  
A: はい。API を通じてタスク、リソース、割り当て、カスタム フィールドの作成、変更、削除が可能です。

**Q: Aspose.Tasks はエンタープライズ規模のプロジェクトに適していますか？**  
A: 適しています。エンタープライズでは、Aspose.Tasks を使用して大量処理、バッチ変換、サーバー側レポートを行い、Microsoft Project のインストールが不要です。

**Q: Aspose.Tasks 使用中に問題が発生した場合、どこでサポートを受けられますか？**  
A: [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) でコミュニティやサポートチームから支援を受けられます。

## 結論
このチュートリアルでは、**get resource by id** の取得方法と、Aspose.Tasks for Java を使用してリソースの時間別作業およびコスト データを読み取る手順を学びました。これらの手順に従うことで、プロジェクト ファイルから貴重なスケジューリング情報を効率的に抽出し、カスタム レポートや分析パイプラインに統合できます。

---

**最終更新日:** 2026-06-15  
**テスト環境:** Aspose.Tasks 24.11 for Java  
**著者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks for Java を使用してプロジェクトにリソースを追加する](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java で MS Project のリソース コストを管理する](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks で MS Project カレンダーから Java の作業週を読み取る](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}