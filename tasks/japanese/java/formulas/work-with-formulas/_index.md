---
date: 2026-10-05
description: Aspose.Tasks for Java を使用してテストプロジェクトを作成し、日付間の日数を計算する方法、カスタム フィールドを追加する方法、そして
  MPP ファイルを効率的に操作する方法を学びます。
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Aspose.Tasks で数式を使用する
og_description: Aspose.Tasks for Java を使用してテストプロジェクトを作成し、日付間の日数を計算します。このガイドでは、カスタム
  フィールドの追加方法、タスクの期限設定方法、そしてプロジェクトを MPP ファイルとして保存する方法を示します。
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: テストプロジェクトを作成し、日付間の日数を計算する
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: テストプロジェクトを作成し、日付間の日数を計算する
url: /ja/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# テストプロジェクトを作成し、日付間の日数を計算する

このチュートリアルでは、カスタム フィールドを追加し、拡張属性を定義し、Aspose.Tasks for Java ライブラリを介して Microsoft Project の数式を適用することで、**テストプロジェクトを作成**し、**日付間の日数を計算**します。スケジュールの生成、期限の計算、レポートの自動化が必要な場合でも、Aspose.Tasks を使用すればデスクトップ インストールなしでプログラムから Project データを操作でき、50 以上の入力・出力フォーマットに対応し、メモリ効率の高いモードで数百ページのファイルを処理できます。

## クイック回答
- **チュートリアルの内容は何ですか？** テストプロジェクトの作成方法、拡張属性の定義、タスクの期限設定、および日付間の日数を計算する数式の使用方法を示します。  
- **必要なライブラリはどれですか？** Aspose.Tasks for Java（最新バージョン）。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **どの IDE を使用できますか？** JDK 8+ をサポートする任意の Java IDE（IntelliJ IDEA、Eclipse、VS Code）です。  
- **実装にどれくらい時間がかかりますか？** コードをコピーして実行するだけで、概ね 10‑15 分です。

## Aspose.Tasks における「日付間の日数を計算する」とは何ですか？
Aspose.Tasks では、数式はタスク フィールドを参照し計算を行う文字列です。`[Deadline] - [Finish]` は、2 つの日付フィールド間の日数の数値差を返すために Aspose.Tasks が使用する数式構文です。結果は整数の日数として数値で保存され、カスタム フィールドに表示したり、さらに計算に使用したりできます。

## なぜ Aspose.Tasks を使用して日付間の日数を計算するのか？
Aspose.Tasks は、すべての Project、Task、Resource プロパティに対して **フル API カバレッジ** を提供し、Windows、Linux、macOS 上で動作し、**Microsoft Project や Office のインストールは不要**です。エンジンは、典型的なサーバー ハードウェア上で **500 件以上のタスク** を 1 秒未満で処理でき、CI パイプライン、Docker コンテナ、そして大量バッチ処理に最適です。

## タスクの期限を設定する方法
java.util.Calendar は、特定の時点を表す Java クラスです。`java.util.Calendar` の値をタスクの `Tsk.DEADLINE` フィールドに割り当てることで期限を設定します。Calendar インスタンスを作成したら、年・月・日を目的の期限に設定し、`task.set(Tsk.DEADLINE, calendar);` を呼び出します。期限はプロジェクト ファイルに保存され、`[Deadline] - [Finish]` などの数式で使用できます。

## 拡張属性の定義方法
拡張属性は、数式の結果を格納するカスタム フィールドです。一度作成し、わかりやすいエイリアスを付け、`[Deadline] - [Finish]` の式を添付すれば、すべてのタスクが自動的に間隔を計算します。`ExtendedAttribute` をインスタンス化し、Alias を設定し、数式を割り当て、プロジェクトのコレクションに追加することで作成します。

## 前提条件
開始する前に、以下が揃っていることを確認してください。

- **Java Development Kit (JDK) 8+** – Oracle のウェブサイトからダウンロードするか、OpenJDK を採用してください。  
- **Aspose.Tasks for Java** – 最新の JAR を [Aspose.Tasks for Java ダウンロードページ](https://releases.aspose.com/tasks/java/) から取得し、プロジェクトのクラスパスまたは Maven/Gradle の依存関係に追加します。

## パッケージのインポート
まず、必要なクラスをインポートします。

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## ステップバイステップ ガイド

### 手順 1: カスタム フィールド付きのテストプロジェクトを作成する
まず **テストプロジェクトを作成** し、後で数式結果を保持するカスタム フィールドを追加します。

```java
Project project = CreateTestProjectWithCustomField();
```

> *プロのコツ:* `CreateTestProjectWithCustomField()` は、最小限のスケジュールを構築し、数式割り当ての準備ができた拡張属性を登録するヘルパーメソッドです。

### 手順 2: 拡張属性を定義する（カスタム フィールドを追加）
次に、**拡張属性を定義** します（実質的にカスタム フィールドです）し、わかりやすいエイリアスを付けます。ここで **カスタム フィールドを追加** するロジックを実装します。

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** は、Project でフィールドを読みやすくします。  
- **Formula** は、タスクの *Finish* 日付と *Deadline* の間の日数を計算します – これが *日付間の日数を計算する* の核心です。

### 手順 3: タスクの期限を設定する（期限タスクを追加し、タスク期限を設定）
ここでは、特定のタスクの *Deadline* プロパティを設定して **期限タスクを追加** します。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` インスタンスは正確な期限の時点を定義します。  
- `set(Tsk.DEADLINE, …)` は、選択したタスクの **タスク期限を設定** します。

### 手順 4: プロジェクトを保存する（Microsoft Project ファイルを操作）
最後に、変更を MPP ファイルに永続化することで **Microsoft Project を操作** します。

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

`SaveFile.mpp` を Microsoft Project で開くと、カスタム フィールド、数式結果、期限がスケジュールに反映されていることが確認できます。

## よくある問題と解決策
| Issue | Solution |
|-------|----------|
| **数式が評価されない** | 属性の `Formula` 文字列が正しいフィールド名（例: `[Deadline]`、`[Finish]`）を使用していることを確認してください。 |
| **タスクが見つからない** | タスク ID（例では `1`）が存在するか確認し、`project.getRootTask().getChildren().size()` でデバッグしてください。 |
| **ライセンス例外** | API メソッドを呼び出す前に有効な Aspose.Tasks ライセンスを適用してください（`License license = new License(); license.setLicense("Aspose.Tasks.lic");`）。 |

## よくある質問

**Q: Aspose.Tasks を他のプログラミング言語で使用できますか？**  
A: はい、Aspose.Tasks は .NET、Java、その他のプラットフォーム向けに API を提供しており、好きな言語で Microsoft Project ファイルを操作できます。

**Q: Aspose.Tasks の無料トライアルはありますか？**  
A: もちろんです。完全に機能するトライアルは [Aspose.Tasks ダウンロードページ](https://releases.aspose.com/) からダウンロードできます。

**Q: Aspose.Tasks の詳細なドキュメントはどこで見つけられますか？**  
A: 公式ドキュメントは [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/) に掲載されています。

**Q: Aspose.Tasks のサポートはどのように受けられますか？**  
A: [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) にアクセスして質問したり、コミュニティと経験を共有してください。

**Q: 評価のために一時ライセンスが必要ですか？**  
A: 短期テスト用の一時ライセンスが利用可能です。[一時ライセンス申請ページ](https://purchase.aspose.com/temporary-license/) からリクエストできます。

---

**最終更新日:** 2026-10-05  
**テスト環境:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**作者:** Aspose

## 関連チュートリアル

- [MPP ファイルの作成方法 – Aspose.Tasks で空のプロジェクトを作成・保存 (MPP フォーマット)](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks for Java を使用して MS Project のプロジェクト開始日を設定する](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks を使用した Java での拡張属性の作成方法](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}