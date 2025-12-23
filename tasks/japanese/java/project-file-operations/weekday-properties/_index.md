---
date: 2025-12-23
description: Aspose.Tasks Java を使用してプロジェクトスケジュールを更新し、週の開始日を設定し、月の日数を変更し、プロジェクトカレンダーを効率的にカスタマイズする方法を学びましょう。
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – 週日のプロパティの管理
url: /ja/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – 曜日プロパティの管理

## Introduction
Aspose.Tasks for Java (aspose tasks java) は、Microsoft Project がインストールされていなくても Java 開発者が Microsoft Project ファイルを操作できる堅牢な API です。このチュートリアルでは、**MPP ファイルの読み込み**、**週の開始曜日の設定**、**月あたりの日数の変更**、そして **プロジェクト カレンダーのカスタマイズ** といった、プロジェクト スケジュールを更新するために必要な手順を学びます。最後まで実施すれば、曜日プロパティをプログラムで調整し、必要な形式で変更を保存できるようになります。

## Quick Answers
- **プロジェクトを扱う主なクラスは何ですか？** Aspose.Tasks ライブラリの `Project`。  
- **週の開始曜日はどう変更しますか？** `project.set(Prj.WEEK_START_DAY, DayType.Monday)` を使用します。  
- **既存の .mpp ファイルを読み込めますか？** はい、ファイルパスを指定して `Project` をインスタンス化します。  
- **プロジェクトを XML として保存するメソッドはどれですか？** `project.save(path, SaveFileFormat.Xml)`。  
- **開発にライセンスは必要ですか？** 評価用の無料トライアルで動作しますが、本番環境ではライセンスが必要です。

## Prerequisites
開始する前に、以下が揃っていることを確認してください。

- **Java Development Kit (JDK)** – 最新バージョンがインストール済み。  
- **Aspose.Tasks for Java ライブラリ** – [こちら](https://releases.aspose.com/tasks/java/) からダウンロード。  
- **IDE** – IntelliJ IDEA、Eclipse、NetBeans など。

## Import Packages
まず、必要な Aspose.Tasks クラスをインポートします。

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

それでは、曜日プロパティの管理手順を順に見ていきましょう。

## Step 1: Load an MPP File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*ここでは **既存の .mpp ファイルを読み込み**（`load mpp file`）て、カレンダー設定を確認・変更できるようにします。*

## Step 2: Display Current Weekday Properties
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
このコードは現在の **週の開始曜日**、**月あたりの日数**、**1 日あたりの分数**、**1 週あたりの分数** を出力します。これらは **プロジェクト カレンダーをカスタマイズ** する際に頻繁に使用する要素です。

## Step 3: Set New Weekday Properties
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
このステップでは **週の開始曜日を Monday に設定**し、**月あたりの日数を 24 に変更**、さらに日次・週次の分数を調整します。非標準の作業カレンダーに合わせて **プロジェクト スケジュールを更新** する典型的な設定です。

## Step 4: Save the Updated Project
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
変更されたプロジェクトは XML ファイルとして保存され、他のツールへの共有やインポートが容易になります。

## Step 5: Confirm the Operation
```java
System.out.println("Process completed Successfully");
```
シンプルなコンソール メッセージで、エラーなくワークフローが完了したことを確認できます。

## Common Issues & Tips
- **ファイルパスが正しくない** – `dataDir` の末尾にスラッシュが付いているか確認するか、プラットフォームに依存しない `Paths.get(...)` を使用してください。  
- **ライセンスが設定されていない** – 本番環境では `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` を `Project` 作成前に呼び出してください。  
- **予期しない週の開始曜日** – 正しい `DayType` 列挙値（例: `DayType.Sunday`）を使用しているか確認してください。  

## Frequently Asked Questions

**Q: Aspose.Tasks for Java は複雑なプロジェクト構造を扱えますか？**  
A: はい、Aspose.Tasks for Java は複雑なプロジェクト構造を容易に処理できる包括的なサポートを提供します。

**Q: Aspose.Tasks for Java はさまざまなバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: もちろんです。Aspose.Tasks for Java は多数の Microsoft Project ファイル バージョンをサポートし、プラットフォーム間の互換性を確保します。

**Q: 既存の Java アプリケーションに Aspose.Tasks for Java を統合できますか？**  
A: はい、Aspose.Tasks for Java はシームレスな統合機能を提供し、強力なプロジェクト管理機能で Java アプリケーションを拡張できます。

**Q: Aspose.Tasks for Java のドキュメントやサポートはありますか？**  
A: はい、Aspose.Tasks for Java の豊富なドキュメントとコミュニティ サポートは、[こちらのウェブサイト](https://releases.aspose.com/) で利用できます。

**Q: Aspose.Tasks for Java の無料トライアルはありますか？**  
A: はい、機能を確認した上で購入をご検討いただけるよう、[こちらのウェブサイト](https://reference.aspose.com/tasks/java/) から無料トライアル版をダウンロードできます。

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}