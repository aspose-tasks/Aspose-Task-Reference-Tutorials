---
date: 2026-02-05
description: Aspose.Tasks for Java を使用して、カレンダーに祝日を追加し、カレンダーをプロジェクトに割り当て、MS Project
  ファイルを MPP として保存する方法を学びましょう。
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでカレンダーに祝日を追加し、MPPとして保存
url: /ja/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用してカレンダーに祝日を追加し、MPP として保存

## はじめに

現代のプロジェクト管理では、**カレンダーに祝日を追加**するファイルや、**MS Project カレンダー**を作成し、ネイティブな MPP 形式でスケジュールを共有する必要が頻繁にあります。複数のソースからタイムラインを統合したり、レガシーデータを移行したりする場合でも、プログラムでカレンダーを生成すれば手作業のミスがなくなり、納期が短縮されます。このチュートリアルでは、MS Project でカレンダーを作成し、祝日でカスタマイズし、**カレンダーをプロジェクトに割り当て**、最後に Aspose.Tasks Java API を使用して **プロジェクトを MPP に変換**するまでの全工程を解説します。

## クイック回答
- **このチュートリアルでカバーする内容は何ですか？** カレンダーに祝日を追加し、プロジェクトに割り当て、Aspose.Tasks for Java を使用して結果を MPP ファイルとして保存します。  
- **ライセンスは必要ですか？** 開発目的であれば無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **必要な Java バージョンは？** Java 8 以上 (JDK 8+)。  
- **カレンダーはカスタマイズできますか？** はい。作業時間、例外、祝日を追加できます。  
- **実装にどれくらい時間がかかりますか？** 基本的なカレンダーで約 10‑15 分です。  

## 「create calendar MS Project」とは何ですか？

カレンダー MS Project を作成するとは、Microsoft Project ファイル内でタスクのスケジューリングを制御する作業日、作業時間、例外をプログラムで定義することを指します。Aspose.Tasks を使用すれば、**java create project calendar**（Java でプロジェクトカレンダーを作成）し、変更を加えて、Microsoft Project の UI を開くことなく永続化できます。

## なぜこのタスクに Aspose.Tasks を使用するのか？

- **完全な .NET/Java 互換性** – Java をサポートする任意のプラットフォームで動作します。  
- **COM や Office のインストール不要** – サーバー側の自動化や **automate schedule generation**（スケジュール生成の自動化）に最適です。  
- **豊富な API** – カスタム作業週や祝日を含むすべてのカレンダー属性をサポートします。  
- **直接 MPP 出力** – 中間変換なしで **save project as MPP**（プロジェクトを MPP として保存）できます。  

## 前提条件

1. **Java Development Kit (JDK) 8+** – `java -version` が 1.8 以上であることを確認してください。  
2. **Aspose.Tasks for Java** – 最新の JAR を [Aspose のウェブサイト](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **IDE** – IntelliJ IDEA、Eclipse、またはお好みのエディタを使用してください。  
4. **基本的な Java 知識** – クラス、メソッド、ファイル I/O に慣れていること。  

## カレンダーに祝日を追加する方法

以下では、環境設定から最終的な MPP ファイルの保存まで、各ステップを順に解説します。コードブロックは元のチュートリアルと同じままです。説明文は分かりやすくするために拡充しています。

### ステップ 1: 必要なパッケージをインポート

まず、Aspose.Tasks のクラスと Java のユーティリティをインポートします。

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### ステップ 2: データディレクトリを設定

入力テンプレートと出力ファイルの保存場所を定義します。プレースホルダーを実際のパスに置き換えてください。

```java
String dataDir = "Your Data Directory";
```

### ステップ 3: 入力および出力ファイル名を定義

既存の MPP ファイル（または空のプロジェクト）を読み込み、結果を新しいファイルに書き出します。

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### ステップ 4: プロジェクトを読み込み、新しいカレンダーを追加

ソースファイルから `Project` インスタンスを作成し、**“Calendar 1”** という名前のカレンダーを追加します。

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### ステップ 5: カレンダーをカスタマイズ（オプション）

特定の作業時間、祝日、例外が必要な場合は、独自のヘルパーメソッドを呼び出してください。サンプルでは `GetTestCalendar` をプレースホルダーとして使用しています。

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **プロのコツ:** `cal1.getWeekDays()` を直接操作して各曜日の作業時間を設定したり、`cal1.getExceptions()` を使用して **add holidays to calendar**（カレンダーに祝日を追加）できます。

### ステップ 6: カレンダーをプロジェクトに割り当て

プロジェクトに、作成した新しいカレンダーをすべてのスケジューリング計算に使用するよう指示します。

```java
project.set(Prj.CALENDAR, cal1);
```

### ステップ 7: プロジェクトを MPP として保存

`SaveFileFormat.Mpp` オプションで保存することで、**convert project to MPP**（プロジェクトを MPP に変換）します。

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### ステップ 8: 正常完了を確認

シンプルなコンソールメッセージで、エラーなく処理が完了したことが確認できます。

```java
System.out.println("Process completed Successfully");
```

## 一般的なユースケース

- **Automated schedule generation**（自動スケジュール生成）を、定期的なプロジェクト（例: 週次スプリント）に適用。  
- **Migrating legacy CSV or Excel calendars**（レガシーな CSV や Excel カレンダーの移行）を、フル機能の MS Project ファイルに変換。  
- **Server‑side reporting**（サーバー側レポート）で、Web サービスが要求に応じて MPP ファイルを返す。  

## トラブルシューティングと一般的な落とし穴

| 問題 | 原因 | 対策 |
|------|------|------|
| `project.save` 時の `NullPointerException` | `dataDir` が存在しないフォルダーを指している | ディレクトリが存在することを確認するか、プログラムで作成してください。 |
| カレンダーがタスクに適用されない | タスクがデフォルトのカレンダーを参照したまま | `Prj.CALENDAR` を設定した後、以前に上書きされている場合は各タスクの `Task.CALENDAR` も更新してください。 |
| 出力ファイルが 0 KB | 書き込み権限がない | JVM を適切なファイルシステム権限で実行するか、書き込み可能なパスを選択してください。 |

## よくある質問

**Q: Aspose.Tasks for Java はさまざまなバージョンの MS Project と互換性がありますか？**  
A: はい、Aspose.Tasks for Java は Project 2007 から最新リリースまで、幅広い MS Project バージョンをサポートしており、シームレスな互換性を提供します。

**Q: 特定のプロジェクト要件に合わせてカレンダーをカスタマイズできますか？**  
A: もちろん可能です。作業日を定義し、カスタム作業週を設定し、祝日を追加し、さらには単一のプロジェクトファイル内に複数のカレンダーを作成できます。

**Q: Aspose.Tasks for Java はトラブルシューティングやサポートを提供していますか？**  
A: はい、Aspose.Tasks コミュニティフォーラムでサポートを受けられます [こちら](https://forum.aspose.com/c/tasks/15)。

**Q: Aspose.Tasks for Java の無料トライアルは利用できますか？**  
A: はい、完全に機能する無料トライアルが利用可能です [こちら](https://releases.aspose.com/)。

**Q: Aspose.Tasks for Java の一時ライセンスはどのように取得できますか？**  
A: Aspose のウェブサイトで一時ライセンスをリクエストできます [こちら](https://purchase.aspose.com/temporary-license/)。

---

**最終更新日:** 2026-02-05  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}