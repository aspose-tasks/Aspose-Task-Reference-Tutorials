---
date: 2026-02-26
description: Aspose.Tasks for Java を使用して、タスクの完了日を分割し、プロジェクトのタイムラインを管理する方法を学びましょう。このガイドでは、タスクを効率的に分割する方法を示します。
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: プロジェクトタイムラインの管理 – Aspose.Tasks における分割タスクの完了日
url: /ja/java/task-properties/split-task-finish-date/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のタスク完了日の分割

## はじめに
プロジェクトのタイムラインを効果的に **管理する** ことは、成功するプロジェクト納品の基礎です。タスクの期間が変更されると、スケジュールの正確性を保つために完了日を再計算する必要があります。このチュートリアルでは、Aspose.Tasks for Java を使用して **タスクの完了日を分割する方法** を示し、プロジェクトのタイムラインを正確にコントロールできるようにします。

## クイック回答
- **タスクの完了日を分割すると何が得られますか？** 任意の期間に対して終了日を計算でき、スケジュールをリアルタイムで調整するのに役立ちます。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（公式サイトからダウンロード可能）。  
- **開発にライセンスは必要ですか？** テスト用には一時ライセンスで動作しますが、本番環境では正式ライセンスが必要です。  
- **任意のプロジェクトカレンダーで使用できますか？** はい、API はプロジェクトのカレンダーを使用して稼働日や祝日を考慮します。  
- **必要なコード行数は？** 任意の期間の完了日を取得するのに 10 行未満です。

## Aspose.Tasks における「プロジェクトタイムラインの管理」とは？
プロジェクトタイムラインの管理とは、カレンダー、リソース、タスクの依存関係を考慮しながら、すべてのタスクの開始日と完了日を全体スケジュールと同期させることです。正確な完了日計算は、現実的な見積もりとステークホルダーの信頼を得るために不可欠です。

## なぜタスクの完了日を分割するのか？
- **柔軟性:** 異なる作業時間の割り当てが納期に与える影響をすぐに確認できます。  
- **リスク評価:** 元の計画を変更せずに「もしも」シナリオを評価できます。  
- **リソース計画:** タスク期間をチームのキャパシティやカレンダーの制約に合わせられます。

## 前提条件
開始する前に、以下が揃っていることを確認してください。

- Java プログラミングの基本知識。  
- Aspose.Tasks for Java ライブラリがインストールされていること。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から。  
- Java 開発環境が構築されていること。

## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインクルードします。
```java
import com.aspose.tasks.*;
```

## 手順 1: 分割タスクを見つける
プロジェクト内で分割したいタスクを見つけます。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## 手順 2: プロジェクトカレンダーを取得する
正確な日付計算のためにプロジェクトカレンダーを取得します。
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## 手順 3: 異なる期間でタスクの完了日を計算する
それでは、さまざまな期間に対してタスクの完了日を計算します。

### 手順 3.1: 8 時間の期間
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*上記のコードを異なる期間で繰り返し、時間を調整して各変更が完了日に与える影響を確認してください。*

## よくある問題と解決策
- **カレンダー参照の誤り:** 新しいカレンダーを作成せず、プロジェクトのカレンダー (`project.get(Prj.CALENDAR)`) を取得していることを確認してください。  
- **タスク UID の誤り:** UID は実際に存在するタスクと一致している必要があります。そうでない場合、`getByUid` は `null` を返し、`NullPointerException` が発生します。  
- **タイムゾーンの不一致:** API はカレンダーのタイムゾーンで動作します。結果がずれている場合は、システムのデフォルトゾーンを確認してください。

## 結論
**プロジェクトタイムラインの管理** をタスクの完了日を分割して習得することは、効果的なプロジェクト管理にとって重要です。Aspose.Tasks for Java はこのプロセスを簡素化し、スケジュールを手間なく最適化できます。

## FAQ
### Q1: Aspose.Tasks for Java はどこからダウンロードできますか？
A1: [here](https://releases.aspose.com/tasks/java/) からダウンロードできます。

### Q2: Aspose.Tasks のドキュメントはどこで見つけられますか？
A2: ドキュメントは [here](https://reference.aspose.com/tasks/java/) を参照してください。

### Q3: Aspose.Tasks の一時ライセンスはどう取得しますか？
A3: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Q4: Aspose.Tasks のサポートはどこで受けられますか？
A4: サポートフォーラムは [here](https://forum.aspose.com/c/tasks/15) をご覧ください。

### Q5: Aspose.Tasks を購入できますか？
A5: はい、[here](https://purchase.aspose.com/buy) から購入できます。

## 追加のよくある質問

**Q: カスタムカレンダーでもこの手法を使用できますか？**  
A: もちろんです。`project.get(Prj.CALENDAR)` をカスタムの `Calendar` インスタンスに置き換えるだけです。

**Q: 非稼働日を考慮しますか？**  
A: はい、完了日を計算する際にカレンダーの稼働時間定義が適用されます。

**Q: 小数時間（例: 3.5 時間）の完了日を取得する方法はありますか？**  
A: `getTaskFinishDateFromDuration` に `3.5d` のような `double` 値を渡してください。API は小数の期間を処理します。

**Q: 出力日付のフォーマットはどうすればよいですか？**  
A: 返された `Date` オブジェクトに `java.time.format.DateTimeFormatter` を使用して、好みの形式で表示します。

---

**最終更新日:** 2026-02-26  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}