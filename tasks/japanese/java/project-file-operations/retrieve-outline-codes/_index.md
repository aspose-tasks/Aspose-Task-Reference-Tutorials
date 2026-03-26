---
date: 2025-12-20
description: Aspose.Tasks for Java を使用して、MS Project のアウトラインコードをプログラムで取得する方法を学びましょう。プロジェクト管理能力を向上させましょう。
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.TasksでMS Projectのアウトラインコードを取得する
url: /ja/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で MS Project のアウトラインコードを取得する

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用して **MS Project のアウトラインコードを取得する方法** を紹介します。MS Project のアウトラインコードは、タスク、リソース、割り当てを分類する強力な手段であり、プログラムからアクセスすることでカスタムレポートや自動化、統合ソリューションを構築できます。自分のプロジェクトにコピーして使用できる、完全なステップバイステップの例を一緒に見ていきましょう。

## クイック回答
- **このコードは何をするのですか？** プロジェクト ファイルを読み込み、すべてのアウトラインコード定義、そのマスク、値を出力します。  
- **必要なライブラリは？** Aspose.Tasks for Java（最新バージョン）。  
- **ライセンスは必要ですか？** 開発段階はトライアルで動作しますが、本番環境ではフル ライセンスが必要です。  
- **対応している Java バージョンは？** Java 8 以降。  
- **取得後にコードを変更できますか？** はい。同じ API でアウトラインコードの追加、編集、削除が可能です。

## MS Project のアウトラインコードとは？
アウトラインコードは、プロジェクト マネージャーがデフォルトの階層構造を超えてタスクをグループ化・フィルタリングできるカスタム フィールドです。数値、文字列、あるいは組織全体で定義されたエンタープライズ カスタムコードなど、さまざまな形式が利用できます。これらのコードを読み取ることで、ダッシュボードの駆動、データのエクスポート、命名規則の自動適用などが実現できます。

## なぜ Aspose.Tasks で MS Project のアウトラインコードを取得するのか？
- **自動化:** 手動エクスポートなしでレポート生成やワークフローのトリガーが可能。  
- **統合:** ERP、PPM、BI ツールとアウトラインコードを同期。  
- **カスタマイズ:** コード値に基づくビジネス ルールの適用（例: コスト配分）。  
- **クロスプラットフォーム:** Windows、Linux、macOS で動作し、Microsoft Project の UI に依存しません。

## 前提条件
開始する前に、以下の環境が整っていることを確認してください。

### 1. Java 開発環境
システムに Java Development Kit（JDK）がインストールされていることを確認します。Oracle の公式サイトから JDK をダウンロードしてインストールできます。

### 2. Aspose.Tasks ライブラリ
Aspose.Tasks ライブラリをダウンロードし、Java プロジェクトに組み込みます。ライブラリは [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/) から入手できます。

## パッケージのインポート
まず、Java コードで Aspose.Tasks の必要なパッケージをインポートします:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

次に、提供されたサンプルコードを複数のステップに分解して説明します。

## ステップ 1: プロジェクトのロード
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
このステップでは、指定したファイル名で Microsoft Project ファイルを `Project` オブジェクトにロードします。

## ステップ 2: アウトラインコードの取得
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
プロジェクト内の各アウトラインコード定義を列挙します。

## ステップ 3: アウトラインコード プロパティへのアクセス
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
エイリアス、フィールド ID、フィールド名など、アウトラインコード定義のさまざまなプロパティを取得して表示します。

## ステップ 4: エンタープライズ カスタム コードの確認
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
アウトラインコードがエンタープライズ カスタムコードかどうかをチェックし、結果を出力します。

## ステップ 5: アウトラインコード マスクの表示
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
アウトラインコードに関連付けられた各マスクを走査し、レベルとマスク値を表示します。

## ステップ 6: アウトラインコード 値の表示
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
各アウトラインコード値を走査し、説明、値 ID、実際の値、タイプを出力します。

## よくある問題と対策
| 問題 | 原因 | 対策 |
|------|------|------|
| **出力がない** | プロジェクト ファイルのパスが間違っている | `projectName` が有効な `.mpp` ファイルを指しているか確認してください。 |
| **null 値が出る** | ファイルにアウトラインコードが定義されていない | MS Project の UI で実際にアウトラインコードが存在するか確認してください。 |
| **LicenseException** | トライアル版を適切にアクティベートしていない | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` で一時またはフル ライセンスを適用してください。 |

## よくある質問

**Q: Aspose.Tasks for Java を使って Project ファイル内のアウトラインコードを変更できますか？**  
A: はい。Aspose.Tasks for Java はアウトラインコードをプログラムから変更できる API を提供しています。同じ `Project` オブジェクトを使って定義の追加、編集、削除が可能です。

**Q: Aspose.Tasks for Java のトライアル版はありますか？**  
A: はい。無料トライアル版は [Aspose.Tasks website](https://releases.aspose.com/) からダウンロードできます。

**Q: Aspose.Tasks for Java のテクニカルサポートはどこで受けられますか？**  
A: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) にアクセスし、質問を投稿してください。

**Q: Aspose.Tasks for Java の一時ライセンスを購入できますか？**  
A: はい。[purchase page](https://purchase.aspose.com/temporary-license/) から一時ライセンスを購入できます。

**Q: Aspose.Tasks for Java の完全なドキュメントはどこにありますか？**  
A: 詳細な情報は [documentation](https://reference.aspose.com/tasks/java/) を参照してください。

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して **MS Project のアウトラインコードを取得する方法** を学びました。示した手順に従うことで、Java アプリケーションからアウトラインコードにアクセス・操作でき、カスタムレポート、自動化、他のエンタープライズ システムとの統合といった高度なプロジェクト管理機能を実現できます。

---

**最終更新日:** 2025-12-20  
**テスト環境:** Aspose.Tasks for Java 24.12（執筆時点の最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}