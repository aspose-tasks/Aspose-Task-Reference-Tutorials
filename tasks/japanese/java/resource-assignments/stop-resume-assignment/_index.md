---
date: 2026-07-14
description: このステップバイステップガイドでは、Java の Resource Assignment を停止する方法、Resource Assignment
  の管理方法、そして Aspose.Tasks for Java を使用した例をご紹介します。
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Aspose.Tasks で Resource Assignments を停止および再開
og_description: Aspose.Tasks を使用して Java の Resource Assignment を停止します。このチュートリアルでは、割り当ての一時停止と再開、日付の処理、Microsoft
  Project を使用せずに API を統合する方法を示します。
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Java の Resource Assignment を停止 – Aspose.Tasks ガイド
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Java の Resource Assignment を停止する方法 – Aspose.Tasks で再開
url: /ja/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Javaでリソース割り当てを停止する方法 – Aspose.Tasksで再開

## はじめに
このチュートリアルでは、**how to stop resource assignment java** を学び、後で Aspose.Tasks for Java を使用して再開する方法を紹介します。Aspose.Tasks は、Microsoft Project ファイルの読み書き、スケジュールの操作、リソース割り当ての制御を可能にする堅牢な Java API で、Microsoft Project をインストールする必要はありません。各ステップを順に解説し、各行が重要な理由を説明し、実際のプロジェクト計画に適用できる実用的なヒントを共有します。

## クイック回答
- **“stop assignment” とは何ですか？** 特定の停止日からリソース割り当てを一時的に非アクティブとしてマークします。  
- **同じ割り当てを後で再開できますか？** はい、同じ割り当てに再開日を設定することで可能です。  
- **この API を使用するのに Microsoft Project は必要ですか？** いいえ、Aspose.Tasks は Microsoft Project とは独立して動作します。  
- **必要な Java バージョンは？** Java 8 以上が推奨されます。  
- **ライブラリはどこからダウンロードできますか？** 公式の Aspose.Tasks Java ダウンロードページから入手できます。

## Javaでリソース割り当てを停止する方法
プロジェクトをロードし、対象の `ResourceAssignment` を見つけ、`STOP` 日付を設定し、必要に応じて `RESUME` 日付を設定してからファイルを保存します。この手順により、指定された期間の作業が一時停止され、再開日以降に自動的に再アクティブ化されます。手動でファイルを編集することなく、リソースカレンダーを正確に制御できます。

## Aspose.Tasks のコンテキストで「how to stop assignment」とは何ですか？
割り当てを停止すると、スケジューラは **stop date** 以降（※再開日があれば **resume date** まで）にリソースに割り当てられた作業を無視するよう指示します。これは、休暇や機器のダウンタイム、リソースをアクティブと見なすべきでない期間の管理に便利です。

## なぜ Aspose.Tasks を使用してリソース割り当てを管理するのか
Aspose.Tasks を使用すると、割り当て日付をプログラムで制御でき、手動編集を排除しエラーリスクを低減できます。**50 以上の入出力フォーマット** をサポートし、**最大 10,000 タスク** のプロジェクトを処理でき、データをストリーミングしてファイル全体をメモリに読み込まないためメモリ使用量は 200 MB 未満に抑えられます。API は Java をサポートする任意の OS 上で動作し、クロスプラットフォームの柔軟性を提供します。

## 前提条件
- Java Development Kit (JDK) 8 以上がインストールされていること。  
- Aspose.Tasks for Java ライブラリをダウンロード済みであること。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から行えます。  
- Java プログラミングの基本的な理解があること。  

## パッケージのインポート
`Project`、`ResourceAssignment`、`Asn` クラスは `com.aspose.tasks` 名前空間にあります。ソースファイルの先頭でこれらをインポートしてください。

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## 手順 1: プロジェクト ファイルのロード
`Project` クラスは Aspose.Tasks の最上位オブジェクトで、メモリ内で単一の Microsoft Project ファイルを表します。インスタンスを作成するとファイルがロードされ、タスク、リソース、割り当てにアクセスできるようになります。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## 手順 2: リソース割り当てを反復処理する
`ResourceAssignment` オブジェクトはすべての割り当て関連フィールドを公開します。プレースホルダー日付を除外するために **minimum date** を設定し、各割り当てをループ処理します。このパターンは、検査や変更のための標準的な *resource assignment example* です。

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## 手順 3: 停止日と再開日を確認する
このブロックでは各割り当ての `STOP` と `RESUME` フィールドを調べます。日付が `minDate` より前の場合は未設定 (`"NA"`) とみなし、そうでなければ実際の日付を出力します。このロジックは **manage resource assignments** を正しく行うために不可欠です。

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## よくある問題と解決策
- **Null dates** – `ra.get(Asn.STOP)` は `null` を返す可能性があります。`.before(minDate)` を呼び出す前に null チェックを追加して対策してください。  
- **Incorrect file path** – `dataDir` が OS に適したパス区切り文字（`/` または `\\`）で終わっていることを確認してください。  
- **Version mismatch** – 欠落している enum 値を防ぐため、最新の Aspose.Tasks for Java バージョンを使用してください。

## よくある質問
**Q: 割り当ての停止日をプログラムで設定するにはどうすればよいですか？**  
A: `ra.set(Asn.STOP, yourDateObject);` を使用します。`yourDateObject` は `java.util.Date` です。

**Q: 再開日が停止日よりも早い場合はどうなりますか？**  
A: API は時系列順序を強制しませんが、スケジューラは2つの日付のうち遅い方以降に割り当てをアクティブとみなすため、日付は自分で検証する必要があります。

**Q: 停止日が設定されている割り当てだけをフィルタリングできますか？**  
A: はい、`prj.getResourceAssignments()` を反復し、`ra.get(Asn.STOP) != null` を確認してください。

**Q: 設定した停止日を削除することは可能ですか？**  
A: `ra.set(Asn.STOP, null);` で停止日を `null` に設定し、プロジェクトを保存してください。

**Q: Aspose.Tasks は start、finish、actual start などの他の日付関連フィールドもサポートしていますか？**  
A: はい。`Asn` 列挙体は `Asn.START`、`Asn.FINISH` など、すべての割り当てフィールドの定数を提供します。

## 結論
これらの手順に従うことで、**how to stop resource assignment java** を理解し、停止/再開日を確認し、必要に応じて割り当てを再開できるようになりました。この機能により、特にリソースの休暇や機器のダウンタイムなどのシナリオで、**manage resource assignments** をより正確に行えます。例を拡張して日付を更新したり、レポートを生成したり、独自のスケジューリングロジックと統合したりしてください。

---

**最終更新日:** 2026-07-14  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks でリソース割り当てを作成する](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks でコスト差異を計算し、割り当てコストを管理する方法](/tasks/java/resource-assignments/assignment-cost/)
- [Aspose.Tasks でリソース割り当てにノートを追加する方法](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}