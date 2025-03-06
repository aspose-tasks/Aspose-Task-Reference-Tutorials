---
title: Aspose.Tasks でのリソース割り当ての読み取りおよび書き込みレート スケール
linktitle: Aspose.Tasks でのリソース割り当ての読み取りおよび書き込みレート スケール
second_title: Aspose.Tasks Java API
description: この包括的なチュートリアルで、Aspose.Tasks for Java でリソース割り当てレート スケールを効果的に管理する方法を学びましょう。
type: docs
weight: 20
url: /ja/java/resource-assignments/read-write-rate-scale/
---
## 導入
このチュートリアルでは、Microsoft Project ファイルをプログラムで操作するための堅牢なライブラリである Aspose.Tasks for Java を使用したリソース割り当てレート スケールの管理について詳しく説明します。これらの手順に従うことで、Java アプリケーションでのリソース割り当てのレート スケール設定を効果的に操作できるようになります。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java 開発環境: システムに Java Development Kit (JDK) がインストールされていることを確認してください。
2.  Aspose.Tasks for Java ライブラリ:Aspose.Tasks for Java ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/java/).

## パッケージのインポート
まず、Aspose.Tasks 機能を使用するために必要なパッケージをインポートする必要があります。 
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
## ステップ 1: プロジェクトをセットアップする
まず Java プロジェクトを設定し、Aspose.Tasks ライブラリを依存関係に含めます。
## ステップ 2: プロジェクト ファイルをロードする
操作するプロジェクト ファイルを Java アプリケーションにロードします。
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## ステップ 3: タスクを追加する
新しいタスクをプロジェクトに追加します。
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## ステップ 4: リソースを定義する
有形リソースと非有形リソースを定義し、そのタイプを指定します。
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## ステップ 5: リソースをタスクに割り当てる
以前に定義したリソースを、そのレート スケール タイプとともにタスクに割り当てます。
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## ステップ 6: プロジェクトを保存する
変更したリソース割り当てを使用してプロジェクトを保存します。
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## ステップ 7: リソース割り当ての取得
保存したプロジェクトを再ロードし、リソース割り当てを取得して、レート スケール設定を確認します。
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## 結論
Aspose.Tasks for Java でリソース割り当てレート スケールを管理することは、効果的なプロジェクト管理にとって重要です。このステップバイステップのガイドに従うことで、Java アプリケーションでのリソース割り当てのレート スケール設定をシームレスに操作できます。
## よくある質問
### Q1: Aspose.Tasks for Java を任意の Java IDE で使用できますか?
A: はい、Aspose.Tasks for Java は、IntelliJ IDEA、Eclipse、NetBeans などのすべての主要な Java IDE と互換性があります。
### Q2: Aspose.Tasks は MPP 以外のファイル形式をサポートしていますか?
A: はい、Aspose.Tasks は MPP、XML、HTML などのさまざまなファイル形式をサポートしています。
### Q3: Aspose.Tasks はエンタープライズ レベルのプロジェクト管理に適していますか?
A: もちろん、Aspose.Tasks はあらゆる規模のプロジェクトを管理するための包括的な機能を提供しており、エンタープライズ レベルのプロジェクト管理に適しています。
### Q4: レートスケールを超えてリソース割り当てをカスタマイズできますか?
A: はい、Aspose.Tasks は、コスト、作業時間、期間の調整など、リソースの割り当てをカスタマイズするための広範な機能を提供します。
### Q5: Aspose.Tasks サポートのためのコミュニティ フォーラムはありますか?
 A: はい、Aspose.Tasks フォーラムでサポートを見つけたり、他のユーザーと交流したりできます。[ここ](https://forum.aspose.com/c/tasks/15).