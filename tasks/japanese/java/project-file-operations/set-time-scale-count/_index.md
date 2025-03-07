---
title: Aspose.Tasks での MS プロジェクトのタイム スケール カウントのマスタリング
linktitle: Aspose.Tasks でタイム スケール カウントを設定する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して MS Project でタイム スケール カウントを効果的に管理する方法を学びます。プロジェクトの視覚化と管理を簡単に最適化します。
weight: 22
url: /ja/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での MS プロジェクトのタイム スケール カウントのマスタリング

## 導入
MS Project でのタイム スケール数の管理は、プロジェクトの視覚化と管理に大きな影響を与える可能性があります。プロジェクト管理タスクをプログラムで処理するための強力な API である Aspose.Tasks for Java を使用すると、タイム スケール カウントを効率的に操作して、プロジェクト ビューを特定のニーズに合わせて調整できます。
## 前提条件
始める前に、次のものが整っていることを確認してください。
1. Java 開発環境: システムに Java Development Kit (JDK) がインストールされていることを確認してください。
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリをダウンロードしてインストールします。から入手できます[ここ](https://releases.aspose.com/tasks/java/).
3. Java プログラミングの基礎知識: Java プログラミング言語に精通していると役立ちます。

## パッケージのインポート
必要なパッケージを Java プロジェクトにインポートします。
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## ステップ 1: データ ディレクトリを設定する
プロジェクト ファイルが保存されるデータ ディレクトリへのパスを定義します。
```java
String dataDir = "Your Data Directory";
```
交換する`"Your Data Directory"`データ ディレクトリへのパスを置き換えます。
## ステップ 2: プロジェクト インスタンスを作成する
新しいインスタンスを作成する`Project`物体：
```java
Project project = new Project();
```
これにより、新しいプロジェクト オブジェクトが作成されます。
## ステップ 3: ガント チャート ビューを構成する
を作成します`GanttChartView`ガント チャート ビューを構成するオブジェクト:
```java
GanttChartView view = new GanttChartView();
```
## ステップ 4: 最下層のタイムスケールカウントを設定する
一番下のタイムスケール層のカウントとティックの表示を設定します。
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
これは、間隔の数と、最下層のティックを表示するかどうかを指定します。
## ステップ 5: 中間層のタイム スケール カウントを設定する
同様に、中間のタイムスケール層を構成します。
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## ステップ 6: ビューをプロジェクトに追加する
構成されたビューをプロジェクトに追加します。
```java
project.getViews().add(view);
```
これにより、カスタマイズされたビューがプロジェクトに追加されます。
## ステップ 7: テスト データをプロジェクトに追加する
デモンストレーション用にいくつかのテスト データをプロジェクトに追加します。
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
これにより、指定された期間を持つ 2 つのタスクが作成されます。
## ステップ 8: プロジェクトを PDF として保存する
プロジェクトを PDF ファイルとして保存します。
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
これにより、適用された構成を含むプロジェクトが PDF ファイルに保存されます。

## 結論
Aspose.Tasks for Java を使用して MS Project のタイム スケール数を効果的に管理すると、プロジェクト ビューをカスタマイズして視覚化と管理を改善できるようになります。
## よくある質問
### Q: Aspose.Tasks for Java は大規模なプロジェクト ファイルを処理できますか?
A: はい、Aspose.Tasks for Java は大規模なプロジェクト ファイルを効率的に処理できます。
### Q: Aspose.Tasks for Java はさまざまな Java IDE と互換性がありますか?
A: はい、Aspose.Tasks for Java は、Eclipse や IntelliJ IDEA などの一般的な Java 統合開発環境 (IDE) とシームレスに動作します。
### Q: Aspose.Tasks for Java を使用してガント チャートの外観をカスタマイズできますか?
A: もちろん、Aspose.Tasks for Java は、要件に応じてガント チャートの外観をカスタマイズする広範な機能を提供します。
### Q: Aspose.Tasks for Java の試用版はありますか?
 A: はい、以下から無料試用版を入手できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java のサポートはどこで入手できますか?
 A: Aspose.Tasks フォーラムでサポートと支援を見つけることができます。[ここ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
