---
title: Aspose.Tasks でのリソース割り当ての停止と再開
linktitle: Aspose.Tasks でのリソース割り当ての停止と再開
second_title: Aspose.Tasks Java API
description: このステップバイステップのチュートリアルで、Aspose.Tasks for Java でリソースの割り当てを効果的に管理する方法を学びましょう。
weight: 23
url: /ja/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でのリソース割り当ての停止と再開

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用してリソース割り当てを停止および再開する方法を学習します。 Aspose.Tasks は、開発者がシステムに Microsoft Project をインストールしなくても Microsoft Project ファイルを操作できるようにする強力な Java API です。理解しやすいように、プロセスを管理可能なステップに分割していきます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Java Development Kit (JDK) がシステムにインストールされています。
-  Aspose.Tasks for Java ライブラリがダウンロードされました。からダウンロードできます[ここ](https://releases.aspose.com/tasks/java/).
- Java プログラミングの基本的な理解。
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートしましょう。
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## ステップ 1: プロジェクト ファイルをロードする
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Data Directory";
//プロジェクトファイルをロードする
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
このステップでは、プロジェクト ファイルを`Project`ファイルパスを使用してオブジェクトを指定します。
## ステップ 2: リソース割り当てを繰り返す
```java
//最小日付を定義する
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
//リソース割り当てを反復処理する
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
ここでは、最小日付を定義し、プロジェクト内の各リソース割り当ての反復を開始します。
## ステップ 3: 停止日と再開日を確認する
```java
    //停止日を確認する
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    //再開日を確認する
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
このステップでは、各リソース割り当ての停止日と再開日が最小日より前であるかどうかを確認します。一致する場合は「NA」を出力し、そうでない場合はそれぞれの日付を出力します。
## 結論
このチュートリアルでは、Aspose.Tasks for Java でリソース割り当てを停止および再開する方法を学習しました。提供された手順に従うことで、この機能を Java プロジェクトに簡単に実装できます。

## よくある質問
### Microsoft Project がインストールされていない状態で Aspose.Tasks を使用できますか?
はい、Aspose.Tasks を使用すると、システムに Microsoft Project がインストールされていなくても、Microsoft Project ファイルを操作できます。
### さらに詳しいドキュメントはどこで入手できますか?
詳細なドキュメントを見つけることができます[ここ](https://reference.aspose.com/tasks/java/).
### 無料トライアルはありますか?
はい、無料トライアルを利用できます[ここ](https://releases.aspose.com/).
### 問題が発生した場合、どうすればサポートを受けられますか?
コミュニティからサポートを受けることができます[ここ](https://forum.aspose.com/c/tasks/15).
### 一時ライセンスを購入できますか?
はい、一時ライセンスを購入できます[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
