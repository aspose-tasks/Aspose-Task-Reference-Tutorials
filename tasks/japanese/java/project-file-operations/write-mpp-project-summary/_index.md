---
title: MPP プロジェクトの概要を Aspose.Tasks に書き込む
linktitle: MPP プロジェクトの概要を Aspose.Tasks に書き込む
second_title: Aspose.Tasks Java API
description: Aspose.Tasks を使用して Java で MPP プロジェクトの概要を作成する方法を学びます。プロジェクト情報を簡単に設定および取得できます。
weight: 27
url: /ja/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP プロジェクトの概要を Aspose.Tasks に書き込む

## 導入
このチュートリアルでは、Aspose.Tasks for Java を利用して MPP プロジェクトの概要を作成する方法を学びます。 Aspose.Tasks は、Microsoft Project ファイルを操作するための強力な Java ライブラリです。以下に概説する手順に従うことで、このライブラリを使用してプロジェクトに関するさまざまな概要情報を設定および取得できるようになります。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。
2.  Aspose.Tasks for Java: Aspose.Tasks for Java ライブラリをダウンロードしてインストールします。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
3. 統合開発環境 (IDE): IntelliJ IDEA、Eclipse、NetBeans など、Java 開発に適した IDE を選択します。

## パッケージのインポート
まず、必要なパッケージを Java クラスにインポートします。
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## ステップ 1: プロジェクトを設定し、概要情報を定義する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Data Directory";
//プロジェクト ファイルへのパスを使用して新しい Project オブジェクトを初期化します。
Project project = new Project(dataDir + "project.mpp");
//プロジェクトに関する概要情報を設定する
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
//プロジェクトの作成日を設定する
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
//プロジェクトのキーワードを設定する
project.set(Prj.KEYWORDS, "MPP Aspose");
//プロジェクトの最終印刷日を設定する
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## ステップ 2: プロジェクトの概要情報を保存する
```java
//プロジェクトを MPP 形式で保存し直します
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
//成功メッセージを表示する
System.out.println("Process completed Successfully");
```
## ステップ 3: プロジェクトの概要情報を読む
```java
//プロジェクトの概要情報を読む
project = new Project(dataDir + "MppAspose.xml");
//プロジェクトの印刷作者
System.out.println("Author: " + project.get(Prj.AUTHOR));
//プロジェクトの最後の作成者を出力します
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
//プロジェクトのリビジョン番号を出力します
System.out.println("Revision: " + project.get(Prj.REVISION));
//プロジェクトのキーワードを印刷します
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
//プロジェクトのコメントを印刷する
System.out.println("Comments: " + project.get(Prj.COMMENTS));
//プロジェクトの作成日を印刷します
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
//プロジェクトのキーワードを出力します（再度）
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
//プロジェクトの最終印刷日を印刷する
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して MPP プロジェクトの概要を作成する方法について説明しました。これらの手順に従うことで、プロジェクト ファイルに関するさまざまな概要情報を効率的に設定および取得できます。 Aspose.Tasks は、Java アプリケーションで Microsoft Project ファイルを操作するプロセスを簡素化し、堅牢な機能と使いやすさを提供します。
## よくある質問
### Q: Aspose.Tasks for Java を他の Java ライブラリと一緒に使用できますか?
A: はい、Aspose.Tasks for Java は他の Java ライブラリとシームレスに統合して、プロジェクト管理機能を強化できます。
### Q: Aspose.Tasks for Java の試用版はありますか?
 A: はい、以下から無料試用版をダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java はどのくらいの頻度で更新されますか?
A: Aspose.Tasks for Java は、最新バージョンの Java および Microsoft Project ファイルとの互換性を確保するために定期的に更新されます。
### Q: プロジェクトの概要情報をさらにカスタマイズできますか?
A: もちろん、Aspose.Tasks for Java には、特定の要件に応じてプロジェクトの概要情報をカスタマイズするための広範なオプションが用意されています。
### Q: Aspose.Tasks for Java のサポートはどこで入手できますか?
A: Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
