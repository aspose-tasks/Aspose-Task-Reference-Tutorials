---
date: 2026-04-06
description: Aspose.Tasks for .NETで、すべてのベースラインを削除し、ベースラインコレクションを管理する方法を、ステップバイステップのコード例とともに学びましょう。
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Aspose.Tasks のベースライン コレクションで全ベースラインを削除
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks ベースラインコレクションを使用してすべてのベースラインを削除
url: /ja/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ベースラインコレクションで全ベースラインを削除する

## はじめに

Aspose.Tasks for .NET は、.NET アプリケーションから直接 Microsoft Project ファイルを操作できます。最も強力な機能の一つは、リソースに対して **全ベースラインを削除** する機能で、プロジェクトのトラッキング データをリセットしたり、新しいベースライン期間を開始したりする際に不可欠です。このチュートリアルでは、プロジェクト ファイルの読み込みから特定のリソースに付随するすべてのベースラインを削除するまでの全工程を、分かりやすく会話調の説明とすぐに実行できる C# コードで解説します。

## クイック回答
- **“全ベースラインを削除” は何をするのですか？** 選択したリソースの保存されたすべてのベースライン レコードを削除し、過去のコストと作業データをクリアします。  
- **なぜこれが必要ですか？** 大規模なプロジェクト変更後や、元のベースラインがもはや適切でなくなったときにトラッキングをリセットするためです。  
- **どのライブラリがこの機能を提供しますか？** Aspose.Tasks for .NET。  
- **ライセンスは必要ですか？** 本番環境で使用するには有効な Aspose.Tasks ライセンスが必要です。無料トライアルも利用可能です。  
- **コードは .NET 6+ と互換性がありますか？** はい、API は .NET Framework 4.5 以降、.NET Core 3.1 以降、そして .NET 5/6 で動作します。

## ベースラインとは何か、そして全ベースラインを削除する理由

ベースラインは、特定の時点におけるコスト、作業、スケジュールの元の計画を記録したものです。プロジェクトの期間中に、実際の進捗を異なる計画スナップショットと比較するために、ベースライン 1、ベースライン 2 など複数のベースラインを作成することがあります。しかし、プロジェクトのスコープ変更や新たな開始などのシナリオでは、過去のベースラインを保持することが混乱を招くことがあります。全ベースラインを削除することで、クリーンな状態になり、現在の実情を反映した新しいベースラインを設定できるようになります。

## 前提条件

コードに入る前に、以下が揃っていることを確認してください。

1. **Visual Studio** – 最近のエディション（Community、Professional、Enterprise のいずれか）。  
2. **Aspose.Tasks for .NET** – [ダウンロードリンク](https://releases.aspose.com/tasks/net/) からダウンロードしてください。  
3. **基本的な C# の知識** – 変数、ループ、コンソール出力に慣れていること。  
4. **Microsoft Project ファイル**（`.mpp`） – 例では *WorkWithBaselineCollection.mpp* というサンプルファイルを使用します。

## 名前空間のインポート

まず、必要な名前空間をスコープにインポートし、コンパイラが使用するクラスの場所を認識できるようにします。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 手順 1: プロジェクト ファイルの読み込み

既存の Project ファイルを読み込みます。`DataDir` を、`.mpp` ファイルが格納されているフォルダーを指すように調整してください。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 手順 2: 対象リソースの取得

デモ用に UID = 1 のリソースを取得します。実際のシナリオでは、名前や他の識別子でリソースを検索します。

```csharp
var resource = project.Resources.GetByUid(1);
```

## 手順 3: 既存のベースライン情報の表示

何かを削除する前に、リソースに現在付随しているベースラインを確認すると便利です。これにより、正しいデータを削除していることを確認できます。

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 手順 4: すべてのベースラインを反復処理

ここでは各ベースラインをループし、コスト、作業、獲得価値（BCWP/BCWS）などの主要指標を出力します。このステップは任意ですが、ログ記録や監査目的で役立ちます。

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## 全ベースラインの削除

ここでコアとなる操作、選択したリソースに対する **全ベースラインの削除** を実行します。イテレーション中にコレクションを変更しないよう、まずコレクションをリストにコピーし、次にベースラインを一つずつ削除します。

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

このブロックが実行されると、`resource.Baselines.Count` は `0` になり、すべてのベースライン レコードがクリアされたことが確認できます。

## よくある問題とヒント

- **NullReferenceException** – プロジェクト ファイルに対象のリソースが実際に含まれていることを確認してください。そうでない場合、`GetByUid` は `null` を返します。  
- **ライセンス** – 有効な Aspose.Tasks ライセンスがない場合、出力に透かしが表示され、機能が制限されます。  
- **パフォーマンス** – 非常に大規模なプロジェクトの場合、`Parallel.ForEach` を使用して削除プロセスを高速化することを検討してください。ただし、基になるコレクションはスレッドセーフではないことに注意してください。

## よくある質問

**Q: Aspose.Tasks は大規模なプロジェクト ファイルを処理できますか？**  
A: はい、Aspose.Tasks はパフォーマンスを最適化しており、マルチギガバイトの `.mpp` ファイルも効率的に処理できます。

**Q: ライブラリはすべての Microsoft Project バージョンと互換性がありますか？**  
A: Aspose.Tasks は Project 2000 から Project 2024 までをサポートし、古い `.mpp` フォーマットと新しい XML ベースのファイルの両方に対応しています。

**Q: ベースラインを削除する前にカスタマイズできますか？**  
A: もちろんです。削除を決定する前に、ベースラインの任意のプロパティ（コスト、作業、日付など）を読み取ったり変更したりできます。

**Q: Aspose.Tasks はクラウド プラットフォームで動作しますか？**  
A: はい、API は Azure App Service、AWS Lambda（.NET Core 経由）、Docker コンテナなど、.NET 対応環境であればどこでも動作します。

**Q: コミュニティに質問したい場合はどこへ行けばよいですか？**  
A: 他の開発者や Aspose スタッフと交流できる [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) をご利用ください。

## 結論

このガイドでは、Aspose.Tasks for .NET を使用してリソースから **全ベースラインを削除** する方法を示しました。ステップバイステップのコードに従うことで、ベースライン データをリセットし、プロジェクトのトラッキングをクリーンに保ち、スケジュールを新たな計画サイクルに備えることができます。削除後に新しいベースラインを作成して、ライブラリがプロジェクト ファイルをどのように更新するかを試してみてください。

---

**最終更新日:** 2026-04-06  
**テスト済み:** Aspose.Tasks 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}