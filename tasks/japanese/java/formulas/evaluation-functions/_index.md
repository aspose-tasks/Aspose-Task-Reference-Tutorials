---
date: 2026-02-13
description: Javaでプロジェクトオブジェクトを作成し、拡張属性を追加し、Aspose.Tasksの評価機能を使用してプロジェクトレポートを生成する方法を学びます。
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: プロジェクトレポートの生成 – Javaでプロジェクトオブジェクトを作成
url: /ja/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks フォーミュラで評価関数をサポート

## はじめに
Aspose.Tasks for Java を使用すると、Java で **プロジェクト オブジェクト** を作成し、Microsoft Project の関数をコード内で直接評価して **プロジェクト レポートを生成** できます。これらのフォーミュラを埋め込むことで、複雑な計算を実行し、カスタム レポートを作成し、開発環境を離れることなくプロジェクト分析を自動化できます。このチュートリアルでは、プロジェクト オブジェクトの作成、拡張属性の追加、評価関数を使用した **カスタム フィールド タスク** データの **追加** 方法を順を追って説明します。

## クイック アンサー
- **「create project object java」とは何ですか？** メモリ内に `Project` インスタンスを作成し、プログラムから操作できるようにします。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（公式サイトからダウンロード）。  
- **ライセンスは必要ですか？** 本番利用には一時ライセンスまたはフル ライセンスが必要です。無料トライアルも利用可能です。  
- **カスタム フィールドは使用できますか？** はい。タスクに **拡張属性** を追加してカスタム フィールドとして扱えます。  
- **すべての Project ファイル形式に対応していますか？** Aspose.Tasks は MPP、MPT、XML 形式をサポートしています。

## 前提条件
開始する前に、以下を用意してください。

1. **Java 開発環境** – JDK 8 以上と IntelliJ IDEA または Eclipse などの IDE。  
2. **Aspose.Tasks for Java ライブラリ** – [Aspose.Tasks for Java ダウンロードページ](https://releases.aspose.com/tasks/java/) からダウンロードし、プロジェクトに組み込んでください。

## パッケージのインポート
プロジェクト、タスク、拡張属性を操作できるように、Java クラスに Aspose.Tasks 名前空間を追加します。

```java
import com.aspose.tasks.*;
```

## プロジェクト レポートの生成 – Create Project Object Java
新しい `Project` オブジェクトをインスタンス化します。これがすべてのタスク、リソース、カスタム データのコンテナになります。

```java
Project project = new Project();
```

上記の行は **create project object java** を作成し、空の状態からカスタマイズできるようにします。

## 拡張属性の追加方法
各タスクにカスタム数値データ（例: 正弦値）を格納する拡張属性を定義します。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

ここでは `Number` 型の「Sine」という名前の **拡張属性** を追加し、タスクに関連付けています。

## 拡張属性をプロジェクトに登録
属性定義をプロジェクトに登録し、すべてのタスクが参照できるようにします。

```java
project.getExtendedAttributes().add(attr);
```

## 新しいタスクの作成
プロジェクトのルート タスクの下に、シンプルなタスク「Task」を追加します。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## タスクに拡張属性を関連付け
先に定義した拡張属性を新しく作成したタスクにリンクします。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

これでタスクはカスタム「Sine」フィールドを保持し、フォーミュラや計算で使用できます。これが **カスタム フィールド タスク** データをプログラムで **追加** する方法です。

## なぜ評価関数を使用するのか？
Aspose.Tasks のフォーミュラに MS Project 関数を埋め込むことで、次のことが可能になります。

- 外部ツールなしでオンザフライ計算（例: `Sin([Start])`）を実行。  
- プロジェクト ロジックを単一の保守しやすいコードベースに統合。  
- リアルタイム データ変更を反映した動的レポートを生成し、**プロジェクト レポートを自動生成** できる。

## よくある問題と解決策
| 問題 | 解決策 |
|------|--------|
| **フォーミュラが `NaN` を返す** | カスタム フィールドの型が期待する数値型と一致しているか確認してください。 |
| **拡張属性が表示されない** | タスクを作成する **前に** 属性定義がプロジェクトに追加されていることを確認してください。 |
| **ライセンス例外が発生** | 一時ライセンスまたはフル **Aspose.Tasks ライセンス** をインストールしてください。トライアル モードでは一部機能が制限される場合があります。 |
| **一時ライセンスがない** | Aspose のウェブサイトから **一時 Aspose ライセンス** を取得してください。 |

## FAQ

**Q: Aspose.Tasks for Java は複雑な MS Project フォーミュラを処理できますか？**  
A: はい、Aspose.Tasks for Java は幅広い MS Project 関数の評価をサポートしており、Java アプリケーション内で複雑な計算が可能です。

**Q: Aspose.Tasks for Java はさまざまなバージョンの Microsoft Project ファイルに対応していますか？**  
A: はい、MPP、MPT、XML 形式を含む多数の Microsoft Project ファイル バージョンをサポートしています。

**Q: 購入前に Aspose.Tasks for Java を試すことはできますか？**  
A: はい、[こちら](https://purchase.aspose.com/buy) から無料トライアル版をダウンロードできます。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
A: [こちら](https://forum.aspose.com/c/tasks/15) の Aspose.Tasks コミュニティ フォーラムでサポートを受けられます。

**Q: Aspose.Tasks for Java 用の一時ライセンスはありますか？**  
A: はい、[こちら](https://purchase.aspose.com/temporary-license/) からテスト用の一時ライセンスを取得できます。

## 結論
本手順に従うことで、**プロジェクト オブジェクトの作成**、**拡張属性の追加**、評価関数を活用した **プロジェクト レポートの自動生成** 方法を学びました。この基盤を拡張して、より高度なプロジェクト分析、カスタム ダッシュボード、または自動スケジューリング ツールを構築でき、すべて Aspose.Tasks for Java が支えます。

---

**最終更新日:** 2026-02-13  
**テスト環境:** Aspose.Tasks for Java 24.10  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}