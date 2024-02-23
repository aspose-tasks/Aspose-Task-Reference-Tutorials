---
title: Aspose.Tasks で使用状況ビューを構成する
linktitle: Aspose.Tasks で使用状況ビューを構成する
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でタスク使用状況ビューを構成する方法を学習します。詳細な手順でプロジェクトの視覚化を強化します。今すぐライブラリをダウンロードしてください!
type: docs
weight: 17
url: /ja/net/text-view-configuration/usage-views/
---
## 導入
プロジェクト管理機能の強化を検討している .NET 開発者にとって、Aspose.Tasks は Microsoft Project ファイルを簡単に操作できる強力なツールです。このチュートリアルでは、Aspose.Tasks for .NET を使用した使用状況ビューの構成に焦点を当てます。フォローして、プロジェクトの視覚化を改善するための詳細を含むタスク使用状況ビューのレンダリングに関する洞察を得ることができます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Aspose.Tasks ライブラリ: Aspose.Tasks ライブラリが .NET プロジェクトに統合されていることを確認します。そうでない場合は、ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/)インストール手順に従ってください。
- ドキュメント ディレクトリ: プロジェクト ドキュメントが保存されるディレクトリを設定します。コード スニペット内の「ドキュメント ディレクトリ」をドキュメント ディレクトリへの実際のパスに置き換えます。
## 名前空間のインポート
提供されているコード スニペットでは、特定の名前空間が使用されていることがわかります。シームレスな統合のために、プロジェクトにこれらを必ず含めてください。
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## ステップ 1: 詳細を含むタスク使用状況ビューをレンダリングする
まずは、詳細を含むタスク使用状況ビューをレンダリングしてみましょう。次の手順を実行します：
## ステップ 1.1: プロジェクトをロードする
```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## ステップ 1.2: ビューを取得する
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## ステップ 1.3: ビュー設定をカスタマイズする
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## ステップ 1.4: プロジェクトを PDF として保存する
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## ステップ 2: 詳細ヘッダー列を表示する
このステップでは、詳細ヘッダー列を表示し、プロジェクトを PDF として保存するようにビュー設定を変更します。
## ステップ 2.1: 詳細ヘッダー列を表示する
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## ステップ 2.2: すべての行で詳細ヘッダーを繰り返す
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## ステップ 2.3: プロジェクトを PDF として保存する
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## 結論
おめでとう！ Aspose.Tasks で使用状況ビューが正常に構成されました。このチュートリアルでは、Aspose.Tasks ライブラリを使用した効率的なプロジェクト管理と視覚化の基礎を提供します。

### よくある質問
### Q: Aspose.Tasks ドキュメントはどこで見つけられますか?
包括的なドキュメントが利用可能です[ここ](https://reference.aspose.com/tasks/net/).
### Q: Aspose.Tasks for .NET をダウンロードするにはどうすればよいですか?
ライブラリをダウンロードする[ここ](https://releases.aspose.com/tasks/net/).
### Q: Aspose.Tasks はどこで購入できますか?
Aspose.Tasks を購入できます[ここ](https://purchase.aspose.com/buy).
### Q: 無料トライアルはありますか?
はい、無料トライアルを試してみましょう[ここ](https://releases.aspose.com/).
### Q: サポートが必要ですか? 質問がありますか?
サポートフォーラムにアクセスしてください[ここ](https://forum.aspose.com/c/tasks/15).