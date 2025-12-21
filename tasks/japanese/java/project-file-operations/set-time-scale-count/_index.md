---
date: 2025-12-21
description: Aspose.Tasks for Java を使用して、ガントチャートのビューをカスタマイズし、プロジェクトの可視化を管理し、プロジェクトを
  PDF として保存する方法を学びましょう。時間スケールのカウントを簡単に調整できます。
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ガントチャートのカスタマイズ – Aspose.TasksでMS Projectの時間スケールカウントをマスターする
url: /ja/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ガントチャートのカスタマイズ – Aspose.TasksでMS Projectのタイムスケールカウントをマスターする

## はじめに
Microsoft Projectで **customize Gantt chart** のビジュアルをカスタマイズする必要がある場合、タイムスケールのカウントを制御することが重要なテクニックです。Aspose.Tasks for Java を使用すると、プログラムで下位および中位のタイムスケール層を設定し、ティックの表示を微調整し、そして **save project as PDF** でステークホルダーと共有できます。このチュートリアルでは、環境設定からカスタマイズされたガントビューを反映した洗練された PDF の生成まで、プロセス全体を順を追って説明します。

## クイック回答
- **What does “customize Gantt chart” mean?** レポート要件に合わせて、タイムスケール層、色、レイアウトを調整することです。  
- **Which API method sets the bottom tier count?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Can I generate a PDF directly from the project?** はい—`project.save(..., SaveFileFormat.Pdf)` を使用します。  
- **Do I need a license for production use?** 本番環境で使用するにはライセンスが必要です；無料トライアルが利用可能です。  
- **Which Java version is supported?** Java 8 以上が最新の Aspose.Tasks ライブラリで動作します。

## Aspose.Tasksにおける “customize Gantt chart” とは何ですか？
**customize Gantt chart** とは、ガントチャートのビジュアルコンポーネント（タイムスケール間隔、ティックマーク、タスクバーなど）をプログラムで変更し、**manage project visualization** に合わせてチャートを調整することを指します。タイムスケールカウントを変更することで、各セグメントが表す日数、週数、月数を制御し、異なるオーディエンスに対してチャートをより分かりやすくします。

## 前提条件
1. **Java Development Environment** – JDK 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java Library** – [here](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **Basic Java Knowledge** – Java の構文とオブジェクト指向の概念に慣れていること。  

## パッケージのインポート
Java プロジェクトに必要なクラスをインポートします:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## ステップバイステップガイド

### ステップ 1: データディレクトリの設定
プロジェクトファイルの読み込み先と書き込み先を定義します:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` をマシン上の絶対パスに置き換えてください。

### ステップ 2: 新しい Project インスタンスの作成
`Project` オブジェクトを新規にインスタンス化し、すべてのタスクとビュー設定を保持させます:

```java
Project project = new Project();
```

### ステップ 3: ガントチャートビューの構成
`GanttChartView` オブジェクトを作成します—ここでチャートの外観を制御する **generate Gantt view Java** コードを生成します:

```java
GanttChartView view = new GanttChartView();
```

### ステップ 4: 下位層のタイムスケールカウントの設定
下位層を 2 つの間隔に設定し、ティックマークを非表示にします:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### ステップ 5: 中位層のタイムスケールカウントの設定
同じ設定を中位層に適用します:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### ステップ 6: カスタマイズされたビューをプロジェクトに追加
先ほど設定したビューを `Project` インスタンスに添付します:

```java
project.getViews().add(view);
```

### ステップ 7: サンプルタスクの追加（テストデータ）
カスタマイズされたガントチャートを示すために、特定の期間を持つタスクをいくつか作成します:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### ステップ 8: プロジェクトを PDF として保存
最後に、**customized Gantt chart** を含むプロジェクトを PDF ファイルにエクスポートします:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

生成された PDF は、下位および中位のタイムスケール層が **customized** されたことを示し、ステークホルダーにスケジュールの明確で印刷可能なビューを提供します。

## 一般的な問題とトラブルシューティング
- **PDF is blank** – `dataDir` パスがファイル区切り文字（`/` または `\`）で終わっていること、かつディレクトリが存在することを確認してください。  
- **Ticks still appear** – 両方の層で `setShowTicks(false)` が呼び出されていることを確認してください。  
- **Duration not applied** – 期間を作成する際に `TimeUnitType.Hour`（または適切な単位）を使用していることを確認してください。  

## よくある質問

**Q: Can Aspose.Tasks for Java handle large‑scale project files?**  
A: はい、ライブラリは大規模なプロジェクトデータの高性能処理に最適化されています。

**Q: Is Aspose.Tasks for Java compatible with different Java IDEs?**  
A: もちろんです—Eclipse、IntelliJ IDEA、NetBeans、その他の主要な IDE でシームレスに動作します。

**Q: Can I customize the appearance of Gantt charts beyond time‑scale settings?**  
A: はい、Aspose.Tasks はバーの色、フォント、グリッドラインなど、幅広いスタイリングオプションを提供しています。

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: はい、[here](https://releases.aspose.com/) から無料トライアル版を入手できます。

**Q: Where can I get support for Aspose.Tasks for Java?**  
A: Aspose.Tasks フォーラム [here](https://forum.aspose.com/c/tasks/15) でサポートと支援を受けられます。

**Q: How do I programmatically change the Gantt chart’s background color?**  
A: `java.awt.Color` をインポートした後、`view.getGanttChartProperties().setBackgroundColor(Color)` メソッドを使用します。

## 結論
これらの手順に従うことで、**customize Gantt chart** のタイムスケール層を設定し、**project visualization** を向上させ、Aspose.Tasks for Java を使用して **save project as PDF** ができるようになりました。このアプローチにより、ビジュアル出力を完全にコントロールでき、チームやクライアントと明確でプロフェッショナルなスケジュールを共有しやすくなります。

---

**最終更新日:** 2025-12-21  
**テスト済み:** Aspose.Tasks for Java 24.12 (執筆時点での最新バージョン)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}