---
date: 2026-01-10
description: Aspose.Tasks for Javaでレートスケールの読み取り方法とリソース割り当ての管理方法を学びます。マテリアルリソースを定義し、スケールの設定方法とタスクへのリソース割り当てを行います。
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks のリソース割り当てにおけるレートスケールの読み取りと書き込み方法
url: /ja/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のリソース割り当てにおけるレート スケールの読み取りと書き込み方法

このチュートリアルでは、Aspose.Tasks for Java を使用してリソース割り当ての **レート スケール** 設定を読み取り、調整する方法を学びます。スケジューラやレポート ツールの構築、あるいはプロジェクト更新の自動化が目的であっても、レート スケールの操作をマスターすれば、材料リソースや作業リソースを細かく制御できます。

## Quick Answers
- **レート処理の主要クラスはどれですか？** `ResourceAssignment` とその `Asn.RATE_SCALE` プロパティ。  
- **スケールオプションを定義している enum はどれですか？** `RateScaleType`（Day、Week、Month など）。  
- **サンプル実行にライセンスは必要ですか？** 無料評価ライセンスでテスト可能です。商用利用には商用ライセンスが必要です。  
- **保存後にスケールを変更できますか？** はい – プロジェクトを再読み込みし、示したように `Asn.RATE_SCALE` を変更します。  
- **対応 IDE は？** 任意の Java IDE（IntelliJ IDEA、Eclipse、NetBeans）でコンパイル可能です。

## Rate Scale とは？
Rate scale は、リソースのコスト レートが適用される時間単位（日、週、月など）を決定します。スケールを調整することで、材料消費や労働工数を正確にモデル化できます。

## なぜレート スケールを読み書きするのか？
現在のスケールを読み取ることで既存スケジュールを監査でき、新しいスケールを書き込むことでプロジェクトの請求や消費ポリシーにリソースを合わせられます。特に **材料リソース** のコストを定義する場合や、**非標準作業カレンダー** のスケールを設定する必要がある場合に有用です。

## 前提条件
開始する前に、以下の前提条件を満たしていることを確認してください。
1. **Java 開発環境** – JDK 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java ライブラリ** – ライブラリは [here](https://releases.aspose.com/tasks/java/) からダウンロードしてインストールしてください。

## Import Packages
まず、必要な Aspose.Tasks クラスをインポートします。

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Step 1: Set up your Java project
Maven または Gradle プロジェクトを作成し、Aspose.Tasks JAR をクラスパスに追加します。この手順により、コンパイラがインポートしたクラスを見つけられるようになります。

## Step 2: Load the Project File
操作対象となる既存の Microsoft Project ファイルをロードします。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Step 3: Add a Task
後でリソース割り当てを行う新しいタスクを作成します。

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Step 4: Define Resources
ここで **材料リソース** と通常の作業リソースを **定義** します。材料タイプのリソースには `ResourceType.Material` を使用する点に注意してください。

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Step 5: Assign Resources to Task
次に **リソースをタスクに割り当て**、`RateScaleType.Week` を使用して **スケールの設定方法** を指定します。これにより、レート スケールの読み取りと書き込みの両方を示します。

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Step 6: Save the Project
変更を新しいファイルに保存し、後で保存されたレート スケールを検証できるようにします。

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Step 7: Retrieve Resource Assignments
保存したプロジェクトを再読み込みし、**レート** スケールを読み取って正しく書き込まれたことを確認します。

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Common Pitfalls & Tips
- **UID の不一致** – UID で割り当てを取得する際は、作成時に割り当てた UID と一致していることを確認してください。  
- **リソース タイプの誤用** – 作業リソースに `ResourceType.Material` を使用すると、レート計算が予期せぬ動作をします。  
- **保存形式** – カスタム フィールド（レート スケールなど）を保持するため、必ず `SaveFileFormat.Mpp`（または他のサポート形式）で保存してください。

## Conclusion
Aspose.Tasks for Java でリソース割り当てのレート スケールを管理・検査するのは、関連クラスとプロパティを把握すれば簡単です。本ガイドに従えば、**レート情報の読み取り**、**材料リソースオブジェクトの定義**、**スケールの設定**、そして **タスクへのリソース割り当て** を自信を持って実行できます。

## Frequently Asked Questions

**Q: 任意の Java IDE で Aspose.Tasks for Java を使用できますか？**  
A: はい、Aspose.Tasks for Java は IntelliJ IDEA、Eclipse、NetBeans などの主要な Java IDE と互換性があります。

**Q: Aspose.Tasks は MPP 以外のファイル形式もサポートしていますか？**  
A: はい、Aspose.Tasks は MPP、XML、HTML などさまざまなファイル形式をサポートしています。

**Q: エンタープライズ規模のプロジェクト管理に Aspose.Tasks は適していますか？**  
A: もちろんです。Aspose.Tasks はあらゆる規模のプロジェクト管理に対応できる包括的な機能を提供しており、エンタープライズレベルでも利用可能です。

**Q: レート スケール以外にもリソース割り当てをカスタマイズできますか？**  
A: はい、Aspose.Tasks はコスト、作業量、期間の調整など、リソース割り当ての幅広いカスタマイズ機能を提供しています。

**Q: Aspose.Tasks のサポート用コミュニティフォーラムはありますか？**  
A: はい、Aspose.Tasks フォーラムは [here](https://forum.aspose.com/c/tasks/15) で利用でき、サポートや他のユーザーとの交流が可能です。

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}