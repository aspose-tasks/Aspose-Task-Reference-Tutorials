---
date: 2026-02-13
description: Aspose.Tasks for Java を使用して Microsoft Project ファイルを操作しながら、日付間の日数を計算し、テストプロジェクトを作成し、カスタム
  フィールドを追加する方法を学びます。
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java を使用して日付間の日数を計算する
url: /ja/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java で日付間の日数を計算する

## はじめに
このチュートリアルでは、テストプロジェクトを作成し、カスタム フィールドを追加し、Aspose.Tasks for Java ライブラリを使用して Microsoft Project の数式を利用することで、**日付間の日数を計算**します。スケジュールの生成、期限の算出、レポートの自動化が必要な場合でも、Aspose.Tasks を使えばデスクトップのインストールなしで Project データをプログラムから操作できます。ガイドの最後には、拡張属性を定義し、タスクの期限を設定し、プロジェクトを MPP ファイルとして保存する実行可能なサンプルが完成します。

## クイック アンサー
- **このチュートリアルで扱う内容は？** テストプロジェクトの作成、カスタム フィールドの追加、拡張属性の定義、そして日付間の日数を計算する数式を用いたタスクの期限設定。  
- **必要なライブラリは？** Aspose.Tasks for Java（最新バージョン）。  
- **ライセンスは必要ですか？** 開発目的であれば無料トライアルで動作します。製品環境ではライセンスが必要です。  
- **使用できる IDE は？** JDK 8 以上に対応した任意の Java IDE（IntelliJ IDEA、Eclipse、VS Code など）。  
- **実装にかかる時間は？** コードをコピーして実行するまで、約 10‑15 分です。

## Aspose.Tasks の「日付間の日数を計算する」とは？
日付間の日数を計算するとは、Project の数式である **[Deadline] - [Finish]** のように、ある日付フィールド（例: **Finish**）から別の日付フィールド（例: **Deadline**）を減算し、結果を日数として数値で返すことです。スケジュール遅延の把握、バッファ時間の測定、カスタム レポートの作成に役立ちます。

## Aspose.Tasks で日付間の日数を計算するメリット
- **フル API カバレッジ** – Project、Task、Resource のすべてのプロパティにアクセス可能。  
- **Office インストール不要** – サーバー、CI パイプライン、Docker コンテナ上でも動作。  
- **クロスプラットフォーム** – 同一の Java コードで Windows、Linux、macOS 上で実行可能。  
- **高機能数式エンジン** – プロジェクト ファイル内で直接 `[Deadline] - [Finish]` などの計算式を定義できる。

## タスクに期限を設定する方法
期限を設定することが、間隔を計算する最初のステップです。期限はタスクの `Tsk.DEADLINE` フィールドに格納され、`java.util.Calendar` インスタンスを使って割り当てます。

## 拡張属性を定義する方法
拡張属性は、数式の結果を保持するカスタム フィールドです。一度定義し、読みやすいエイリアスを付けたうえで、日付減算を行う数式を添付します。

## 前提条件
作業を始める前に、以下を用意してください。

- **Java Development Kit (JDK) 8+** – Oracle のサイトまたは AdoptOpenJDK からダウンロード。  
- **Aspose.Tasks for Java** – 最新の JAR を [Aspose.Tasks for Java ダウンロード ページ](https://releases.aspose.com/tasks/java/) から取得し、プロジェクトのクラスパスまたは Maven/Gradle の依存関係に追加。

## パッケージのインポート
まず、必要なクラスをインポートします。

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 手順別ガイド

### 手順 1: カスタム フィールド付きテストプロジェクトを作成
**テストプロジェクト** を作成し、後で数式結果を保持するカスタム フィールドを追加します。

```java
Project project = CreateTestProjectWithCustomField();
```

> *プロのコツ:* `CreateTestProjectWithCustomField()` は、最小限のスケジュールを構築し、数式割り当て用の拡張属性を登録するヘルパー メソッドです。

### 手順 2: 拡張属性を定義（カスタム フィールドを追加）
次に **拡張属性** を定義します。これは実質的にカスタム フィールドで、分かりやすいエイリアスを付けます。ここで **カスタム フィールド** のロジックを追加します。

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **エイリアス** は Project 内でフィールドを読みやすくします。  
- **数式** はタスクの *Finish* 日付と *Deadline* 日付の差分（日数）を計算し、*日付間の日数を計算する* の核心です。

### 手順 3: タスクに期限を設定（期限タスクの追加とタスク期限の設定）
特定のタスクに対して *Deadline* プロパティを設定し、**期限タスク** データを追加します。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` インスタンスで正確な期限時刻を定義。  
- `set(Tsk.DEADLINE, …)` で対象タスクの **期限を設定** します。

### 手順 4: プロジェクトを保存（Microsoft Project ファイルの操作）
最後に、変更を MPP ファイルとして永続化し、**Microsoft Project** を操作します。

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

`SaveFile.mpp` を Microsoft Project で開くと、カスタム フィールド、数式結果、期限がスケジュールに反映されていることが確認できます。

## よくある問題と対策
| 問題 | 対策 |
|------|------|
| **数式が評価されない** | 属性の `Formula` 文字列が正しいフィールド名（例: `[Deadline]`, `[Finish]`）を使用しているか確認してください。 |
| **タスクが見つからない** | タスク ID（例: `1`）が存在するか確認。デバッグには `project.getRootTask().getChildren().size()` を使用。 |
| **ライセンス例外が発生** | 任意の API 呼び出しの前に有効な Aspose.Tasks ライセンスを適用します（`License license = new License(); license.setLicense("Aspose.Tasks.lic");`）。 |

## FAQ

**Q: 他のプログラミング言語でも Aspose.Tasks を使えますか？**  
A: はい。Aspose.Tasks は .NET、Java、その他のプラットフォーム向け API を提供しており、好きな言語で **Microsoft Project** ファイルを操作できます。

**Q: Aspose.Tasks の無料トライアルはありますか？**  
A: あります。完全に機能するトライアル版を [Aspose.Tasks ダウンロード ページ](https://releases.aspose.com/) から取得できます。

**Q: Aspose.Tasks の詳細なドキュメントはどこにありますか？**  
A: 公式ドキュメントは [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/) に掲載されています。

**Q: Aspose.Tasks のサポートは受けられますか？**  
A: はい。質問や情報共有は [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) で行えます。

**Q: 評価用に一時ライセンスは必要ですか？**  
A: 短期テスト用の一時ライセンスが利用可能です。取得は [こちら](https://purchase.aspose.com/temporary-license/) からお願いします。

---

**最終更新日:** 2026-02-13  
**テスト環境:** Aspose.Tasks for Java 24.12（執筆時点の最新）  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}