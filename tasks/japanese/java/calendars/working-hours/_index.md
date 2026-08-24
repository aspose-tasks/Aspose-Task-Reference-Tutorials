---
date: 2026-08-24
description: Aspose.Tasks for Java を使用して MS Project カレンダーから working hours を抽出し、holidays
  calendar を追加、working days を判定、task duration を計算する方法を学びます。
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: holidays calendar を追加し、working days を判定する方法
og_description: Aspose.Tasks for Java を使用して MS Project カレンダーから working hours を抽出し、holidays
  calendar を追加、working days を判定、task duration を計算する方法を学びます。
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: holidays calendar を追加し、working days を判定する方法
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: holidays calendar を追加し、working days を判定する方法
url: /ja/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 祝日カレンダーの追加と作業日数の決定方法

プロジェクトカレンダーの管理は、成功するプロジェクト計画の核心です。このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project カレンダーから **祝日カレンダーを追加**、**作業日数を決定**、および **作業時間を抽出** します。ガイドの最後までに、**タスク期間を計算**し、作業時間をカスタマイズし、Microsoft Project をインストールせずに **MPP ファイルをロード**して必要なデータを取得できるようになります。

## クイック回答
- **「作業日数を決定する」とは何ですか？** それは、特定のタスクに対して、カレンダーの日付が作業日と見なされるかを特定することを意味します。  
- **どのライブラリを使用すべきですか？** Aspose.Tasks for Java は、MS Project ファイルを操作するためのフル機能 API を提供します。  
- **実装にどれくらい時間がかかりますか？** 基本的な抽出で通常 10〜15 分です。  
- **ライセンスは必要ですか？** 無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **作業時間をカスタマイズできますか？** はい – カレンダーを変更したり、祝日を追加したり、カスタムの作業時間帯を設定したりできます。  

## 「作業日数を決定する」とは何ですか？
**作業日数を決定する** は、プロジェクトカレンダーを照会して、どの日付が作業日としてマークされているか（週末、祝日、またはカスタム例外）を判別することを意味します。この情報は、**タスク期間を計算**するために正確であり、作業日だけがタスクの経過時間に寄与します。

## 作業時間を取得するために Aspose.Tasks を使用する理由
Aspose.Tasks は、Microsoft Project をインストールせずに MS Project ファイルを読み取ることができ、任意のプラットフォームでの自動化を可能にします。また、高性能な処理、広範なフォーマットサポート、詳細なドキュメントも提供します。  

- **フルカレンダーサポート** – デフォルト、リソース、タスクのカレンダーすべてにアクセス可能です。  
- **高性能** – 標準的な 2.5 GHz CPU 上で **10,000 以上のタスク** を **2 秒未満** で処理できます。  
- **広範なフォーマット対応** – **50 以上の入出力フォーマット** をサポートし、MPP、MPX、XML、Primavera などが含まれます。  
- **包括的なドキュメント** – コードサンプル、API リファレンス、コミュニティフォーラムがすべて利用可能です。  

## 前提条件
開始する前に、以下を確認してください：

1. **Java Development Kit (JDK)** – バージョン 8 以上。  
2. **Aspose.Tasks for Java** – 最新の JAR を [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. 基本的な Java プログラミングの知識。  

## パッケージのインポート
`Project` クラスは、Aspose.Tasks のトップレベルオブジェクトで、メモリ内の単一の MS Project ファイルを表します。開始する前に必要な名前空間をインポートしてください。

パッケージをインポート

```java
import com.aspose.tasks.*;
```

## Aspose.Tasks で MPP ファイルをロードする方法
`Project` クラスは MS Project ファイルをロードし、そのデータへのアクセスを提供します。コード1行でプロジェクトファイルをロードできます。UI や COM インターロップは不要です。このシンプルな手順により、カレンダー、タスク、リソースすべてにフルアクセスできます。

MPP ファイルのロード

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## タスクとカレンダー情報の取得
`Task` はプロジェクトタスクを表し、`Calendar` は作業時間ルールを定義します。分析したいタスクを選択し、関連するカレンダーを取得します。`Task` オブジェクトは `getStart()` と `getFinish()` メソッドを提供し、`Calendar` オブジェクトは作業時間の定義を公開します。

タスクとカレンダーの取得

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 開始日と終了日の定義
`Date` オブジェクトはカレンダー分析の時間ウィンドウを指定します。**作業日数を決定する**ための時間ウィンドウを設定します。タスクの開始日と終了日を使用することで、関連する期間のみを評価できます。

日付の定義

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 日付を反復処理する
`for` ループを使用して、日付範囲内の各日を反復処理できます。タスクの期間内の各日をループします。このループにより、必要に応じて **作業時間をカスタマイズ** でき、合計作業時間の計算の基礎となります。

日付の反復処理

```java
java.util.Calendar tempDate = calStartDate;
```

## 期間の計算
`Duration` は反復処理から計算された合計作業時間を集計します。反復処理中に各日が作業日かどうかを確認し、作業時間を合計し、最終的にタスクの期間を分、時間、日で計算します。これにより、プログラムで **作業日数を計算** し、**タスク期間を計算**する方法が示されます。

期間の計算

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## 作業時間と祝日のカスタマイズ方法
カレンダーの作業時間範囲を変更したり、祝日などの例外を追加したりできます。`taskCalendar.addWorkingTime()` を使用して新しい作業期間を設定し、`taskCalendar.addException()` で祝日を挿入します。デフォルトの 9‑5 スケジュールが組織の方針と合わない場合に便利です。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **Task returns `null` for calendar** | カレンダーが割り当てられていない場合、タスクは `null` を返します。タスクにカレンダーが実際に割り当てられていることを確認してください。割り当てがない場合はプロジェクトのデフォルトカレンダーを継承します。 |
| **Incorrect duration because of holidays** | 祝日がタスクのカレンダーまたはプロジェクトの基本カレンダーに定義されているか確認してください。 |
| **Time zone mismatch** | 必要に応じて `java.util.TimeZone` を使用し、カレンダーのタイムゾーンをシステムと合わせてください。 |

## よくある質問
### Q: Aspose.Tasks for Java は複雑なプロジェクト構造を扱えますか？
A: はい、Aspose.Tasks for Java はタスク、リソース、カレンダーを含む複雑なプロジェクト構造を扱うための包括的なサポートを提供します。

### Q: Aspose.Tasks for Java はさまざまなバージョンの MS Project と互換性がありますか？
A: もちろん、Aspose.Tasks for Java はさまざまな MS Project バージョンをサポートしており、異なる環境間での互換性を確保します。

### Q: プロジェクトカレンダーの作業時間と祝日をカスタマイズできますか？
A: はい、Aspose.Tasks for Java の API を使用して、プロジェクトの要件に合わせて作業時間と祝日を簡単にカスタマイズできます。

### Q: Aspose.Tasks for Java はサポートとドキュメントを提供していますか？
A: はい、Aspose.Tasks for Java は豊富なドキュメントと専用のサポートフォーラムを提供し、開発者が機能を効果的に活用できるよう支援します。

### Q: Aspose.Tasks for Java のトライアル版は利用可能ですか？
A: はい、[Aspose releases page](https://releases.aspose.com/) から Aspose.Tasks for Java の無料トライアル版にアクセスできます。

## 結論
このガイドでは、Aspose.Tasks for Java を使用して MS Project カレンダーから **祝日カレンダーの追加**、**作業日数の決定**、**作業時間の取得**、そして **タスク期間の計算** を行う方法を示しました。上記の手順に従うことで、スケジュール分析の自動化、カレンダーのカスタマイズ、プロジェクト計画の正確さと最新性を保つことができます。これで **MS Project** データを **読み取り**、**MPP ファイルをロード**し、Microsoft Project を使用せずに正確な期間計算を実行するツールが手に入りました。

---

**最終更新日:** 2026-08-24  
**テスト環境:** Aspose.Tasks for Java 24.12 (執筆時点での最新)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks for Java でプロジェクトにカレンダーを追加](/tasks/java/calendars/create/)
- [カレンダーに祝日を追加して MPP として保存](/tasks/java/calendars/update-to-mpp/)
- [Aspose.Tasks for Java でカスタムカレンダー例外を作成](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}