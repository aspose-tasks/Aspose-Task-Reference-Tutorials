---
date: 2026-08-03
description: Aspose.Tasks for Java を使用して、ms project カレンダーの作成方法、プロジェクトへのカレンダー追加方法、XML
  形式でプロジェクトを保存する方法を学びます。
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Aspose.Tasks を使用してプロジェクトにカレンダーを追加
og_description: Aspose.Tasks for Java を使用してプログラムで ms project カレンダーを作成します。カレンダーを追加し、スケジュールをカスタマイズし、数分で
  XML にエクスポートできます。
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Aspose.Tasks for Java を使用して ms project カレンダーを作成する
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java を使用して ms project カレンダーを作成する
url: /ja/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用して MS Project カレンダーを作成する

## はじめに
最新のプロジェクト管理ワークフローでは、プログラムで **create ms project calendar** を作成できることにより、手作業の編集にかかる時間を何時間も節約できます。Aspose.Tasks for Java は、デスクトップクライアントを開くことなく Microsoft Project ファイルを操作できる、クリーンで型安全な API を提供します。このチュートリアルでは、カレンダーの追加方法、MS Project カレンダーの作成方法、プロジェクトを XML として保存する方法を、数行の Java コードだけで学びます。

## クイック回答
- **create ms project calendar の意味は何ですか？**  
  Microsoft Project ファイルにコードで新しい作業時間定義（カレンダー）を挿入することを意味します。  
- **どのライブラリがこれを処理しますか？**  
  Aspose.Tasks for Java は `Calendar` クラスと `Project` コンテナを提供し、カレンダーを管理します。  
- **ライセンスは必要ですか？**  
  テスト用には一時的な評価ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **ファイルを XML として保存できますか？**  
  はい — `SaveFileFormat.Xml` を使用してプロジェクトを XML ファイルとしてエクスポートします。  
- **前提条件は何ですか？**  
  Java JDK 8 以上と、クラスパスに Aspose.Tasks for Java の JAR が必要です。

## create ms project calendar とは何ですか？
MS Project カレンダーを作成することは、プログラムで新しいカレンダー定義をプロジェクトファイルに追加し、作業日、例外、日々の作業時間を指定し、そのカレンダーをタスク、リソース、またはプロジェクト全体に割り当てて、スケジュール計算が定義された作業時間を考慮するようにすることを意味します。

## プロジェクトにカレンダーを追加するために Aspose.Tasks for Java を使用する理由は？
Microsoft Project がインストールされていなくても動作する完全な型安全 API を提供し、主要な Project バージョン（2007‑2021、5 以上のリリース）すべてをサポートし、XML、MPP、**10+** のその他の形式へエクスポートできるため、任意のサーバー上で自動化された大量のカレンダー作成が可能になるからです。

## 前提条件
- **Java Development Kit (JDK) 8 以上** がインストールされ、設定されていること。  
- **Aspose.Tasks for Java** ライブラリ – [公式サイト](https://releases.aspose.com/tasks/java/) からダウンロードし、JAR をプロジェクトのクラスパスに追加します。  
- お好みの IDE またはビルドツール（Maven/Gradle）。

## 手順ガイド

### 手順 1: 必要な Aspose.Tasks パッケージをインポートする
まず、Aspose.Tasks のクラスをスコープに持ち込み、プロジェクトやカレンダーを操作できるようにします。

```java
import com.aspose.tasks.*;
```

### 手順 2: データディレクトリのパスを設定する
生成されたプロジェクトファイルを書き込む場所を定義します。プレースホルダーをマシン上の絶対パスまたは相対パスに置き換えてください。

```java
String dataDir = "Your Data Directory";
```

### 手順 3: 新しい Project インスタンスを作成する
`Project` は、メモリ内で Microsoft Project ファイルを表すコアクラスです。

```java
Project prj = new Project();
```

### 手順 4: 追加したいカレンダーを定義する
`Calendar` は、プロジェクトの作業日、例外、作業時間を含むスケジュールを定義します。

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **プロのコツ:** カレンダーを追加した後、`cal1.getWeekDays().add(...)` で作業日をカスタマイズでき、`cal1.getBaseCalendar().setWorkingTime(...)` で日々の作業時間を設定できます。

### 手順 5: プロジェクトを保存する（XML として保存）
`SaveFileFormat.Xml` は、Aspose.Tasks にプロジェクトを XML 形式で書き出すよう指示します。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 手順 6: 完了メッセージを表示する
操作が正常に完了したことをユーザーに知らせます。

```java
System.out.println("Process completed Successfully");
```

これらの 6 つの簡潔な手順に従うことで、**カレンダーをプロジェクトに追加**し、結果を XML ファイルとして保存することに成功しました。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Project オブジェクトが正しく初期化されていません。 | `new Project()` がカレンダーにアクセスする前に呼び出されていることを確認してください。 |
| **保存時にファイルが見つからない** | `dataDir` が存在しないフォルダーを指しています。 | まずディレクトリを作成するか、絶対パスを使用してください。 |
| **カレンダー名が “no info” と表示される** | サンプルでプレースホルダー名が使用されていました。 | スケジュールを反映した意味のある名前に置き換えてください（例: “US Holiday Calendar”。） |
| **保存した XML が MS Project で開けない** | 古いバージョンの Aspose.Tasks を使用しています。 | 最新の Aspose.Tasks for Java リリースに更新してください。 |

## よくある質問

**Q: Aspose.Tasks は複数の例外を持つ複雑なカレンダーを処理できますか？**  
A: はい — カレンダーを追加した後、`WeekDay` と `Exception` クラスを使用して例外、作業時間、非作業日を定義できます。

**Q: 新しいカレンダーを特定のタスクに割り当てることは可能ですか？**  
A: もちろんです。`prj.getRootTask().getChildren().add("Task Name")` でタスクを取得し、`task.set(Tsk.CALENDAR, cal3);` でカレンダーを設定します。

**Q: ライブラリは MPP などの他の形式での保存をサポートしていますか？**  
A: はい。必要に応じて `SaveFileFormat.Xml` を `SaveFileFormat.Mpp` または `SaveFileFormat.P6` に置き換えてください。Aspose.Tasks は **12** の出力形式をサポートしています。

**Q: 開発ビルドにライセンスは必要ですか？**  
A: テストには一時的な評価ライセンスで十分ですが、本番環境のデプロイにはフルライセンスが必要です。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: Aspose.Tasks コミュニティフォーラムは優れたリソースです: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

---

**最終更新日:** 2026-08-03  
**テスト環境:** Aspose.Tasks for Java 24.12（執筆時点の最新）  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [MS Project カレンダーで平日を定義する方法 – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aspose.Tasks を使用した Java のプロジェクト カレンダー設定方法](/tasks/java/calendars/properties/)
- [Aspose.Tasks for Java でカスタム カレンダー例外を作成する](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}