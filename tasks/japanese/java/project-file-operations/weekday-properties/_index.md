---
date: 2026-03-29
description: Aspose.Tasks for Java で月ごとの日数を変更し、他の曜日プロパティを管理する方法を学びましょう。週の開始日をカスタマイズし、プロジェクトカレンダーを変更し、プロジェクトを
  XML として保存します。
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks の Weekday プロパティで月ごとの日数を変更する
url: /ja/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks の平日プロパティで月ごとの日数を変更する

## はじめに
Aspose.Tasks for Java を使用すると、**月ごとの日数を変更**し、Microsoft Project をインストールせずに他の平日設定を微調整できます。プロジェクト カレンダーを標準外の会計月に合わせる場合や、単に週の開始日を調整するだけの場合でも、このチュートリアルでは最も一般的なシナリオ（現在の週開始日の取得、週開始日のカスタマイズ、プロジェクト カレンダーの変更、XML 形式でのプロジェクト保存）を順を追って説明します。

## クイック回答
- **月ごとの日数を変更できますか？** はい、`Project` オブジェクトの `Prj.DAYS_PER_MONTH` を使用します。  
- **週開始日をカスタマイズするには？** `Prj.WEEK_START_DAY` に `DayType` の値（例: `DayType.Monday`）を設定します。  
- **プロジェクトをエクスポートする形式は？** 例では `SaveFileFormat.Xml` を使用して XML 形式でファイルを保存しています。  
- **本番環境でライセンスは必要ですか？** 評価版以外のデプロイには有効な Aspose.Tasks ライセンスが必要です。  
- **対応 IDE はどれですか？** IntelliJ IDEA、Eclipse、NetBeans など、任意の Java IDE が使用できます。

## Aspose.Tasks における「月ごとの日数を変更する」とは？
月ごとの日数を変更するとは、`Project` インスタンスの `Prj.DAYS_PER_MONTH` プロパティを更新することです。このプロパティはエンジンに各月で何日を稼働日として扱うかを指示し、タスクのスケジューリングやコスト計算に直接影響します。

## なぜプロジェクト カレンダーのプロパティを変更するのか？
プロジェクト カレンダーをカスタマイズする（例: 週開始日の変更や1日の分数の調整）ことで、以下のことが可能になります:

- 地域の労働週に合わせてスケジュールを調整する。  
- 標準外の勤務パターン（例: 4日週）をモデル化する。  
- カスタム カレンダーを使用する契約の正確なレポートを確保する。

## 前提条件
- **Java Development Kit (JDK)** – Oracle から最新の JDK をインストールします。  
- **Aspose.Tasks for Java ライブラリ** – 公式サイトの[こちら](https://releases.aspose.com/tasks/java/)からダウンロードします。  
- **お好みの IDE** – IntelliJ IDEA、Eclipse、NetBeans など。

## パッケージのインポート
まず、必要な Aspose.Tasks クラスをインポートします:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 手順 1: プロジェクト ファイルの読み込み
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
指定したフォルダーから既存の Microsoft Project ファイル（`project.mpp`）を読み込みます。

## 手順 2: 平日プロパティの表示
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
ここでは、現在の平日設定（**週開始日** と **月ごとの日数** を含む）を取得して表示します。

## 手順 3: 平日プロパティの設定
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
この手順では、**月ごとの日数** を 24 に変更し、週開始日を月曜日に設定し、1日/1週あたりの分数を調整します。これにより、プログラムで **プロジェクト カレンダー** の値を **変更する** 方法を示します。

## 手順 4: プロジェクトの保存
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
変更されたプロジェクトは **XML 形式でプロジェクトを保存** するフォーマットで永続化されます。これは他のツールとの統合やバージョン管理された保存に便利です。

## 手順 5: 結果の表示
```java
System.out.println("Process completed Successfully");
```
エラーなく処理が完了したことを簡単に確認します。

## 週開始日のカスタマイズ方法
組織が日曜始まりのカレンダーを使用している場合は、`DayType.Monday` を `DayType.Sunday` に置き換えます。同じプロパティ（`Prj.WEEK_START_DAY`）を使用するため、変更は簡単です。

## 週開始日の取得方法
`project.get(Prj.WEEK_START_DAY)` を任意のタイミングで呼び出すことで、**週開始日** の情報を取得できます（手順 2 を参照）。

## プロジェクト カレンダーの変更方法
週開始日以外にも、`Prj.MINUTES_PER_DAY` や `Prj.MINUTES_PER_WEEK` を調整して、カスタムの労働時間やシフト パターンを反映させることができます。

## よくある問題と解決策
- **不正な DayType 値** – `DayType` 列挙体（例: `DayType.Monday`）を使用していることを確認してください。  
- **ファイル パスエラー** – `dataDir` が適切なファイル区切り文字（`/` または `\`）で終わっているか確認してください。  
- **ライセンス未設定** – ライセンス警告が表示された場合は、`Project` オブジェクトを作成する前に Aspose.Tasks のライセンスを登録してください。

## よくある質問

**Q: Aspose.Tasks for Java は複雑なプロジェクト構造を扱えますか？**  
A: はい、Aspose.Tasks for Java は複雑なプロジェクト構造を容易に扱うための包括的なサポートを提供します。

**Q: Aspose.Tasks for Java はさまざまなバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: もちろんです。Aspose.Tasks for Java は多数の Microsoft Project ファイルバージョンをサポートし、プラットフォーム間の互換性を確保します。

**Q: Aspose.Tasks for Java を既存の Java アプリケーションに統合できますか？**  
A: はい、Aspose.Tasks for Java はシームレスな統合機能を提供し、強力なプロジェクト管理機能で Java アプリケーションを拡張できます。

**Q: Aspose.Tasks for Java はドキュメントやサポートを提供していますか？**  
A: はい、Aspose.Tasks for Java の豊富なドキュメントとコミュニティサポートは、公式[ウェブサイト](https://releases.aspose.com/)で利用できます。

**Q: Aspose.Tasks for Java の無料トライアルはありますか？**  
A: はい、購入前に機能を試すために、公式[ウェブサイト](https://reference.aspose.com/tasks/java/)から Aspose.Tasks for Java の無料トライアル版をダウンロードできます。

**最終更新日:** 2026-03-29  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}