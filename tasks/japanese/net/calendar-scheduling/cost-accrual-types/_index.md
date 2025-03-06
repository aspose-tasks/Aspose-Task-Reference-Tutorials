---
title: Aspose.Tasks の原価発生タイプ
linktitle: Aspose.Tasks の原価発生タイプ
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用してプロジェクトのコストを効果的に管理する方法を学びます。正確な予算追跡のために原価見越タイプを定義します。
weight: 19
url: /ja/net/calendar-scheduling/cost-accrual-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks の原価発生タイプ

## 導入

プロジェクト管理では、コストを正確に追跡することは、予算管理を維持し、プロジェクトの成功を確実にするために非常に重要です。 Aspose.Tasks for .NET は、さまざまな見越タイプのコストを定義する機能など、プロジェクト コストを管理するための強力なツール セットを提供します。このチュートリアルでは、Aspose.Tasks for .NET を使用して原価見越タイプを理解して実装するプロセスについて説明します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

### 1. Aspose.Tasks for .NET をインストールする

開始するには、開発環境に Aspose.Tasks for .NET がインストールされている必要があります。ライブラリはからダウンロードできます。[ダウンロードページ](https://releases.aspose.com/tasks/net/)提供されるインストール手順に従ってください。

### 2. .NET Framework に関する知識

このチュートリアルの例に従うには、.NET Framework と C# プログラミング言語の基本的な知識が必要です。

## 名前空間のインポート

まず、.NET プロジェクトの Aspose.Tasks 機能にアクセスするために必要な名前空間をインポートします。

```csharp

```

前提条件を満たし、必要な名前空間をインポートしたので、各例を複数のステップに分割してみましょう。

## ステップ 1: プロジェクト ファイルをロードする

```csharp
var project = new Project("Project2.mpp");
```

まず、プロジェクト ファイルをアプリケーションにロードする必要があります。新しいものを作成します`Project`オブジェクトを作成し、プロジェクト ファイルへのパスで初期化します。

## ステップ 2: リソースにアクセスする

```csharp
var resource = project.Resources.GetById(1);
```

次に、コスト見越タイプを適用するリソースにアクセスします。私たちが使用するのは、`GetById`の方法`Resources`コレクションを指定し、引数としてリソース ID を渡します。

## ステップ 3: 原価見越タイプの設定

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

ここでは、リソースのコスト発生タイプを設定します。この例では、次のように設定しています。`CostAccrualType.End`つまり、残りの作業がゼロになるまでコストは発生しません。

## ステップ 4: プロジェクトで作業する

見越原価タイプを設定した後、必要に応じてプロジェクトの作業を続行し、追加の操作や計算を実行できます。

## 結論

効果的なプロジェクトのコスト管理には、見越原価タイプを理解して実装することが不可欠です。 Aspose.Tasks for .NET を使用すると、プロジェクトの要件に応じて原価見越タイプを簡単に定義およびカスタマイズでき、プロジェクトのライフサイクル全体にわたって正確な原価追跡と予算管理を確保できます。

## よくある質問

### Q1: 複数のリソースのコスト見越タイプを同時に変更できますか?

A1: はい、リソース コレクションをループして、各リソースのコスト見越タイプを個別に設定できます。

### Q2: 「終了」以外に利用可能な見越タイプにはどのようなものがありますか?

A2: Aspose.Tasks for .NET は、次のような他のいくつかの発生コスト タイプを提供します。`Start`, `Prorated`、 そして`Duration`.

### Q3: リソースの現在のコスト見越タイプを確認するにはどうすればよいですか?

 A3: 現在の原価見越タイプを取得するには、`Get`リソースオブジェクトのメソッド。

### Q4: 同じプロジェクト内の異なるタスクに異なる原価見越タイプを適用できますか?

A4: はい、プロジェクト内の各タスクとリソースに対して個別に原価見越タイプを設定できます。

### Q5: Aspose.Tasks for .NET はカスタムの発生原価タイプをサポートしていますか?

A5: 最新バージョンの時点では、Aspose.Tasks for .NET はカスタム原価見越タイプの定義をサポートしていません。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
