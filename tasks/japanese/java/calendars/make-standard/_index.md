---
date: 2026-08-13
description: Aspose.Tasks を使用して Java で標準の MS Project カレンダーを作成する方法を学びます。このステップバイステップガイドでは、標準の
  MS Project カレンダーを作成し、デフォルトとして設定し、ファイルを保存する手順を示します。
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Aspose.Tasks で標準カレンダーを作成
og_description: Aspose.Tasks を使用した Java でのカレンダー作成方法。標準の MS Project カレンダーを構築し、デフォルトに設定し、数分でプロジェクトファイルを保存する方法を学びます。
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: カレンダーの作成方法 – Aspose.Tasksで標準カレンダーを作成
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: カレンダーの作成方法 – Aspose.Tasksで標準カレンダーを作成
url: /ja/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# カレンダーの作成方法 – Aspose.Tasksで標準カレンダーを作成する

## はじめに
このチュートリアルでは、Aspose.Tasks for Java ライブラリを使用して Microsoft Project ファイル用のカレンダー オブジェクトを **作成する方法** を学びます。標準的な MS Project カレンダーを作成し、それをデフォルト（標準）カレンダーに設定し、プロジェクト ファイルを保存する手順を順に説明します。ガイドの最後までに、任意の Java ベースのプロジェクト管理ソリューションにカレンダー作成を統合できるようになります。

## クイック回答
- **「標準カレンダー」とは何ですか？** カスタム カレンダーが割り当てられていないタスクに適用されるデフォルトの作業時間定義です。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java – Microsoft Project がインストールされていなくても動作する純粋な Java API です。  
- **ライセンスは必要ですか？** 開発目的であれば無料トライアルで動作しますが、本番環境での展開には商用ライセンスが必要です。  
- **生成されるファイル形式は何ですか？** XML ベースの Microsoft Project ファイル（`.xml`）です。  
- **実装にどれくらい時間がかかりますか？** 基本的なカレンダー設定で約 5〜10 分です。

## Microsoft Project の標準カレンダーとは何ですか？
標準カレンダーは、プロジェクトのデフォルトの作業日と作業時間を定義します。通常は月曜日から金曜日の午前 8 時から午後 5 時です。標準カレンダーを追加すると、カスタム カレンダーが割り当てられていないタスクはこれらの作業時間を継承し、プロジェクト全体で一貫したスケジューリングが確保されます。

## カレンダー作成に Aspose.Tasks を使用する理由は何ですか？
Aspose.Tasks for Java は **50 以上の入力および出力形式** をサポートし、**10,000 タスク** までのプロジェクトをファイル全体をメモリにロードせずに処理できます。この純粋な Java ライブラリを使用すると、サーバー、CI パイプライン、または任意の Java アプリケーション上で Project ファイルの作成を自動化でき、ライセンス付き Microsoft Project のインストールが不要になります。

## 前提条件
開始する前に、以下が準備されていることを確認してください。

### Java Development Kit (JDK) のインストール
Oracle のウェブサイトまたは OpenJDK ディストリビューションから最新の JDK をインストールしてください。

### Aspose.Tasks for Java ライブラリ
ライブラリは[ダウンロードページ](https://releases.aspose.com/tasks/java/)から取得してください。JAR をプロジェクトのクラスパスに追加します。

## パッケージのインポート
このチュートリアルではインポートが 1 つだけ必要です。

```java
import com.aspose.tasks.*;
```

## ステップバイステップ ガイド

### ステップ 1: データ ディレクトリの設定
生成されたプロジェクト ファイルの保存先を定義します。

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` をマシン上の絶対パスに置き換えてください（例: `C:/Projects/Output/`）。

### ステップ 2: プロジェクト インスタンスの作成
`Project` は Aspose.Tasks のトップレベルオブジェクトで、メモリ内の単一の Microsoft Project ファイルを表します。インスタンス化することで、カレンダー、タスク、リソース、その他のプロジェクト データのコンテナが得られます。

```java
Project project = new Project();
```

### ステップ 3: カレンダーを定義し標準に設定する
`Calendar` は作業時間スケジュールをモデル化するクラスです。**“My Cal”** という名前の新しいカレンダーを追加し、`makeStandardCalendar` を呼び出すと、プロジェクト全体のデフォルト カレンダーとして設定されます。

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **プロのヒント:** `makeStandardCalendar` メソッドは、指定したカレンダーをプロジェクトのデフォルトとして自動的にマークします。これは **標準カレンダーを追加** する機能が必要なときにまさに求められる動作です。

### ステップ 4: プロジェクトの保存
SaveFileFormat は、プロジェクトを保存する際に使用するファイル形式を指定する列挙型です。  
新しいカレンダーを含むプロジェクトを XML ファイルに永続化します。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

別の Project バージョンが必要な場合は、ファイル名や形式（`SaveFileFormat.Pp`）を変更できます。

### ステップ 5: 完了メッセージの表示
エラーなく処理が完了したことを視覚的に示すメッセージを表示します。

```java
System.out.println("Process completed Successfully");
```

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|-------|-------|-----|
| **ファイルが見つかりません** | `dataDir` が存在しないフォルダーを指しています | フォルダーを作成するか、絶対パスを使用してください |
| **ライセンス例外** | 本番環境で有効な Aspose.Tasks ライセンスなしで実行しています | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` を使用してライセンス ファイルを適用します |
| **空のカレンダー** | 作業時間定義の追加を忘れています | カスタム時間が必要な場合は `cal1.getWeekDays().add(WeekDay.DayType.Monday)` などを使用してください |

## よくある質問

**Q: Aspose.Tasks はすべてのバージョンの Microsoft Project と互換性がありますか？**  
A: はい、Aspose.Tasks は 2000 年版から最新リリースまで、幅広い Microsoft Project バージョンをサポートしています。

**Q: カレンダー設定をさらにカスタマイズできますか？**  
A: もちろんです！`WeekDay` と `WorkingTime` クラスを使用して、作業日を変更したり、例外を追加したり、特定の作業時間を定義したりできます。

**Q: Aspose.Tasks はエンタープライズレベルのアプリケーションに適していますか？**  
A: はい。ライブラリは高性能でスケーラブルな環境向けに設計されており、大規模な Project ファイルに対する包括的なサポートを提供します。

**Q: Aspose.Tasks は開発者向けの技術サポートを提供していますか？**  
A: はい、Aspose は専用フォーラム、チケットベースのサポート、豊富なドキュメントを提供し、問題を迅速に解決できるよう支援します。

**Q: 購入前に Aspose.Tasks を試すことはできますか？**  
A: はい、[ウェブサイト](https://purchase.aspose.com/buy) で利用できる無料トライアル版を試すことで、すべての機能を評価した上で購入を検討できます。

---

**最終更新日:** 2026-08-13  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks for Java を使用してプロジェクトにカレンダーを追加する](/tasks/java/calendars/create/)
- [Aspose.Tasks を使用した Java のプロジェクト カレンダー設定方法](/tasks/java/calendars/properties/)
- [Aspose.Tasks for Java でカスタム カレンダー例外を作成する](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}