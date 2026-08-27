---
date: 2026-03-27
description: Aspose.Tasks for Java を使用して、MS Project のアウトラインコードをプログラムで取得する方法を学び、プロジェクト管理能力を向上させましょう。
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.TasksでMS Projectのアウトラインコードを取得する
url: /ja/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TasksでMS Projectアウトラインコードを取得する

## Introduction
このチュートリアルでは、Aspose.Tasks for Java を使用して **MS Project アウトラインコードを取得する方法** を学びます。MS Project のアウトラインコードは、タスク、リソース、割り当てを分類する強力な手段であり、プログラムからアクセスすることでカスタムレポート、Automation、統合ソリューションを構築できます。自分のプロジェクトにコピーできる完全なステップバイステップの例を順に解説します。

## Quick Answers
- **What does the code do?** プロジェクト ファイルを読み込み、すべてのアウトラインコード定義、そのマスク、値を出力します。  
- **Which library is required?** Aspose.Tasks for Java（最新バージョン可）。  
- **Do I need a license?** 開発目的ならトライアルで動作しますが、本番環境ではフル ライセンスが必要です。  
- **What Java version is supported?** Java 8 以上。  
- **Can I modify the codes after retrieving them?** はい。同じ API を使ってアウトラインコードの追加、編集、削除が可能です。

## What are ms project outline codes?
アウトラインコードは、プロジェクト マネージャーがデフォルトの階層構造を超えてタスクをグループ化・フィルタリングできるカスタム フィールドです。数値、文字列、あるいは組織全体で定義されたエンタープライズ カスタムコードなど、さまざまな形式が利用できます。これらのコードを読み取ることで、ダッシュボードの生成、データエクスポート、命名規則の自動適用などが可能になります。

## Why retrieve ms project outline codes with Aspose.Tasks?
- **Automation:** 手動エクスポートなしでレポート作成やワークフローのトリガーが可能。  
- **Integration:** ERP、PPM、BI ツールとアウトラインコードを同期。  
- **Customization:** コード値に基づくビジネス ルール（例：コスト配分）を適用。  
- **Cross‑platform:** Windows、Linux、macOS 上で動作し、Microsoft Project の UI に依存しません。

## How to read MPP files for outline codes?
MPP（Microsoft Project）ファイルの読み取りは、アウトラインコード抽出の第一歩です。Aspose.Tasks はファイル形式を抽象化するため、バイナリ構造を自分で解析する必要はありません。`Project` クラスが重い処理を担い、必要なデータに集中できます。

## Custom fields in MS Project
アウトラインコードは MS Project の **カスタム フィールド** の一種です。標準フィールドが日付や期間、リソースを扱うのに対し、カスタム フィールドは組織固有の情報を保存できます。Aspose.Tasks を通じてこれらにアクセスすれば、プログラムから同様の柔軟性が得られます。

## Prerequisites
開始する前に、以下の前提条件が整っていることを確認してください。

### 1. Java Development Environment
システムに Java Development Kit（JDK）がインストールされていることを確認します。Oracle の公式サイトから JDK をダウンロードしてインストールしてください。

### 2. Aspose.Tasks Library
Aspose.Tasks ライブラリをダウンロードし、Java プロジェクトに組み込みます。ライブラリは [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/) から入手できます。

## Import Packages
まず、Java コードで Aspose.Tasks の必要なパッケージをインポートします:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

次に、提供されたサンプルコードを複数のステップに分解して説明します。

## Step 1: Load the Project
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
このステップでは、指定されたファイル名を使って Microsoft Project ファイルを `Project` オブジェクトにロードします。

## Step 2: Retrieve Outline Codes
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
プロジェクト内の各アウトラインコード定義を列挙します。

## Step 3: Access Outline Code Properties
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
アウトラインコード定義の Alias、Field ID、Field Name などのプロパティを取得し、出力します。

## Step 4: Check Enterprise Custom Code
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
アウトラインコードがエンタープライズ カスタムコードかどうかを確認し、結果を表示します。

## Step 5: Display Outline Code Masks
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
アウトラインコードに関連付けられた各マスクを走査し、レベルとマスク値を出力します。

## Step 6: Display Outline Code Values
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
各アウトラインコード値を走査し、説明、Value ID、値、タイプを出力します。

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **No output** | Project file path incorrect | `projectName` が有効な `.mpp` ファイルを指しているか確認してください。 |
| **Null values** | Outline code not defined in the file | プロジェクト ファイルにアウトラインコードが実際に含まれているか（MS Project UI で確認）を確認してください。 |
| **LicenseException** | Using trial without proper activation | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` で一時またはフル ライセンスを適用してください。 |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks for Java to modify outline codes in a Project file?**  
A: はい、Aspose.Tasks for Java はアウトラインコードをプログラムから変更する API を提供しています。同じ `Project` オブジェクトを使って定義の追加、編集、削除が可能です。

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: はい、[Aspose.Tasks website](https://releases.aspose.com/) から無料トライアル版をダウンロードできます。

**Q: How can I get technical support for Aspose.Tasks for Java?**  
A: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) にアクセスし、質問を投稿することで技術サポートを受けられます。

**Q: Can I purchase a temporary license for Aspose.Tasks for Java?**  
A: はい、[purchase page](https://purchase.aspose.com/temporary-license/) から一時ライセンスを購入できます。

**Q: Where can I find the complete documentation for Aspose.Tasks for Java?**  
A: 詳細な情報は [documentation](https://reference.aspose.com/tasks/java/) を参照してください。

## Conclusion
このチュートリアルでは、Aspose.Tasks for Java を使用して **MS Project アウトラインコードを取得する方法** を学びました。示した手順に従うことで、Java アプリケーションからアウトラインコードに効果的にアクセス・操作でき、カスタムレポート、Automation、他のエンタープライズ システムとの統合といった高度なプロジェクト管理機能を実現できます。

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}