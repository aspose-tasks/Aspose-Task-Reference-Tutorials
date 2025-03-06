---
title: Aspose.Tasks のハンドル平準化遅延プロパティ
linktitle: Aspose.Tasks のリソース割り当てのハンドル平準化遅延プロパティ
second_title: Aspose.Tasks Java API
description: この包括的なチュートリアルでは、Aspose.Tasks for Java でリソース割り当ての平準化遅延プロパティを処理する方法を学習します。
weight: 17
url: /ja/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のハンドル平準化遅延プロパティ

## 導入
このチュートリアルでは、Aspose.Tasks for Java でリソース割り当ての平準化遅延プロパティを処理するプロセスについて説明します。 Aspose.Tasks は、システムに Microsoft Project をインストールしなくても Microsoft Project ファイルを操作できる強力な Java ライブラリです。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Java 開発キット (JDK): システムに Java JDK がインストールされていることを確認します。からダウンロードしてインストールできます。[Webサイト](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリを次の場所からダウンロードします。[ダウンロードページ](https://releases.aspose.com/tasks/java/).

## パッケージのインポート
まず、Aspose.Tasks 機能を使用するために必要なパッケージを Java プロジェクトにインポートします。
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## ステップ 1: プロジェクト オブジェクトを作成する
インスタンス化する`Project`物体：
```java
Project prj = new Project();
```
## ステップ 2: タスクを作成する
プロジェクトにタスクを追加します。
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## ステップ 3: タスクの開始日と期間を設定する
タスクの開始日と期間を設定します。
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## ステップ 4: リソースを追加する
リソースをプロジェクトに追加します。
```java
Resource resource = prj.getResources().add("Resource 1");
```
## ステップ 5: リソース割り当てを作成する
タスクとリソースのリソース割り当てを作成します。
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## ステップ 6: レベリング遅延を設定する
割り当てのレベリング遅延を設定します。
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## ステップ 7: 結果の表示
レベリング遅延とその他の関連情報を出力します。
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## 結論
このチュートリアルでは、Aspose.Tasks for Java でリソース割り当ての平準化遅延プロパティを処理する方法を学習しました。これらの手順に従うことで、Java プロジェクトでのリソース割り当てを効率的に管理できます。
## よくある質問
### Q: Aspose.Tasks を他の Java ライブラリで使用できますか?

A: はい、Aspose.Tasks を他の Java ライブラリと統合して、プロジェクト管理機能を強化できます。

### Q: Aspose.Tasks は、Microsoft Project ファイルのさまざまなバージョンと互換性がありますか?

A: はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルをサポートしており、さまざまな環境間での互換性を確保しています。

### Q: Aspose.Tasks の追加サポートはどこで見つけられますか?

 A: サポートとリソースは次のサイトで見つけることができます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).

### Q: 購入する前に Aspose.Tasks を試すことはできますか?

 A: はい、Aspose.Tasks の無料トライアルを次のサイトから入手できます。[リリースページ](https://releases.aspose.com/).

### Q: Aspose.Tasks の一時ライセンスを取得するにはどうすればよいですか?

 A: 一時ライセンスは次のサイトからリクエストできます。[一時ライセンスのページ](https://purchase.aspose.com/temporary-license/)評価目的のため。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
