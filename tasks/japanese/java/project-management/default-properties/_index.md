---
title: Aspose.Tasks で MS プロジェクトのプロパティを効率的に管理する
linktitle: Aspose.Tasks でのデフォルトのプロジェクト プロパティの管理
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を使用してデフォルトの MS Project プロパティを管理する方法を学びます。プロジェクト管理ワークフローを簡単に合理化します。
type: docs
weight: 11
url: /ja/java/project-management/default-properties/
---
## 導入
Aspose.Tasks for Java を使用してプロジェクト管理プロセスを合理化したいと考えていますか? Microsoft Project ファイルのデフォルト プロパティを管理すると、効率が大幅に向上します。このチュートリアルでは、Aspose.Tasks を使用してデフォルトの MS Project プロパティを管理する方法を段階的に説明します。
## 前提条件
チュートリアルを詳しく説明する前に、次の前提条件を満たしていることを確認してください。
### 1. Java 開発キット (JDK)
   - JDK がシステムにインストールされていることを確認してください。
   - からダウンロードできます[ここ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Java ライブラリの Aspose.Tasks
   - Aspose.Tasks for Java ライブラリをダウンロードしてプロジェクトに組み込みます。
   - からダウンロードできます。[Webサイト](https://releases.aspose.com/tasks/java/).
## パッケージのインポート
まず、必要なパッケージを Java ファイルにインポートします。
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
プロセスを管理可能なステップに分割してみましょう。
## ステップ 1: プロジェクト ファイルをロードする
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## ステップ 2: デフォルトのプロパティを表示する
```java
//デフォルトのプロパティを表示する
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## ステップ 3: デフォルトのプロパティを設定する
```java
//デフォルトのプロパティを設定する
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## ステップ 4: プロジェクトを XML 形式で保存する
```java
//プロジェクトを XML 形式で保存します
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## ステップ 5: 結果の表示
```java
//変換結果を表示します。
System.out.println("Process completed Successfully");
```
これらの手順に従うと、Aspose.Tasks for Java を使用してデフォルトの MS Project プロパティを効率的に管理できます。
## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用してデフォルトの MS Project プロパティを管理する方法を学習しました。これらのテクニックを利用することで、プロジェクト管理ワークフローを最適化し、生産性と組織性を向上させることができます。
## よくある質問
### Q1: Aspose.Tasks を他のプログラミング言語で使用できますか?
A1: はい、Aspose.Tasks は .NET、Python、Java などのさまざまなプログラミング言語をサポートしています。
### Q2: Aspose.Tasks は個人使用と企業使用の両方に適していますか?
A2: もちろんです！小規模な個人プロジェクトを管理している場合でも、大規模な企業の取り組みを管理している場合でも、Aspose.Tasks はすべてに対応します。
### Q3: Aspose.Tasks はカスタマー サポートを提供しますか?
A3: はい、次のサイトでサポートとコミュニティ サポートを見つけることができます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).
### Q4: 購入する前に Aspose.Tasks を試すことはできますか?
 A4: もちろんです！から無料トライアルを利用できます。[Webサイト](https://releases.aspose.com/).
### Q5: Aspose.Tasks の一時ライセンスを取得するにはどうすればよいですか?
 A5: 仮ライセンスは次のサイトから取得できます。[購入ページ](https://purchase.aspose.com/temporary-license/)テストと評価の目的で。