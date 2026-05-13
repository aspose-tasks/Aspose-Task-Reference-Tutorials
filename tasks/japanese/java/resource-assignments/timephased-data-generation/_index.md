---
date: 2026-01-10
description: Aspose.Tasks for Java を使用してリソース割り当てのコンターを変更し、タイムフェーズ データを生成する方法を学び、プロジェクト管理の効率を向上させましょう。
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksで時間相関データのコンツアを変更する方法
url: /ja/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用したタイムフェーズ データのコンター変更方法

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用してリソース割り当ての **コンターを変更** し、タイムフェーズ データを生成する方法を紹介します。タイムフェーズ データは、プロジェクトのタイムライン上での作業の分布を示し、スケジュールの微調整、作業負荷のバランス、データに基づく意思決定を可能にします。

## クイック回答
- **コンターとは何ですか？** 作業コンターは、タスクの期間全体にわたって労力がどのように分配されるかを定義します（例: Flat、Turtle、Bell）。  
- **コンターを変更する理由は？** 前倒しや後倒しなど、現実的な作業パターンを反映させるためです。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（最新バージョン）。  
- **ライセンスは必要ですか？** はい、実稼働環境では有効な Aspose.Tasks ライセンスが必要です。  
- **結果をコンソールで確認できますか？** サンプルは各タイムフェーズ セグメントの開始日と値を出力します。

## 「コンターの変更方法」とは何ですか？
コンターを変更するとは、`ResourceAssignment` の `WORK_CONTOUR` プロパティを更新することです。Aspose.Tasks では、Flat、Turtle、Bell など、作業が時間とともにどのように割り当てられるかを決定する事前定義されたコンターが複数用意されています。

## なぜ Aspose.Tasks を使用してタイムフェーズ データを生成するのか？
- **正確なレポート:** レポート ツール向けに正確な作業分布をエクスポートできます。  
- **シナリオプランニング:** 元のスケジュールを変更せずに、さまざまなコンターをテストできます。  
- **自動化:** CI パイプラインに統合し、プロジェクトの健全性を自動的に検証できます。

## 前提条件
開始する前に、以下の前提条件を満たしていることを確認してください：
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。JDK は [こちら](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) からダウンロードしてインストールできます。  
2. Aspose.Tasks for Java Library: Aspose.Tasks for Java ライブラリが必要です。ライブラリは [ウェブサイト](https://releases.aspose.com/tasks/java/) からダウンロードできます。

## パッケージのインポート
まず、Aspose.Tasks を使用するために必要なパッケージをインポートしましょう：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## ステップ 1: ソース MPP ファイルを読み込む
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## ステップ 2: タスクとリソース割り当てを取得する
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## コンターの変更方法 – フラット（デフォルト）
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## コンターの変更方法 – タートル
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## コンターの変更方法 – バックロード
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## コンターの変更方法 – フロントロード
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## コンターの変更方法 – ベル
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## コンターの変更方法 – アーリーピーク
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## コンターの変更方法 – レイトピーク
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## コンターの変更方法 – ダブルピーク
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 一般的な問題とヒント
- **コンターが更新されませんか？** タイムフェーズ データを取得する *前に* `firstRA.set(Asn.WORK_CONTOUR, …)` を呼び出していることを確認してください。  
- **予期しない値が出ますか？** ソース MPP のタスク開始日と終了日が正しく設定されているか確認してください。  
- **パフォーマンスのヒント:** 複数のコンターを反復処理する際は、不要なファイル I/O を避けるために同じ `Project` インスタンスを再利用してください。

## よくある質問

### Aspose.Tasks を他の Java ライブラリと併用できますか？
はい、Aspose.Tasks は他の Java ライブラリと統合してプロジェクト管理機能を拡張できます。

### Aspose.Tasks は大規模エンタープライズ プロジェクトに適していますか？
もちろんです。Aspose.Tasks は規模を問わず、特に大規模エンタープライズ プロジェクトにも対応できるよう設計されています。

### Aspose.Tasks はさまざまなプロジェクト ファイル形式をサポートしていますか？
はい、MPP、XML、MPX など、さまざまな形式をサポートしています。

### プロジェクトの要件に合わせて作業コンターをカスタマイズできますか？
はい、特定のスケジューリング要件に合わせてカスタム作業コンターを定義できます。

### Aspose.Tasks に関するサポートを受けられるコミュニティ フォーラムはありますか？
はい、[Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) でサポートやディスカッションが行えます。

---

**最終更新日:** 2026-01-10  
**テスト環境:** Aspose.Tasks for Java (latest release)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}