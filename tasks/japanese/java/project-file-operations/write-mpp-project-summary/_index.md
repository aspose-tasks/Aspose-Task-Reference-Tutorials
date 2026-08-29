---
date: 2026-03-29
description: Aspose.Tasks for Java を使用して、MPP プロジェクトでキーワードと作成日を設定する方法を学びましょう。コード例付きのステップバイステップガイド。
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用した MPP プロジェクトサマリーでキーワードを設定する方法
url: /ja/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP プロジェクト サマリーでキーワードを設定する方法 (Aspose.Tasks 使用)

## はじめに
このチュートリアルでは、Aspose.Tasks for Java を使用して MPP プロジェクト ファイルのキーワードやその他のサマリー情報を設定する方法を学びます。作成者情報、リビジョン番号、カスタム作成日などを埋め込む必要がある場合でも、このガイドは実行可能なコードとともに正確な手順を示します。最後には、キーワードの設定、作成日（java）の設定、そしてファイルからデータを取得できるようになります。

## クイック回答
- **使用されているライブラリは何ですか？** Aspose.Tasks for Java  
- **主な目的は？** MPP ファイルにキーワード、作成者情報、作成日を設定すること  
- **コードステップはいくつですか？** 3 つのシンプルなコードブロック（初期化、保存、読み取り）  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です  
- **サポートされている Java バージョンは？** Java 8 以上  

## MPP ファイルで「キーワードを設定する方法」とは何ですか？
キーワードは Microsoft Project (MPP) ファイル内に保存されるメタデータ フィールドです。プロジェクトを分類したり、迅速な検索を可能にしたり、下流ツール向けのコンテキスト情報を提供したりします。Aspose.Tasks は `Prj.KEYWORDS` プロパティを公開しており、プログラムからこの値を書き込んだり更新したりするのが簡単です。

## キーワードと作成日を設定するために Aspose.Tasks for Java を使用する理由
* **完全な .MPP 互換性** – Project 2007‑2023 のすべての形式に対応。  
* **COM や Office のインストール不要** – 純粋な Java 実装で、サーバーサイド環境に最適。  
* **リッチ API** – キーワードだけでなく、作成者、リビジョン、コメント、日付も一括で設定可能。  
* **パフォーマンス最適化** – 大規模プロジェクト ファイルでも高速な読み書きが実現。  

## 前提条件
開始する前に以下を確認してください：
1. **Java Development Kit (JDK)** – JDK 8 以上がインストールされていること。  
2. **Aspose.Tasks for Java** – 最新の JAR を [here](https://releases.aspose.com/tasks/java/) からダウンロード。  
3. **IDE** – IntelliJ IDEA、Eclipse、NetBeans、またはお好みのエディタ。

## パッケージのインポート
まず、必要なクラスをインポートします。このインポートにより、`Project` オブジェクト、サマリー フィールド用の `Prj` 列挙型、保存形式を指定する `SaveFileFormat` 列挙型にアクセスできます。

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## ステップ 1: プロジェクトの設定とサマリー情報の定義
`Project` インスタンスを作成し、`set` メソッドを使用して目的のメタデータを書き込みます。`Calendar` オブジェクトを使って **キーワードの設定** と **作成日（java）の設定** を行う様子をご覧ください。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## ステップ 2: プロジェクト サマリー情報の保存
フィールドに値を設定したら、変更を永続化します。ここでは検証しやすいように XML 形式で保存していますが、MPP 形式で保存することも可能です。

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## ステップ 3: プロジェクト サマリー情報の読み取り
メタデータが正しく書き込まれたことを確認するため、ファイルを再読み込みし、各プロパティを取得します。このステップで **キーワードを設定する方法** がエンドツーエンドで機能することを実証します。

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## 一般的な問題と解決策
| 問題 | 発生原因 | 対策 |
|-------|----------------|-----|
| **NullPointerException が `project.get(Prj.CREATION_DATE)` で発生** | 保存する前にカレンダーが設定されていませんでした。 | `save()` の前に `project.set(Prj.CREATION_DATE, cal.getTime())` を呼び出してください。 |
| **Microsoft Project の UI にキーワードが表示されない** | ファイルが XML として保存され、Project で直接開かれたためです。 | MPP (`SaveFileFormat.MPP`) に保存し直すか、Project の *Import* 機能で XML を開いてください。 |
| **タイムゾーンによる日付値のずれ** | Java の `Date` はタイムゾーン情報を含んでいます。 | UTC 日付が必要な場合は `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` を使用してください。 |

## よくある質問

**Q: Aspose.Tasks for Java を他の Java ライブラリと併用できますか？**  
**A:** はい、Aspose.Tasks for Java は他の Java ライブラリとシームレスに統合でき、プロジェクト管理機能を強化できます。

**Q: Aspose.Tasks for Java のトライアル版はありますか？**  
**A:** はい、[here](https://releases.aspose.com/) から無料トライアル版をダウンロードできます。

**Q: Aspose.Tasks for Java はどのくらいの頻度で更新されますか？**  
**A:** Aspose.Tasks for Java は定期的に更新され、最新の Java および Microsoft Project ファイルとの互換性が保たれます。

**Q: プロジェクト サマリー情報をさらにカスタマイズできますか？**  
**A:** もちろん、Aspose.Tasks for Java はプロジェクト サマリー情報を特定の要件に合わせて幅広くカスタマイズするオプションを提供します。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
**A:** Aspose.Tasks コミュニティフォーラム [here](https://forum.aspose.com/c/tasks/15) でサポートを受けられます。

---

**最終更新日:** 2026-03-29  
**テスト環境:** Aspose.Tasks for Java 24.11 (執筆時点での最新バージョン)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}