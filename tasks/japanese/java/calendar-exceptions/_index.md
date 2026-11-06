---
date: 2026-11-06
description: Aspose.Tasks を使用した Java プロジェクトで、カスタム calendar exceptions を簡単に作成し、MS Project
  カレンダーを統合し、calendar exceptions の管理、定義、処理、取得を行います。プロジェクトワークフローを効率化し、効果的なプロジェクト管理を実現します。
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Calendar Exceptions
og_description: Aspose.Tasks を使用して Java で calendar exceptions の作成方法を学びます。プロジェクト カレンダーを管理し、nonworking
  days を設定し、MS Project カレンダーを効率的に変更します。
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Aspose.Tasks for Java で calendar exceptions を作成
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks for Java を使用して calendar exceptions を作成する方法
url: /ja/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Javaでカレンダー例外を作成する方法

## はじめに

`Aspose.Tasks` は、Microsoft Project ファイルのプログラムによる作成、操作、変換を可能にする Java ライブラリです。このチュートリアルでは、**カレンダー例外の作成**（プロジェクトのデフォルトカレンダーを上書きするカスタムの非作業期間）について学びます。作業日と非作業日の正確な管理は、正確なスケジュール予測、リソース配分、地域の祝日に対するコンプライアンスに不可欠です。本ガイドの最後までに、**MS Project カレンダーを Java アプリケーションに統合し、その例外を取得または変更する方法**も理解できるようになります。

## クイック回答
- **What can I achieve?** カスタムカレンダー例外を作成、変更、取得できます。  
- **Which library is required?** 必要なライブラリは Aspose.Tasks for Java（最新の安定版）です。  
- **Do I need a license?** はい、製品版の使用には有効な Aspose.Tasks ライセンスが必要です。  
- **Can I work with MS Project files?** もちろんです。MS Project のカレンダー データをインポート、編集、エクスポートできます。  
- **Is any special setup needed?** Aspose.Tasks の JAR をクラスパスに追加し、関連クラスをインポートするだけです。

## Aspose.Tasks for Javaでカスタムカレンダー例外を作成する方法

Aspose.Tasks for Javaでカスタムカレンダー例外を作成するには、対象の Project をロードし、その Calendar を取得し、例外の開始日と終了日を希望の作業時間で定義し、必要に応じて繰り返しパターンを設定してからプロジェクトを保存します。この手順により例外が即座に追加され、.mpp ファイルに永続化されます。

`Project` クラスは、Aspose.Tasks の主要オブジェクトで、Microsoft Project ファイル全体をモデル化します。`Project` クラスは Microsoft Project ファイルを表し、その内容へのアクセスを提供します。`Calendar` オブジェクトはプロジェクトの作業時間と非作業時間を定義します。`Calendar` クラスは例外を含むすべての作業時間ルールのコンテナです。`addException()` メソッドはカレンダーに新しい例外を追加します。`addException()` は、指定した日付範囲の非作業期間を登録するシングルコール API です。

`Project project = new Project("example.mpp")` で対象プロジェクトをロードし、`Calendar` オブジェクトを取得して、希望する日付範囲と作業時間設定で `addException()` を呼び出します。この2ステップのパターンにより新しい例外が即座に作成され、プロジェクトを保存すると永続化されます。繰り返しの祝日については、保存前に例外の `RecurrencePattern` を設定してください。

この方法でカレンダー例外を作成すると、**非作業日を正確に設定**でき、単発の停止や年次の祝日などに対応できます。例外を追加した後は、`project.save("updated.mpp")` を呼び出して変更をディスクに書き戻すことができます。

### 手順概要
1. プロジェクト ファイルをロードする。  
2. `Calendar` インスタンスを取得または作成する。  
3. 例外の日付範囲と作業時間を定義する。  
4. （オプション）年次祝日の繰り返しを設定する。  
5. プロジェクトを保存する。

## Aspose.Tasksでカレンダー例外を管理する

[Aspose.Tasks for Javaでカレンダー例外の追加と削除を効率的に行う方法を学ぶ](./add-remove/)。プロジェクト管理において柔軟性は重要です。Aspose.Tasks はカレンダー例外を簡単に管理できるようにし、プロジェクトのタイムラインを動的に調整できます。このチュートリアルはステップバイステップのガイドを提供し、プロセスを効率的に把握できるようにします。簡単にプロジェクト管理ワークフローを強化する方法を発見してください。

## Aspose.Tasksでカレンダー例外の平日を定義する

[Java プロジェクトでカレンダー例外の平日を定義する技術をマスターする](./define-weekdays/) Aspose.Tasks を使用します。正確なプロジェクトスケジューリングには細部への注意が必要です。Aspose.Tasks を使えば、カレンダー例外の平日を正確に定義でき、プロジェクトが特定のタイムラインにシームレスに合わせられます。このチュートリアルはスケジューリング最適化の知識を提供し、プロジェクトのタイムラインをコントロールできるようにします。

## Aspose.Tasksでカレンダー例外の発生を処理する

[Java プロジェクトでカレンダー例外を効果的に処理する](./handle-occurrences/) Aspose.Tasks for Java を使用します。プロジェクト管理は動的なプロセスであり、予期しない事象への調整がしばしば必要です。Aspose.Tasks はカレンダー例外を効果的に処理できるようにし、プロジェクト管理を簡素化します。この詳細なチュートリアルで、プロジェクトの不確実性を容易に管理する技術を学びましょう。

## Aspose.Tasksでカレンダー例外を取得する

[Aspose.Tasks for Java を使用して MS Project からカレンダー例外を取得する方法を学ぶ](./retrieve/)。Aspose.Tasks でカレンダー例外をプロジェクト管理プロセスにシームレスに統合できます。このチュートリアルはカレンダー例外取得のステップバイステッププロセスを案内し、プロジェクトへのスムーズで効率的な統合を保証します。Aspose.Tasks の力を活用してプロジェクト管理機能を強化しましょう。

## Aspose.Tasks と MS Project カレンダーを統合する方法

Aspose.Tasks と MS Project カレンダーを統合するには、Project クラスを使用してソースの .mpp ファイルをロードし、デフォルトまたはカスタムの Calendar オブジェクトにアクセスし、必要に応じて例外を変更またはマージし、更新されたプロジェクトを保存します。これにより、手動の UI 操作なしでプログラムから MS Project カレンダーを操作できます。

`Project` クラスは、Aspose.Tasks の主要オブジェクトで、Microsoft Project ファイル全体をモデル化します。`new Project("source.mpp")` を使用して既存の MS Project ファイルをインポートすると、ライブラリは自動的にデフォルトカレンダーとカスタム例外をロードします。その後、例外を読み取り、変更、またはマージしてからプロジェクトをディスクに保存できます。このアプローチにより、MS Project の UI で手動編集することなく、**MS Project カレンダー** データをプログラムで変更できます。

## 一般的な使用例
- **Holiday scheduling** – 複数のプロジェクトで国の祝日を非作業日として定義します。  
- **Shift work** – 標準外のスケジュールで運用するチーム向けにカスタム作業週を設定します。  
- **Project phase gating** – メンテナンスウィンドウなど、作業をスケジュールすべきでない期間をブロックします。  
- **Legacy migration** – 古い MS Project ファイルからカレンダーをインポートし、プログラムで調整します。

## ヒントとベストプラクティス
- **Pro tip:** 重複を防ぐため、常に新しい例外を追加する前に既存のカレンダーを取得してください。  
- **Warning:** すでにタスクに割り当てられているカレンダーを変更するとタスクの日付がシフトする可能性があります。変更後はスケジュールを再計算してください。  
- **Performance:** 複数の例外更新を単一のトランザクションでバッチ処理し、ファイル I/O のオーバーヘッドを削減します。Aspose.Tasks は最大 1 GB のファイルをメモリ使用量 200 MB 未満で処理でき、一般的なサーバーハードウェア上で秒間 30 件以上のカレンダー関連 API 呼び出しを処理できます。

## カレンダー例外チュートリアル
### [Aspose.Tasksでカレンダー例外を管理する](./add-remove/)
Aspose.Tasks for Javaでカレンダー例外の追加と削除を効率的に行う方法を学びます。プロジェクト管理ワークフローを簡単に強化できます。

### [Aspose.Tasksでカレンダー例外の平日を定義する](./define-weekdays/)
Aspose.Tasks を使用して Java プロジェクトでカレンダー例外の平日を定義し、正確なプロジェクトスケジューリングを実現する方法を学びます。

### [Aspose.Tasksでカレンダー例外の発生を処理する](./handle-occurrences/)
Aspose.Tasks for Java を使用して Java プロジェクトでカレンダー例外を効果的に処理する方法を学びます。今すぐプロジェクト管理プロセスを効率化しましょう。

### [Aspose.Tasksでカレンダー例外を取得する](./retrieve/)
Aspose.Tasks for Java を使用して MS Project からカレンダー例外を取得する方法を学びます。シームレスな統合のためのステップバイステップチュートリアルです。

## よくある質問

**Q: プロジェクトが既に公開された後でもカレンダー例外を変更できますか？**  
A: はい。add‑remove と define‑weekdays API を使用してカレンダーを更新し、プロジェクト ファイルを再保存してください。

**Q: Aspose.Tasks は繰り返しの例外（例：毎月第1月曜日）をサポートしていますか？**  
A: もちろんです。「handle occurrences」チュートリアルで繰り返しパターンの設定方法を取り上げています。

**Q: カスタムカレンダーがプロジェクト内のすべてのタスクで使用されるようにするには？**  
A: カレンダーをプロジェクトのデフォルトカレンダーに割り当てるか、各タスクの `Calendar` プロパティに明示的に設定してください。

**Q: 複数の MS Project ファイルからカレンダーをマージすることは可能ですか？**  
A: はい。各カレンダーを取得し、例外をプログラムで結合してから、マージしたカレンダーを対象プロジェクトに割り当てます。

**Q: これらの機能に必要な Aspose.Tasks のバージョンは？**  
A: すべての機能は現在の安定版 Aspose.Tasks for Java (2025.x) で利用可能です。

## 関連チュートリアル
- [プロジェクト カレンダー作成 Aspose – カレンダー例外の平日を定義する](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasksでカレンダー例外を取得する – asp tasks java チュートリアル](/tasks/java/calendar-exceptions/retrieve/)
- [Aspose for Javaでカレンダー例外を作成する](/tasks/java/calendar-exceptions/add-remove/)

---
**最終更新日:** 2026-11-06  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}