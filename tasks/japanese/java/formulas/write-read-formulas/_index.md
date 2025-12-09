---
date: 2025-12-07
description: Aspose.Tasks for Java を使用して、プロジェクト ファイルの保存方法、MS Project の数式の書き込みと読み取り、カスタム
  フィールド数式の追加方法を学びます。
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでプロジェクトファイルを保存し、MS Projectの数式を書き込む
url: /ja/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクト ファイルの保存と Aspose.Tasks を使用した MS Project 数式の記述

## はじめに
プロジェクト管理の領域では、データの効果的な取り扱いが極めて重要です。Aspose.Tasks for Java は、Microsoft Project ファイルからデータの操作と抽出を容易にする堅牢なソリューションです。提供される強力な機能の一つは、MS Project の数式を書き込み・読み取る機能です。**数式を適用した後に *save project file* を行う方法も学べます**。これにより、変更が将来の分析のために永続化されます。本チュートリアルでは、この機能を活用してプロジェクト管理タスクを強化する手順をご案内します。

## クイック回答
- **“save project file” は何をしますか？** メモリ上のすべての変更をディスク上の .mpp ファイルに書き戻します。  
- **カスタム フィールドの数式を追加できますか？** はい。カスタム フィールドを作成し、例えば “double task cost” のような数式を割り当てることができます。  
- **コードを実行するのにライセンスが必要ですか？** 評価には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **どの IDE が最適ですか？** 任意の Java IDE（IntelliJ IDEA、Eclipse、VS Code）でサンプルをコンパイルできます。  
- **API は最新の MS Project バージョンと互換性がありますか？** Aspose.Tasks は最近のすべての .mpp フォーマットをサポートしています。

## Aspose.Tasks における “save project file” とは？
プロジェクト ファイルを保存することは、`Project` オブジェクトの現在の状態（タスク、リソース、カスタム数式を含む）を実際の Microsoft Project ファイル（`.mpp`）に永続化することを意味します。カスタム フィールドの追加やタスクコストの変更など、データを変更した後にこの操作は必須です。

## なぜカスタム フィールドを追加し、カスタム フィールド数式を作成するのか？
カスタム フィールドを追加すると、デフォルトのフィールドではカバーできない追加情報を柔軟に格納できます。**double task cost** のような数式を付与することで、計算を自動化し、手動エラーを減らし、スケジュール データの一貫性を保つことができます。

## 前提条件
1. **Java Development Kit (JDK)** – マシンに Java 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java** – [here](https://releases.aspose.com/tasks/java/) からダウンロードしてインストールしてください。  
3. **Integrated Development Environment (IDE)** – Java 開発用に好みの IDE（IntelliJ IDEA、Eclipse、VS Code など）を選択してください。  

## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## 手順 1: データ ディレクトリの設定
MS Project ファイルが格納されているフォルダーを定義します。ここでソース ファイルを読み込み、後で **save project file** を行います。
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## 手順 2: プロジェクト ファイルの読み込み
既存の Microsoft Project ファイルを `Project` オブジェクトに読み込み、内容を読み取ったり変更したりできるようにします。
```java
Project project = new Project(dataDir + "project.mpp");
```

## 手順 3: カスタム フィールドの追加とカスタム フィールド数式の作成
この手順では **add custom field** “Double Costs” を追加し、タスクの `[Cost]` を 2 倍する **create custom field formula** を作成します。これにより実質的に **double task cost** が実現されます。`setFormula` メソッドは計算式をプロジェクト ファイルに直接埋め込みます。
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```

## 手順 4: タスクの追加とコストの設定
新しいタスクを作成し、基本コストとして `100` を割り当てます。プロジェクトを保存すると、先に定義した数式によりカスタム フィールドは自動的に `200` を表示します。
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```

## 手順 5: プロジェクト ファイルの保存
最後に、すべての変更を加えた **save project file** を実行します。`save` メソッドは新しいカスタム フィールドとその計算結果を含む更新されたプロジェクトを `saved.mpp` に書き込みます。
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```

## よくある問題と解決策
| Issue | Reason | Fix |
|-------|--------|-----|
| **数式が適用されていません** | カスタム フィールドがプロジェクトの `ExtendedAttributes` コレクションに追加されていません。 | 保存前に `project.getExtendedAttributes().add(attr);` が実行されていることを確認してください。 |
| **ファイルが見つかりません** | `dataDir` パスが正しくありません。 | ディレクトリ文字列がパス区切り文字（`/` または `\\`）で終わっているか確認してください。 |
| **コストが 0 と表示されます** | 保存前にタスクのコストが設定されていません。 | `project.save` の前に `task.set(Tsk.COST, ...)` を呼び出してください。 |

## よくある質問
**Q: Aspose.Tasks はすべてのバージョンの MS Project と互換性がありますか？**  
A: はい、Aspose.Tasks は古い .mpp フォーマットから最新リリースまで、幅広い MS Project バージョンをサポートしています。

**Q: 既存の Java プロジェクトに Aspose.Tasks を統合できますか？**  
A: もちろんです。API はシームレスな統合を想定して設計されており、Aspose.Tasks の JAR をプロジェクトのクラスパスに追加するだけです。

**Q: 作成できる数式の種類に制限はありますか？**  
A: ライブラリは算術、論理、組み込み関数など、ほとんどのネイティブ MS Project 数式構文をサポートしています。複雑なカスタム関数は回避策が必要になる場合があります。

**Q: Aspose.Tasks はマルチプラットフォーム展開をサポートしていますか？**  
A: はい、Java をサポートするすべてのプラットフォーム（Windows、Linux、macOS など）で動作します。

**Q: Aspose.Tasks の技術サポートはどのように受けられますか？**  
A: コミュニティの支援は [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) で受けられます。商用ライセンスをお持ちの場合はサポートチケットを開いてください。

## 結論
本チュートリアルでは、Aspose.Tasks for Java を使用して **save project file**、**add custom field**、そして **double task cost** になる **create a custom field formula** の方法を解説しました。これらの手順に従うことで、計算を自動化し、プロジェクト データを充実させ、すべての変更を将来のレポートや分析のために永続化できるようになります。

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}