---
date: 2025-12-20
description: Java を使用して Aspose.Tasks を使い、Microsoft Project ファイルからプロジェクト カレンダーの詳細を抽出する方法を学びましょう。コード例付きのステップバイステップ
  ガイド。
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

## はじめに
このチュートリアルでは、**Aspose.Tasks を使用して** Microsoft Project ファイルからプログラムでカレンダー情報を取得する方法を学びます。稼働日、稼働時間、例外といったカレンダー データへのアクセスは、**プロジェクト カレンダー** の詳細をレポート作成、統合、またはカスタム スケジューリング ロジックのために抽出する際に不可欠です。手順を順を追って見ていきましょう。

## クイック回答
- **このチュートリアルで使用しているライブラリは？** Aspose.Tasks for Java。  
- **対象となる主なキーワードは？** *how to use aspose.tasks*。  
- **何が抽出できる？** 稼働日と時間を含むプロジェクト カレンダー。  
- **ライセンスは必要？** 無料トライアルが利用可能です。製品版ではライセンスが必要です。  
- **サポートされている Java バージョンは？** Java 8 以上。

## なぜプロジェクト カレンダー情報を抽出するのか？
プロジェクト カレンダーはタスクの日付、リソース割り当て、全体のタイムライン計算を左右します。このデータを抽出することで、以下が可能になります。
- 実際の稼働スケジュールを反映したカスタム レポートの作成。  
- Microsoft Project のタイムラインを外部システム（ERP、BI など）と同期。  
- カレンダー設定をプログラムで変更し、シナリオ分析（what‑if）を実施。

## 前提条件
開始する前に、以下を確認してください。

- Java プログラミングの基本知識。  
- システムに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Tasks for Java ライブラリ。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から。

## パッケージのインポート
まず、必要な Aspose.Tasks クラスを Java プロジェクトにインポートします。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## 手順 1: データ ディレクトリの設定
*.mpp* ファイルが格納されているフォルダーを定義します。

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` を **project.mpp** が存在するフォルダーへの絶対パスに置き換えてください。

## 手順 2: 時間単位の定義
内部の時間表現を人が読める時間（時間）に変換するための定数を作成します。

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

これらの値はマイクロ秒単位で表され、Aspose.Tasks が内部で時間を保持する方法です。

## 手順 3: Project インスタンスの作成
Microsoft Project ファイルを `Project` オブジェクトにロードします。

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` コンストラクタは *.mpp* ファイルを解析し、カレンダーを含むすべてのプロジェクト データを API 経由で利用可能にします。

## 手順 4: カレンダー情報の取得
プロジェクトに定義されているカレンダーのコレクションを取得します。

```java
CalendarCollection alCals = project.getCalendars();
```

プロジェクトは標準カレンダー、リソース カレンダー、カスタム カレンダーなど複数のカレンダーを保持できます。このコレクションで各カレンダーにアクセスできます。

## 手順 5: カレンダーの反復処理
すべてのカレンダーをループし、UID、名前、稼働日と対応する時間を表示します。

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

内部ループでは各 `WeekDay` オブジェクトをチェックし、稼働日としてマークされている場合は曜日名（Monday、Tuesday …）と計算された稼働時間を出力します。

## 手順 6: 完了メッセージの表示
抽出処理が完了したことを示すメッセージを出力します。

```java
System.out.println("Process completed Successfully");
```

## 結論
これらの手順に従うことで、**Java を使用して Aspose.Tasks で MS Project ファイルからプロジェクト カレンダー情報を抽出する方法**が理解できました。このロジックを大規模アプリケーションに組み込んだり、レポートを自動化したり、他のエンタープライズ システムとスケジュールを同期したりできます。

## よくある質問

**Q: Aspose.Tasks は他のプログラミング言語でも使用できますか？**  
A: はい、Aspose.Tasks は .NET、C++、Python、Java など複数のプラットフォームとプログラミング言語をサポートしています。

**Q: Aspose.Tasks の無料トライアルはありますか？**  
A: はい、[here](https://releases.aspose.com/) から無料トライアル版をダウンロードできます。

**Q: Aspose.Tasks のサポートはどこで受けられますか？**  
A: Aspose.Tasks コミュニティ フォーラムは [here](https://forum.aspose.com/c/tasks/15) で利用できます。

**Q: Aspose.Tasks の一時ライセンスを購入できますか？**  
A: はい、一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から購入可能です。

**Q: Aspose.Tasks の詳細なドキュメントはどこにありますか？**  
A: ドキュメントは [here](https://reference.aspose.com/tasks/java/) を参照してください。

---

**最終更新日:** 2025-12-20  
**テスト環境:** Aspose.Tasks for Java 24.12（執筆時点での最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}