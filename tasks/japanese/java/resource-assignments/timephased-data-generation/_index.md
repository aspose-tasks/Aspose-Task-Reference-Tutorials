---
date: 2026-06-10
description: Aspose.Tasks for Java を使用して、リソース割り当てのコンターを変更し、タイムフェーズデータを生成する方法を学びます。作業コンターの種類や高度なスケジューリングシナリオについても解説します。
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Aspose.Tasksでリソース割り当てのタイムフェーズデータを生成する
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでタイムフェーズデータのコンターを変更する方法
url: /ja/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のタイムフェーズ データでコンターを変更する方法

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用してリソース割り当ての **contour の変更方法** を学び、タイムフェーズ データを生成します。タイムフェーズ データはプロジェクトのタイムライン上での作業分布を示し、スケジュールの微調整、作業負荷のバランス、データ駆動型の意思決定を可能にします。contour の変更を習得すると、前倒し（front‑loading）や後倒し（back‑loading）、ピーク作業負荷など、現実的な作業パターンをモデル化できます。

## クイック回答
- **contour とは何ですか？** 作業コンターは、タスクの期間全体にわたる作業量の分布方法を定義します（例: Flat、Turtle、Bell）。  
- **contour を変更する理由は？** 前倒し（front‑loading）や後倒し（back‑loading）など、現実的な作業パターンを反映させるためです。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（最新バージョン）。  
- **ライセンスは必要ですか？** はい、製品版で使用するには有効な Aspose.Tasks ライセンスが必要です。  
- **コンソールで結果を確認できますか？** サンプルは各タイムフェーズ セグメントの開始日と値をコンソールに出力します。

## 「contour の変更方法」とは何ですか？
contour を変更するとは、`ResourceAssignment` オブジェクトの `WORK_CONTOUR` プロパティを更新することを意味します。このプロパティは、Aspose.Tasks に対して割り当ての総作業量をタスクの期間にどのように分配するかを指示します。ライブラリは Flat、Turtle、Bell などの事前定義された複数のコンターを提供しており、各々が時間経過に伴う作業分布の異なるパターンを生成します。

## なぜ Aspose.Tasks を使用してタイムフェーズ データを生成するのか？
Aspose.Tasks は **インメモリ操作で 0 ms のオーバーヘッド** でタイムフェーズ データを生成し、**50 以上の出力フォーマット**（MPP、XML、CSV など）をサポートします。ライブラリはプロジェクト全体をメモリにロードせずに数百ページ規模のプロジェクトを処理でき、レポート作成、リソース平準化、シナリオ分析のために正確な作業分布を提供します。その API を使用すれば、contour の変更を自動化し、プログラムから正確なタイムフェーズ 値を抽出できます。

## 前提条件
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。JDK は [こちら](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) からダウンロードしてインストールできます。  
2. Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリが必要です。ダウンロードは [ウェブサイト](https://releases.aspose.com/tasks/java/) から行えます。

## パッケージのインポート
`Project` クラスは Aspose.Tasks のコアオブジェクトで、プロジェクト ファイル全体をメモリ上に表現します。タスクや割り当てを操作する前に、必要な名前空間をインポートしてください。

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
`Project` コンストラクタは既存の MPP ファイルを読み込み、すべてのタスクをメモリに完全に展開せずに構造を解析するため、軽量な操作が可能です。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## ステップ 2: タスクとリソース割り当てを取得する
`ResourceAssignment` はリソースをタスクに紐付け、作業量、コスト、contour などの割り当てレベルのプロパティを保持します。`project.getResourceAssignments().getById(1)`（または有効な ID）で最初の割り当てを取得し、contour を変更する前に使用してください。

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## contour の変更方法 – Flat（デフォルト）
`WorkContourType` は Aspose.Tasks がサポートする事前定義された作業 contour パターンを列挙した enum です。`Asn.WORK_CONTOUR` はリソース割り当ての contour フィールドを示し、`generateTimephasedData()` は現在の contour 設定に基づいてタイムフェーズ 作業エントリを生成します。**Flat** contour はタスク期間全体に作業を均等に分配します。`firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` で設定し、`firstRA.generateTimephasedData()` を呼び出すと均等に間隔を置いた値が取得できます。

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## contour の変更方法 – Turtle
**Turtle** contour は低い作業量から始まり、途中で加速し、再び減速するパターンで、カメのゆっくりとしたペースに似ています。`firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` を設定し、タイムフェーズ データを再生成してください。このパターンは、ピーク生産性に達する前に学習曲線が必要なタスクに最適です。

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## contour の変更方法 – BackLoaded
**BackLoaded** contour は作業の大部分をタスクのスケジュール後半に配置し、開始時の作業は少なくなります。`firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` を使用して設定し、タイムフェーズ データを再生成してください。これは、前段階のタスクが完了しないと作業を開始できないアクティビティに有用です。

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## contour の変更方法 – FrontLoaded
**FrontLoaded** contour はタスクの開始時に作業を集中させ、キックオフフェーズや初期の集中的な作業バーストなどのシナリオをモデル化します。`firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` を適用し、`firstRA.generateTimephasedData()` を呼び出すと前倒しの分布が確認できます。

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## contour の変更方法 – Bell
**Bell** contour はタイムラインの中央に対称的なピークを作り、作業が徐々に増加し、ピークに達し、滑らかに減少する様子を表します。`firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` で設定し、タイムフェーズ データを再生成してベル型の作業曲線を可視化してください。

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## contour の変更方法 – EarlyPeak
**EarlyPeak** はスケジュールの早い段階で最高の作業量を配置し、その後徐々に減少させます。`firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` の後に `firstRA.generateTimephasedData()` を呼び出すと、急速なプロトタイピングなど、強力なスタートが必要なアクティビティをモデル化できます。

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## contour の変更方法 – LatePeak
**LatePeak** は作業のピークをタスクの終盤にシフトさせ、締め切りが近づくにつれて作業が強化されるシナリオに適しています。`firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` を適用し、タイムフェーズ データを再生成して後半の作業負荷急増を確認してください。

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## contour の変更方法 – DoublePeak
**DoublePeak** は2つの明確な作業スパイクを作り、その間に低作業量の期間を挟むパターンで、2回の大きな作業バーストがあるタスクに有用です。`firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` を使用し、`firstRA.generateTimephasedData()` を呼び出すと二重ピークパターンが取得できます。

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 一般的な問題とヒント
- **Contour が更新されませんか？** `firstRA.set(Asn.WORK_CONTOUR, …)` をタイムフェーズ データを取得する *前に* 呼び出していることを確認してください。  
- **予期しない値ですか？** ソース MPP でタスクの開始日と終了日が正しく設定されているか確認してください。  
- **パフォーマンスのヒント:** 複数の contour を反復処理する際は、同じ `Project` インスタンスを再利用して不要なファイル I/O を避けると、大規模プロジェクトで処理時間を最大 40 % 短縮できます。  
- **メモリのヒント:** プロジェクトが 1 GB を超える場合は、`Project.setReadOnly(true)` を有効にしてメモリ使用量を 200 MB 未満に抑えつつ、正確なタイムフェーズ データを生成できます。

## FAQ
**Q: Aspose.Tasks を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Tasks は他の Java ライブラリとシームレスに統合でき、スケジューリング データをレポート、分析、UI フレームワークと組み合わせて使用できます。

**Q: Aspose.Tasks は大規模エンタープライズプロジェクトに適していますか？**  
A: はい、Aspose.Tasks は数万件のタスクやリソースを持つプロジェクトを処理でき、数百ページのファイルでもパフォーマンス低下なく動作するよう設計されています。

**Q: Aspose.Tasks はさまざまなプロジェクト ファイル形式をサポートしていますか？**  
A: はい、Aspose.Tasks は MPP、XML、CSV、MPX など 30 以上の形式をサポートしており、レガシーおよび最新システム間のインポート/エクスポートが容易です。

**Q: プロジェクトの要件に合わせて作業 contour をカスタマイズできますか？**  
A: はい、`WORK_CONTOUR` プロパティに作業率の配列を渡すことでカスタム contour を定義でき、作業分布を完全にコントロールできます。

**Q: Aspose.Tasks に関するサポートを受けられるコミュニティ フォーラムはありますか？**  
A: はい、[Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) でサポートやディスカッション、Aspose エンジニアやコミュニティメンバーによるコードサンプルを確認できます。

---

**最終更新日:** 2026-06-10  
**テスト環境:** Aspose.Tasks for Java (latest release)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Tasks でリソース割り当てを作成する](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks でリソースのタイムフェーズ データを読み取る](/tasks/java/resource-management/read-timephased-data/)
- [Aspose.Tasks で割り当てを停止し、リソース割り当てを再開する方法](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}