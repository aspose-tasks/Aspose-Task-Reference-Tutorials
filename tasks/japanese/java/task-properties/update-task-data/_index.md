---
title: Aspose.Tasks でタスク データを MPP 形式に更新する
linktitle: Aspose.Tasks でタスク データを MPP 形式に更新する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してタスク データを MPP 形式に更新する方法を学習します。効率的なプロジェクト管理のために、ステップバイステップのガイドに従ってください。
weight: 35
url: /ja/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でタスク データを MPP 形式に更新する

## 導入
Aspose.Tasks for Java を使用してタスク データを MPP 形式に更新するためのステップバイステップ ガイドへようこそ。このチュートリアルでは、プロセスを順を追って説明し、各ステップを明確に理解できるようにします。 Aspose.Tasks for Java は、Microsoft Project ファイルを操作するための堅牢なソリューションを提供しており、このガイドを終了するまでに、タスク データを MPP 形式で効率的に更新できるようになります。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Tasks for Java: Aspose.Tasks ライブラリがインストールされていることを確認してください。からダウンロードできます。[リリースページ](https://releases.aspose.com/tasks/java/).
- Java 開発キット (JDK): システムに Java がインストールされていることを確認してください。
- 統合開発環境 (IDE): Java 開発には任意の IDE を使用します。
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。次のスニペットは、パッケージをインポートする方法を示しています。
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. 初期タスクの作成と構成
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (コードの残りの部分を続けます)
```
## 2. 開始日と期間を設定する
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (コードの残りの部分を続けます)
```
## 3. サマリータスクを作成する
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (コードの残りの部分を続けます)
```
## 4. 期限とタスクメモを設定する
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (コードの残りの部分を続けます)
```
## 5. タスク制約の構成
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (コードの残りの部分を続けます)
```
## 6. 追加のタスクを作成する
```java
//10 個の新しいタスクを作成する
for (int i = 0; i < 10; i++) {
    //... (コードの残りの部分を続けます)
}
//... (コードの残りの部分を続けます)
```
## 7. プロジェクトを保存する
```java
//プロジェクトを保存する
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
これらの手順に従って、Aspose.Tasks for Java を使用してタスク データを MPP 形式に正常に更新しました。
## 結論
おめでとう！ Aspose.Tasks for Java を使用して MPP 形式でタスク データを更新するための包括的なガイドが完了しました。この強力なライブラリはプロジェクト管理タスクを簡素化し、Java 開発者にとって貴重なツールになります。
## よくある質問
### Q: Aspose.Tasks for Java ドキュメントはどこで見つけられますか?
 A: ドキュメントは入手可能です[ここ](https://reference.aspose.com/tasks/java/).
### Q: Java 用 Aspose.Tasks をダウンロードするにはどうすればよいですか?
 A: 以下からダウンロードできます。[リリースページ](https://releases.aspose.com/tasks/java/).
### Q: 無料トライアルはありますか?
 A: はい、無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java のサポートはどこで入手できますか?
 A: サポート フォーラムにアクセスしてください[ここ](https://forum.aspose.com/c/tasks/15).
### Q: テスト目的で一時ライセンスを提供していますか?
 A: はい、一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
