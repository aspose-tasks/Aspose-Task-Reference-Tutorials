---
title: Aspose.Tasks での MS プロジェクトの更新と再スケジュール
linktitle: Aspose.Tasks でプロジェクトを更新し、未完了の作業を再スケジュールする
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してプログラムで MS Project ファイルを更新および再スケジュールする方法を学びます。
type: docs
weight: 23
url: /ja/java/project-file-operations/update-project-reschedule-work/
---
## 導入
Microsoft Project は、ユーザーがタスク、リソース、タイムラインを効率的に管理できるようにする、広く使用されているプロジェクト管理ソフトウェアです。 Aspose.Tasks for Java は、Microsoft Project ファイルをプログラムで操作するための強力な API セットを提供します。このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project ファイルを更新し、未完了の作業を再スケジュールする方法を学びます。
## 前提条件
始める前に、以下のものがあることを確認してください。
1. Java Development Kit (JDK) がシステムにインストールされています。
2.  Java ライブラリの Aspose.Tasks。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
3. Java プログラミング言語の基本的な理解。

## パッケージのインポート
まず、必要なパッケージを Java コードにインポートします。
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
## ステップ 1: プロジェクトをセットアップする
新しい Project オブジェクトを初期化し、その中にタスクをその期間と依存関係とともに定義します。
```java
String dataDir = "Your Data Directory";
Project project = new Project();
//タスクとその期間を定義する
//...
//タスクの依存関係を定義する
//...
//プロジェクトの初期状態を保存する
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## ステップ 2: プロジェクト作業を更新する
プロジェクトの作業を更新して、特定の日付までに完了としてマークします。
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
//更新したプロジェクトを保存する
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## ステップ 3: 未完了の作業のスケジュールを変更する
未完了の作業を指定日以降に開始するようにスケジュールを変更します。
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
//再スケジュールされたプロジェクトを保存する
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project ファイルを更新し、未完了の作業を再スケジュールする方法を学びました。これは、進捗状況や優先順位の変更に基づいてプロジェクトのタイムラインを調整する必要があるシナリオで特に役立ちます。

## よくある質問
### Q: Aspose.Tasks for Java は複雑なプロジェクト構造を処理できますか?
A: はい、Aspose.Tasks for Java は、タスク、依存関係、リソース、およびその他のプロジェクト要素を効率的に管理するための堅牢な API を提供します。
### Q: Aspose.Tasks for Java の試用版はありますか?
 A: はい、以下から無料トライアルを利用できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java のサポートを受けるにはどうすればよいですか?
 A: にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートやご質問がございましたら。
### Q: Aspose.Tasks for Java の一時ライセンスを購入できますか?
 A: はい、一時ライセンスを購入できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks for Java の詳細なドキュメントはどこで見つけられますか?
 A: ドキュメントを参照してください。[ここ](https://reference.aspose.com/tasks/java/)包括的なガイドと API リファレンスをご覧ください。