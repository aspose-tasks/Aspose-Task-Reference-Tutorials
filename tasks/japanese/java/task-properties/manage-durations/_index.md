---
title: Aspose.Tasks でタスクの期間を管理する
linktitle: Aspose.Tasks でタスクの期間を管理する
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を調べて、タスクの期間を簡単に管理する方法を学びましょう。効果的なプロジェクトの計画と実行については、段階的なガイドに従ってください。
weight: 20
url: /ja/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でタスクの期間を管理する

## 導入
Aspose.Tasks for Java は、プロジェクトのタスクと期間を効率的に管理するための堅牢なソリューションを提供します。このチュートリアルでは、Aspose.Tasks を使用してタスクの期間を管理する方法を説明し、各ステップを説明します。経験豊富な開発者であっても、初心者であっても、このガイドは、プロジェクトでタスク期間を扱う際の基本事項を理解するのに役立ちます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Java Development Kit (JDK): マシンに Java がインストールされていることを確認してください。ダウンロードできます[ここ](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks ライブラリ: Aspose.Tasks ライブラリをダウンロードしてプロジェクトに組み込みます。図書館を見つけることができます[ここ](https://releases.aspose.com/tasks/java/).
## パッケージのインポート
Java プロジェクトで、Aspose.Tasks を操作するために必要なパッケージをインポートします。
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## ステップ 1: プロジェクトをセットアップする
```java
//新しいプロジェクトを作成する
Project project = new Project();
```
## ステップ 2: 新しいタスクを追加する
```java
//新しいタスクをプロジェクトに追加する
Task task = project.getRootTask().getChildren().add("Task");
```
## ステップ 3: タスク期間の取得と変換
```java
//タスクの期間を日単位で取得します（デフォルトの時間単位）
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
//期間を時間単位に変換する
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## ステップ 4: タスクの期間を 1 週間に更新する
```java
//タスクの期間を 1 週間に延長する
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## ステップ 5: タスクの期間を短縮する
```java
//タスクの期間を短縮する
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
これらの手順に従うことで、Aspose.Tasks for Java プロジェクトのタスクの期間を正常に管理できました。
## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用してタスク期間を管理する基本について説明しました。これらのテクニックを自信を持ってプロジェクトに組み込んで、タスク期間を効果的に管理できるようになりました。
## よくある質問
### Aspose.Tasks はすべての Java バージョンと互換性がありますか?
Aspose.Tasks は Java 6 以降のバージョンと互換性があります。
### Aspose.Tasks を商用プロジェクトに使用できますか?
はい、Aspose.Tasks は個人プロジェクトと商用プロジェクトの両方に使用できます。訪問[ここ](https://purchase.aspose.com/buy)ライセンスの詳細については、
### 追加のサポートやリソースはどこで入手できますか?
訪問[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティのサポートとディスカッションのために。
### テスト目的で一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/)テストと評価用。
### Aspose.Tasks に利用できる無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/)購入する前に Aspose.Tasks を調べてください。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
