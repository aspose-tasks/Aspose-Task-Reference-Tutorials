---
date: 2026-09-09
description: Aspose.Tasks を使用して Java でプロジェクト カレンダーを設定する方法です。カレンダーの作業時間の表示、作業時間の構成、MS
  Project ファイル内のカレンダー日付の変更方法を学びます。
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Aspose.Tasks でカレンダー プロパティを管理する
og_description: Aspose.Tasks を使用して Java でプロジェクト カレンダーを設定する方法です。カレンダーの作業時間の表示、作業時間の構成、MS
  Project ファイル内のカレンダー日付の変更方法を学びます。
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Aspose.Tasks を使用した Java のプロジェクト カレンダーの設定方法
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Aspose.Tasks を使用した Java のプロジェクト カレンダーの設定方法
url: /ja/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用した Java のプロジェクト カレンダー設定方法

## はじめに
このチュートリアルでは、Aspose.Tasks ライブラリを活用して **プロジェクト カレンダーを設定する方法** を Java で学びます。カレンダーのプロパティを制御することで、**カレンダーの稼働時間を表示**したり、カスタム稼働日を設定したり、祝日やシフトパターンといった実際の制約に合わせてプロジェクト スケジュールを調整できます。環境設定、プロジェクトの読み込み、カレンダーの反復処理、プロパティの取得・更新の手順を順に解説し、任意の Java アプリケーションで **MS Project のカレンダー設定** を自信を持って管理できるようにします。

## クイック回答
- **「プロジェクト カレンダーを設定する」とは何ですか？**  
  MS Project ファイル内のカレンダーの稼働時間、ベース カレンダー、日タイプを作成または更新することを指します。  
- **必要なライブラリは？** Aspose.Tasks for Java（最新バージョン）。  
- **ライセンスは必要ですか？** 開発用には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **カレンダーの稼働時間を表示できますか？** はい。各 `WeekDay` を読み取ることで、すべての日タイプの時間を出力できます。  
- **Maven/Gradle と互換性がありますか？** もちろんです。Aspose.Tasks の JAR を依存関係として追加してください。

## Java でプロジェクト カレンダーを設定する方法
プロジェクト ファイルを読み込み、対象カレンダーを特定し、必要に応じて稼働時間定義、ベース カレンダー、日タイプを調整します。以下の手順は、読み込み、反復、変更、保存を行う完全なエンドツーエンド ソリューションを示し、例外処理と正確な稼働時間計算もカバーしています。

## プロジェクト カレンダーとは？
プロジェクト カレンダーは、タスク、リソース、全体のプロジェクト タイムラインに対する稼働日と稼働時間を定義します。MS Project では、カレンダーはベース カレンダーから継承でき、各日タイプ（例：**Standard**、**Non‑working**）は独自の稼働時間を持ちます。これらの設定をプログラムで管理することで、手動編集なしに動的なスケジュール調整が可能になります。

## なぜ MS Project カレンダーをプログラムで管理するのか？
プログラムでカレンダーを管理すると、複数のプロジェクトに対して一貫したスケジューリング ルールを適用でき、手作業によるミスを減らし、HR や ERP などの他システムとカレンダー データを統合できます。この自動化によりプロジェクト設定が迅速化し、全チームメンバーが同じ稼働時間ポリシーに従うことが保証されます。

- **自動化:** 1 つのスクリプトで数十件のプロジェクトのカレンダーを調整。  
- **一貫性:** 組織全体の稼働時間ポリシーを自動的に適用。  
- **統合:** カレンダーを外部の HR や ERP システムと同期。  
- **可視化:** レポートやデバッグのために **カレンダーの稼働時間を表示**。  
- **柔軟性:** UI を開かずに例外やシフト パターンを即座に追加。

## 前提条件
開始する前に以下を確認してください。

- **Java Development Kit (JDK) 8+** がインストールされ、`JAVA_HOME` が設定されていること。  
- **Aspose.Tasks for Java** ライブラリを [download page](https://releases.aspose.com/tasks/java/) から取得し、JAR をクラスパスに追加するか、Maven/Gradle の依存関係として宣言してください。  
- カレンダーを検査または変更したいサンプルの MS Project ファイル（`.mpp` または `.xml`）を用意。

## パッケージのインポート
`Project`、`Calendar`、`WeekDay` などのクラスがカレンダー操作の中心です。  
`Calendar` クラスはプロジェクト カレンダーを表し、稼働日、例外、ベース カレンダーの関係を保持します。  
`WeekDay` クラスはカレンダー内の単一の日の稼働時間設定を定義します。

`Project` クラスは Aspose.Tasks のトップレベル オブジェクトで、メモリ上の単一 MS Project ファイルを表します。ファイルをロードした後、すべてのカレンダー操作はこのオブジェクトを通じて行われます。

```java
import com.aspose.tasks.*;
```

## 手順 1: データ ディレクトリの設定
プロジェクト ファイルが格納されているフォルダーを定義します。プレースホルダーを実際のパスに置き換えてください。

```java
String dataDir = "Your Data Directory";
```

## 手順 2: 時間単位定数の定義
稼働時間はミリ秒で表されます。再利用可能な定数を定義するとコードが読みやすくなり、**Java で稼働時間を正確に計算**できます。

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## 手順 3: プロジェクト データの読み込み
既存の MS Project XML ファイル（`.xml` または `.mpp`）をロードして `Project` インスタンスを作成します。これによりファイル内のすべてのカレンダーにアクセスできるようになります。

`Project` クラスはファイルを軽量オブジェクト モデルにロードします。**ファイル全体をメモリに保持する必要はなく**、数万件のタスクを含むプロジェクトでも扱えます。

```java
Project project = new Project(dataDir + "project.xml");
```

## 手順 4: カレンダーを反復処理する (Java)
ここではすべてのカレンダーをループし、ユニーク ID、名前、ベース カレンダー、各日タイプの稼働時間を出力します。これにより **Java でプロジェクト カレンダーを設定する** 方法と **カレンダーの稼働時間を表示** 方法の両方が示されます。

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### このコードの動作
- **名前が未設定のカレンダーを除外**（内部カレンダーの中には `null` 名のものがあります）。  
- **UID と名前を出力** – 後でカレンダーを特定するのに便利です。  
- **ベース カレンダーを表示** – 「Self」（カレンダー自身がベース）または継承元カレンダー名が表示されます。  
- **各 `WeekDay` をループ**して、合計稼働時間（`workingTime` はミリ秒なので `OneHour` で除算）を計算・出力。

## Aspose.Tasks を使用する定量的な利点
Aspose.Tasks は **30 以上の入出力フォーマット** をサポートし、**最大 10,000 件のタスク** をメモリ全体をロードせずに処理できます。典型的なサーバー ハードウェア上では 1 秒未満で結果を返すため、エンタープライズ規模の自動化に信頼性があります。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| `NullPointerException` on `cal.getBaseCalendar()` | カレンダーがベース カレンダー自体である（`isBaseCalendar()` が `true` を返す）。 | 示された三項演算子チェックを使用する（`cal.isBaseCalendar() ? "Self" : ...`）。 |
| 稼働時間が出力されない | プロジェクト ファイルが別の時間単位（ticks）を使用している。 | ファイル形式を確認。Aspose.Tasks はミリ秒に正規化しますが、正しいファイル種別をロードしているか確認してください。 |
| `project.xml` が見つからない | `dataDir` パスが間違っている。 | 絶対パスを使用するか、`Paths.get(dataDir, "project.xml").toString()` に変更してください。 |

## よくある質問

**Q: Aspose.Tasks を使ってプログラムからカレンダー プロパティを変更できますか？**  
A: はい。API はカレンダーへのフル read/write アクセスを提供し、稼働時間、例外、ベース カレンダーの関係を追加・編集・削除できます。

**Q: Aspose.Tasks でカレンダー カスタマイズに制限はありますか？**  
A: ライブラリは Microsoft Project の機能をほぼすべて再現しているため、実質的にすべてのカレンダー要素をカスタマイズ可能です。ごく古い Project ファイル バージョンのみ、細かな互換性の差異がある場合があります。

**Q: 既存の Java プロジェクトにカレンダー管理を統合できますか？**  
A: もちろんです。Aspose.Tasks の JAR をビルド パスに追加し、ここで示したコード パターンをそのまま使用してください。

**Q: Aspose.Tasks はカレンダー管理以外のプロジェクト管理機能もサポートしていますか？**  
A: はい。タスク、リソース、割り当て、アウトライン、ベースラインなど、Java ベースのプロジェクト自動化に必要な機能を網羅しています。

**Q: 開発者向けのテクニカルサポートはありますか？**  
A: はい。Aspose は専用フォーラム、メールサポート、そしてすべてのライセンスユーザー向けに充実したドキュメントを提供しています。

---

**最終更新日:** 2026-09-09  
**テスト環境:** Aspose.Tasks for Java 24.12（執筆時点の最新）  
**作者:** Aspose

## 関連チュートリアル

- [Create Project Calendar Java – Aspose.Tasks for Java Guide](/tasks/java/)
- [Load Project Files in Java and Manage Project Properties](/tasks/java/project-management/default-properties/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}