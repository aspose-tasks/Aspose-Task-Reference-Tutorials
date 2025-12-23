---
date: 2025-12-23
description: Aspose.Tasks for Java を使用して、MS Project ファイルの更新方法と未完了の作業の再スケジュール方法を学びます。また、MS
  Project XML の保存方法も確認してください。
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.TasksでMS Projectを更新し、作業を再スケジュールする
url: /ja/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用した MS Project の更新と作業の再スケジュール

## はじめに
Microsoft Project は、チームが計画、追跡、期限通りに作業を提供するのに役立つ、広く使用されているプロジェクト管理ツールです。スケジュールが変わると、**update MS Project** ファイルをプログラムで更新する必要がよくあります—作業を完了としてマークし、残りのタスクを移動し、プロジェクトのベースラインを正確に保ちます。Aspose.Tasks for Java は、GUI を開かずにこれを実現するクリーンで型安全な API を提供します。このチュートリアルでは、プロジェクトを更新し、特定の日付まで作業を完了としてマークし、そして **how to reschedule MS Project** の未完了作業を再スケジュールする方法を示します。

## クイック回答
- **“update MS Project” は何を意味しますか？** 指定された日付までタスクを完了としてマークし、変更をファイルに書き戻します。  
- **残りの作業を自動的に再スケジュールできますか？** はい—`rescheduleUncompletedWorkToStartAfter` を使用して未完了タスクを前方に移動します。  
- **どのファイル形式で保存されますか？** 例ではプロジェクトを XML (`SaveFileFormat.Xml`) として保存します。  
- **コードを実行するのにライセンスが必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **必要な Java バージョンは何ですか？** JDK 8 以上。

## コードでの “update MS Project” とは何ですか？
プロジェクトを更新するとは、タスクの日付、期間、または完了率をプログラムで変更し、その変更を永続化することです。Aspose.Tasks は、提供した基準 `Date` に基づいて変更を適用する `updateProjectWorkAsComplete` などのメソッドを公開しています。

## MS Project を更新するために Aspose.Tasks for Java を使用する理由は？
- **UI 依存なし** – 多数のファイルに対して一括変更を自動化します。  
- **高忠実度** – ライブラリはすべてのネイティブ Project データ（リソース、カレンダー、カスタム フィールド）を保持します。  
- **クロスプラットフォーム** – 同じコードを Windows、Linux、macOS で実行できます。  
- **MS Project XML の保存** – 更新されたプロジェクトを、下流ツールで広くサポートされている XML 形式にエクスポートできます。

## 前提条件
1. Java Development Kit (JDK) がインストールされていること。  
2. Aspose.Tasks for Java ライブラリ – [here](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. Java の構文とオブジェクト指向概念に関する基本的な知識。

## パッケージのインポート
まず、必要な Aspose.Tasks クラスと Java ユーティリティをインポートします。

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
新しい `Project` インスタンスを作成し、サンプルタスクをいくつか定義し、期間を設定し、依存関係を確立します。その後、初期状態を永続化して、ビフォーアフターの効果を確認できます。

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
特定のカットオフ日まで作業を完了としてマークします。これが **update MS Project** の核心であり、API がタスクの進捗と日付を自動的に調整します。

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## ステップ 3: 未完了作業の再スケジュール
完了した作業をマークした後、残りのタスクを前方に押し出す必要がよくあります。次の呼び出しは、未完了の作業を同じカットオフ日以降に開始するように移動し、実質的に **how to reschedule MS Project** を実現します。

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| タスクに更新された日付が表示されない | プロジェクトが別の形式（例: `.mpp`）で保存されていた | `SaveFileFormat.Xml` を使用して XML 構造をそのまま保持してください。 |
| `updateProjectWorkAsComplete` が何も行わないように見える | 基準日がプロジェクト開始日より前になっている | `Calendar` の日付がプロジェクトのタイムライン内にあることを確認してください。 |
| 再スケジュールされたタスクが重なる | カレンダーやリソースレベリングが適用されていない | `Project` カレンダーを適用するか、再スケジュール後に `Task.setStart` を手動で使用してください。 |

## よくある質問（拡張）

**Q: Aspose.Tasks for Java は複雑なプロジェクト構造を扱えますか？**  
A: はい、Aspose.Tasks for Java はタスク、依存関係、リソース、その他のプロジェクト要素を効率的に管理するための堅牢な API を提供します。

**Q: Aspose.Tasks for Java のトライアル版はありますか？**  
A: はい、[here](https://releases.aspose.com/) から無料トライアルを取得できます。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
A: 支援や質問がある場合は、[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) をご覧ください。

**Q: Aspose.Tasks for Java の一時ライセンスを購入できますか？**  
A: はい、一時ライセンスは[here](https://purchase.aspose.com/temporary-license/) で購入可能です。

**Q: Aspose.Tasks for Java の詳細なドキュメントはどこで見つけられますか？**  
A: 包括的なガイドと API リファレンスは[here](https://reference.aspose.com/tasks/java/) のドキュメントをご参照ください。

## 結論
このチュートリアルでは、**updating MS Project** ファイルの完全なプロセス、作業を完了としてマークする方法、そして未完了の **how to reschedule MS Project** タスクを再スケジュールする方法を順に解説しました。プロジェクトを XML として保存することで、他のツールとの互換性を保ち、変更の明確な監査トレイルを維持できます。これらのパターンを使用して、大規模ポートフォリオのスケジュール調整を自動化したり、CI パイプラインと統合したり、カスタムレポートダッシュボードを構築したりしてください。

---

**最終更新日:** 2025-12-23  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}