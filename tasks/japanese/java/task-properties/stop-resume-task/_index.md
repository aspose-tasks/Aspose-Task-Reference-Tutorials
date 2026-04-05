---
date: 2026-02-26
description: Aspose.Tasks for Javaでタスクの再開と停止の方法を学び、日付でタスクをフィルタリングして正確なプロジェクト管理を実現します。
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでタスクを再開および停止する方法
url: /ja/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でタスクを再開および停止する方法

## はじめに
Java ベースのプロジェクト管理ソリューションを構築している場合、タスクを一時的に **一時停止** し、後で **再開** する必要が頻繁にあります。Aspose.Tasks for Java は、タスクの停止と再開のための組み込みプロパティを提供しており、これを簡単に実現できます。このチュートリアルでは、プログラムで **タスクの再開方法** と **タスクの停止方法** を学び、さらに **日付でタスクをフィルタリング** する方法を紹介します。これにより、スケジュール内の関連タスクだけを対象に操作できます。

## クイック回答
- **タスクの「停止」とは何ですか？** 停止日を設定し、その時点以降の作業を一時停止します。  
- **停止したタスクを再開するにはどうすればよいですか？** 停止日より後の再開日を割り当てることで再開できます。  
- **操作を日付範囲に限定できますか？** はい、最小日付を使用してタスクをフィルタリングします。  
- **必要なライブラリのバージョンは？** 最近の Aspose.Tasks for Java のリリースであればどれでも構いません（API は安定しています）。  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境ではライセンスが必要です。

## Aspose.Tasks の「タスクの再開方法」とは？
タスクを再開するということは、`Task` オブジェクトに **RESUME** 日付を設定することを意味します。プロジェクトエンジンがスケジュールを処理すると、その日付以降の作業が再開されます。これは、リソースの利用不可や外部依存関係などの中断を扱う際に特に有用です。

## なぜ停止/再開機能を使用するのか？
- **タイムラインの制御:** タスクを削除せずに作業を一時停止できます。  
- **正確なレポート:** ガントチャートに実際の開始/完了日を表示できます。  
- **自動化が容易:** 日付フィルタと組み合わせて、多数のタスクを一括で更新できます。

## 前提条件
開始する前に、以下を確認してください。

- Java の基礎をしっかり理解していること。  
- マシンに JDK がインストールされていること。  
- プロジェクトに Aspose.Tasks for Java ライブラリを追加すること（[here](https://releases.aspose.com/tasks/java/) からダウンロード）。

## パッケージのインポート
まず、プロジェクトとタスクを操作できるように必要なクラスをインポートします。

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## ステップ 1: プロジェクトとコレクタの初期化
MPP ファイルを指す `Project` インスタンスを作成し、階層内のすべてのタスクを収集する `ChildTasksCollector` を設定します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## ステップ 2: フィルタリング用の最小日付を定義
停止日または再開日が設定されているタスクだけを対象にしたい場合は、**最小日付** を定義します。これが *日付でタスクをフィルタリング* テクニックの核心です。

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## ステップ 3: 反復処理、チェック、停止/再開値の表示
収集したタスクをループし、**タスクの停止** ロジックを適用し、日付を出力します。また、`RESUME` プロパティを読み取ることで **タスクの再開** 方法も示しています。

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **プロのコツ:** `System.out.println` 呼び出しを独自のロジック（例: 日付の更新、ファイルへのログ出力、タスクオブジェクトの変更）に置き換えて、必要に応じてタスクを実際に *停止* または *再開* できるようにします。

## 一般的な問題と解決策
| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | タスクに停止日が設定されていない。 | `.before(minDate)` を呼び出す前に `null` チェックを行う。 |
| Dates appear as `NA` even after setting | 最小日付が新しすぎる。 | より過去の `minDate` を使用するか、フィルタを削除する。 |
| Changes not reflected in the saved MPP | 変更後にプロジェクトを保存していない。 | タスクを更新した後に `project.save("output.mpp");` を呼び出す。 |

## よくある質問

### Aspose.Tasks for Java は大規模プロジェクトに適していますか？
もちろんです！Aspose.Tasks for Java は規模に応じたプロジェクトを効率的かつ信頼性を持って処理できるよう設計されています。

### タスクの停止日と再開日をカスタマイズできますか？
はい、サンプルコードはプロジェクト要件に合わせて最小日付や停止・再開日を柔軟に設定できるようになっています。

### Aspose.Tasks for Java の追加サポートはどこで見つけられますか？
コミュニティサポートやディスカッションは [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) でご利用いただけます。

### Aspose.Tasks for Java の無料トライアルはありますか？
はい、購入前に機能を試せる [free trial](https://releases.aspose.com/) をご利用いただけます。

### Aspose.Tasks for Java の一時ライセンスはどこで取得できますか？
テスト目的で使用できる一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

**追加 Q&A**

**Q: タスクの新しい停止日を実際に設定するには？**  
A: `tsk.set(Tsk.STOP, new Date(...));` を使用し、プロジェクトを保存してください。

**Q: 最小日付だけでなく、特定の範囲でタスクをフィルタリングできますか？**  
A: はい、開始日と終了日を設定し、`before` と `after` の両方で比較すれば範囲指定が可能です。

**Q: 停止/再開日を変更した後、API は自動的にスケジュールを再計算しますか？**  
A: 日付を変更した後は `project.calculateCriticalPath();` を呼び出してスケジュールを更新してください。

## 結論
本ガイドでは、Aspose.Tasks for Java を使用した **タスクの再開方法** と **タスクの停止方法**、さらに **日付でタスクをフィルタリング** する実用的な手法を紹介しました。これらのコードスニペットをアプリケーションに組み込むことで、プロジェクトのタイムラインを細かく制御でき、スケジュール調整を自信を持って自動化できます。

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}