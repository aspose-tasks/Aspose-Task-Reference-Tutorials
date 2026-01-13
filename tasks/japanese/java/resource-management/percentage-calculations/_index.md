---
date: 2026-01-13
description: Aspose.Tasks を使用して Java でリソースのパーセンテージを計算する方法を学び、MS Project のリソースの作業完了率の取得方法も含めます。コード例付きのステップバイステップガイド。
linktitle: Perform Percentage Calculations for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用した Java でリソースパーセンテージを計算する
url: /ja/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用した Java のリソースパーセンテージ計算

 Introduction
ようこそ！このチュートリアルでは、Aspose.Tasks ライブラリ for Java を使用して **Java でリソースパーセンテージを計算する方法** を学びます。Microsoft Project ファイル内の各リソースの *percent work complete* を抽出する手順を解説し、この指標がなぜ重要かを説明し、必要なコードをそのまま提示します。最後まで実践すれば、任意の Java ベースのプロジェクト管理ソリューションにリソースパーセンテージ計算を組み込むことができるようになります。

## Quick Answers
- **「リソースパーセンテージ」とは何ですか？** リソースが割り当てられた総作業量に対して完了した作業量の割合です。  
- **どの API 呼び出しでこの値を取得しますか？** `Resource` クラスの `Rsc.PERCENT_WORK_COMPLETE` です。  
- **ライセンスは必要ですか？** 本番環境で使用する場合は、テンポラリまたはフルの Aspose.Tasks ライセンスが必要です。  
- **他の Java フレームワークでも使用できますか？** はい – API は Spring、Hibernate、純粋な Java プロジェクトでも動作します。  
- **必要な Aspose.Tasks のバージョンは？** `Rsc` 列挙体をサポートしている最近のバージョン（例: 24.x）であれば問題ありません。

## What is calculate resource percentage java?
Java でリソースパーセンテージを計算するとは、Microsoft Project ファイルをプログラムで読み取り、各リソースがどれだけの作業を完了したかを算出することです。この情報は、プロジェクトマネージャがスケジュール予測、作業負荷のバランス調整、ボトルネックの特定に役立ちます。

## Why get percent work complete?
- **Progress tracking:** チームメンバーが予定通りに進んでいるかを一目で確認できます。  
- **Capacity planning:** 実績に基づいて将来の割り当てを調整できます。  
- **Reporting:** 手作業の計算なしで、ステークホルダー向けに正確なステータスレポートを生成できます。

## Prerequisites
### Java Development Environment
Java Development Kit (JDK) がインストールされていることを確認してください。JDK は [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) からダウンロードできます。

### Aspose.Tasks Library
Aspose.Tasks ライブラリは [here](https://releases.aspose.com/tasks/java/) からダウンロードし、プロジェクトに追加してください。インストール手順はドキュメントの [here](https://reference.aspose.com/tasks/java/) に記載されています。

## Import Packages
コードを書き始める前に、このチュートリアルで必要となるパッケージをインポートします:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Step 1: Set up Project File Path
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` を、Microsoft Project ファイルが格納されているフォルダーに置き換えてください。

## Step 2: Load the Project
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
指定したディレクトリから **Software Development.mpp** ファイルを読み込みます。

## Step 3: Iterate Through Resources
```java
for (Resource res : prj.getResources()) {
```
プロジェクト内で定義されているすべてのリソースをループ処理します。

## Step 4: Check Resource Name and Get Percent Work Complete
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
まずリソースに名前が設定されていることを確認し、続いてそのリソースの **percent work complete** 値を出力します。

## Common Issues and Solutions
- **NullPointerException** – プロジェクトファイルのパスが正しいか、ファイルがエラーなく読み込めているか確認してください。  
- **Incorrect percentages** – リソースに実際に割り当てられた作業があるか確認してください。割り当てがない場合はパーセンテージは `0` になります。  
- **License errors** – 有効な Aspose.Tasks ライセンスまたはテンポラリ評価ライセンスを使用して、実行時の制限を回避してください。

## Frequently Asked Questions (Original)

### Can I use Aspose.Tasks for Java with other Java frameworks?
はい、Aspose.Tasks for Java は Spring、Hibernate などさまざまな Java フレームワークと互換性があります。

### Does Aspose.Tasks support all versions of Microsoft Project files?
Aspose.Tasks は MPP、MPT、XML など、Microsoft Project のすべてのバージョンをサポートしています。

### Can I manipulate project schedules using Aspose.Tasks?
もちろんです。Aspose.Tasks はタスク、リソース、カレンダーなど、プロジェクトスケジュールを操作するための包括的な機能を提供します。

### Is there a community forum for Aspose.Tasks support?
はい、Aspose.Tasks コミュニティフォーラムは [here](https://forum.aspose.com/c/tasks/15) で利用できます。

### Does Aspose.Tasks offer temporary licenses for evaluation purposes?
はい、評価用のテンポラリライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

## Additional FAQ

**Q: How do I format the output to show percentages with a % sign?**  
A: `res.get(Rsc.PERCENT_WORK_COMPLETE)` で数値を取得し、`String.format("%.2f%%", value)` で `%` 記号付きにフォーマットします。

**Q: Can I filter resources to only show those with less than 50 % complete?**  
A: はい、出力前に `if (res.get(Rsc.PERCENT_WORK_COMPLETE) < 50)` の条件を追加してください。

**Q: Is it possible to write the percentages back to the Project file?**  
A: `Rsc.PERCENT_WORK_COMPLETE` フィールドは読み取り専用です。パーセンテージを変更したい場合は、タスク割り当てを調整する必要があります。

**Q: Does this work with Project Online (cloud) files?**  
A: まず .mpp ファイルをローカルにダウンロードする必要があります。Aspose.Tasks はファイル形式に対して動作し、クラウドサービス自体には直接対応していません。

## Conclusion
本ガイドでは、Aspose.Tasks を使用して **Java でリソースパーセンテージを計算する方法** を実演し、各リソースの *percent work complete* を取得する手順に焦点を当てました。上記の手順に従うことで、Java アプリケーションに正確なリソースパーセンテージ分析を組み込み、プロジェクトの健全性とリソース活用状況をより明確に把握できるようになります。

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}