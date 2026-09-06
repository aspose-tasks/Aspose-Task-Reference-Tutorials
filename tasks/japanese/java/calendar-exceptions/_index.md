---
date: 2026-08-18
description: Aspose.Tasks を使用し、Java プロジェクトでカスタム calendar exceptions を簡単に作成し、MS Project
  カレンダーと統合し、calendar exceptions の管理、定義、処理、取得を行えます。プロジェクトワークフローを効率化し、効果的なプロジェクト管理を実現します。
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: Calendar Exceptions
og_description: Aspose.Tasks を使用して Java で calendar exceptions を作成し、プロジェクトカレンダーを管理し、nonworking
  days を設定する方法を学びます。開発者向けの簡潔なガイドです。
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Aspose.Tasks for Java を使用して calendar exceptions を作成する方法
schemas:
- author: Aspose
  dateModified: '2026-08-18'
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

# Aspose.Tasks for Java を使用したカレンダー例外の作成方法

## 概要

`Aspose.Tasks` は、Microsoft Project ファイルのプログラムによる作成、操作、変換を可能にする Java ライブラリです。このチュートリアルでは、**カレンダー例外の作成**（プロジェクトのデフォルトカレンダーを上書きするカスタムの非稼働期間）方法を学びます。作業日と非稼働日の正確な管理は、スケジュール予測、リソース配分、地域の祝日への準拠に不可欠です。本ガイドの最後までに、**MS Project カレンダーを Java アプリケーションに統合し**、例外を取得または変更する方法も理解できるようになります。

## クイック回答
- **何が実現できますか？** Java プロジェクトでカスタムカレンダー例外を作成、変更、取得できます。  
- **どのライブラリが必要ですか？** Aspose.Tasks for Java（最新の安定版）。  
- **ライセンスは必要ですか？** はい、製品環境で使用するには有効な Aspose.Tasks ライセンスが必要です。  
- **MS Project ファイルを扱えますか？** もちろんです。MS Project のカレンダーデータをインポート、編集、エクスポートできます。  
- **特別なセットアップは必要ですか？** Aspose.Tasks の JAR をクラスパスに追加し、関連クラスをインポートするだけです。

## Aspose.Tasks for Java でカスタムカレンダー例外を作成する方法？

`Project` クラスは Microsoft Project ファイルを表し、その内容にアクセスできます。`Calendar` オブジェクトはプロジェクトの稼働時間と非稼働時間を定義します。`addException()` メソッドはカレンダーに新しい例外を追加します。

対象プロジェクトは `Project project = new Project("example.mpp")` でロードし、`Calendar` オブジェクトを取得して、希望する日付範囲と稼働時間設定で `addException()` を呼び出します。この 2 段階のパターンにより、例外は即座に作成され、プロジェクトを保存すると永続化されます。繰り返しの祝日については、保存前に例外の `RecurrencePattern` を設定します。

この方法でカレンダー例外を作成すると、**非稼働日を正確に設定**でき、単発の停止や年次祝日などに対応できます。例外を追加した後、`project.save("updated.mpp")` を呼び出して変更をディスクに書き戻すことができます。

### 手順概要
1. プロジェクトファイルをロードする。  
2. `Calendar` インスタンスを取得または作成する。  
3. 例外の日付範囲と稼働時間を定義する。  
4. (オプション) 年次祝日の繰り返しを設定する。  
5. プロジェクトを保存する。

## Aspose.Tasks でカレンダー例外を管理する
[Aspose.Tasks for Java でカレンダー例外を効率的に追加・削除する方法を学ぶ](./add-remove/)。プロジェクト管理において柔軟性は重要です。Aspose.Tasks はカレンダー例外を簡単に管理できるようにし、プロジェクトのタイムラインを動的に調整できます。このチュートリアルはステップバイステップのガイドを提供し、プロセスを効率的に習得できるようにします。簡単にプロジェクト管理ワークフローを強化する方法を発見してください。

## Aspose.Tasks でカレンダー例外の平日を定義する
[Aspose.Tasks を使用して Java プロジェクトのカレンダー例外の平日を定義する方法をマスターする](./define-weekdays/)。正確なプロジェクトスケジューリングには細部への注意が必要です。Aspose.Tasks を使えば、カレンダー例外の平日を正確に定義でき、プロジェクトをシームレスに特定のタイムラインに合わせられます。このチュートリアルはスケジューリング最適化に必要な知識を提供し、プロジェクトタイムラインのコントロールを可能にします。

## Aspose.Tasks を使用したカレンダー例外の発生処理
[Aspose.Tasks for Java で Java プロジェクトのカレンダー例外を効果的に処理する方法](./handle-occurrences/)。プロジェクト管理は動的なプロセスであり、予期せぬ事象に対応する調整が頻繁に求められます。Aspose.Tasks はカレンダー例外を効果的に処理できるようにし、プロジェクト管理をスムーズにします。この詳細なチュートリアルで、プロジェクトの不確実性を簡単に管理する方法を学んでください。

## Aspose.Tasks でカレンダー例外を取得する
[Aspose.Tasks for Java を使用して MS Project からカレンダー例外を取得する方法を学ぶ](./retrieve/)。Aspose.Tasks を使ってカレンダー例外をプロジェクト管理プロセスにシームレスに統合できます。このチュートリアルはカレンダー例外の取得手順をステップバイステップで案内し、プロジェクトへのスムーズで効率的な統合を実現します。Aspose.Tasks の力を活用してプロジェクト管理機能を強化してください。

## Aspose.Tasks と MS Project カレンダーを統合する方法

`Project` クラスは Microsoft Project ファイルをロードし、カレンダーやその他のプロジェクトデータを公開します。`new Project("source.mpp")` で既存の MS Project ファイルをインポートすると、ライブラリはデフォルトカレンダーとカスタム例外を自動的にロードします。その後、例外を読み取り、変更、またはマージしてからプロジェクトをディスクに保存できます。このアプローチにより、MS Project UI で手動編集することなく、**MS Project カレンダー** データをプログラムで変更できます。

## 一般的な使用例
- **休日スケジューリング** – 複数プロジェクトで国の祝日を非稼働日として定義する。  
- **シフト勤務** – 標準外のスケジュールで運用するチーム向けにカスタム作業週を設定する。  
- **プロジェクトフェーズのゲーティング** – メンテナンスウィンドウなど、作業をスケジュールすべきでない期間をブロックする。  
- **レガシー移行** – 古い MS Project ファイルからカレンダーをインポートし、プログラムで調整する。

## ヒントとベストプラクティス
- **プロのコツ:** 重複を防ぐため、常に新しい例外を追加する前に既存のカレンダーを取得してください。  
- **警告:** すでにタスクに割り当てられているカレンダーを変更するとタスクの日付がずれる可能性があります。変更後はスケジュールを再計算してください。  
- **パフォーマンス:** 複数の例外更新を単一トランザクションでバッチ処理し、ファイル I/O のオーバーヘッドを削減します。Aspose.Tasks は、ドキュメント全体をメモリにロードせずに最大 500 MB のファイルを処理し、一般的なサーバーハードウェアで秒間 50 件以上のカレンダー関連 API 呼び出しを処理します。

## カレンダー例外チュートリアル
### [Aspose.Tasks でカレンダー例外を管理する](./add-remove/)
Aspose.Tasks for Java でカレンダー例外を効率的に追加・削除する方法を学びます。プロジェクト管理ワークフローを手間なく強化できます。
### [Aspose.Tasks でカレンダー例外の平日を定義する](./define-weekdays/)
Aspose.Tasks を使用して Java プロジェクトのカレンダー例外の平日を定義し、正確なプロジェクトスケジューリングを実現する方法を学びます。
### [Aspose.Tasks を使用したカレンダー例外の発生処理](./handle-occurrences/)
Aspose.Tasks for Java で Java プロジェクトのカレンダー例外を効果的に処理する方法を学び、プロジェクト管理プロセスを今すぐ合理化します。
### [Aspose.Tasks でカレンダー例外を取得する](./retrieve/)
Aspose.Tasks for Java を使用して MS Project からカレンダー例外を取得する方法を学びます。シームレスな統合のためのステップバイステップチュートリアルです。

## よくある質問

**Q: プロジェクトがすでに公開された後でもカレンダー例外を変更できますか？**  
**A:** はい。add‑remove と define‑weekdays API を使用してカレンダーを更新し、プロジェクトファイルを再保存すれば変更できます。

**Q: 繰り返しの例外（例：毎月第1月曜日）をサポートしていますか？**  
**A:** もちろんです。「カレンダー例外の発生処理」チュートリアルで繰り返しパターンの設定方法を取り上げています。

**Q: カスタムカレンダーがプロジェクト内のすべてのタスクで使用されていることをどう保証しますか？**  
**A:** カレンダーをプロジェクトのデフォルトカレンダーに割り当てるか、各タスクの `Calendar` プロパティに明示的に設定してください。

**Q: 複数の MS Project ファイルからカレンダーをマージすることは可能ですか？**  
**A:** はい。各カレンダーを取得し、例外をプログラムで結合してから、統合したカレンダーを対象プロジェクトに割り当てます。

**Q: これらの機能に必要な Aspose.Tasks のバージョンは？**  
**A:** すべての機能は現在の安定版 Aspose.Tasks for Java（2025.x）で利用可能です。

---

**最終更新日:** 2026-08-18  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose

## 関連チュートリアル

- [Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions](/tasks/java/calendar-exceptions/define-weekdays/)
- [Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Create Calendar Exception Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}