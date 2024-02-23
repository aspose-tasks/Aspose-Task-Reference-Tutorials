---
title: Aspose.Tasks で MS Project の表示オプションを構成する
linktitle: Aspose.Tasks でプロジェクト表示オプションを構成する
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project の表示オプションをプログラムで構成する方法を学びます。プロジェクトの外観を簡単にカスタマイズできます。
type: docs
weight: 17
url: /ja/net/project-management-integration/project-display-options/
---
## 導入
Microsoft Project には、プロジェクトの外観をカスタマイズするための豊富な表示オプションが用意されています。 Aspose.Tasks for .NET は、これらのオプションをプログラムで操作するための堅牢なフレームワークを提供します。このチュートリアルでは、Aspose.Tasks を使用して MS Project の表示オプションを構成する方法を説明します。
## 前提条件
チュートリアルに入る前に、次のものが揃っていることを確認してください。
1.  Aspose.Tasks for .NET: からライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
2. Microsoft Project ファイル: 表示オプションを適用できる有効な MS Project ファイル (.mpp) を用意します。
3. C# の基本知識: C# プログラミング言語に精通していることが必要です。

## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートしてください。
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## ステップ 1: プロジェクト ファイルをロードする
次のコマンドを使用して MS Project ファイルをロードします。`Project` Aspose.Tasks によって提供されるクラス:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## ステップ 2: 表示オプションを構成する
次に、MS Project で使用できるさまざまな表示オプションを構成しましょう。
### タスクスケジュールの警告を無効にする
手動でスケジュールされたタスクとのスケジュールの競合に関する警告を無効にするには (Project 2010 以降で利用可能):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### ラベルの前にスペースを追加
数値と時間の省略形の前にスペースを追加するように設定します。
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### 時間単位のラベル表示を構成する
さまざまな時間単位の表示方法をカスタマイズします。
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### プロジェクトの概要タスクを表示
プロジェクト全体に関する概要情報を 1 行に表示します。
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### タスクスケジュールの提案を有効にする
手動でスケジュールされたタスクとスケジュールが競合する場合の提案の表示を許可します。
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### ハイパーリンクに下線を引く
プロジェクト内のハイパーリンクに下線を付けるように設定します。
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## ステップ 3: プロジェクトを保存する
最後に、適用された表示オプションを使用してプロジェクトを保存します。
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project の表示オプションを構成する方法を学びました。これらの機能を使用すると、プロジェクト ファイルの外観をプログラムで効率的にカスタマイズできます。
## よくある質問
### Q: これらの表示オプションを特定のタスクにのみ適用できますか?
A: はい、Aspose.Tasks API を使用して、表示オプションを個々のタスクに選択的に適用できます。
### Q: これらの表示オプションは、基礎となるプロジェクト データに影響しますか?
A: いいえ、これらのオプションはプロジェクトの視覚的表現を変更するだけであり、基礎となるデータは変更しません。
### Q: これらの表示オプションは Microsoft Project のすべてのバージョンと互換性がありますか?
A: いいえ、一部のオプションは MS Project の特定のバージョンに固有である場合があります。互換性の詳細については、ドキュメントを参照してください。
### Q: 表示オプションをデフォルト設定に戻すことはできますか?
A: はい、Aspose.Tasks API を使用して表示オプションをデフォルト値にリセットできます。
### Q: 表示オプションをプログラムでカスタマイズする場合に制限はありますか?
A: Aspose.Tasks は広範なカスタマイズ機能を提供しますが、MS Project ファイル形式の制限により、特定の表示オプションにプログラムからアクセスできない場合があります。