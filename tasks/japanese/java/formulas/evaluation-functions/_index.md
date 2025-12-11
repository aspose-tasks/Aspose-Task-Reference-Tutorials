---
date: 2025-12-09
description: Java を使用してプロジェクト オブジェクトを作成し、Aspose.Tasks の数式で評価関数をサポートする方法を学びます。タスクの拡張属性の作成方法を確認してください。
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Javaでプロジェクトオブジェクトを作成 – Aspose.Tasksの評価機能をサポート
url: /ja/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks フォーミュラで評価関数をサポートする

## はじめに
Aspose.Tasks for Java を使用すると、**create project object java** インスタンスを作成し、Microsoft Project の関数を Java コード内で直接評価できます。これらの数式を埋め込むことで、複雑な計算を実行し、カスタムレポートを生成し、開発環境を離れることなくプロジェクト分析を自動化できます。このチュートリアルでは、プロジェクトオブジェクトの設定からカスタムデータを保持できる拡張属性の追加まで、全工程を順に解説します。

## クイック回答
- **“create project object java” とは何ですか？** メモリ上の `Project` インスタンスを作成し、プログラムから操作できるようにします。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（公式サイトからダウンロード）。  
- **ライセンスは必要ですか？** 本番利用には一時ライセンスまたはフルライセンスが必要です。無料トライアルも利用可能です。  
- **カスタムフィールドは使用できますか？** はい。タスクに拡張属性を定義して付与できます。  
- **すべての Project ファイル形式に対応していますか？** Aspose.Tasks は MPP、MPT、XML 形式をサポートしています。

## 前提条件
開始する前に、以下が揃っていることを確認してください：

1. **Java 開発環境** – JDK 8 以上と IntelliJ IDEA や Eclipse などの IDE。  
2. **Aspose.Tasks for Java ライブラリ** – [Aspose.Tasks for Java ダウンロードページ](https://releases.aspose.com/tasks/java/) からダウンロードし、プロジェクトに組み込んでください。

## パッケージのインポート
Java クラスに Aspose.Tasks の名前空間を追加し、プロジェクト、タスク、拡張属性を操作できるようにします：

```java
import com.aspose.tasks.*;
```

## 手順 1: Create Project Object Java の作成
新しい `Project` オブジェクトをインスタンス化します。これがタスク、リソース、カスタムデータすべてのコンテナとなります。

```java
Project project = new Project();
```

上記の行は **creates project object java** を作成し、空の状態でカスタマイズ可能な状態になります。

## 手順 2: 拡張属性の作成方法
各タスクのカスタム数値データ（例: 正弦値）を格納する拡張属性を定義します。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

ここでは `Number` 型で “Sine” という名前の **create extended attribute** を作成し、タスクに関連付けます。

## 手順 3: プロジェクトへの拡張属性の追加
属性定義をプロジェクトに登録し、すべてのタスクが参照できるようにします。

```java
project.getExtendedAttributes().add(attr);
```

## 手順 4: 新しいタスクの作成
プロジェクトのルートタスクの下に “Task” というシンプルなタスクを追加します。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 手順 5: タスクへの拡張属性の関連付け
先に定義した拡張属性を新しく作成したタスクにリンクします。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

これでタスクはカスタムの “Sine” フィールドを保持し、数式や計算で使用できます。

## なぜ評価関数を使用するのか？
Aspose.Tasks の数式に MS Project の関数を埋め込むことで、以下が可能になります：

- 外部ツールを使用せずに、オンザフライ計算（例: `Sin([Start])`）を実行できます。  
- すべてのプロジェクトロジックを単一の保守しやすいコードベースに保てます。  
- リアルタイムのデータ変更を反映した動的レポートを生成できます。

## よくある問題と解決策
| Issue | Solution |
|-------|----------|
| **Formula returns `NaN`** | カスタムフィールドの型が期待される数値型と一致していることを確認してください。 |
| **Extended attribute not visible** | 属性定義がタスク作成 **前** にプロジェクトに追加されていることを確認してください。 |
| **License exception** | 一時ライセンスまたはフルライセンスをインストールしてください。トライアルモードでは一部機能が制限される場合があります。 |

## よくある質問

**Q: Aspose.Tasks for Java は複雑な MS Project の数式を処理できますか？**  
A: はい、Aspose.Tasks for Java は幅広い MS Project 関数の評価をサポートしており、Java アプリケーション内で複雑な計算が可能です。

**Q: Aspose.Tasks for Java はさまざまなバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: はい、Aspose.Tasks for Java は MPP、MPT、XML 形式を含むさまざまなバージョンの Microsoft Project ファイルをサポートしています。

**Q: 購入前に Aspose.Tasks for Java を試すことはできますか？**  
A: はい、ウェブサイトの [here](https://purchase.aspose.com/buy) から Aspose.Tasks for Java の無料トライアル版をダウンロードできます。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
A: Aspose.Tasks コミュニティフォーラム [here](https://forum.aspose.com/c/tasks/15) でサポートを受けられます。

**Q: Aspose.Tasks for Java 用の一時ライセンスはありますか？**  
A: はい、テスト目的の一時ライセンスは Aspose のウェブサイト [here](https://purchase.aspose.com/temporary-license/) から取得できます。

**最終更新日:** 2025-12-09  
**テスト環境:** Aspose.Tasks for Java 24.10  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}