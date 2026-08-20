---
date: 2026-08-13
description: Aspose.Tasks for Java を使用して、カレンダーに祝日を追加し、プロジェクトにカレンダーを割り当て、MS Project
  ファイルを MPP として保存する方法を学びます。
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Aspose.Tasksでカレンダーを MPP 形式に更新
og_description: カレンダーに祝日を追加し、プロジェクトに割り当て、Aspose.Tasks for Java を使用してスケジュールを MPP に変換します。ステップバイステップの自動化を学びましょう。
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Aspose.Tasksでカレンダーに祝日を追加し、MPPとして保存
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasksでカレンダーに祝日を追加し、MPPとして保存
url: /ja/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# カレンダーに祝日を追加し、Aspose.TasksでMPPとして保存

## はじめに

現代のプロジェクト管理では、**add holidays to calendar** ファイルを追加し、**MS Project calendar** を作成し、ネイティブな MPP 形式でスケジュールを共有する必要があります。複数のソースからタイムラインを統合したり、レガシーデータを移行したりする場合でも、プログラムでカレンダーを生成すれば手作業のミスを排除し、納期を短縮できます。このチュートリアルでは、MS Project でカレンダーを作成し、祝日でカスタマイズし、**assign calendar to project** を行い、最後に **convert project to MPP** を Aspose.Tasks Java API を使用して実行する手順をすべて解説します。

## クイック回答
- **What does this tutorial cover?** カレンダーに祝日を追加し、プロジェクトに割り当て、Aspose.Tasks for Javaで結果をMPPファイルとして保存します。  
- **Do I need a license?** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **Which Java version is required?** Java 8 以上 (JDK 8+) が必要です。  
- **Can I customize the calendar?** はい、作業時間、例外、祝日を追加できます。  
- **How long does implementation take?** 基本的なカレンダーで約10〜15分です。  

## “create calendar MS Project”とは？

カレンダー MS Project を作成することは、Microsoft Project ファイル内でタスクのスケジューリングを制御する作業日、作業時間、例外を定義することを意味します。Aspose.Tasks を使用すれば、コードからこのカレンダーを構築し、祝日を設定し、MS Project の UI を開かずにプロジェクトに埋め込むことができます。

## なぜこのタスクにAspose.Tasksを使用するのか？

Aspose.Tasks を使用すべき理由は、完全な Java 互換性があり、Microsoft Office が不要で、コードから直接ネイティブ MPP ファイルを生成・保存できる点です。ライブラリはすべてのカレンダー機能をサポートし、任意のサーバー環境で動作し、10,000 タスクまでのプロジェクトを 1 秒未満で処理します。

## 前提条件

1. **Java Development Kit (JDK) 8+** – `java -version` が 1.8 以上であることを確認してください。  
2. **Aspose.Tasks for Java** – 最新の JAR を [Aspose website](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **IDE** – IntelliJ IDEA、Eclipse、またはお好みのエディタ。  
4. **Basic Java knowledge** – クラス、メソッド、ファイル I/O に慣れていること。  

## カレンダーに祝日を追加する方法

カレンダーに祝日を追加するには、新しい `Calendar` オブジェクトを作成し、その `Exceptions` コレクションを取得して、各祝日の日付に対して `DateException` エントリを追加します。`DateException` はカレンダー内の単一の非作業日または期間を表します。Aspose.Tasks はこれらの日付を非作業日として扱い、タスクが定義された祝日を回避してスケジュールされます。

### 手順 1: 必要なパッケージをインポート

まず、Aspose.Tasks のクラスと Java のユーティリティをスコープに持ち込みます。

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 手順 2: データディレクトリを設定

入力テンプレートと出力ファイルが格納される場所を定義します。プレースホルダーを実際のパスに置き換えてください。

```java
String dataDir = "Your Data Directory";
```

### 手順 3: 入力および出力ファイル名を定義

既存の MPP ファイル（または空のプロジェクト）をロードし、結果を新しいファイルに書き込みます。

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 手順 4: プロジェクトをロードし、新しいカレンダーを追加

`Project` クラスはメモリ内の MS Project ファイルを表し、カレンダー、タスク、リソースへのアクセスを提供します。

ソースファイルから `Project` インスタンスを作成し、**“Calendar 1”** という名前のカレンダーを追加します。

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 手順 5: カレンダーをカスタマイズ（オプション）

`Calendar` オブジェクトはプロジェクトスケジュールの作業日、作業時間、例外を定義します。

特定の作業時間、祝日、例外が必要な場合は、独自のヘルパーメソッドを呼び出してください。サンプルでは `GetTestCalendar` をプレースホルダーとして使用しています。

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** `cal1.getWeekDays()` を直接操作して各曜日の作業時間を設定したり、`cal1.getExceptions()` を使用して **add holidays to calendar** を行うことができます。

### 手順 6: カレンダーをプロジェクトに割り当て

新しく作成したカレンダーをプロジェクト全体のスケジューリング計算に使用するよう指示します。

```java
project.set(Prj.CALENDAR, cal1);
```

### 手順 7: プロジェクトをMPPとして保存

`SaveFileFormat` 列挙型は出力形式を指定し、`Mpp` はネイティブ Microsoft Project 形式を示します。

`SaveFileFormat.Mpp` オプションで保存し、**convert project to MPP** を実行します。

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 手順 8: 正常完了を確認

簡単なコンソールメッセージで、エラーなしで処理が完了したことを通知します。

```java
System.out.println("Process completed Successfully");
```

## 一般的な使用例

- **Automated schedule generation** の自動スケジュール生成（例：週次スプリント）  
- **Migrating legacy CSV or Excel calendars** をフル機能の MS Project ファイルに移行  
- **Server‑side reporting** で、Web サービスが要求に応じて MPP ファイルを返す  

## トラブルシューティングと一般的な落とし穴

| 問題 | 原因 | 対策 |
|------|------|------|
| `NullPointerException` on `project.save` | `dataDir` が存在しないフォルダーを指している | ディレクトリが存在することを確認するか、プログラムで作成してください。 |
| カレンダーがタスクに適用されていない | タスクがまだデフォルトカレンダーを参照している | `Prj.CALENDAR` を設定した後、以前に上書きされている場合は各タスクの `Task.CALENDAR` も更新してください。 |
| 出力ファイルが 0 KB です | 書き込み権限がない | JVM を適切なファイルシステム権限で実行するか、書き込み可能なパスを選択してください。 |

## よくある質問

**Q: Aspose.Tasks for Java はさまざまなバージョンの MS Project と互換性がありますか？**  
**A:** はい、Aspose.Tasks は Project 2007 から Project 2024 までのすべての Microsoft Project ファイル形式をサポートしており、10 以上のバージョンに対応しています。

**Q: 特定のプロジェクト要件に合わせてカレンダーをカスタマイズできますか？**  
**A:** もちろんです。作業日を定義し、カスタム作業週を設定し、祝日を追加し、さらに単一プロジェクトファイル内に複数のカレンダーを作成することも可能です。

**Q: Aspose.Tasks for Java はトラブルシューティングやサポートを提供していますか？**  
**A:** はい、[Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15) でサポートを受けることができます。

**Q: Aspose.Tasks for Java の無料トライアルは利用できますか？**  
**A:** はい、[Aspose.Tasks free trial](https://releases.aspose.com/) で完全機能の無料トライアルが利用可能です。

**Q: Aspose.Tasks for Java の一時ライセンスはどう取得できますか？**  
**A:** 一時ライセンスは [Aspose temporary license request](https://purchase.aspose.com/temporary-license/) からリクエストできます。

---

**最終更新日:** 2026-08-13  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Tasks for Javaでプロジェクトにカレンダーを追加](/tasks/java/calendars/create/)
- [MS Project カレンダーで平日を定義する方法 – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aspose.Tasks for Javaでカスタムカレンダー例外を作成](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}