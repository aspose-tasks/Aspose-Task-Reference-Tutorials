---
title: Aspose.Tasks for Java を使用して Primavera から MS プロジェクトを読み取る
linktitle: Aspose.Tasks で Primavera からプロジェクトを読み取る
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用して、Primavera XML から MS Project ファイルをシームレスに読み取る方法を学びます。プロジェクト管理の効率を高めます。
weight: 20
url: /ja/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用して Primavera から MS プロジェクトを読み取る

## 導入
プロジェクト管理では、異なるソフトウェア プラットフォーム間の相互運用性がシームレスなワークフローにとって重要です。 Aspose.Tasks for Java は、Primavera XML から Microsoft Project ファイルを読み取るための堅牢な機能を提供します。このチュートリアルでは、Aspose.Tasks for Java を使用して Primavera から MS Project ファイルを読み取るプロセスを説明し、タスクの Primavera 固有のプロパティを効率的に調べることができます。
## 前提条件
続行する前に、次の前提条件がインストールおよび設定されていることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。
2.  Aspose.Tasks for Java:Aspose.Tasks for Java を次からダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/java/).

## パッケージのインポート
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## ステップ 1: データ ディレクトリを設定する
```java
String dataDir = "Your Data Directory";
```
必ず交換してください`"Your Data Directory"`データディレクトリへの実際のパスを使用します。
## ステップ 2: Primavera XML からプロジェクトを読み取る
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
必ず交換してください`"PrimaveraProject.xml"`Primavera XML ファイルの実際の名前を置き換えます。
## ステップ 3: タスクを反復処理し、Primavera 固有のプロパティを取得する
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
このコードは、プロジェクト内の各タスクを反復処理して、関連する Primavera 固有のプロパティを出力します。

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して Primavera XML から MS Project ファイルを読み取る方法を学習しました。この機能により、さまざまなプラットフォームにわたるプロジェクト データのシームレスな統合と分析が可能になり、全体的なプロジェクト管理の効率が向上します。
## よくある質問
### Q: Aspose.Tasks for Java を使用してタスクの Primavera 固有のプロパティを変更できますか?
A: はい、Aspose.Tasks for Java は、必要に応じてタスクの Primavera 固有のプロパティを変更するための API を提供します。
### Q: Aspose.Tasks for Java は他のプロジェクト ファイル形式の読み取りをサポートしていますか?
A: はい、Aspose.Tasks for Java は、MPP、XML、Primavera XML などのさまざまなプロジェクト ファイル形式の読み取りをサポートしています。
### Q: Aspose.Tasks for Java はエンタープライズ レベルのプロジェクト管理アプリケーションに適していますか?
A: もちろん、Aspose.Tasks for Java は堅牢な機能と拡張性を備えているため、エンタープライズ レベルのプロジェクト管理アプリケーションに適しています。
### Q: Aspose.Tasks for Java を使用して Primavera プロジェクトからリソース情報を抽出できますか?
A: はい、Aspose.Tasks for Java を使用すると、Primavera プロジェクトからタスクの詳細とともにリソース情報を抽出できます。
### Q: Aspose.Tasks for Java の追加サポートやドキュメントはどこで見つけられますか?
 A: 包括的なドキュメントを見つけたり、サポートのためのフォーラムにアクセスしたりできます。[Aspose.Tasks for Java ドキュメント](https://reference.aspose.com/tasks/java/)ページ。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
