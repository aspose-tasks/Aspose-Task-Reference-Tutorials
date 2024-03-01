---
title: Aspose.Tasks でのタスクの完了率の計算
linktitle: Aspose.Tasks でのタスクの完了率の計算
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java を探索し、プロジェクトの進捗状況の追跡を合理化します。タスクの割合を簡単に計算して、効率的なプロジェクト管理を実現します。
type: docs
weight: 25
url: /ja/java/task-properties/percentage-complete-calculations/
---
## 導入
Aspose.Tasks for Java を使用したタスクの割合の計算をマスターするための詳細ガイドへようこそ。 Aspose.Tasks は、Microsoft Project ファイルを操作するために設計された強力な Java ライブラリであり、プロジェクト管理のための堅牢な機能セットを提供します。このチュートリアルでは、完了率の計算に焦点を当て、プロジェクトの進捗状況を効果的に監視および分析するための知識を提供します。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
- Java 開発環境: システムに Java がインストールされていることを確認してください。
-  Aspose.Tasks ライブラリ: Java 用の Aspose.Tasks ライブラリを次からダウンロードします。[このリンク](https://releases.aspose.com/tasks/java/).
## パッケージのインポート
まずは、Aspose.Tasks for Java プロジェクトに必要なパッケージをインポートします。次のコード スニペットをプロジェクトに含めます。
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
それでは、各ステップを詳しく説明しながら説明していきます。
## ステップ 1: パッケージのインポート
最初のステップでは、Aspose.Tasks プロジェクトを設定するために必要なパッケージをインポートします。
## ステップ 2: ドキュメント ディレクトリの設定
を使用してドキュメント ディレクトリへのパスを定義します。`dataDir`変数。 「Software Development.mpp」などの Microsoft Project ファイルがこのディレクトリにあることを確認してください。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
```
## ステップ 3: プロジェクトをロードする
新しいものを初期化する`Project`オブジェクトを作成し、Microsoft Project ファイルをプロジェクト インスタンスにロードします。
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## ステップ 4: タスク コレクションの取得
プロジェクトのルート タスクを取得し、その子をコレクションとして取得します。`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## ステップ 5: 印刷完了率
コレクション内の各タスクをループし、完了率、作業完了率、物理的な完了率を出力します。
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
プロジェクト内のタスクごとにこれらの手順を繰り返して、各タスクの進捗状況を把握します。
## 結論
おめでとう！ Aspose.Tasks for Java を使用したタスクの割合の計算をマスターしました。この強力なライブラリにより、開発者はプロジェクトの進行状況を効率的に管理および分析できるようになります。
## よくある質問
### Q: Aspose.Tasks ドキュメントはどこで見つけることができますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/tasks/java/).
### Q: Java 用の Aspose.Tasks ライブラリをダウンロードするにはどうすればよいですか?
ダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
### Q: 無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks のサポートはどこで入手できますか?
サポートフォーラムにアクセスしてください[ここ](https://forum.aspose.com/c/tasks/15).
### Q: 一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得できます[ここ](https://purchase.aspose.com/temporary-license/).