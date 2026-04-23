---
date: 2026-02-13
description: Aspose.Tasks Javaで新しいアクティビティの作成方法、データディレクトリの設定方法、プロジェクトをMPPとして保存する方法を学びます。このステップバイステップガイドでは、テーブルフィールドのカスタマイズについても説明しています。
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasksで新しいアクティビティを作成し、データディレクトリを設定する方法
url: /ja/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新しいアクティビティの作成とデータディレクトリの設定 Aspose.Tasks

## Introduction
このチュートリアルでは、**データディレクトリの設定方法**、**新しいアクティビティの作成方法**、および **MPP としてプロジェクトを保存** する方法を学びます。さらに、Aspose.Tasks for Java を使用して Gantt MS Project Chart View を構成します。Aspose.Tasks は、Microsoft Project ファイルをプログラムから操作できる強力な Java API です。本ガイドを終える頃には、**テーブルフィールドのカスタマイズ**、データディレクトリの調整、そしてプロジェクトを必要な形で可視化できるようになります。

## Quick Answers
- **最初のステップは何ですか？** プロジェクトファイルが格納されているデータディレクトリのパスを設定します。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（公式サイトからダウンロード可能）。  
- **カスタム属性を追加できますか？** はい – 拡張属性を定義し、Gantt チャートに表示できます。  
- **テスト用にライセンスは必要ですか？** 評価目的の一時ライセンスが利用可能です。  
- **どの IDE が最適ですか？** 任意の Java IDE（IntelliJ IDEA、Eclipse、NetBeans）で動作します。

## What is “set data directory” and why does it matter?
データディレクトリを設定すると、Aspose.Tasks がプロジェクトファイルの読み書き先を認識します。パスが正しくないと API は `.mpp` ファイルを見つけられず、FileNotFound エラーが発生します。コードの冒頭でこのディレクトリを定義しておくことで、以降の処理をクリーンかつ再現可能にできます。

## Why customize table fields in a Gantt chart?
カスタムテーブルフィールドを使用すると、カスタム属性やリソース情報、プロジェクト固有のメモなど、追加情報を Gantt ビューに直接表示できます。これによりステークホルダーへの情報提供が充実し、複数のレポートを行き来する手間が減ります。

## How to create new activity?
新しいアクティビティ（タスク）を作成することは、プロジェクトスケジュールを構築・更新する際の基本操作です。プログラムからタスクを追加すれば、複雑な計画の自動生成や他システムからのデータ統合、手作業なしでの一括変更が可能になります。

## Prerequisites
開始する前に、以下を用意してください。

1. **Java Development Kit (JDK)** – 任意の最新バージョン（8 以上）。  
2. **Aspose.Tasks Library** – [here](https://releases.aspose.com/tasks/java/) からダウンロード。  
3. **IDE** – IntelliJ IDEA、Eclipse、またはお好みの Java 対応エディタ。

## Import Packages
まず、Aspose.Tasks の名前空間をインポートしてクラスを使用できるようにします。

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
プロジェクトファイルが格納されているフォルダーを定義します。これが本チュートリアルの中心である **データディレクトリの設定** 手順です。

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` を `project.mpp` が保存されているフォルダーの絶対パスに置き換えてください。

### Step 2: Load Project File
既存の Microsoft Project ファイルを読み込み、`Project` インスタンスを作成します。

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: Add New Activity
プロジェクトのルートに新しいタスク（アクティビティ）を挿入します。これにより **プログラムから新しいアクティビティを作成** する方法が示されます。

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Step 4: Define Custom Attribute
後でタスクに付与できるカスタム属性定義を作成します。

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Step 5: Add Custom Attribute to Task
先ほど定義した属性を作成したタスクに割り当てます。

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Step 6: Customize Table – **customize table fields**
カスタム属性を Gantt チャートのテーブルに列として追加し、幅・タイトル・配置を指定します。

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Step 7: Save Project
変更を新しいファイルに保存し、Microsoft Project で開けるようにします。この手順で **プロジェクトを MPP として保存** します。

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** when loading the project | **データディレクトリ** のパスが間違っている、または末尾のスラッシュが欠けている | `dataDir` が正確なフォルダーを指しているか確認し、適切なファイル区切り文字（`/` または `\\`）を含める |
| Custom attribute not visible in Gantt view | テーブルフィールドを誤ったインデックスに追加した、または列幅が狭すぎる | `table.getTableFields().add(3, attrField);` のインデックスが有効か確認し、`setWidth` を必要に応じて調整 |
| LicenseException on save | 本番使用の有効なライセンスが適用されていない | `project.save()` を呼び出す前に、一時または永続ライセンスを適用する |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks is available for multiple programming languages including .NET, Java, and C++.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Yes, you can download a free trial from [here](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: How can I purchase a license for Aspose.Tasks?**  
A: You can purchase a license from [here](https://purchase.aspose.com/buy).

**Q: Do I need a temporary license for testing purposes?**  
A: Yes, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
これで **データディレクトリの設定**、**新しいアクティビティの作成**、カスタム属性の定義とタスクへの付与、そして **MPP としてプロジェクトを保存** しながら **テーブルフィールドのカスタマイズ** を行う方法が習得できました。これらの手順により、プロジェクトデータの表示方法を完全にコントロールでき、ステークホルダーのニーズに合わせた情報豊富な Gantt チャートを作成できます。

---

**最終更新日:** 2026-02-13  
**テスト環境:** Aspose.Tasks Java 24.12 (latest)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}