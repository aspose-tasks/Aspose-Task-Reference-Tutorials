---
date: 2025-12-05
description: Aspose.Tasks for Java を使用して、MS Project カレンダーから作業時間を抽出し、作業日数を決定し、タスク期間を計算する方法を学びましょう。
language: ja
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksで作業日と作業時間を決定する
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用した作業日と作業時間の決定

## はじめに
プロジェクトカレンダーの管理は、成功するプロジェクト計画の重要な要素です。このチュートリアルでは、Aspose.Tasks for Java を使用して任意のタスクの **作業日を決定**し、MS Project カレンダーから **作業時間を抽出**します。ガイドの最後までに、**タスク期間を計算**し、作業時間をカスタマイズし、必要なデータを取得するために **MPP ファイルを確実に読み込む**ことができるようになります。

## クイック回答
- **“作業日を決定” とは何ですか？** それは、特定のタスクに対して作業日とみなされるカレンダーの日付を特定することを意味します。  
- **どのライブラリを使用すべきですか？** Aspose.Tasks for Java は、MS Project ファイルを操作するためのフル機能 API を提供します。  
- **実装にはどれくらい時間がかかりますか？** 基本的な抽出で通常 10〜15 分です。  
- **ライセンスは必要ですか？** 無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **作業時間をカスタマイズできますか？** はい – カレンダーを変更したり、祝日を追加したり、カスタムの作業時間範囲を設定したりできます。  

## “作業日を決定” とは何ですか？
タスクがスケジュールされると、プロジェクトカレンダーは作業日と非作業日（週末、祝日）を定義します。作業日を決定することは、そのカレンダーを照会して作業が可能な正確な日時を把握することであり、正確な **タスク期間の計算** に不可欠です。

## 作業時間を取得するために Aspose.Tasks を使用する理由は？
- **Microsoft Project は不要** – 任意のプラットフォームで .MPP ファイルを操作できます。  
- **フルカレンダーサポート** – デフォルト、リソース、タスクのカレンダーを含みます。  
- **高性能** – 大規模プロジェクトを迅速に処理します。  
- **豊富なドキュメント** – サンプルと API リファレンスがすぐに利用可能です。  

## 前提条件
開始する前に、以下が揃っていることを確認してください：

1. **Java Development Kit (JDK)** – バージョン 8 以上。  
2. **Aspose.Tasks for Java** – 最新の JAR を [here](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. 基本的な Java プログラミングの知識。  

## パッケージのインポート
まず、コアの Aspose.Tasks 名前空間をインポートします：

```java
import com.aspose.tasks.*;
```

## 手順 1: MPP ファイルの読み込み
プロジェクトファイル（**load mpp file** 手順）を読み込み、カレンダーを操作できるようにします：

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

##順 2: タスクとカレンダー情報の取得
分析したいタスクを選択し、関連付けられたカレンダーを取得します。ここでタスクの **作業時間を取得** します：

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 手順 3: 開始日と終了日の定義
**作業日を決定**したい期間の時間ウィンドウを設定します：

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 手順 4: 日付を反復処理
タスクの期間内の各日付をループします。このループは、必要に応じて後で **作業時間をカスタマイズ**するのに役立ちます：

```java
java.util.Calendar tempDate = calStartDate;
```

## 手順 5: 期間の計算
反復処理中に各日が作業日かどうかを確認し、作業時間を合計し、最終的にタスクの期間を分、時間、日単位で計算します：

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

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **タスクのカレンダーが `null` を返す** | タスクにカレンダーが割り当てられていることを確認してください。割り当てられていない場合、プロジェクトのデフォルトカレンダーを継承します。 |
| **祝日が原因で期間が正しくない** | 祝日がタスクのカレンダーまたはプロジェクトの基本カレンダーに定義されているか確認してください。 |
| **タイムゾーンの不一致** | 必要に応じて `java.util.TimeZone` を使用し、カレンダーのタイムゾーンをシステムと合わせてください。 |

## よくある質問
### Q: Aspose.Tasks for Java は複雑なプロジェクト構造を処理できますか？
A: はい、Aspose.Tasks for Java はタスク、リソース、カレンダーを含む複雑なプロジェクト構造の処理に包括的に対応しています。

### Q: Aspose.Tasks for Java はさまざまなバージョンの MS Project と互換性がありますか？
A: もちろんです。Aspose.Tasks for Java はさまざまなバージョンの MS Project をサポートしており、異なる環境間での互換性を確保します。

### Q: プロジェクトカレンダーの作業時間や祝日をカスタマイズできますか？
A: はい、Aspose.Tasks for Java の API を使用して、プロジェクトの要件に合わせて作業時間や祝日を簡単にカスタマイズできます。

### Q: Aspose.Tasks for Java はサポートとドキュメントを提供していますか？
A: はい、Aspose.Tasks for Java は豊富なドュメントと専用のサポートフォー開発者が機能を効果的に活用できるよう支援します。

### Q: Aspose.Tasks for Java のトライアル版は利用可能ですか？
A: はい、[here](https://releases.aspose.com/) から Aspose.Tasks for Java の無料トライアル版にアクセスできます。

## 結論
このガイドでは、Aspose.Tasks for Java を使用して MS Project カレンダーから **作業日を決定**、**作業時間を取得**、そして **タスク期間を計算**する方法を示しました。上記の手順に従うことで、スケジュール分析を自動化し、カレンダーをカスタマイズし、プロジェクト計画を正確かつ最新の状態に保つことができます。

---

**最終更新日:** 2025-12-05  
**テスト環境:** Aspose.Tasks for Java 24.12 (執筆時点での最新)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}