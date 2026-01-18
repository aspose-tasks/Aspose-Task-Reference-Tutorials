---
date: 2026-01-18
description: Aspose.Tasks を使用して、MS Project を使用せずにベースラインを設定しながら、Java でタスクリストを作成し、Microsoft
  Project にタスクを追加する方法を学びましょう。
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用した Java でのタスクリスト作成 – MS Project ベースライン
url: /ja/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# タスク一覧 Java の作成 – Aspose.Tasks を使用した MS Project ベースライン

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用して Microsoft Project のタスクベースラインを生成することで、**タスク一覧 Java を作成**します。Aspose.Tasks を使用すれば、Microsoft Project をインストールせずにプロジェクトファイルを操作でき、**Microsoft Project にタスクを追加**したり、リソースを操作したり、さらには **MS Project なしでベースラインを設定** することも、純粋な Java コードだけで行えます。

## クイック回答
- **Aspose.Tasks は何をしますか？** Microsoft Project を使用せずに、Microsoft Project ファイルの作成、読み取り、編集を行うための Java API を提供します。  
- **Microsoft Project をインストールする必要がありますか？** いいえ、Aspose.Tasks は単独で動作します。  
- **必要な Java バージョンは？** JDK 8 以上。  
- **単一タスクのベースラインを設定できますか？** はい、タスクリストと共に `setBaseline` を使用します。  
- **本番環境でライセンスが必要ですか？** はい、商用ライセンスを取得すると評価版の制限が解除されます。

## タスクベースラインとは何ですか？
タスクベースラインは、タスクの元々計画された開始日、終了日、作業量を記録したものです。実際の進捗を元の計画と比較するための基準点として機能します。

## なぜ Aspose.Tasks を使用してタスク一覧 Java を作成するのか？
- **MS Project への依存なし** – サーバー側の自動化に最適です。  
- **フルコントロール** – Java コードを通じてタスク、リソース、カレンダーを完全に制御できます。  
- **バージョン間互換性** – Project 2007 から 2024 のファイルに対応しています。

## 前提条件
1. **Java Development Kit (JDK)** – JDK 8 以上をインストールしてください。  
2. **Aspose.Tasks for Java** – ライブラリは [download link](https://releases.aspose.com/tasks/java/) からダウンロードしてください。

## パッケージのインポート
Java プロジェクトで Aspose.Tasks を使用し始めるには、必要なパッケージをインポートします:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## ステップ 1: Project オブジェクトの作成
ここでは新しい `Project` オブジェクトをインスタンス化します。これは、タスク一覧を保持する MS Project ファイルを表します。
```java
Project project = new Project();
```

## ステップ 2: プロジェクトにタスクを追加
`getRootTask()` を使用してプロジェクト階層のルートにアクセスし、**Microsoft Project にタスクを追加**します。文字列 `"Task"` はタスク名です。必要に応じて任意の説明に置き換えることができます。
```java
Task task = project.getRootTask().getChildren().add("Task");
```

## ステップ 3: 指定タスクのベースライン設定
**MS Project なしでベースラインを設定**するには、ベースラインを設定したいタスクのリスト（ここでは `myList`）を作成し、`setBaseline` に渡します。選択的なベースラインが必要な場合は、追加したタスクで `myList` を構成してください。
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```

## ステップ 4: プロジェクト全体のベースライン設定
プロジェクト全体を一度にベースライン設定したい場合は、目的の `BaselineType` を指定して `setBaseline` を呼び出すだけです。
```java
project.setBaseline(BaselineType.Baseline);
```

## Aspose.Tasks を使用して Microsoft Project にタスクを追加する方法
上記の単一タスクに加えて、複数のタスクやサブタスクを追加したり、リソースを割り当てたりできます。`add()` を呼び出すたびに `Task` オブジェクトが返され、さらに（期間、開始日など）を設定できます。

## MS Project なしでベースラインを設定する方法
Aspose.Tasks を使用すれば、コードだけでベースラインを作成できます。`BaselineType` 列挙体を変更することで、異なるベースラインタイプ（Baseline、Baseline1‑Baseline10）を設定でき、MS Project を開くことなく複数のリビジョンベースラインを追跡できます。

## 一般的な問題と解決策
- **ベースラインが表示されない:** ベースライン設定後に `project.save("output.mpp")` を呼び出していることを確認してください（簡略のためここでは保存手順を省略しています）。  
- **タスク一覧が空になる:** 正しい親（`getRootTask()` またはサブタスク）にタスクを追加しているか確認してください。  
- **バージョン不一致エラー:** 最新の Aspose.Tasks JAR を使用して、最新の .mpp フォーマットとの互換性を確保してください。

## よくある質問

**Q: Microsoft Project をインストールせずに Aspose.Tasks for Java を使用できますか？**  
A: はい、Aspose.Tasks は単独で動作し、ホストマシンに Microsoft Project は必要ありません。

**Q: Aspose.Tasks for Java はさまざまなバージョンの Microsoft Project と互換性がありますか？**  
A: はい、完全に対応しています。このライブラリは 2007 年から最新の 2024 年リリースまでの Project ファイルをサポートします。

**Q: Aspose.Tasks for Java を使ってプロジェクトのリソースを操作できますか？**  
A: はい、タスクと同様にリソースをプログラムで追加、更新、削除できます。

**Q: Aspose.Tasks for Java はタスクの依存関係設定をサポートしていますか？**  
A: はい、`TaskLink` クラスを使用して前任者‑後続者の関係を定義できます。

**Q: Aspose.Tasks for Java の技術サポートは利用できますか？**  
A: はい、[サポートフォーラム](https://forum.aspose.com/c/tasks/15) で Aspose のスタッフやコミュニティが質問に回答しています。

## 結論
これらの手順に従うことで、Aspose.Tasks を使用して **タスク一覧 Java を作成**し、**Microsoft Project にタスクを追加**し、**MS Project なしでベースラインを設定**する方法を学びました。このアプローチにより、プロジェクトの自動化が簡素化され、デスクトップ版 Project のインストールが不要になり、プロジェクトデータを完全にプログラムで制御できるようになります。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-01-18  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose