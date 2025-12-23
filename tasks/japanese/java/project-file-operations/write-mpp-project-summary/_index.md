---
date: 2025-12-23
description: Aspose.Tasks for Java を使用して MPP のサマリーを作成し、プロジェクトの作成者を更新する方法を学びましょう。プロジェクト情報の設定と取得が簡単に行えます。
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.TasksでMPPサマリーを作成し、プロジェクトの作成者を更新する方法
url: /ja/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TasksでMPPプロジェクトサマリーを書く

## はじめに
このチュートリアルでは、Microsoft Project ファイルの **MPP サマリー** 情報を作成し、Aspose.Tasks ライブラリ for Java を使用して **プロジェクトの作成者** 詳細を更新する方法を学びます。プロジェクト管理ツールを構築する場合でも、レポートを自動化する場合でも、サマリー プロパティをプログラムで制御することで時間を節約し、プロジェクト全体の一貫性を確保できます。

## クイック回答
- **“create MPP summary” とは何ですか？** Microsoft Project の「プロジェクト サマリー情報」ダイアログに表示される、作者、リビジョン、キーワードなどの高レベルのプロジェクト プロパティを設定することを意味します。  
- **どのライブラリがこれを処理しますか？** Aspose.Tasks for Java は、これらのプロパティを読み書きするためのフルエント API を提供します。  
- **ライセンスは必要ですか？** 無料トライアルは利用可能ですが、本番環境で使用するには商用ライセンスが必要です。  
- **ファイル保存後に作者を変更できますか？** はい、`project.set(Prj.AUTHOR, "New Author")` を呼び出して **project author を更新** し、ファイルを再保存すれば可能です。  
- **サポートされているファイル形式は何ですか？** MPP と XML (SaveFileFormat.Xml) の両方が完全にサポートされています。

## create MPP summary とは何ですか？
MPP サマリーを作成することは、プロジェクトのメタデータ（作者、リビジョン番号、キーワード、コメント、作成日、印刷日）を設定することを意味します。このメタデータは Project Summary Information レコードに格納され、Microsoft Project の **File → Info** セクションに表示されます。

## なぜ project author を更新するのか？
**project author** 情報を正確に保つことは、監査トレイル、コラボレーション、レポート作成において重要です。複数のチームメンバーが関与する場合、最新の変更を反映させたり、作業の帰属を正しく示すために **project author を更新** する必要があります。

## 前提条件
1. マシンに Java Development Kit (JDK) がインストールされていること。  
2. Aspose.Tasks for Java – ダウンロードは [here](https://releases.aspose.com/tasks/java/) から。  
3. IntelliJ IDEA、Eclipse、NetBeans などの IDE。

## パッケージのインポート
まず、必要なパッケージを Java クラスにインポートします：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## ステップ 1: プロジェクトの設定とサマリー情報の定義
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
上記のコードでは、author、revision、keywords などの **MPP サマリー** フィールドを **作成** しています。後で `project.set(Prj.AUTHOR, "New Name")` を呼び出すことで **project author を更新** することも可能です。

## ステップ 2: プロジェクトサマリー情報の保存
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
プロジェクトを保存すると、先ほど定義したすべてのサマリーデータが永続化されます。

## ステップ 3: プロジェクトサマリー情報の読み取り
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
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
このスニペットは、サマリー情報を **読み戻す** 方法を示しており、**create MPP summary** 操作が成功したことを確認できます。

## 一般的な問題と解決策
- **読み取り後に Null 値が出る:** 再読み込みする前にプロジェクトが正しく保存されたことを確認してください。ファイルパスと権限をチェックします。  
- **日付フォーマットの違い:** `project.get(Prj.CREATION_DATE)` は `java.util.Date` を返します。カスタム表示形式が必要な場合は `SimpleDateFormat` を使用してください。  
- **ライセンスが設定されていない:** 有効なライセンスがない場合、Aspose.Tasks は評価モードで動作し、透かしが埋め込まれることがあります。コードの早い段階でライセンスを登録してください。

## よくある質問
**Q: Aspose.Tasks for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Tasks for Java は他の Java ライブラリとシームレスに統合でき、プロジェクト管理機能を強化できます。

**Q: Aspose.Tasks for Java のトライアル版はありますか？**  
A: はい、[here](https://releases.aspose.com/) から無料トライアル版をダウンロードできます。

**Q: Aspose.Tasks for Java はどのくらいの頻度で更新されますか？**  
A: Aspose.Tasks for Java は、最新の Java および Microsoft Project ファイルとの互換性を保つために定期的に更新されています。

**Q: プロジェクトサマリー情報をさらにカスタマイズできますか？**  
A: もちろんです。Aspose.Tasks for Java は、特定の要件に合わせてプロジェクトサマリー情報をカスタマイズするための豊富なオプションを提供します。

**Q: Aspose.Tasks for Java のサポートはどこで受けられますか？**  
A: Aspose.Tasks コミュニティフォーラム [here](https://forum.aspose.com/c/tasks/15) でサポートを受けられます。

## 結論
このチュートリアルでは、**MPP サマリー** データの **作成**、**project author の更新**、およびそれらの変更を Aspose.Tasks for Java を使用して検証する方法を示しました。これらの手順を自動化することで、プロジェクトのメタデータを完全に制御でき、アプリケーションの堅牢性が向上し、プロジェクトレポートの精度が高まります。

---

**最終更新日:** 2025-12-23  
**テスト環境:** Aspose.Tasks for Java 24.10  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}