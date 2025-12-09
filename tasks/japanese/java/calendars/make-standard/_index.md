---
date: 2025-12-03
description: Aspose.Tasks を使用して Java でカレンダーを作成する方法を学びます。このステップバイステップガイドでは、標準の MS Project
  カレンダーの作成方法、標準カレンダーの追加方法、そして Aspose.Tasks を効果的に使用する方法を示します。
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: カレンダーの作成方法 – Aspose.Tasksで標準カレンダーを作成
url: /ja/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# カレンダーの作成方法 – Aspose.Tasksで標準カレンダーを作成する

## Introduction
このチュートリアルでは、Aspose.Tasks for Java ライブラリを使用して Microsoft Project ファイル用の **カレンダーの作成方法** を学びます。標準の MS Project カレンダーを作成し、デフォルト（標準）カレンダーとして設定し、プロジェクトファイルを保存する手順を説明します。ガイドの最後までに、任意の Java ベースのプロジェクト管理ソリューションにカレンダー作成を統合できるようになります。

## Quick Answers
- **「標準カレンダー」とは何ですか？** カスタムカレンダーを指定していないタスクで使用されるデフォルトの作業時間定義です。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（「Aspose の使用方法」パート）。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **生成されるファイル形式は何ですか？** XML ベースの Microsoft Project ファイル（`.xml`）。  
- **実装にかかる時間はどれくらいですか？** 基本的なカレンダーで約 5〜10 分です。

## What is a Standard Calendar in Microsoft Project?
**標準カレンダー** はプロジェクトのデフォルトの作業日と作業時間を定義します。標準カレンダーを追加すると、特定のカレンダーが割り当てられていないすべてのタスクはそのスケジュールに従います。

## Why Use Aspose.Tasks to Create a Calendar?
Aspose.Tasks は、Microsoft Project をインストールせずにプロジェクトファイルを操作できる純粋な Java API を提供します。これにより、サーバー側の自動化、CI パイプライン、またはプログラムで **MS Project カレンダー** オブジェクトを作成する必要がある任意の Java アプリケーションに最適です。

## Prerequisites
Before you start, ensure the following are in place:

### Java Development Kit (JDK) Installation
Java Development Kit (JDK) のインストール  
Install the latest JDK from the Oracle website or an OpenJDK distribution.

### Aspose.Tasks for Java Library
Aspose.Tasks for Java ライブラリ  
Download the library from the [download page](https://releases.aspose.com/tasks/java/). Add the JAR to your project’s classpath.

## Import Packages
We need only one import for this tutorial:

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set up the Data Directory
Define where the generated project file will be saved.

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).  
`"Your Data Directory"` をマシン上の絶対パスに置き換えてください（例: `C:/Projects/Output/`）。

### Step 2: Create a Project Instance
Instantiate a new, empty Project object that will hold the calendar.

```java
Project project = new Project();
```

### Step 3: Define and Make the Calendar Standard
Add a new calendar named **“My Cal”** and promote it to the standard calendar for the project.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **プロのコツ:** `makeStandardCalendar` メソッドは、指定されたカレンダーをプロジェクトのデフォルトとして自動的にマークします。これは **標準カレンダーを追加** したいときにまさに必要な機能です。

### Step 4: Save the Project
Persist the project (including the new calendar) to an XML file.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

You can change the file name or format (`SaveFileFormat.Pp`) if you prefer a different Project version.  
別の Project バージョンが必要な場合は、ファイル名や形式（`SaveFileFormat.Pp`）を変更できます。

### Step 5: Display Completion Message
Give yourself a visual cue that the process finished without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| 問題 | 原因 | 対策 |
|-------|-------|-----|
| **File not found** | `dataDir` が存在しないフォルダーを指している | フォルダーを作成するか、絶対パスを使用する |
| **License exception** | 本番環境で有効な Aspose.Tasks ライセンスなしで実行している | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` のようにライセンスファイルを適用する |
| **Empty calendar** | 作業時間定義を追加し忘れた | カスタム時間が必要な場合は `cal1.getWeekDays().add(WeekDay.DayType.Monday)` などを使用する |

## Frequently Asked Questions

**Q: Aspose.TasksはすべてのMicrosoft Projectバージョンと互換性がありますか？**  
A: はい、Aspose.Tasks は 2000 から最新リリースまで幅広い Microsoft Project バージョンをサポートしています。

**Q: カレンダー設定をさらにカスタマイズできますか？**  
A: もちろんです！`WeekDay` と `WorkingTime` クラスを使用して、作業日を変更したり、例外を追加したり、特定の作業時間を定義したりできます。

**Q: Aspose.Tasksはエンタープライズレベルのアプリケーションに適していますか？**  
A: 確かに。ライブラリは高性能でスケーラブルな環境向けに設計されており、大規模な Project ファイルに対する包括的なサポートを提供します。

**Q: Aspose.Tasksは開発者向けの技術サポートを提供していますか？**  
A: はい、Aspose は専用フォーラム、チケットベースのサポート、豊富なドキュメントを提供しており、問題解決を迅速に支援します。

**Q: 購入前に Aspose.Tasks を試用できますか？**  
A: はい、[website](https://purchase.aspose.com/buy) で利用できる無料トライアル版を試すことで、すべての機能を評価した上で導入を検討できます。

## Conclusion
You now know **カレンダーの作成方法** objects in Aspose.Tasks for Java, make them the standard calendar, and save the resulting Project file. This capability lets you automate project scheduling, enforce consistent working times, and integrate Microsoft Project data directly into your Java applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---