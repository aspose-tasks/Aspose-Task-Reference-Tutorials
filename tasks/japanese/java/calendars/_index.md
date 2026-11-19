---
date: 2026-11-19
description: Aspose.Tasks を使用して Java のカスタム カレンダーを作成する方法を学びます。このガイドでは、作業日を定義し、作業時間を設定し、MS
  Project のカレンダーをプログラムで変更する手順を示します。
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: カレンダー
og_description: Aspose.Tasks を使用した Java のカスタム カレンダーの作成方法を学びます。作業日の定義、作業時間の設定、MS Project
  カレンダーの効率的な変更をマスターしましょう。
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Aspose.Tasks を使用した Java カスタム カレンダーの作成方法
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Aspose.Tasks を使用した Java カスタム カレンダーの作成方法
url: /ja/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# カレンダー

## はじめに

Java 開発者で **カスタム カレンダー Java を作成** したい方は、まさに適切な場所に来ました。このハブでは、Aspose.Tasks for Java のすべてのチュートリアルを集めており、**MS Project の作業日を定義**、**MS Project の作業時間を設定**、そしてプログラムでカレンダー設定を調整する方法を示しています。新しいスケジューリング エンジンを構築する場合でも、既存の計画を拡張する場合でも、これらの API をマスターすれば、作業日パターン、祝日、カスタムシフトを UI を開くことなく正確に制御できます。

## クイック回答
- **平日の定義の主な目的は何ですか？**  
  MS Project に対し、どの日が作業日であり、その作業時間が何であるかを指示するためです。  
- **Java で平日定義を処理するライブラリはどれですか？**  
  Aspose.Tasks for Java がカレンダー操作のためのフルエント API を提供します。  
- **ライセンスは必要ですか？**  
  無料の評価ライセンスでテストは可能ですが、商用環境では商用ライセンスが必要です。  
- **チームごとに複数のカレンダーを定義できますか？**  
  はい – 各プロジェクトは複数のカレンダーを保持でき、各カレンダーは独自の平日設定を持ちます。  
- **開始用のサンプルプロジェクトはありますか？**  
  下記の「Define Weekdays in Calendar」チュートリアルに、すぐに実行できるサンプルが含まれています。

## カスタム カレンダー Java の作成方法は？

プロジェクトを読み込み、カレンダーを作成または取得し、平日定義を追加してファイルを保存します—すべて数回の API 呼び出しで完了します。この方法により手動 UI 手順が不要になり、数十のプロジェクトにわたってカレンダー作成を自動化でき、組織全体で一貫した作業日パターンが保証されます。

## Project クラスとは？

`Project` クラスは、MS Project ファイルの読み込み、編集、保存の中心オブジェクトです。タスク、リソース、カレンダーのコレクションを保持し、プロジェクトのあらゆる側面をプログラムで読み書きできるメソッドを公開します。このクラスを使用すると、プロジェクトのカレンダーコレクションにアクセスし、作業時間を調整し、変更を MPP または XML ファイルに永続化できます。

## MS Project カレンダーで平日を定義する方法は？

`Project` クラスは MS Project ファイルを表し、そのデータ構造へのアクセスを提供します。`Calendar` オブジェクトは作業時間定義と例外を格納します。`new Project("myproject.mpp")` でプロジェクトを読み込み、`Calendar` オブジェクトを取得（または作成）し、次のように呼び出します。`calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`。この 1 行で月曜日の 8 時間シフトが作成されます。他の日についても同様に繰り返し、最後に `project.save("updated.mpp")` でプロジェクトを保存します。この簡潔なパターンにより、数回の API 呼び出しで平日の追加、変更、削除が可能になり、手動 UI 操作が不要です。

## WeekDay オブジェクトとは？

`WeekDay` オブジェクトはカレンダー内の単一の曜日エントリを表します。作業日かどうか、当日の作業時間間隔、デフォルト動作のフラグを保持します。`WorkingTime` 間隔を 1 つまたは複数添付してシフト分割をモデル化したり、非作業日に設定したり、親カレンダーからデフォルトを継承したりできます。

## MS Project の作業日を定義する方法は？

`WeekDay` オブジェクトをカレンダーの `WeekDays` コレクションに追加して作業日を定義します。各 `WeekDay` はその日が作業日かどうか、作業時間帯を指定します。たとえば、土曜日を半日とするには、10:00 から 14:00 の単一 `WorkingTime` を持つ `WeekDay` を追加します。API は自動的にプロジェクトのスケジュール計算を更新します。

## MS Project の作業時間を設定する方法は？

各 `WeekDay` に対して 1 つまたは複数の `WorkingTime` 間隔を作成します。`WorkingTime` は開始時、開始分、終了時、終了分の値を取ります。1 日に複数の間隔を割り当ててシフト分割（例：08:00‑12:00 と 13:00‑17:00）をモデル化できます。すべての平日を設定し終えたら `project.save(...)` を呼び出して変更を永続化します。

## 平日を定義するために Aspose.Tasks for Java を使用する理由は？

- **フル API コントロール** – UI の制限がなく、プログラムで平日エントリを作成、変更、削除できます。  
- **クロスプラットフォーム** – デスクトップ アプリからクラウド サービスまで、JVM 対応環境ならどこでも動作します。  
- **精度** – 曜日ごとに異なる作業時間を設定し、祝日の例外を追加し、複数プロジェクト間でカレンダーを同期できます。  
- **パフォーマンス** – 500 件以上のタスクと 100 週以上のカレンダーを UI 全体をロードせずに処理し、標準的な 2.5 GHz サーバーで 2 秒未満の変換時間を実現します（Aspose ベンチマークに基づく定量的主張）。  
- **幅広いフォーマットサポート** – Aspose.Tasks は 30 以上のカレンダー関連 API をサポートし、20 以上のファイル形式へのインポート/エクスポートが可能で、既存のプロジェクト データ パイプラインとシームレスに統合できます。

## 前提条件
- Java 8 以上がインストールされていること。  
- Aspose.Tasks for Java ライブラリ（Aspose のウェブサイトからダウンロードするか、Maven/Gradle で追加）。  
- 有効な Aspose.Tasks ライセンス（評価ライセンスでも学習目的は可）。

## Aspose.Tasks で MS Project カレンダー プロパティを管理する

Java で Aspose.Tasks を使用して MS Project カレンダー プロパティを管理するための完全なポテンシャルを解き放ちます。当チュートリアルでは、カレンダー管理の複雑さを段階的に解説し、カスタマイズと最適化に関する貴重な洞察を提供します。作業時間の調整から特別な日付の定義まで、すべてをマスターできます。

プロジェクトのタイムラインを制御したいですか？[こちらのチュートリアルをご覧ください](./properties/)。

## Aspose.Tasks を使用した MS Project カレンダーの作成

Aspose.Tasks for Java を使用して MS Project カレンダーを作成し、プロジェクト管理をシンプルにします。当チュートリアルはプロセスを簡素化し、プロジェクト固有のニーズに合わせたカレンダー設定をすぐに行えるようにします。効率的なプロジェクト計画と組織化への第一歩を踏み出しましょう。

簡単にカレンダーを作成したいですか？[こちらのチュートリアルをご覧ください](./create/)。

## Aspose.Tasks でカレンダーの平日を定義

Aspose.Tasks for Java を使用して MS Project カレンダーの平日を定義します。このチュートリアルは、作業日と時間帯を調整するプロセスを案内し、プロジェクト管理の成功に必要な柔軟性を提供します。カレンダーを自分のものにしましょう。

平日を簡単に定義したいですか？[こちらから開始してください](./define-weekdays/)。

これらのチュートリアルを進めると、作業時間の抽出、標準カレンダーの作成、作業週の読み取り、カレンダーの MPP 形式への更新など、追加トピックも見つかります。各チュートリアルは実践的な知識を提供し、学んだことを直接 Java プロジェクトに適用できるよう設計されています。

## Aspose.Tasks を使用してカレンダーから作業時間を取得

Aspose.Tasks for Java を使用して MS Project カレンダーから作業時間を抽出し、プロジェクト管理タスクを簡素化します。このチュートリアルで、プロジェクトのタイムラインを効率的に最適化するスキルを身につけましょう。

作業時間を簡単に抽出したいですか？[こちらのチュートリアルをご覧ください](./working-hours/)。

## Aspose.Tasks で標準カレンダーを作成

Aspose.Tasks for Java を使用して Java で標準的な MS Project カレンダーを作成する方法を学びます。このステップバイステップのチュートリアルにより、プロジェクトのタイムラインに標準化されたアプローチを実装できます。

標準カレンダーを作成したいですか？[こちらのチュートリアルをご覧ください](./make-standard/)。

## Aspose.Tasks を使用して MS Project カレンダーから作業週を読み取る

Aspose.Tasks for Java を使用して MS Project カレンダーから作業週を読み取る方法を包括的に学びます。このチュートリアルは詳細な手順を提供し、プロジェクト スケジュールの効果的な管理を可能にします。

作業週を簡単に読み取りたいですか？[こちらから開始してください](./read-work-weeks/)。

## Aspose.Tasks を使用して MS Project カレンダーを MPP 形式に更新

Aspose.Tasks for Java を使用して MS Project カレンダーを MPP 形式にシームレスに更新します。このチュートリアルは、プロジェクト データを最適な互換性のある形式に保つための簡単なアプローチを提供します。

カレンダーを MPP 形式に更新したいですか？[こちらのチュートリアルをご覧ください](./update-to-mpp/)。

Aspose.Tasks for Java の完全なポテンシャルを解き放ち、プロジェクト管理スキルを向上させましょう。各チュートリアルはすべてのレベルの開発者向けに設計されており、スムーズな学習体験を保証します。今すぐ始めて、Java プロジェクト管理の旅を変革してください！

## カレンダー チュートリアル
### [Aspose.Tasks で MS Project カレンダー プロパティを管理](./properties/)
Java で Aspose.Tasks を使用して MS Project カレンダー プロパティを管理する方法を学びます。Java アプリケーション内でのカレンダー操作に関するステップバイステップのガイダンスを提供します。
### [Aspose.Tasks を使用した MS Project カレンダーの作成](./create/)
Aspose.Tasks for Java を使用して MS Project カレンダーを作成する方法を学びます。プロジェクト管理を簡素化します。
### [Aspose.Tasks でカレンダーの平日を定義](./define-weekdays/)
Aspose.Tasks for Java を使用して MS Project カレンダーの平日を定義する方法を学びます。作業日と時間帯を簡単にカスタマイズできます。
### [Aspose.Tasks を使用してカレンダーから作業時間を取得](./working-hours/)
Aspose.Tasks for Java を使用して MS Project カレンダーから作業時間を簡単に抽出します。プロジェクト管理タスクを簡素化します。
### [Aspose.Tasks で標準カレンダーを作成](./make-standard/)
Aspose.Tasks for Java を使用して Java で標準的な MS Project カレンダーを作成する方法を学びます。このステップバイステップのチュートリアルでプロジェクト管理能力を向上させましょう。
### [Aspose.Tasks を使用して MS Project カレンダーから作業週を読み取る](./read-work-weeks/)
Aspose.Tasks for Java を使用して MS Project カレンダーから作業週を読む方法を学びます。この包括的なチュートリアルでステップバイステップの指示を取得できます。
### [Aspose.Tasks を使用して MS Project カレンダーを MPP 形式に更新](./update-to-mpp/)
Aspose.Tasks for Java を使用して MS Project カレンダーを MPP 形式に簡単に更新する方法を学びます。

## よくある質問

**Q: 曜日ごとに異なる作業時間を設定できますか？**  
A: はい。Aspose.Tasks を使用すると、月曜日から日曜日まで個別に開始時刻と終了時刻を設定できます。

**Q: 祝日や非作業日をどのように扱いますか？**  
A: 平日を定義した後、例外（日付）を追加して祝日やカスタムの非作業期間をマークできます。

**Q: あるカレンダーから別のカレンダーへ平日定義をコピーできますか？**  
A: もちろんです。既存のカレンダーから `WeekDay` オブジェクトを取得し、別のカレンダーインスタンスに追加できます。

**Q: 平日を更新した後にプロジェクトを再読み込みする必要がありますか？**  
A: いいえ。変更はメモリ上の `Project` オブジェクトに直接適用されます。作業が完了したらプロジェクトを保存するだけです。

**Q: 平日操作に必要な Aspose.Tasks のバージョンは？**  
A: 20.10 以降のすべての最新バージョンが完全な平日 API をサポートしています。最高のパフォーマンスを得るために、最新の安定版リリースの使用を推奨します。

**最終更新日:** 2026-11-19  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks for Java でプロジェクトにカレンダーを追加](/tasks/java/calendars/create/)
- [Aspose.Tasks で作業日と作業時間を決定](/tasks/java/calendars/working-hours/)
- [Aspose.Tasks for Java でカスタム カレンダー例外を作成](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}