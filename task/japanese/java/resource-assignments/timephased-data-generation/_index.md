---
title: Aspose.Tasks でタイムスケール データを生成する
linktitle: Aspose.Tasks でのリソース割り当てのタイムスケール データの生成
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して、リソース割り当てのタイムスケール データを生成する方法を学習します。この包括的なガイドを使用して、プロジェクト管理の効率を向上させます。
type: docs
weight: 24
url: /ja/java/resource-assignments/timephased-data-generation/
---
## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して、リソース割り当てのタイムスケール データを生成するプロセスについて説明します。タイムスケール データは、プロジェクト内で時間の経過とともにリソースがどのように割り当てられるかについての貴重な洞察を提供し、プロジェクト マネージャーが情報に基づいた意思決定を行うのに役立ちます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。 JDK は次からダウンロードしてインストールできます。[ここ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリが必要です。からダウンロードできます。[Webサイト](https://releases.aspose.com/tasks/java/).

## パッケージのインポート
まず、Aspose.Tasks を操作するために必要なパッケージをインポートしましょう。
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## ステップ 1: ソース MPP ファイルを読み取る
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Data Directory";
//ソース MPP ファイルを読み取ります
Project project = new Project(dataDir + "project.mpp");
```
## ステップ 2: タスクとリソースの割り当てを取得する
```java
//プロジェクトの最初のタスクを取得する
Task task = project.getRootTask().getChildren().getById(1);
//プロジェクトの最初のリソース割り当てを取得する
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## ステップ 3: 平坦な等高線でタイムフェーズ データを生成する
```java
//平らな輪郭がデフォルトの輪郭です
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ステップ 4: 輪郭をカメに変更する
```java
//輪郭をカメに変更
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ステップ 5: 輪郭をバックロードに変更する
```java
//輪郭を BackLoaded に変更
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ステップ 6: 輪郭を FrontLoaded に変更する
```java
//輪郭をFrontLoadedに変更
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ステップ 7: 輪郭をベルに変更する
```java
//輪郭をベルに変更
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ステップ 8: 輪郭を EarlyPeak に変更する
```java
//輪郭をEarlyPeakに変更
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ステップ9: 輪郭をLatePeakに変更する
```java
//輪郭をLatePeakに変更
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ステップ 10: 輪郭を DoublePeak に変更する
```java
//輪郭をDoublePeakに変更
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用してリソース割り当てのタイムスケール データを生成する方法について説明しました。さまざまな作業の輪郭を理解すると、プロジェクト マネージャーがプロジェクト内のリソースの割り当てとスケジュールを効果的に管理するのに役立ちます。
## よくある質問
### Aspose.Tasks を他の Java ライブラリで使用できますか?
はい、Aspose.Tasks を他の Java ライブラリと統合して、プロジェクト管理機能を強化できます。
### Aspose.Tasks は大規模なエンタープライズ プロジェクトに適していますか?
確かに、Aspose.Tasks は、大規模なエンタープライズ プロジェクトを含む、あらゆる規模のプロジェクトを処理できるように設計されています。
### Aspose.Tasks はさまざまなプロジェクト ファイル形式をサポートしていますか?
はい、Aspose.Tasks は、MPP、XML、MPX などのさまざまなプロジェクト ファイル形式をサポートしています。
### プロジェクトの要件に応じて作業輪郭をカスタマイズできますか?
はい、Aspose.Tasks を使用すると、ユーザーは特定のプロジェクトのニーズに合わせてカスタムの作業輪郭を定義できます。
### Aspose.Tasks に関するサポートが得られるコミュニティ フォーラムはありますか?
はい、次の場所にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートとディスカッションのため。