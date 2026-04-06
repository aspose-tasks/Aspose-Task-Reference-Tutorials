---
date: 2026-04-06
description: Aspose.Tasks for .NET でバーのスタイルを変更し、バーの色をカスタマイズして、プロジェクトの可視化を向上させる方法を学びましょう。
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Aspose.Tasks のスタイリングバー
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksでバーのスタイリングを変更する方法
url: /ja/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のバー スタイリングの変更方法

## はじめに

Microsoft Project ファイルで **バーの変更方法** が必要な場合、Aspose.Tasks for .NET はバーの色、形状、テキストスタイルを完全に制御できます。バーの色やその他のビジュアル属性をカスタマイズすることで、プロジェクト計画をより読みやすくし、組織のブランディングに合わせることができます。このチュートリアルでは、プロジェクトの読み込みから新しいビジュアルルールを適用してエクスポートするまで、バー スタイリングの変更方法を示す完全なステップバイステップの例を紹介します。

## クイック回答
- **何をスタイル設定できますか？** Gantt チャートのバー、マイルストーン、タスクテキスト。  
- **どの形式がスタイル付きバーをサポートしますか？** PDF、XLSX、HTML、そして `PdfSaveOptions` で保存した場合のネイティブ MPP。  
- **ライセンスは必要ですか？** 本番使用には商用ライセンスが必要です。テストには無料トライアルが利用できます。  
- **複数のスタイルを適用できますか？** はい – 必要なだけの `BarStyle` オブジェクトを追加できます。  
- **.NET Core と互換性がありますか？** 完全に対応しています – .NET Framework と .NET Core/5/6+ で動作します。

## Aspose.Tasks のバー スタイリングとは？

バー スタイリングを使用すると、Aspose.Tasks エンジンが Gantt チャートを描画する際に適用するビジュアル ルールを定義できます。各ルール（**BarStyle**）は特定のアイテムタイプ（タスク、マイルストーン、またはサマリタスク）を対象とし、色、形状、さらにはカスタムテキストを設定できます。

## なぜバーの色をカスタマイズするのか？

バーの色をカスタマイズすることで、ステークホルダーはクリティカルパスや遅延タスク、マイルストーンを瞬時に識別できます。また、企業のカラースキームに合わせることで、レポートをプロフェッショナルかつブランドに沿った外観にできます。

## 前提条件

1. **Aspose.Tasks for .NET** – [download page](https://releases.aspose.com/tasks/net/) からダウンロードしてください。  
2. .NET をサポートする開発環境（Framework 4.6+、.NET Core 3.1+、またはそれ以降）。  
3. C# の基本的な知識 – 例はシンプルで自己完結型のコードを使用しています。

## 名前空間のインポート

まず、使用するクラスが含まれる名前空間をインポートします:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 手順 1: プロジェクトの読み込み

既存の MPP ファイルを読み込む（または新規作成）ことで、操作対象となるプロジェクト オブジェクトを取得します:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## 手順 2: 保存オプションの構成

`PdfSaveOptions` のインスタンスを作成し、カスタム スタイルを格納する `BarStyles` コレクションを初期化します:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## 手順 3: バー スタイルの定義

ここで `BarStyle` オブジェクトを作成し、バーの外観を制御するプロパティを設定します。ここで **バーの色と形状をカスタマイズ** します:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## 手順 4: テキストコンバータのカスタマイズ（オプション）

バーに表示されるテキストを調整したい場合は、カスタム コンバータを割り当てることができます。例では、すでに “T” で始まっていないタスク名にプレフィックスを付加しています:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## 手順 5: オプションにバー スタイルを追加

完全に構成されたスタイルを、保存オプションの `BarStyles` コレクションに追加します:

```csharp
options.BarStyles.Add(style);
```

## 手順 6: プロジェクトの保存

最後に、プロジェクトをエクスポートします。PDF（または他の形式）は、定義したバー スタイルを使用して Gantt チャートを描画します:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## よくある問題と解決策

| 問題 | 原因 | 解決策 |
|------|------|--------|
| **バー スタイルが適用されない** | `BarStyles` コレクションが空、または保存オプションに添付されていませんでした。 | `Save` を呼び出す前に `BarStyle` を `options.BarStyles` に追加していることを確認してください。 |
| **PDF で色が異なる** | PDF のレンダリングが異なるカラープロファイルを使用している可能性があります。 | 標準の `System.Drawing.Color` 値を使用するか、カスタム ARGB 色を定義してください。 |
| **テキストコンバータが null 参照例外をスロー** | タスクプロパティ `Tsk.Name` が一部のタスクで null です。 | `task.Get(Tsk.Name)` にアクセスする前に null チェックを追加してください。 |

## FAQ

### Q1: 単一のプロジェクトに複数のバー スタイルを適用できますか？

A1: はい、同じプロジェクト内の異なるタスクタイプに対して複数のバー スタイルを定義し、適用できます。

### Q2: 実行時にバー スタイルを動的に変更することは可能ですか？

A2: はい、アプリケーション内で特定の条件やユーザー設定に基づいてバー スタイルを動的に変更できます。

### Q3: Aspose.Tasks は、スタイル付きバーを含むプロジェクトをさまざまなファイル形式にエクスポートすることをサポートしていますか？

A3: はい、Aspose.Tasks は PDF、XLSX、HTML などのさまざまな形式へのエクスポートをサポートしています。

### Q4: Aspose.Tasks に事前定義されたバー スタイルはありますか？

A4: Aspose.Tasks はデフォルトのバー スタイルを提供していますが、開発者はプロジェクト要件に合わせたカスタム バー スタイルも作成できます。

### Q5: API を使用してプロジェクト内の既存のバー スタイルを取得・変更できますか？

A5: はい、Aspose.Tasks for .NET API を使用してプログラムから既存のバー スタイルを取得・変更できます。

## よくある質問

**Q: マイルストーンではなく通常タスクのバーの色を変更するにはどうすればよいですか？**  
A: `style.ItemType = BarItemType.Task;` を設定し、`style.BarColor` に目的の `Color` を割り当てます。

**Q: HTML にエクスポートする際にこの方法でバーをスタイル設定できますか？**  
A: はい。`HtmlSaveOptions` を使用し、同様に `BarStyles` コレクションに設定します。

**Q: 定義できるバー スタイルの数に制限はありますか？**  
A: 実質的に制限はありません。必要なだけ追加できますが、非常に大きなコレクションの場合はパフォーマンスに留意してください。

**Q: スタイル変更後に `project.Calculate()` を呼び出す必要がありますか？**  
A: いいえ、スタイルは保存時に適用されます。再計算はスケジュール変更時のみ必要です。

---

**最終更新日:** 2026-04-06  
**テスト対象:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}