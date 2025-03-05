---
title: Aspose.Tasks でクロスプロジェクト タスク リンクを作成する
linktitle: Aspose.Tasks でクロスプロジェクト タスク リンクを作成する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してプロジェクトのコラボレーションを強化します。プロジェクト間のタスク リンクを作成する方法を段階的に学習します。今すぐ効率を高めましょう！
type: docs
weight: 10
url: /ja/java/task-links/create-cross-project-task-link/
---
## 導入
ダイナミックなプロジェクト管理の世界では、効率とコラボレーションが最も重要です。 Aspose.Tasks for Java は、プロジェクト管理機能を強化する堅牢なソリューションを提供します。このチュートリアルでは、Aspose.Tasks for Java を使用してプロジェクト間のタスク リンクを作成するプロセスを詳しく説明します。このステップバイステップのガイドでは、さまざまなプロジェクト間でタスクをシームレスにリンクし、調整の向上とワークフローの合理化を促進するスキルを身につけることができます。
## 前提条件
このチュートリアルを開始する前に、次の前提条件が満たされていることを確認してください。
- Java プログラミングに関する実用的な知識。
-  Aspose.Tasks for Java がインストールされています。からダウンロードできます。[Aspose.Tasks for Java リリース ページ](https://releases.aspose.com/tasks/java/).
- プロジェクト管理とタスクの依存関係についての基本的な理解。
## パッケージのインポート
プロセスを開始するには、Java 環境に必要なパッケージをインポートしましょう。これにより、Aspose.Tasks for Java の機能に確実にアクセスできるようになります。次のコード スニペットを使用します。
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
ここで、上記のコードをわかりやすい手順に分解してみましょう。
## ステップ 1: 環境をセットアップする
コードに入る前に、Java がインストールされていること、および Aspose.Tasks for Java ライブラリがプロジェクトに正しく追加されていることを確認してください。
## ステップ 2: プロジェクト インスタンスを作成する
Aspose.Tasks ライブラリを使用して新しいプロジェクトを初期化します。
```java
Project project = new Project();
```
## ステップ 3: サマリー タスクを追加する
サマリー タスクを作成して、リンクされたタスクを整理および管理します。
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## ステップ 4: 外部タスクの追加
別のプロジェクトからタスクへのリンクを作成するには、外部タスクをサマリー タスクに追加します。
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## ステップ 5: ローカル タスクを追加する
ローカル タスクをサマリー タスクに追加します。これは、外部タスクにリンクされたタスクになります。
```java
Task t = summary.getChildren().add("Task");
```
## ステップ 6: タスクリンクの作成
外部タスクとローカル タスク間のタスク リンクを確立します。
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## ステップ 7: 結果の表示
最後に、変換の結果を表示します。
```java
System.out.println("Process completed Successfully");
```
## 結論
おめでとう！ Aspose.Tasks for Java を使用してプロジェクト間のタスク リンクを作成する方法を学習しました。この機能により、プロジェクト管理におけるコラボレーションと調整が強化され、異なるプロジェクトのタスク間のシームレスな統合が保証されます。
## よくある質問
### 同じサマリー タスク内で複数の外部プロジェクトのタスクをリンクできますか?
はい、同様のプロセスに従って、同じサマリー タスク内の異なる外部プロジェクトのタスクをリンクできます。
### リンクされたプロジェクトの外部タスクが変更されるとどうなりますか?
外部タスクへの変更は、現在のプロジェクトのリンクされたタスクに反映されます。
### 異なるファイル形式のタスク間にリンクを作成することはできますか?
はい、Aspose.Tasks for Java は、さまざまなファイル形式のプロジェクト間のタスクのリンクをサポートしています。
### プロジェクト間でリンクされているタスクのリンクを解除できますか?
はい、適切な Aspose.Tasks メソッドを使用してタスク リンクを削除することで、タスクのリンクを解除できます。
### プロジェクト間でリンクできるタスクの数に制限はありますか?
リンクできるタスクの数は、Aspose.Tasks ライセンスの機能と制限によって決まります。