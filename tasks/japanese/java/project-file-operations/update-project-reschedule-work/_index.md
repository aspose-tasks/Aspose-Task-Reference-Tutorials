---
date: 2026-03-29
description: Aspose.Tasks for Java を使用して、未完了の作業を再スケジュールし、プロジェクト作業を更新し、MS Project ファイルを
  XML として保存する方法を学びましょう。
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 未完了の作業を再スケジュールし、Aspose.TasksでMS Projectファイルを更新する
url: /ja/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 未完了作業の再スケジュールと Aspose.Tasks を使用した MS Project ファイルの更新

## 概要
Microsoft Project は、チームがタスクを計画し、リソースを割り当て、タイムラインを追跡するのに役立つ、広く使用されているプロジェクト管理ツールです。Aspose.Tasks for Java は、開発者に Microsoft Project ファイルをプログラムで操作するための豊富な API を提供します。このチュートリアルでは、**プロジェクト作業の更新**、**未完了作業の再スケジュール**、および **MS Project ファイルの保存** を XML 形式で Aspose.Tasks for Java を使用して行う方法を学びます。

## 簡潔な回答
- **“reschedule uncompleted work” は何を意味しますか？** 選択した日付の後に開始するように、残りのタスク作業を移動し、完了した部分はそのままにします。  
- **どのメソッドが作業を完了としてマークしますか？** `project.updateProjectWorkAsComplete(date, false)`。  
- **変更を永続化するにはどうすればよいですか？** `project.save(<path>, SaveFileFormat.Xml)` を使用します。  
- **本番環境でライセンスが必要ですか？** はい、商用利用には有効な Aspose.Tasks ライセンスが必要です。  
- **サポートされている Java バージョンはどれですか？** Java 8 以降が完全にサポートされています。

## “reschedule uncompleted work” とは何ですか？
未完了作業の再スケジュールは、まだ完了していないすべてのタスクの開始日を調整し、指定された基準日以降に開始するようにします。これは、遅延やスコープ変更によりプロジェクトのタイムラインがシフトした場合に便利です。

## プロジェクト作業を更新しタスクを再スケジュールするために Aspose.Tasks を使用する理由は何ですか？
- **細かい制御**：作業完了率や日付を直接設定できます。  
- **UI 不要**：多数のプロジェクトファイルに対して一括更新を自動化できます。  
- **クロスプラットフォーム**：Java が動作する任意のシステムで使用できます。  
- **データ整合性を保持**：すべての依存関係、制約、リソースが一貫したままです。

## 前提条件
1. システムに Java Development Kit (JDK) がインストールされていること。  
2. Aspose.Tasks for Java ライブラリ。以下からダウンロードできます [here](https://releases.aspose.com/tasks/java/)。  
3. Java プログラミング言語の基本的な理解。

## パッケージのインポート
まず、Java コードで必要なパッケージをインポートします。
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## ステップ 1: プロジェクトの設定
`Project` オブジェクトを新規に初期化し、タスクを定義し、期間を設定し、依存関係を確立します。これにより、後で更新および再スケジュールするベースラインプロジェクトが作成されます。
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## ステップ 2: プロジェクト作業の更新
特定の日付まで作業を完了としてマークします。このステップは、**プロジェクト作業の更新** 操作を示しており、再スケジュールの前に行うことが多いです。
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## ステップ 3: 未完了作業の再スケジュール
ここで、残っている（未完了の）作業を同じ基準日以降に開始するようにシフトします。これがコアとなる **未完了作業の再スケジュール** 機能です。
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して **プロジェクト作業の更新**、**未完了作業の再スケジュール**、および **MS Project ファイルを XML として保存**する方法を取り上げました。これらの機能は、実際の進捗やビジネス優先度の変化に基づいてプロジェクトのタイムラインを調整する必要がある場合に不可欠です。

## FAQ
### Q: Aspose.Tasks for Java は複雑なプロジェクト構造を扱えますか？
A: はい、Aspose.Tasks for Java はタスク、依存関係、リソース、その他のプロジェクト要素を効率的に管理するための堅牢な API を提供します。  
### Q: Aspose.Tasks for Java のトライアル版は利用可能ですか？
A: はい、[here](https://releases.aspose.com/) から無料トライアルを取得できます。  
### Q: Aspose.Tasks for Java のサポートはどのように受けられますか？
A: サポートや質問については、[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) をご利用ください。  
### Q: Aspose.Tasks for Java の一時ライセンスを購入できますか？
A: はい、一時ライセンスは[here](https://purchase.aspose.com/temporary-license/)で購入可能です。  
### Q: Aspose.Tasks for Java の詳細なドキュメントはどこで見つけられますか？
A: 詳細なガイドや API リファレンスについては、[here](https://reference.aspose.com/tasks/java/) のドキュメントをご参照ください。

## 追加のよくある質問

**Q: 保存したファイルが古いバージョンの Microsoft Project と互換性があることをどう確認できますか？**  
A: `SaveFileFormat.Xml` を使用してプロジェクトを保存します。XML は Project のさまざまなバージョンで広くサポートされています。

**Q: プロジェクト全体ではなく、タスクのサブセットだけを再スケジュールできますか？**  
A: はい、特定のタスクを反復処理し、新しい開始日を計算した後で `task.setStart(date)` を呼び出すことができます。

**Q: 未完了作業を再スケジュールした場合、リソース割り当てはどうなりますか？**  
A: リソース割り当ては自動的に新しいタスク開始日に合わせてシフトされ、割り当てロジックが保持されます。

**Q: 再スケジュール操作をプログラムで元に戻すことは可能ですか？**  
A: 元のプロジェクトファイル（またはバックアップ）を再読み込みすることで、変更を元に戻すことができます。

**Q: Aspose.Tasks は .mpp などの他の形式での保存をサポートしていますか？**  
A: もちろんです。`SaveFileFormat.MPP` を使用して、ネイティブな Microsoft Project 形式で保存できます。

---

**最終更新日:** 2026-03-29  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}