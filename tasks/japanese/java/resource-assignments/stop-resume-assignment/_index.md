---
date: 2026-01-10
description: このステップバイステップチュートリアルで、割り当ての停止方法、リソース割り当ての管理方法、そして Aspose.Tasks for Java
  のリソース割り当て例の表示方法を学びましょう。
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksで割り当てを停止し、リソース割り当てを再開する方法
url: /ja/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で割り当てを停止し、リソース割り当てを再開する方法

## Introduction
このチュートリアルでは、**Aspose.Tasks for Java** を使用して割り当てを停止し、後で再開する方法を学びます。Aspose.Tasks は、プロジェクトファイル（Java フォーマット）を読み取り、Microsoft Project データを操作し、Microsoft Project をインストールせずにリソース割り当てを管理できる強力な Java API です。各ステップを順に解説し、各行が重要な理由を説明し、実際のプロジェクトに適用できる実用的なヒントを提供します。

## Quick Answers
- **“割り当ての停止”とは何ですか？** 特定の停止日からリソース割り当てを一時的に非アクティブとしてマークします。  
- **同じ割り当てを後で再開できますか？** はい、同じ割り当てに再開日を設定すれば再開できます。  
- **この API を使用するのに Microsoft Project は必要ですか？** いいえ、Aspose.Tasks は Microsoft Project とは独立して動作します。  
- **必要な Java のバージョンは？** Java 8 以上が推奨されます。  
- **ライブラリはどこからダウンロードできますか？** 公式の Aspose.Tasks Java ダウンロードページから入手できます。  

## Aspose.Tasks のコンテキストで「割り当ての停止」とは何か
割り当てを停止すると、スケジューラは **停止日** 以降、（存在する場合は）**再開日** までリソースに割り当てられた作業を無視するよう指示します。これは、休暇や機器のダウンタイム、リソースをアクティブと見なすべきでない期間の管理に便利です。

## リソース割り当ての管理に Aspose.Tasks を使用する理由
- **Microsoft Project は不要** – .mpp ファイルを直接操作できます。  
- **日付を完全にコントロール** – プログラムから停止日や再開日を確認・調整できます。  
- **クロスプラットフォーム** – Java をサポートする任意の OS で実行できます。  
- **豊富な API** – カスタムレポート作成に拡張可能な *resource assignment example* を提供します。  

## 前提条件
始める前に、以下が揃っていることを確認してください：

- システムに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Tasks for Java ライブラリをダウンロードしていること。ダウンロードは [here](https://releases.aspose.com/tasks/java/) から行えます。  
- Java プログラミングの基本的な理解があること。  

## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートしましょう：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## ステップ 1: プロジェクト ファイルの読み込み
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

ここでは **プロジェクト ファイル（Java フォーマット）**（`.mpp`）を読み込み、リソース割り当てを含むすべてのプロジェクト データにアクセスできる `Project` オブジェクトを作成します。

## ステップ 2: リソース割り当てのイテレーション
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

プレースホルダー日付を除外するために **最小日付** を設定し、各割り当てをループします。これは、割り当てを検査または変更する必要がある場合に使用される典型的な *resource assignment example* パターンです。

## ステップ 3: 停止日と再開日の確認
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

このブロックでは各割り当ての **停止日** と **再開日** を確認します。日付が `minDate` より前の場合は未設定（`"NA"`）として扱い、そうでなければ実際の日付を出力します。このロジックは **リソース割り当ての管理** を正しく行うために不可欠です。

## 一般的な問題と解決策
- **Null 日付** – `ra.get(Asn.STOP)` は `null` を返す可能性があります。`.before(minDate)` を呼び出す前に null チェックを追加して対策してください。  
- **ファイルパスが不正** – `dataDir` が OS に適したパス区切り文字（`/` または `\\`）で終わっていることを確認してください。  
- **バージョン不一致** – 列挙値が欠落しないよう、最新の Aspose.Tasks for Java バージョンを使用してください。  

## FAQ

### Microsoft Project をインストールせずに Aspose.Tasks を使用できますか？
はい、Aspose.Tasks は Microsoft Project がインストールされていなくても Microsoft Project ファイルを操作できます。

### さらに詳しいドキュメントはどこで見つけられますか？
詳細なドキュメントは [here](https://reference.aspose.com/tasks/java/) にあります。

### 無料トライアルはありますか？
はい、無料トライアルは [here](https://releases.aspose.com/) から取得できます。

### 問題が発生した場合、どこでサポートを受けられますか？
コミュニティサポートは [here](https://forum.aspose.com/c/tasks/15) で利用できます。

### 一時ライセンスを購入できますか？
はい、一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から購入できます。

## Frequently Asked Questions

**Q: 割り当ての停止日をプログラムで設定するにはどうすればよいですか？**  
A: `ra.set(Asn.STOP, yourDateObject);` を使用します。`yourDateObject` は `java.util.Date` 型です。

**Q: 再開日が停止日より早い場合はどうなりますか？**  
A: API は時間順序を強制しませんが、スケジューラは両方のうち遅い方の日付以降に割り当てをアクティブとみなすため、日付の検証は自分で行う必要があります。

**Q: 停止日が設定されている割り当てだけをフィルタリングできますか？**  
A: はい、`prj.getResourceAssignments()` をイテレートし、`ra.get(Asn.STOP) != null` をチェックします。

**Q: 設定した停止日を削除できますか？**  
A: `ra.set(Asn.STOP, null);` で停止日を `null` に設定し、プロジェクトを保存すれば削除できます。

**Q: Aspose.Tasks は start、finish、actual start などの他の日付関連フィールドもサポートしていますか？**  
A: もちろんです。`Asn` 列挙は `Asn.START`、`Asn.FINISH` など、すべての割り当てフィールドの定数を提供します。

## 結論
これらの手順に従うことで、**割り当ての停止方法** を理解し、停止日・再開日を確認し、必要に応じて割り当てを再開できるようになりました。この機能により、リソースの休暇や機器のダウンタイムなどのシナリオで、**リソース割り当ての管理** をより正確に行えます。例を拡張して日付の更新、レポートの生成、独自のスケジューリングロジックとの統合などに自由に活用してください。

---

**最終更新日:** 2026-01-10  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}