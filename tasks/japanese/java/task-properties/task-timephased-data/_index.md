---
title: Aspose.Tasks のタスクのタイムスケール データ
linktitle: Aspose.Tasks のタスクのタイムスケール データ
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java とマスター タスクのタイムスケール データ管理を調べてください。ライブラリをダウンロードして無料トライアルを楽しんで、プロジェクトの追跡を効率化してください。
weight: 34
url: /ja/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のタスクのタイムスケール データ

## 導入
プロジェクト管理の分野では、タスクのタイムスケール データを正確に追跡することが、プロジェクトを効率的に実行するために重要です。 Aspose.Tasks for Java は、このプロセスを合理化する強力なツールとして登場し、堅牢な機能と柔軟性を提供します。このチュートリアルでは、Aspose.Tasks for Java を利用してタスクのタイムスケール データを効果的に管理する方法を説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java 開発環境: システムに Java がインストールされていることを確認してください。
-  Aspose.Tasks for Java ライブラリ: Aspose.Tasks ライブラリをダウンロードしてプロジェクトに組み込みます。図書館を見つけることができます[ここ](https://releases.aspose.com/tasks/java/).
- ドキュメント ディレクトリ: プロジェクト ドキュメント用のディレクトリを設定します。
## パッケージのインポート
Java プロジェクトで、Aspose.Tasks に必要なパッケージをインポートします。
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## ステップ 1: プロジェクトの開始日を設定する
```java
Project project = new Project(dataDir + "project.xml");
//パッケージインポート用の追加コード
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
説明: カレンダーオブジェクトを初期化し、開始日を設定して、プロジェクトに適用します。
## ステップ 2: タスクとリソースを定義する
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
説明: タスクとリソースを作成し、標準時間と超過時間の料金を設定します。
## ステップ 3: タスクの期間を設定する
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
説明: タスクの期間を定義します (例: 6 日)。
## ステップ 4: リソースをタスクに割り当てる
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
説明: リソースをタスクに割り当てます。
## ステップ 5: リソース割り当ての構成
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
説明: リソース割り当ての停止、再開、作業輪郭などのパラメータを設定します。
## ステップ 6: ベースラインを設定する
```java
project.setBaseline(BaselineType.Baseline);
```
説明: プロジェクトのベースラインを確立します。
## ステップ 7: 更新タスクの完了
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
説明: タスクの完了率を示します。
## ステップ 8: タイムスケール データを取得する
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
説明: 割り当ての残りの作業時間ごとのデータを取得します。
## ステップ 9: タイムスケール データを表示する
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
//他の値を表示するための追加コード
```
説明: タイムフェーズ データを出力および表示します。
## 結論
プロジェクトの成功には、タスクのタイムスケール データを効果的に管理することが不可欠です。 Aspose.Tasks for Java はこのプロセスを簡素化し、包括的な機能セットを提供します。このチュートリアルに従うことで、Aspose.Tasks を Java プロジェクトにシームレスに統合し、プロジェクトのタイムラインとリソース割り当てを正確に制御できます。
## よくある質問
### Q: Aspose.Tasks for Java はどの Java プロジェクトでも使用できますか?
A: はい、Aspose.Tasks for Java はあらゆる Java ベースのプロジェクトと互換性があります。
### Q: Aspose.Tasks for Java の追加サポートはどこで見つけられますか?
 A: にアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートとディスカッションのため。
### Q: Aspose.Tasks for Java に利用できる無料トライアルはありますか?
 A: はい、無料トライアルを試すことができます[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java の一時ライセンスを取得するにはどうすればよいですか?
A: 一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks for Java はどこで購入できますか?
 A: Aspose.Tasks for Java を購入できます。[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
