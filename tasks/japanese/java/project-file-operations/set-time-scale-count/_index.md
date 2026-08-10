---
date: 2026-03-29
description: Aspose.Tasks for Java を使用して、ガントチャートの時間スケール数をカスタマイズしながらプロジェクトの PDF ファイルを作成する方法を学びましょう。このガイドでは、ガントを
  PDF にエクスポートする際に完全なコントロールを持って、ステップバイステップで説明します。
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: プロジェクトPDFを作成 – ガントチャートの時間スケールをカスタマイズ
url: /ja/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクト PDF を作成 – ガントチャートの時間スケールをカスタマイズ

## はじめに
完璧に調整されたガントチャートを反映した **プロジェクト PDF を作成** する必要がある場合、時間スケールのカウントを制御することが鍵です。Aspose.Tasks for Java を使用すると、プログラムで下部および中部の時間スケール層を設定し、目盛りを非表示にし、そして **プロジェクトを PDF として保存** して簡単に配布できます。このチュートリアルでは、開発環境の設定からカスタマイズされたガントビューを示す洗練された PDF の生成まで、必要なすべての手順を説明します。

## クイック回答
- **“customize Gantt chart” とは何ですか？** レポートのニーズに合わせて時間スケール層、色、レイアウトを調整することです。  
- **どの API メソッドが下部層のカウントを設定しますか？** `view.getBottomTimescaleTier().setCount(int)`。  
- **プロジェクトから直接 PDF を生成できますか？** はい—`project.save(..., SaveFileFormat.Pdf)` を使用します。  
- **本番で使用するにはライセンスが必要ですか？** 商用ライセンスが必要です。無料トライアルも利用可能です。  
- **サポートされている Java バージョンはどれですか？** Java 8 以上であれば、最新の Aspose.Tasks ライブラリが動作します。

## Aspose.Tasks における “customize Gantt chart” とは何ですか？
ガントチャートのカスタマイズとは、プログラムで視覚コンポーネント（時間スケールの間隔、目盛り、タスクバーなど）を変更し、チャートが **プロジェクトの可視化を管理** したい方法に合わせることです。時間スケールのカウントを変更することで、各セグメントが表す日数、週数、月数を制御でき、さまざまな対象者にとってチャートがより分かりやすくなります。

## カスタマイズされたガントチャートでプロジェクト PDF を作成する理由
- **ステークホルダー向け出力:** PDF は普遍的に閲覧可能で、全員が同じスケジュールレイアウトを見ることができます。  
- **印刷に適した形式:** 時間スケール層を正確に制御することで、混み合ったり曖昧な印刷物を防げます。  
- **自動化:** PDF 生成を CI パイプラインやレポートサービスに統合し、手作業をゼロにします。  

## 前提条件
開始する前に、以下が揃っていることを確認してください：
1. **Java 開発環境** – JDK 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java ライブラリ** – [here](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **基本的な Java 知識** – Java の構文とオブジェクト指向の概念に慣れていること。  

## パッケージのインポート
Java プロジェクトに必要なクラスをインポートします：

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## ステップバイステップ ガイド

### 手順 1: データディレクトリの設定
プロジェクトファイルの読み取り先と書き込み先を定義します：

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` をマシン上の絶対パスに置き換えてください。

### 手順 2: 新しい Project インスタンスの作成
すべてのタスクとビュー設定を保持する新しい `Project` オブジェクトをインスタンス化します：

```java
Project project = new Project();
```

### 手順 3: ガントチャートビューの構成
`GanttChartView` オブジェクトを作成します—ここでチャートの外観を制御する **Gantt view Java** コードを **生成** します：

```java
GanttChartView view = new GanttChartView();
```

### 手順 4: 下部層の時間スケールカウントの設定
下部層を 2 つの間隔に設定し、目盛りを非表示にします：

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### 手順 5: 中部層の時間スケールカウントの設定
同じ設定を中部層に適用します：

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### 手順 6: カスタマイズされたビューをプロジェクトに追加
先ほど設定したビューを `Project` インスタンスに添付します：

```java
project.getViews().add(view);
```

### 手順 7: サンプルタスクの追加（テストデータ）
カスタマイズされたガントチャートを示すために、特定の期間を持つタスクをいくつか作成します：

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### 手順 8: プロジェクトを PDF として保存
最後に、**カスタマイズされたガントチャート** を含むプロジェクトを PDF ファイルにエクスポートします：

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

生成された PDF は、下部および中部の時間スケール層が **カスタマイズ** された様子を示し、ステークホルダーに明確で印刷可能なスケジュールビューを提供します。

## よくある問題とトラブルシューティング
- **PDF が空白** – `dataDir` パスがファイル区切り文字（`/` または `\`）で終わり、ディレクトリが存在することを確認してください。  
- **目盛りがまだ表示される** – 両方の層で `setShowTicks(false)` が呼び出されていることを確認してください。  
- **期間が適用されない** – 期間を作成する際に `TimeUnitType.Hour`（または適切な単位）を使用していることを確認してください。

## よくある質問

**Q: Aspose.Tasks for Java は大規模なプロジェクトファイルを処理できますか？**  
A: はい、このライブラリは大量のプロジェクトデータを高性能に処理できるよう最適化されています。

**Q: Aspose.Tasks for Java はさまざまな Java IDE と互換性がありますか？**  
A: もちろんです – Eclipse、IntelliJ IDEA、NetBeans などの一般的な IDE でシームレスに動作します。

**Q: 時間スケール設定以外でガントチャートの外観をカスタマイズできますか？**  
A: はい、Aspose.Tasks はバーの色、フォント、グリッドラインなど、幅広いスタイリングオプションを提供します。

**Q: Aspose.Tasks for Java のトライアル版はありますか？**  
A: はい、[here](https://releases.aspose.com/) から無料トライアル版を入手できます。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
A: Aspose.Tasks フォーラム [here](https://forum.aspose.com/c/tasks/15) でサポートと支援を受けられます。

**Q: プログラムでガントチャートの背景色を変更するにはどうすればよいですか？**  
A: `java.awt.Color` をインポートした後、`view.getGanttChartProperties().setBackgroundColor(Color)` メソッドを使用します。

## 結論
これらの手順に従うことで、完全にカスタマイズされたガントチャートの時間スケールを持つ **プロジェクト PDF を作成** し、**プロジェクトの可視化** を向上させ、Aspose.Tasks for Java を使用して **プロジェクトを PDF として保存** する方法を学びました。このアプローチにより、視覚的な出力を完全に制御でき、チームやクライアントと明確でプロフェッショナルなスケジュールを共有しやすくなります。

---

**最終更新日:** 2026-03-29  
**テスト環境:** Aspose.Tasks for Java (latest)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}