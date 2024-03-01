---
title: Aspose.Tasks のタスクに関連付けられた WBS
linktitle: Aspose.Tasks のタスクに関連付けられた WBS
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java で WBS をマスターする - タスク WBS コードの読み取りと再番号付けを学びます。プロジェクト管理を効率化！
type: docs
weight: 36
url: /ja/java/task-properties/wbs-associated-with-task/
---
## 導入
Aspose.Tasks for Java によるプロジェクト管理の世界へようこそ!このチュートリアルでは、Aspose.Tasks for Java を使用してタスクに関連付けられた Work Breakdown Structure (WBS) の複雑さを詳しく説明します。経験豊富な開発者でも、初心者でも、このガイドは、WBS コードを効率的に管理するための基本事項を理解するのに役立ちます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java Development Kit (JDK) がマシンにインストールされています。
-  Aspose.Tasks for Java ライブラリがダウンロードされ、プロジェクトに追加されました。から入手できます[ここ](https://releases.aspose.com/tasks/java/).
## パッケージのインポート
プロジェクトを開始するために必要なパッケージをインポートしていることを確認してください。
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## WBSコードを読む
まずはタスクに関連付けられた WBS コードを読んでみましょう。次の手順を実行します：
## ステップ 1: プロジェクトをロードする
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## ステップ 2: タスクを収集する
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## ステップ 3: 解析とカスタマイズ
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
このスニペットは、プロジェクト内のタスクに関連付けられた WBS コードを読み取り、カスタマイズします。
## タスク WBS コードの再番号付け
ここで、タスクの WBS コードの再番号付けを検討してみましょう。
## ステップ 1: プロジェクトをロードする
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## ステップ 2: すべてのタスクを選択する
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## ステップ 3: 初期 WBS コードを出力する
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## ステップ 4: WBS コードの再番号付け
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## ステップ 5: 更新された WBS コードを出力する
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
これらの手順に従うことで、プロジェクト内のタスクの WBS コードの番号を効果的に再番号付けできます。
## 結論
おめでとう！ Aspose.Tasks for Java を使用して WBS コードを操作する方法を学習しました。この知識により、プロジェクトのタスク階層を効率的に管理およびカスタマイズできるようになります。
## よくある質問
### Q: Aspose.Tasks for Java のドキュメントはどこで見つけられますか?
 A: ドキュメントは入手可能です[ここ](https://reference.aspose.com/tasks/java/).
### Q: Java 用 Aspose.Tasks をダウンロードするにはどうすればよいですか?
答え: ダウンロードできますよ[ここ](https://releases.aspose.com/tasks/java/).
### Q: Aspose.Tasks for Java に利用できる無料トライアルはありますか?
A: はい、無料トライアルを利用できます[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java のサポートはどこで入手できますか?
 A: にアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートのための。
### Q: Aspose.Tasks for Java の一時ライセンスを取得できますか?
 A: はい、一時ライセンスを取得します[ここ](https://purchase.aspose.com/temporary-license/).