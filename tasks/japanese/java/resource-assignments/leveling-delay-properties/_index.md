---
date: 2026-01-07
description: Aspose.Tasks for Java を使用して、プロジェクトにリソースを追加し、リソース割り当てのレベリング遅延プロパティを処理する方法を学びます。
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksでプロジェクトにリソースを追加し、レベリング遅延プロパティを処理する方法
url: /ja/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasksでリソースをプロジェクトに追加し、レベリング遅延プロパティを処理する方法

## Introduction
このチュートリアルでは、**Aspose.Tasks for Java** を使用して、プロジェクトにリソースを追加し、リソース割り当てのレベリング遅延プロパティを管理する方法を学びます。スケジューリングエンジンを構築したり、プロジェクトの更新を自動化したりする場合でも、Microsoft Project をインストールせずにプロジェクトデータを正確に保つことができます。

## Quick Answers
- **「add resource to project」 は何を意味しますか？** 新しいリソースエントリを作成し、タスクに割り当てることができます。  
- **割り当て後にレベリング遅延を設定できますか？** はい、`Asn.DELAY` または `Asn.LEVELING_DELAY` フィールドを使用します。  
- **このコードを実行するのにライセンスが必要ですか？** 開発には無料トライアルで動作しますが、本番環境では有料ライセンスが必要です。  
- **サポートされている Java バージョンは？** Java 8 以降です。  
- **すべての MS Project ファイル形式と互換性がありますか？** Aspose.Tasks は .MPP、.XML、.XER などをサポートしています。

## What is “add resource to project” in Aspose.Tasks?
プロジェクトにリソースを追加することは、`Project` モデル内に `Resource` オブジェクトを作成することを意味します。このオブジェクトは後で `ResourceAssignment` を介してタスクにリンクでき、作業量、コスト、レベリング設定を追跡できます。

## Why handle leveling delay properties?
レベリング遅延は、リソースが過剰割り当てされている場合にスケジューラが作業を分散させるのに役立ちます。遅延を設定することで、割り当ての開始を遅らせ、競合を回避し、プロジェクトを現実的に保つことができます。

## Prerequisites
開始する前に、以下の前提条件を確認してください：

1. Java Development Kit (JDK): システムに Java JDK がインストールされていることを確認してください。インストールは [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) からダウンロードできます。  
2. Aspose.Tasks for Java ライブラリ: Aspose.Tasks for Java ライブラリは [download page](https://releases.aspose.com/tasks/java/) からダウンロードしてください。

## Import Packages
まず、Aspose.Tasks の機能を使用するために必要なパッケージを Java プロジェクトにインポートします：
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

## Step 1: Create a Project Object
`Project` オブジェクトをインスタンス化します。これがタスク、リソース、割り当てすべてのコンテナとなります：
```java
Project prj = new Project();
```

## Step 2: Create a Task
プロジェクトにタスクを追加します。これはプログラムで **タスクを追加する** 方法のデモです：
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Step 3: Set Task Start Date and Duration
タスクの開始日と期間を定義します：
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Step 4: Add a Resource
ここで新しい `Resource` エントリを作成して **プロジェクトにリソースを追加** します：
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Step 5: Create a Resource Assignment
タスクと先ほど追加したリソースをリンクします：
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Step 6: Set Leveling Delay
割り当てのレベリング遅延を設定します。0 に設定すると追加の遅延はありませんが、必要に応じて値を調整できます：
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Step 7: Display Results
重要なプロパティを出力して、すべてが正しく設定されたことを確認します：
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Common Pitfalls & Tips
- **落とし穴:** タスクの開始日を設定し忘れると、割り当てがプロジェクト開始日にデフォルトされる可能性があります。  
- **ヒント:** `prj.getDuration(value, TimeUnitType.Day)` を使用して遅延の粒度を制御します。  
- **ヒント:** 複数のリソースを追加した後、`prj.updateResourceAssignments()` を呼び出してスケジューラにレベリングを再計算させます。

## Conclusion
これらの手順に従うことで、**プロジェクトにリソースを追加**し、タスクに割り当て、Aspose.Tasks for Java を使用してレベリング遅延プロパティを管理する方法が分かります。この知識により、実際のリソース制約と同期した堅牢なプロジェクト自動化ソリューションを構築できます。

## FAQ's
### Q: Can I use Aspose.Tasks with other Java libraries?
A: はい、Aspose.Tasks は他の Java ライブラリと統合でき、プロジェクト管理機能を強化できます。

### Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?
A: はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project ファイルをサポートしており、異なる環境間での互換性を確保します。

### Q: Where can I find additional support for Aspose.Tasks?
A: サポートやリソースは [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) で確認できます。

### Q: Can I try Aspose.Tasks before purchasing?
A: はい、[releases page](https://releases.aspose.com/) から Aspose.Tasks の無料トライアルを取得できます。

### Q: How can I obtain a temporary license for Aspose.Tasks?
A: 評価目的で一時ライセンスが必要な場合は、[temporary license page](https://purchase.aspose.com/temporary-license/) からリクエストできます。

## Additional Frequently Asked Questions

**Q: 非ゼロのレベリング遅延を設定するとどうなりますか？**  
A: スケジューラは指定された期間だけ割り当ての開始を遅らせ、過剰割り当ての解消に役立ちます。

**Q: プロジェクトを保存した後にレベリング遅延を取得できますか？**  
A: はい、プロジェクトファイルを再度開き、割り当てから `Asn.DELAY` プロパティを読み取れます。

**Q: すべての割り当てに一括でレベリング遅延を適用する方法はありますか？**  
A: `prj.getResourceAssignments()` をイテレートし、ループ内で各割り当ての遅延を設定できます。

---

**最終更新日:** 2026-01-07  
**テスト環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}