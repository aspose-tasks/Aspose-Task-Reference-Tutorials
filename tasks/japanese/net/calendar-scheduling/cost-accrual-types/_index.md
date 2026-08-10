---
date: 2026-07-05
description: Aspose.Tasks for .NET を使用してプロジェクト予算を追跡し、プロジェクトコストを管理する方法を学びます。正確なコスト追跡のために
  cost accrual types を定義します。
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Aspose.Tasks の Cost Accrual Types
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks で Cost Accrual Types を使用してプロジェクト予算を追跡
url: /ja/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のコスト発生タイプでプロジェクト予算を追跡する

## はじめに

正確に **プロジェクト予算を追跡** することは、成功するプロジェクト実行の基盤です。コスト情報が適切なタイミングで取得されれば、超過を予測し、リソースを調整し、ステークホルダーに情報を提供できます。Aspose.Tasks for .NET は、開発者にコスト発生の細かな制御を提供し、コストが記録される *いつ*（作業開始時、継続的に、または作業完了時のみ）を決められます。このチュートリアルでは、概念を解説し、発生タイプの設定方法を示し、信頼できる予算追跡のベストプラクティスを実演します。

## クイック回答
- **コスト発生タイプの主な目的は何ですか？** それはタスクのライフサイクル内でコストが認識されるタイミングを決定し、正確な予算追跡を可能にします。  
- **作業が完了するまでコストを遅延させる列挙値はどれですか？** `CostAccrualType.End`。  
- **コードを実行するのにライセンスは必要ですか？** はい、製品版で使用するには有効な Aspose.Tasks ライセンスが必要です。  
- **複数のリソースの発生タイプを一度に変更できますか？** はい—`Resources` コレクションをループして目的のタイプを割り当てます。  
- **.NET のどのバージョンがサポートされていますか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## コスト発生タイプとは？

**コスト発生タイプ** は、Aspose.Tasks にリソースのコストをプロジェクト予算にいつ適用するかを指示します。`CostAccrualType` 列挙体で表され、リソース単位またはタスク単位で設定できます。適切なタイプを選択することで、コストデータが組織の請求ポリシーと合致し、作業開始時、期間にわたって比例配分、または完了後のみコストを記録する必要があるかどうかに対応できます。

## コスト発生タイプを使用してプロジェクト予算を追跡する理由

Aspose.Tasks は **four** の発生オプション—`Start`、`Prorated`、`Duration`、`End`—をサポートし、典型的なプロジェクト会計シナリオの全範囲をカバーします。適切なオプションを選択することで、コスト認識を契約の請求サイクルに合わせ、財務レポートのばらつきを減らし、ERP システムとスムーズに統合できるコスト明細を生成できます。また、大規模プロジェクトでもメモリ使用量を低く抑えることができます。

## 前提条件

開始する前に、以下の前提条件が揃っていることを確認してください。

### 1. Aspose.Tasks for .NET のインストール
開始するには、開発環境に Aspose.Tasks for .NET がインストールされている必要があります。ライブラリは[download page](https://releases.aspose.com/tasks/net/)からダウンロードでき、提供されているインストール手順に従ってください。

### 2. .NET Framework の基本知識
.NET フレームワークと C# プログラミング言語の基本的な知識が、このチュートリアルの例を理解するために必要です。

## リソースのコスト発生タイプを設定する方法

プロジェクトをロードし、対象リソースを特定し、目的の `CostAccrualType` を割り当てます。以下の2行パターンが標準的な手順です：`Project` インスタンスを作成し、ID でリソースを取得し、`CostAccrualType` を設定します。この簡潔なシーケンスにより、リソースが追加された瞬間から **プロジェクト予算を正確に追跡** できます。

### 手順 1: 名前空間のインポート
まず、.NET プロジェクトで Aspose.Tasks の機能にアクセスするために必要な名前空間をインポートしましょう。

```csharp

```

### 手順 2: プロジェクト ファイルのロード
`Project` クラスは Microsoft Project ファイルを表し、タスク、リソース、その他のデータへのアクセスを提供します。

```csharp
var project = new Project("Project2.mpp");
```

### 手順 3: リソースへのアクセス
`Resources` コレクションはプロジェクトで定義されたすべてのリソースを保持します。`GetById` メソッドは一意の識別子でリソースを取得します。

```csharp
var resource = project.Resources.GetById(1);
```

次に、コスト発生タイプを適用したいリソースにアクセスします。`Resources` コレクションの `GetById` メソッドを使用し、リソース ID を引数として渡します。これは、コスト更新を自動化する際の一般的な要件である **access resource by id** を示しています。

### 手順 4: コスト発生タイプの設定
`Set` メソッドはリソース フィールドに値を割り当てます。

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

ここでは、リソースのコスト発生タイプを設定します。この例では `CostAccrualType.End` を設定しており、残作業がゼロになるまでコストは発生しません。タスクが完全に完了した後にのみ **プロジェクト予算を追跡** したい場合は、`End` を選択するのが理想的です。

### 手順 5: プロジェクトでの作業を続行
コスト発生タイプを設定した後は、必要に応じてプロジェクトでの作業を続行できます。コストレポートの生成、割り当ての更新、ファイルのエクスポートなど、追加の操作や計算を実行できます。

## よくある落とし穴とプロのコツ
- **Pro tip:** アクレショタイプを変更した後は必ず `project.Save` を呼び出して変更を永続化してください。  
- **Pitfall:** 作業を開始しないリソースに `CostAccrualType.Start` を設定すると、予算レポートが膨らみます。まずタスクスケジュールを確認してください。  
- **Pro tip:** 多数のリソースをバッチ更新する必要がある場合は `project.Resources.ToList()` を使用してください。これによりコレクションの繰り返し検索が回避され、大規模プロジェクトでのパフォーマンスが向上します。

## よくある質問

**Q: 複数のリソースのコスト発生タイプを同時に変更できますか？**  
A: はい、`project.Resources` を反復処理し、`foreach` ループ内で各リソースに目的の `CostAccrualType` を割り当てます。

**Q: `End` 以外に利用可能なコスト発生タイプは何ですか？**  
A: Aspose.Tasks は `Start`、`Prorated`、`Duration` を提供しており、各々が異なる請求戦略に対応します。

**Q: 特定のリソースの現在のコスト発生タイプを確認するには？**  
A: `resource.Get(TskResource.CostAccrualType)` で値を取得します。これにより現在の設定を表す列挙値が返されます。

**Q: 同一プロジェクト内の異なるタスクに異なるコスト発生タイプを適用できますか？**  
A: 可能です。タスクとリソースの両方が `CostAccrualType` プロパティを持ち、エンティティごとに独立して設定できます。

**Q: Aspose.Tasks はカスタムのコスト発生タイプをサポートしていますか？**  
A: いいえ、現在のライブラリは4つの組み込みタイプのみをサポートしており、カスタムロジックが必要な場合は外部で実装する必要があります。

---

**最終更新日:** 2026-07-05  
**テスト環境:** Aspose.Tasks 24.8 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Tasks カレンダーとスケジューリング](/tasks/net/calendar-scheduling/)
- [Aspose.Tasks for .NET での MS Project レートの処理](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Aspose.Tasks で MS Project リソースを簡単に管理](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}