---
date: 2025-12-31
description: Aspose.Tasks for Java を使用して、プロジェクトの開始日を設定し、プロジェクト情報を書き込み、XML としてプロジェクトを保存する方法を学びます。
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java を使用して MS Project のプロジェクト開始日を設定する
url: /ja/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS ProjectでAspose.Tasks for Javaを使用してプロジェクト開始日を設定する

## Introduction
このチュートリアルでは、Aspose.Tasks for Java を使用して **プロジェクト開始日を設定**し、追加の MS Project 情報を書き込む方法を紹介します。プロジェクトスケジュールの自動化、レポートの生成、またはプロジェクトデータを大規模システムに統合する場合でも、開始日をプログラムで制御することで、タイムラインを正確に管理できます。環境設定から更新されたプロジェクトを XML ファイルとして保存するまでの各ステップを順に解説するので、すぐにこの手法を適用できます。

## Quick Answers
- **プロジェクトを操作するための主要クラスは何ですか？** `Project` は Aspose.Tasks ライブラリから提供されます。  
- **プロジェクト開始日を設定するには？** `project.set(Prj.START_DATE, <date>)` を使用します。  
- **ステータス日も設定できますか？** はい、`project.set(Prj.STATUS_DATE, <date>)` で設定できます。  
- **プロジェクトをエクスポートする形式は？** `SaveFileFormat.Xml` で XML として保存します。  
- **本番環境でライセンスが必要ですか？** フル機能を利用するには有効な Aspose.Tasks ライセンスが必要です。

## What is **set project start date**?
プロジェクト開始日を設定することは、すべてのスケジュールされたタスクが開始するカレンダー日を定義することです。タスク期間、依存関係、クリティカルパスなどの計算の基準点となります。プログラムでこの日付を設定することで、複数のプロジェクトファイル間で一貫性が保たれ、手動入力エラーが排除されます。

## Why use Aspose.Tasks for Java to write project information?
- **フル API カバレッジ:** Microsoft Project をインストールせずに、すべての Project プロパティを読み取り、変更、書き込みできます。  
- **クロスプラットフォーム:** Windows、Linux、macOS で動作します。  
- **オートメーション対応:** バッチ処理、CI パイプライン、またはリアルタイムでプロジェクトスケジュールを生成するバックエンドサービスに最適です。  

## Prerequisites
開始する前に、以下を確認してください:

1. **Java Development Kit (JDK)** – 任意の最新バージョン（8 以上推奨）。  
2. **Aspose.Tasks for Java ライブラリ** – [here](https://releases.aspose.com/tasks/java/) からダウンロードしてください。  
3. **IDE** – IntelliJ IDEA、Eclipse、またはお好みの Java エディタ。  

## Import Packages
まず、Java プロジェクトで必要なパッケージをインポートします:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Step 1: Set Up Data Directory
プロジェクトデータを保存するディレクトリを定義します。
```java
String dataDir = "Your Data Directory";
```

## Step 2: Create Project Instance
新しいプロジェクトインスタンスを初期化します。
```java
Project project = new Project();
```

## Step 3: Set Project Information Properties
ここでは **プロジェクト開始日**、開始からのスケジュール、ステータス日を設定します — 主なキーワード *write project information* と二次キーワード *how to set status* をカバーします。
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Step 4: Save Project as XML
最後に、更新されたプロジェクトファイルを永続化します。これは二次キーワード **save project as xml** を示しています。
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **開始日が正しくない** | Java の Calendar では月が 0 から始まります。 | `Calendar.JULY` を使用する（または月インデックスに 1 を加える）ようにします。 |
| **ファイルが保存されない** | `dataDir` が存在しない、または書き込み権限がありません。 | 事前にディレクトリを作成するか、書き込み可能なパスを選択してください。 |
| **ライセンス警告** | ライセンスなしで実行すると透かしが付加されます。 | `Project` オブジェクトを作成する前に有効な Aspose.Tasks ライセンスを適用してください。 |

## FAQ's
### Q: Can I use Aspose.Tasks for Java to read MS Project files?
A: はい、Aspose.Tasks for Java は MS Project ファイルの読み取りと書き込みの両方に強力な機能を提供します。  
### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
A: もちろん、Aspose.Tasks for Java はさまざまなバージョンの MS Project をサポートしており、異なるファイル形式間でも互換性があります。  
### Q: Are there any limitations to the trial version of Aspose.Tasks for Java?
A: トライアル版ではライブラリの機能を試すことができますが、出力ファイルに透かしが入るなどの制限があります。  
### Q: How can I get support for Aspose.Tasks for Java?
A: Aspose.Tasks コミュニティフォーラム [here](https://forum.aspose.com/c/tasks/15) でサポートを受けられます。  
### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
A: はい、短期利用向けの一時ライセンスが利用可能です。[here](https://purchase.aspose.com/temporary-license/) から取得できます。  

## Conclusion
これで **プロジェクト開始日を設定**し、重要なプロジェクト情報を書き込み、Aspose.Tasks for Java を使用して **XML としてプロジェクトを保存**する方法を学びました。これらの基本ブロックにより、プロジェクト管理ワークフローの自動化、一貫したスケジュールの生成、MS Project データの Java アプリケーションへの統合が可能になります。

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}