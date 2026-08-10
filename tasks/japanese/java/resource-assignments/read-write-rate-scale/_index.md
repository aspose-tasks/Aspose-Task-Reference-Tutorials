---
date: 2026-06-10
description: Aspose.Tasks for Java を使用して、リソース割り当てのレートを読み取る方法とレートスケールを書き込む方法を学びます。マテリアルリソース、複数のフォーマット、大規模プロジェクトをサポートします。
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Aspose.Tasks のリソース割り当てにおけるレートスケールの読み取りと書き込み
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks でリソース割り当てのレートスケールを読み取る方法と書き込む方法
url: /ja/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のリソース割り当てにおけるレートスケールの読み取りと書き込み方法

このチュートリアルでは、Aspose.Tasks for Java を使用してリソース割り当ての**レート**スケール設定を**読み取る方法**を学び、調整する方法を紹介します。スケジューラやレポートツールの構築、または単にプロジェクト更新を自動化したい場合でも、レートスケールの操作をマスターすれば、素材および作業リソースを細かく制御できます。

## クイック回答
`ResourceAssignment` はタスクとリソースをリンクし、割り当て固有のデータを保持します。  
`Asn` には `RATE_SCALE` を含む割り当てフィールドの定数が含まれます。  
`RateScaleType` 列挙体はレートスケーリングの可能な時間単位を列挙します。  

- **レート処理の主要クラスは何ですか？** `ResourceAssignment` と `Asn.RATE_SCALE` プロパティです。  
- **スケールオプションを定義する列挙体はどれですか？** `RateScaleType`（Day、Week、Month など）。  
- **サンプルを実行するのにライセンスは必要ですか？** 評価用の無料ライセンスでテストは可能ですが、本番環境では商用ライセンスが必要です。  
- **保存後にスケールを変更できますか？** はい – プロジェクトを再読み込みし、示されているように `Asn.RATE_SCALE` を変更します。  
- **サポートされている IDE は？** IntelliJ IDEA、Eclipse、NetBeans など、任意の Java IDE でコードをコンパイルできます。

## リソース割り当てのレートスケールを読み取る方法

プロジェクトをロードし、目的の `ResourceAssignment` を見つけて `getRateScale()` を呼び出します。これにより、レートが日、週、月、またはその他の単位で適用されているかを示す `RateScaleType` の値が返されます。回答は即座に得られ、API 呼び出しはわずか 2 回だけなので、監査スクリプトや UI 表示に最適です。

## リソース割り当てのレートスケールを書き込む方法

`ResourceAssignment` オブジェクトを作成または取得し、その `Asn.RATE_SCALE` プロパティを目的の `RateScaleType`（例: `RateScaleType.Week`）に設定してからプロジェクトを保存します。この単一のプロパティ変更により、コスト計算が自動的に更新され、すべてのサポートされているファイル形式で永続化されます。スケールを設定した後、リソースの標準レートまたは残業レートを新しい時間単位に合わせて調整する必要がある場合があります。これにより、コスト計算の正確性が保たれます。

## レートスケールとは何か

レートスケールは、リソースのコストレートが適用される時間単位（日、週、月など）を決定します。スケールを調整することで、素材消費や労働努力を正確にモデル化できます。例えば、スケールを Week に設定すると、コストレートは「週あたりのコスト」と解釈され、タスクの総コストはリソースが割り当てられた週数に基づいて計算されます。

## なぜレートスケールを読み書きするのか

現在のスケールを読み取ることで既存のスケジュールを監査でき、新しいスケールを書き込むことでリソースをプロジェクトの請求や消費ポリシーに合わせることができます。これは、**素材リソース** のコストを定義する場合や、標準外の作業カレンダーに対して **スケールを設定** する必要がある場合に特に有用です。

## 前提条件
開始する前に、以下の前提条件が揃っていることを確認してください：
1. **Java 開発環境** – JDK 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java ライブラリ** – ライブラリを [here](https://releases.aspose.com/tasks/java/) からダウンロードしてインストールしてください。

## パッケージのインポート
`ResourceAssignment` クラスはタスクとリソースのリンクを表し、`RateScaleType` はレートの可能な時間単位を列挙します。コーディングを開始する前に、必要な Aspose.Tasks クラスをインポートしてください。

`Project` は Microsoft Project ファイルを読み込み・保存するメインオブジェクトです。  
`Resource` は作業や素材などのプロジェクトリソースを定義します。  
`ResourceType` 列挙体はリソースが作業か素材かを指定します。  
`Task` はプロジェクトスケジュール内の作業項目を表します。  
`SaveFileFormat` 列挙体はプロジェクト保存時の出力形式を定義します。

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

## 手順 1: Java プロジェクトの設定
Maven または Gradle プロジェクトを作成し、Aspose.Tasks JAR をクラスパスに追加します。この手順により、コンパイラがインポートされたクラスを見つけられるようになります。

## 手順 2: プロジェクト ファイルの読み込み
操作対象の既存 Microsoft Project ファイルをロードします。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 手順 3: タスクの追加
後でリソース割り当てを受け取る新しいタスクを作成します。

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## 手順 4: リソースの定義
ここでは **素材リソース** と通常の作業リソースを **定義** します。素材タイプのリソースには `ResourceType.Material` を使用していることに注意してください。

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## 手順 5: タスクへのリソース割り当て
ここで **リソースをタスクに割り当て**、`RateScaleType.Week` を使用して **スケールの設定方法** を指定します。これにより、レートスケールの読み取りと書き込みの両方が示されます。

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## 手順 6: プロジェクトの保存
変更を新しいファイルに永続化し、後で保存されたレートスケールを確認できるようにします。

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## 手順 7: リソース割り当ての取得
保存したプロジェクトを再読み込みし、**レート** スケールを読み取って正しく書き込まれたことを確認します。

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## よくある落とし穴とヒント
- **UID Mismatch** – UID で割り当てを取得する際、作成時に割り当てられた UID 値と一致していることを確認してください。  
- **Incorrect Resource Type** – 作業リソースに `ResourceType.Material` を使用すると、レート計算が予期せず動作します。  
- **Saving Format** – カスタムフィールド（レートスケールなど）を保持するため、常に `SaveFileFormat.Mpp`（または他のサポート形式）で保存してください。  
- **Large Projects** – Aspose.Tasks はストリーミングアーキテクチャにより、**500 ページ以上**のファイルでもドキュメント全体をメモリにロードせずに処理できます。

## よくある質問

**Q: Aspose.Tasks for Java は任意の Java IDE で使用できますか？**  
A: はい、Aspose.Tasks for Java は IntelliJ IDEA、Eclipse、NetBeans など、主要な Java IDE すべてと互換性があります。

**Q: Aspose.Tasks は MPP 以外のファイル形式もサポートしていますか？**  
A: はい、Aspose.Tasks は MPP、XML、HTML などさまざまなファイル形式をサポートしています。

**Q: Aspose.Tasks はエンタープライズレベルのプロジェクト管理に適していますか？**  
A: もちろんです。Aspose.Tasks はあらゆる規模のプロジェクト管理に必要な包括的な機能を提供し、エンタープライズレベルのプロジェクト管理に適しています。

**Q: レートスケール以外にもリソース割り当てをさらにカスタマイズできますか？**  
A: はい、Aspose.Tasks はコスト、作業、期間の調整など、リソース割り当てのカスタマイズに関する広範な機能を提供します。

**Q: Aspose.Tasks のサポート用コミュニティフォーラムはありますか？**  
A: はい、Aspose.Tasks フォーラムは [here](https://forum.aspose.com/c/tasks/15) で利用でき、サポートや他のユーザーとの交流が可能です。

---

**最終更新日:** 2026-06-10  
**テスト済み:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks でリソース割り当てを作成する](/tasks/java/resource-assignments/create-resource-assignments/)
- [割り当ての変更方法 – Aspose で共有リソースを読み取る](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Aspose.Tasks でリソース割り当てにノートを追加する方法](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}