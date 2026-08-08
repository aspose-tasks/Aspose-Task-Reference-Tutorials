---
date: 2026-08-08
description: Aspose.Tasks for Java を使用して MS Project カレンダーで平日を定義する方法を学びます。このガイドでは、MS
  Project カレンダーの変更方法、カスタムカレンダー Java の作成方法、そして作業日を効率的にスケジュールする方法を示します。
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: カレンダー
og_description: Aspose.Tasks for Java を使用して MS Project カレンダーで平日を定義する方法を学びます。このガイドでは、MS
  Project カレンダーの変更方法、カスタムカレンダー Java の作成方法、そして作業日を効率的にスケジュールする方法を示します。
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: MS Project カレンダーで平日を定義する方法 – Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: MS Project カレンダーで平日を定義する方法 – Aspose.Tasks Java
url: /ja/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# カレンダー

## はじめに

Java 開発者で、プロジェクトスケジュールに **平日を定義する** ことを探しているなら、ここが適切な場所です。このハブでは、Aspose.Tasks for Java のすべてのチュートリアルを集めており、MS Project カレンダー内で **平日の定義方法** を示し、作業時間を調整し、タイムラインをクリアに保つ方法を解説しています。新しいスケジューリングエンジンを構築する場合でも、既存の計画を微調整する場合でも、平日の定義をマスターすれば、作業日パターン、休日、カスタムシフトを正確にコントロールできます。このガイドでは、**MS Project カレンダーを変更する方法** もプログラムで説明しているので、数十のプロジェクトにわたってカレンダー作成を自動化できます。

## クイック回答
- **平日を定義する主な目的は何ですか？**  
  MS Project に対し、どの日が作業日であり、作業時間が何であるかを伝えるためです。
- **Java で平日定義を扱うライブラリはどれですか？**  
  Aspose.Tasks for Java はカレンダー操作のためのフルエント API を提供します。
- **ライセンスは必要ですか？**  
  無料の評価ライセンスはテストに使用できますが、本番環境では商用ライセンスが必要です。
- **異なるチーム用に複数のカレンダーを定義できますか？**  
  はい。各プロジェクトは複数のカレンダーを保持でき、各カレンダーは独自の平日設定を持ちます。
- **開始用のサンプルプロジェクトはありますか？**  
  以下の「Define Weekdays in Calendar」チュートリアルには、すぐに実行できるサンプルが含まれています。

## MS Project カレンダーで平日を定義する方法は？

`Project` クラスは MS Project ファイルを表し、そのデータ構造へのアクセスを提供します。`Calendar` オブジェクトはプロジェクトの作業時間定義と例外を格納します。`new Project("myproject.mpp")` でプロジェクトをロードし、`Calendar` オブジェクトを取得（または作成）し、次に `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))` を呼び出します。この1行で月曜日の作業日エントリが 8 時間シフトとして作成されます。他の日についても同様に繰り返し、最後に `project.save("updated.mpp")` でプロジェクトを保存します。この簡潔なパターンにより、数回の API 呼び出しだけで平日の定義、変更、削除が可能となり、手動の UI 操作が不要になります。

## WeekDay オブジェクトとは何ですか？

`WeekDay` オブジェクトは Aspose.Tasks カレンダー内の週の特定の日のエントリを表し、作業ステータスと作業時間間隔を保持します。開始/終了時刻を設定したり、非作業日にしたり、残業期間を付加したりできます。複数の `WorkingTime` 間隔を保持してシフト分割をモデル化でき、デフォルト作業日のフラグもサポートします。`WeekDay` API を使用して日を有効化または無効化し、通常の時間を割り当て、または高度なスケジューリングシナリオ向けに残業ルールを指定できます。

## 平日を定義するために Aspose.Tasks for Java を使用する理由は？

- **フル API コントロール** – UI の制限がなく、プログラムで平日エントリを作成、変更、削除できます。  
- **クロスプラットフォーム** – デスクトップアプリからクラウドサービスまで、JVM 互換環境で動作します。  
- **精度** – 各平日に異なる作業時間を設定し、休日の例外を追加し、複数プロジェクト間でカレンダーを同期できます。  
- **パフォーマンス** – UI 全体をロードせずに、500 件以上のタスクと 100 週以上のカレンダーを含むプロジェクトを処理し、標準的な 2.5 GHz サーバーで変換時間を 2 秒未満に達成します（Aspose ベンチマークに基づく定量的主張）。

## 前提条件
- Java 8 以上がインストールされていること。  
- Aspose.Tasks for Java ライブラリ（Aspose のウェブサイトからダウンロードするか、Maven/Gradle で追加）。  
- 有効な Aspose.Tasks ライセンス（評価ライセンスは学習に使用可能）。

## Aspose.Tasks で MS Project カレンダー プロパティを管理する

Java で Aspose.Tasks を使用して MS Project カレンダーのプロパティ管理の可能性を最大限に引き出しましょう。当チュートリアルではカレンダー管理の詳細を順を追って解説し、カスタマイズと最適化に関する貴重な洞察を提供します。作業時間の調整から特別な日付の定義まで、すべてをマスターできます。  
プロジェクトのタイムラインを制御する準備はできましたか？ [ここでチュートリアルを確認してください](./properties/).

## Aspose.Tasks を使用して MS Project カレンダーを作成する

Java 用 Aspose.Tasks で MS Project カレンダーを作成し、プロジェクト管理を手間なく効率化しましょう。当チュートリアルはプロセスを簡素化し、プロジェクト固有のニーズに合わせたカレンダーを設定できるようにします。効率的なプロジェクト計画と組織への第一歩を踏み出しましょう。  
簡単にカレンダーを作成する準備はできましたか？ [チュートリアルをご覧ください](./create/).

## Aspose.Tasks でカレンダーの平日を定義する

Aspose.Tasks for Java を使用して MS Project カレンダーの平日を定義し、カスタマイズしましょう。このチュートリアルは作業日と時間帯の調整プロセスを案内し、プロジェクト管理に必要な柔軟性を提供します。カレンダーをあなたのために活用してください。  
平日を簡単に定義する準備はできましたか？ [ここから始めましょう](./define-weekdays/).

これらのチュートリアルを進めると、作業時間の抽出、標準カレンダーの作成、作業週の読み取り、カレンダーの MPP 形式への更新などの追加トピックが見つかります。各チュートリアルは実践的な知識を提供するよう設計されており、学んだことを直接 Java プロジェクトに適用できるようにします。

## Aspose.Tasks を使用してカレンダーから作業時間を取得する

Aspose.Tasks for Java を使用して MS Project カレンダーから作業時間を抽出し、プロジェクト管理タスクを簡素化しましょう。このチュートリアルは、プロジェクトのタイムラインを効率的に最適化するためのスキルを提供します。  
作業時間を簡単に抽出する準備はできましたか？ [チュートリアルをご覧ください](./working-hours/).

## Aspose.Tasks で標準カレンダーを作成する

Aspose.Tasks を使用して Java で標準的な MS Project カレンダーを作成する方法を学び、プロジェクト管理能力を向上させましょう。このステップバイステップのチュートリアルにより、プロジェクトのタイムラインに標準化されたアプローチを実装できます。  
標準カレンダーを作成する準備はできましたか？ [チュートリアルをご覧ください](./make-standard/).

## Aspose.Tasks で MS Project カレンダーから作業週を読み取る

Aspose.Tasks for Java を使用して MS Project カレンダーから作業週を読み取るための包括的な知見を得ましょう。このチュートリアルは詳細な手順を提供し、プロジェクトスケジュールを効果的に管理できるようにします。  
作業週を簡単に読み取る準備はできましたか？ [ここから始めましょう](./read-work-weeks/).

## Aspose.Tasks で MS Project カレンダーを MPP 形式に更新する

Aspose.Tasks for Java を使用して MS Project カレンダーを MPP 形式に簡単に更新しましょう。このチュートリアルは、プロジェクトデータを最適な互換性のために適切な形式に保つシームレスな方法を提供します。  
カレンダーを MPP 形式に更新する準備はできましたか？ [チュートリアルをご覧ください](./update-to-mpp/).

Aspose.Tasks for Java の可能性を最大限に引き出し、プロジェクト管理スキルを向上させましょう。各チュートリアルはすべてのレベルの開発者向けに設計され、スムーズな学習体験を保証します。さあ、今すぐ取り組んで Java プロジェクト管理の旅を変革しましょう！

## カレンダー チュートリアル
### [Aspose.Tasks で MS Project カレンダー プロパティを管理する](./properties/)
Java で Aspose.Tasks を使用して MS Project カレンダーのプロパティを管理する方法を学びます。Java アプリケーション内のカレンダーに関するステップバイステップのガイダンスを提供します。
### [Aspose.Tasks を使用して MS Project カレンダーを作成する](./create/)
Aspose.Tasks for Java を使用して MS Project カレンダーを作成する方法を学びます。簡単にプロジェクト管理を効率化できます。
### [Aspose.Tasks でカレンダーの平日を定義する](./define-weekdays/)
Aspose.Tasks for Java を使用して MS Project カレンダーの平日を定義する方法を学びます。作業日と時間帯を簡単にカスタマイズできます。
### [Aspose.Tasks を使用してカレンダーから作業時間を取得する](./working-hours/)
Aspose.Tasks for Java を使用して MS Project カレンダーから作業時間を簡単に抽出します。プロジェクト管理タスクを簡素化します。
### [Aspose.Tasks で標準カレンダーを作成する](./make-standard/)
Aspose.Tasks を使用して Java で標準的な MS Project カレンダーを作成する方法を学びます。このステップバイステップのチュートリアルでプロジェクト管理能力を向上させましょう。
### [Aspose.Tasks で MS Project カレンダーから作業週を読み取る](./read-work-weeks/)
Aspose.Tasks for Java を使用して MS Project カレンダーから作業週を読み取る方法を学びます。この包括的なチュートリアルでステップバイステップの手順を取得できます。
### [Aspose.Tasks で MS Project カレンダーを MPP 形式に更新する](./update-to-mpp/)
Aspose.Tasks for Java を使用して MS Project カレンダーを MPP 形式に簡単に更新する方法を学びます。

## よくある質問

**Q: 各平日に異なる作業時間を設定できますか？**  
A: はい。Aspose.Tasks を使用すると、月曜日から日曜日までそれぞれ開始時刻と終了時刻を個別に設定できます。

**Q: 休日や非作業日をどのように扱いますか？**  
A: 平日を定義した後、例外（日付）を追加して休日やカスタムの非作業期間をマークできます。

**Q: あるカレンダーから別のカレンダーへ平日定義をコピーすることは可能ですか？**  
A: もちろん可能です。既存のカレンダーから `WeekDay` オブジェクトを取得し、別のカレンダーインスタンスに追加できます。

**Q: 平日を更新した後にプロジェクトを再読み込みする必要がありますか？**  
A: いいえ。変更はメモリ上の `Project` オブジェクトに直接適用されるので、完了したらプロジェクトを保存するだけです。

**Q: 平日操作に必要な Aspose.Tasks のバージョンはどれですか？**  
A: すべての最新バージョン（20.10 以降）は完全な平日 API をサポートしています。最高のパフォーマンスを得るために、最新の安定版リリースの使用を推奨します。

---

**最終更新日:** 2026-08-08  
**テスト済み:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks でプロジェクトにカレンダーを追加する](/tasks/java/calendars/create/)
- [Aspose.Tasks で作業日と作業時間を決定する](/tasks/java/calendars/working-hours/)
- [Aspose.Tasks for Java でカスタムカレンダー例外を作成する](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}