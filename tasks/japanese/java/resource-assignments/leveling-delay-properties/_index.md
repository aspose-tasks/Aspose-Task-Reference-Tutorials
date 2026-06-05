---
date: 2026-06-05
description: Aspose.Tasks for Java を使用してリソース割り当てを作成し、プロジェクトにリソースを追加し、レベリング遅延プロパティを管理する方法を学びます。
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Aspose.Tasks のリソース割り当てにおけるレベリング遅延プロパティの処理
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java を使用したリソース割り当ての作成
url: /ja/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Javaでリソース割り当てを作成する

この包括的なガイドでは、Aspose.Tasks ライブラリ for Java を使用して **リソース割り当て aspotasks の作成方法** を学びます。カスタムスケジューリングエンジンの構築、プロジェクトの一括更新の自動化、またはデスクトップアプリケーションなしで Microsoft Project ファイルを操作する必要がある場合でも、これらの手順を習得すれば、プロジェクト データを正確かつ完全に制御できるようになります。

## クイック回答
- **「add resource to project」とは何ですか？** それは、後でタスクに割り当て可能な新しいリソースエントリを作成します。  
- **割り当て後にレベリング遅延を設定できますか？** はい、`Asn.DELAY` または `Asn.LEVELING_DELAY` フィールドを使用します。  
- **このコードを実行するのにライセンスが必要ですか？** 開発には無料トライアルで動作しますが、本番環境では有料ライセンスが必要です。  
- **サポートされている Java バージョンはどれですか？** Java 8 以降。  
- **すべての MS Project ファイル形式と互換性がありますか？** Aspose.Tasks は 12 以上の形式をサポートしています—.MPP、.XML、.XER、.CSV、.PDF などを含みます。

## Aspose.Tasks における「add resource to project」とは何ですか？
プロジェクトにリソースを追加することは、`Project` モデル内に `Resource` オブジェクトを作成することを意味します。このオブジェクトは後で `ResourceAssignment` を介してタスクにリンクでき、作業、コスト、レベリング設定を追跡できます。リソースを挿入することで、スケジューラに割り当て対象を提供し、後で可用性、レート、カレンダー割り当てなどのプロパティを照会または変更できます。

## なぜレベリング遅延プロパティを扱うのか？
レベリング遅延は、過剰割り当てされたタスクの開始を遅らせ、作業をタイムライン全体に均等に分散させるようスケジューラに指示します。この遅延を設定することで、非現実的な開始日を回避し、過剰割り当ての警告を減らし、実際のリソース制約を反映したスケジュールを作成できます。遅延を調整することで、エンジンが挿入できる余裕を細かく制御でき、リソース制限を尊重しながらプロジェクトの締め切りを守るのに役立ちます。

## リソース割り当て aspotasks の作成方法
`Project` オブジェクトをロードし、タスクを追加し、リソースを作成し、`ResourceAssignment` でそれらを結び付けます。このエンドツーエンドのフローにより、プログラムで完全なプロジェクト構造を構築し、割り当てのレベリング遅延を即座に制御できます。このプロセスは、プロジェクトの初期化、タスク定義、リソース作成、割り当てリンク、そして最終的にレベリング遅延などのスケジューリングパラメータの適用というコアワークフローを示します。

## 前提条件
1. Java Development Kit (JDK): システムに Java JDK がインストールされていることを確認してください。[website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) からダウンロードしてインストールできます。  
2. Aspose.Tasks for Java ライブラリ: [download page](https://releases.aspose.com/tasks/java/) から Aspose.Tasks for Java ライブラリをダウンロードしてください。

## パッケージのインポート
以下のインポートは、プロジェクト操作に必要なコア Aspose.Tasks クラスを取り込みます。  
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## リソース割り当て aspotasks の作成方法
`Project` オブジェクトをロードし、タスクを追加し、リソースを作成し、`ResourceAssignment` でそれらを結び付けます。このエンドツーエンドのフローにより、プログラムで完全なプロジェクト構造を構築し、割り当てのレベリング遅延を即座に制御できます。このプロセスは、プロジェクトの初期化、タスク定義、リソース作成、割り当てリンク、そして最終的にレベリング遅延などのスケジューリングパラメータの適用というコアワークフローを示します。

## 手順 1: Project オブジェクトの作成
`Project` クラスは、Aspose.Tasks のトップレベルコンテナで、メモリ内のプロジェクト ファイル全体を表します。インスタンス化することで、タスク、リソース、割り当てを追加するためのクリーンな状態が得られます。  
```java
Project prj = new Project();
```

## 手順 2: タスクの作成
`Task` クラスは、スケジュール内の単一の作業項目を表します。タスクを追加することで、プログラムで **タスクの追加方法** を示し、次に行うリソース割り当ての対象を提供します。  
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## 手順 3: タスクの開始日と期間の設定
タスクの開始時期と実行期間を定義します。適切な開始日は重要です。レベリング計算はそれらを基準として、後で指定する遅延を計算します。  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## 手順 4: リソースの追加
ここで、新しい `Resource` エントリを作成して **add resource to project** を実行します。`Resource` クラスは、タスクに割り当て可能な人物、機器、または資材を表します。  
```java
Resource resource = prj.getResources().add("Resource 1");
```

## 手順 5: リソース割り当ての作成
`ResourceAssignment` は `Task` と `Resource` を結び付けます。この関連付けにより、特定のタスク上の特定リソースに対して作業、コスト、レベリングの詳細を記録できます。  
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## 手順 6: レベリング遅延の設定
割り当てのレベリング遅延を設定します。0 に設定すると追加遅延はありませんが、必要に応じて値を調整できます。`Asn.DELAY` フィールドは遅延を分単位で保持し、`Asn.LEVELING_DELAY` は同様に機能するエイリアスです。  
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## 手順 7: 結果の表示
重要なプロパティを出力して、すべてが正しく設定されたことを確認します。この手順により、ファイルを保存する前にリソース、タスク、遅延の値が期待通りであることを確認できます。  
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## よくある落とし穴とヒント
- **落とし穴:** タスクの開始日を設定し忘れると、割り当てがプロジェクト開始日にデフォルトされる可能性があります。  
- **ヒント:** `prj.getDuration(value, TimeUnitType.Day)` を使用して遅延の粒度を制御します。  
- **ヒント:** 複数のリソースを追加した後、`prj.updateResourceAssignments()` を呼び出してスケジューラにレベリングを再計算させます。  
- **プロのヒント:** 大規模プロジェクト（10,000 件以上のタスク）では、バルク更新の前に `prj.setAutoCalculate(false)` を有効にし、最後に一度だけ `prj.calculate()` を呼び出してパフォーマンスを向上させます。

## よくある質問

**Q: Aspose.Tasks を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Tasks は JSON 処理のための Jackson や、追加のスプレッドシート操作のための Apache POI などのライブラリとスムーズに統合でき、よりリッチなプロジェクト管理ソリューションを構築できます。

**Q: Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルと互換性がありますか？**  
A: Aspose.Tasks は 12 以上のファイル形式をサポートしています—.MPP（2003‑2021）、.XML、.XER、.CSV、.PDF、.HTML、.MPP12 などを含み、主要なすべての Project バージョン間でシームレスな往復編集を実現します。

**Q: Aspose.Tasks の追加サポートはどこで見つけられますか？**  
A: [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) でサポートやコミュニティディスカッションを見つけられます。

**Q: 購入前に Aspose.Tasks を試用できますか？**  
A: はい、[releases page](https://releases.aspose.com/) から完全機能の無料トライアルが利用可能です。

**Q: 評価用の一時ライセンスはどのように取得できますか？**  
A: [temporary license page](https://purchase.aspose.com/temporary-license/) から一時ライセンスをリクエストし、評価制限なしでライブラリを実行できます。

---

**最終更新日:** 2026-06-05  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks でリソース割り当てを作成する](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks を使用した Java の割り当て予算管理](/tasks/java/resource-assignments/assignment-budget/)
- [Aspose.Tasks で割り当てを停止し、リソース割り当てを再開する方法](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}