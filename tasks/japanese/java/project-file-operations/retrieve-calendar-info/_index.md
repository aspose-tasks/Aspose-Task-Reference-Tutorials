---
date: 2026-03-27
description: Java を使用して Aspose と Aspose.Tasks を活用し、Microsoft Project ファイルからプロジェクト
  カレンダーの詳細を抽出する方法を学びます。コード例付きのステップバイステップ ガイド。
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して MS Project のカレンダー情報を取得する方法
url: /ja/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用して MS Project カレンダー情報を取得する方法

## Introduction
このチュートリアルでは、**Aspose.Tasks の使い方**を学び、Microsoft Project ファイルからプログラムでカレンダー情報を取得する方法を紹介します。作業日、作業時間、例外などのカレンダー データへのアクセスは、**プロジェクト カレンダー**の詳細をレポート作成、統合、またはカスタム スケジューリング ロジックのために抽出する際に不可欠です。手順を順に追っていき、*.mpp* ファイルからこのデータを **Aspose の使い方**で取得する方法を正確に確認しましょう。

## Quick Answers
- **What library does this tutorial use?** Aspose.Tasks for Java.  
- **Which primary keyword is covered?** *how to use aspose*.  
- **What can you extract?** Project calendars, including working days and hours.  
- **Do I need a license?** A free trial is available; a license is required for production.  
- **What Java version is supported?** Java 8 or higher.

## What is Aspose.Tasks and Why Use It?
Aspose.Tasks は、Microsoft Project 本体がなくても Microsoft Project ファイルを読み書きし、操作できる強力な Java API です。Aspose.Tasks を使用すると、**カレンダー情報の抽出方法**を実現し、スケジュール計算を自動化し、プロジェクト データを他のエンタープライズ システムと統合できます。すべて純粋な Java コードから実行可能です。

## Why extract project calendar information?
プロジェクト カレンダーはタスクの日付、リソース割り当て、全体のタイムライン計算を左右します。このデータを抽出することで、以下が可能になります。
- 実際の作業スケジュールを反映したカスタム レポートの作成。  
- Microsoft Project のタイムラインを外部システム（ERP、BI など）と同期。  
- カレンダー設定をプログラムで変更し、シナリオ分析（what‑if）を実施。  
- **MS Project カレンダー** データを他の計画ツールへの移行に利用。

## Prerequisites
開始する前に、以下を確認してください。

- Java プログラミングの基本知識。  
- システムに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Tasks for Java ライブラリ。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から。

## Import Packages
まず、必要な Aspose.Tasks クラスを Java プロジェクトにインポートします。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Step 1: Set Data Directory
*.mpp* ファイルが格納されているフォルダーを定義します。

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` を、**project.mpp** が存在するフォルダーへの絶対パスに置き換えてください。

## Step 2: Define Time Units
内部の時間表現を人間が読みやすい時間（時間単位）に変換するための定数を作成します。

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

これらの値はマイクロ秒で表されており、Aspose.Tasks が内部で時間を保持する方式です。

## Step 3: Create Project Instance
Microsoft Project ファイルを `Project` オブジェクトに読み込みます。

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` コンストラクタは *.mpp* ファイルを解析し、カレンダーを含むすべてのプロジェクト データを API 経由で利用可能にします。

## Step 4: Retrieve Calendars Information
プロジェクトに定義されているカレンダーのコレクションを取得します。

```java
CalendarCollection alCals = project.getCalendars();
```

プロジェクトは複数のカレンダー（標準、リソース、カスタム カレンダー）を保持できます。このコレクションを通じて各カレンダーにアクセスできます。

## Step 5: Iterate Through Calendars
すべてのカレンダーをループし、UID、名前、作業日と対応する作業時間を表示します。

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

内部ループでは各 `WeekDay` オブジェクトをチェックし、作業日としてマークされている場合は曜日名（Monday、Tuesday、…）と計算された作業時間を出力します。

## Step 6: Display Completion Message
抽出プロセスが完了したことを通知します。

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **No calendars returned** | The project file may not contain any custom calendars. | Verify that the *.mpp* actually defines calendars or open it in Microsoft Project to confirm. |
| **Incorrect working hours** | Time conversion constants are off for a different Project version. | Adjust `OneSec`, `OneMin`, `OneHour` if you work with a newer Aspose.Tasks version that changes the internal time unit. |
| **`NullPointerException` on `cal.getName()`** | Some calendar objects could be null. | Add a null‑check before accessing properties (already demonstrated). |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks supports multiple platforms and programming languages, including .NET, C++, Python, and Java.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).

**Q: How can I get support for Aspose.Tasks?**  
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Can I purchase a temporary license for Aspose.Tasks?**  
A: Yes, temporary licenses are available for purchase [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find detailed documentation for Aspose.Tasks?**  
A: You can refer to the documentation [here](https://reference.aspose.com/tasks/java/).

## Conclusion
この手順に従うことで、**Aspose.Tasks を使用してプロジェクト カレンダーを抽出する方法**を Java で MS Project ファイルから取得できるようになりました。このロジックを大規模アプリケーションに組み込んだり、レポートを自動化したり、他のエンタープライズ システムとスケジュールを同期したりできます。**how to use aspose** をマスターすれば、プロジェクト管理の高度な自動化シナリオへの扉が開かれます。

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}