---
title: Aspose.Tasks での分割タスク終了日
linktitle: Aspose.Tasks での分割タスク終了日
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してタスクの終了日を簡単に分割する方法を学びましょう。正確なタイムラインでプロジェクト管理を強化します。
type: docs
weight: 28
url: /ja/java/task-properties/split-task-finish-date/
---
## 導入
プロジェクト管理では、タスクのタイムラインを理解することが、プロジェクトを正常に完了するために重要です。 Aspose.Tasks for Java は、プロジェクト タスクを効率的に操作するための強力な機能を提供します。このチュートリアルでは、プロジェクトのタイムラインを効果的に管理できるように、Aspose.Tasks を使用してタスクの終了日を分割する方法について詳しく説明します。
## 前提条件
始める前に、以下のものがあることを確認してください。
- Java プログラミングの基本的な知識。
-  Aspose.Tasks for Java ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
- Java 開発環境がセットアップされています。
## パッケージのインポート
まず、Java プロジェクトに必要なパッケージを含めます。
```java
import com.aspose.tasks.*;
```
## ステップ 1: 分割タスクを見つける
プロジェクト内で分割するタスクを見つけます。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//プロジェクトを読む
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## ステップ 2: プロジェクト カレンダーを見つける
正確な日付を計算するためにプロジェクト カレンダーを取得します。
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## ステップ 3: さまざまな期間でタスクの終了日を計算する
ここで、さまざまな期間におけるタスクの終了日を計算します。
## ステップ 3.1: 8 時間の継続時間
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
上記のコードをさまざまな期間に対して繰り返し、それに応じて時間を調整します。
## 結論
タスクの終了日を操作する技術を習得することは、効果的なプロジェクト管理にとって極めて重要です。 Aspose.Tasks for Java はこのプロセスを簡素化し、プロジェクトのタイムラインを簡単に合理化できるようにします。
## よくある質問
### Q1: Aspose.Tasks for Java をダウンロードするにはどうすればよいですか?
 A1: ダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
### Q2: Aspose.Tasks のドキュメントはどこで見つけられますか?
 A2: ドキュメントを参照してください。[ここ](https://reference.aspose.com/tasks/java/).
### Q3: Aspose.Tasks の一時ライセンスを取得するにはどうすればよいですか?
 A3: 仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/).
### Q4: Aspose.Tasks のサポートはどこに問い合わせればよいですか?
 A4: サポート フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tasks/15).
### Q5: Aspose.Tasks を購入できますか?
 A5: はい、購入できます。[ここ](https://purchase.aspose.com/buy).