---
date: 2026-03-19
description: Aspose.Tasks のツリーアルゴリズムを使用してプロジェクトにリソースを追加し、タスクの期間を計算し、.NET でタスクにリソースを割り当てる方法を学びましょう。
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks のツリーアルゴリズムでプロジェクトにリソースを追加
url: /ja/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のツリーアルゴリズムを使用してプロジェクトにリソースを追加する

## はじめに

このチュートリアルでは、Aspose.Tasks for .NET が提供する強力なツリーアルゴリズムを活用して **プロジェクトにリソースを追加する方法** を学びます。タスク階層の作成、タスク期間の計算、タスクへのリソース割り当てを、コピーして自分のソリューションに組み込めるように、明確なステップバイステップで解説します。

## クイック回答
- **ツリーアルゴリズムは何をするのですか？** タスク階層を走査し、作業量の合計を効率的に集計します。  
- **このガイドで扱う主な操作は何ですか？** プロジェクトにリソースを追加し、作業合計を更新することです。  
- **ライセンスは必要ですか？** 本番環境で使用する場合は、一時ライセンスまたはフルライセンスが必要です。  
- **.NET Core でも使用できますか？** はい、Aspose.Tasks は .NET Framework と .NET Core の両方をサポートしています。  
- **実装にどれくらい時間がかかりますか？** 基本的なプロジェクトファイルであれば、10〜15 分程度です。

## Aspose.Tasks における「プロジェクトにリソースを追加する」とは？

プロジェクトにリソースを追加するとは、`Resource` オブジェクトを作成し、そのタイプ（例: work）を定義し、`ResourceAssignments` を介して 1 つ以上のタスクにリンクすることです。これにより、スケジューラは作業量、コスト、全体のプロジェクト期間を計算できるようになります。

## なぜリソース作業計算にツリーアルゴリズムを使うのか？

ツリーアルゴリズムはタスクツリーを一度だけ走査し、リーフタスクからサマリタスクへ作業量を蓄積します。この方法は、特に階層が深く大規模なプロジェクトにおいて、各タスクを個別に反復処理するよりもはるかに効率的です。また、サマリタスクの作業量が子タスクと常に同期されることが保証されます。

## 前提条件

作業を始める前に、以下が揃っていることを確認してください。

1. **Visual Studio** – 最近のエディション（2019、2022、またはそれ以降）。  
2. **Aspose.Tasks for .NET** – [こちら](https://releases.aspose.com/tasks/net/) からダウンロード。  
3. **基本的な C# の知識** – クラス、オブジェクト、簡単な LINQ が扱えること。

## 名前空間のインポート

C# プロジェクトで Aspose.Tasks の機能を使用するために、必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

それでは、各例を複数のステップに分解して説明します。

## ステップ 1: プロジェクト ファイルの読み込み

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

`Project` クラスを使ってプロジェクト ファイルをメモリにロードします。

## ステップ 2: タスク階層の定義

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

親タスクと子タスクを追加してタスク階層を構築します。

## ステップ 3: タスク プロパティの設定（**タスク期間の計算を含む**）

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

ここでは、作業時間を `Duration` オブジェクトに変換し、終了日を導き出すことで **タスク期間を計算** します。

## ステップ 4: リソースの追加（**タスクへのリソース割り当て**）

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

このスニペットは **プロジェクトにリソースを追加** し、**タスクへのリソース割り当て** を行うので、スケジューラが誰が作業を担当するかを認識できるようになります。

## ステップ 5: ツリーアルゴリズムの適用

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

`WorkAccumulator` クラスを初期化し、ツリーアルゴリズムを適用して階層全体の作業量を集計します。

## ステップ 6: タスク作業量の更新

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

集計した情報に基づいてタスクの作業量を更新します。

## 共通の問題とヒント

- **カレンダー設定が欠如している場合:** 終了日がずれて見えるときは、`GetFinishDateByStartAndWork` を呼び出す前にプロジェクト カレンダーが正しく設定されているか確認してください。  
- **リソース タイプの不一致:** 努力ベースのリソースには必ず `Rsc.Type` を `ResourceType.Work` に設定してください。設定しないと作業の蓄積が 0 になることがあります。  
- **プロのコツ:** 作業量を更新した後は `project.Save("UpdatedProject.mpp")` を呼び出して変更を永続化しましょう。

## 結論

この手順に従うことで、**プロジェクトにリソースを追加**し、**タスク期間を計算**し、**タスクへのリソース割り当て**を Aspose.Tasks のツリーアルゴリズムで実現できるようになりました。この方法は階層管理を簡素化し、サマリ作業量を最小限のコードで正確に保ちます。

## FAQ

### Q1: Aspose.Tasks for .NET とは？

A1: Aspose.Tasks for .NET は、C# を使用して Microsoft Project ファイルをプログラムから操作できる強力な API です。

### Q2: Aspose.Tasks for .NET の無料トライアルをダウンロードできますか？

A2: はい、[こちら](https://releases.aspose.com/) から無料トライアルをダウンロードできます。

### Q3: Aspose.Tasks for .NET のドキュメントはどこにありますか？

A3: ドキュメントは [こちら](https://reference.aspose.com/tasks/net/) にあります。

### Q4: Aspose.Tasks for .NET のサポートはどこで受けられますか？

A4: サポートは [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) で受けられます。

### Q5: テスト用の一時ライセンスはありますか？

A5: はい、[こちら](https://purchase.aspose.com/temporary-license/) からテスト用の一時ライセンスを取得できます。

## よくある質問

**Q: 既存の大規模プロジェクト ファイルにもこのアプローチを適用できますか？**  
A: もちろんです。ツリーアルゴリズムはサイズに関係なく任意の `Project` インスタンスで機能します。

**Q: アルゴリズムはコスト値も更新しますか？**  
A: この例は作業量に焦点を当てていますが、同様の手順で `Tsk.Cost` を集計すればコストも更新できます。

**Q: 対応している .NET バージョンは？**  
A: Aspose.Tasks は .NET Framework 4.5 以降、.NET Core 3.1 以降、.NET 5 以降、.NET 6 以降をサポートしています。

**Q: タスクに複数のリソースを割り当てるにはどうすればよいですか？**  
A: `project.ResourceAssignments.Add(task, resource)` をリソースごとに呼び出してください。アキュムレータが自動的に作業量を合算します。

---

**最終更新日:** 2026-03-19  
**テスト環境:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}