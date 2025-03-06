---
title: Aspose.Tasks での超過時間、残存コスト、作業の監視
linktitle: Aspose.Tasks での超過時間、残存コスト、作業の監視
second_title: Aspose.Tasks Java API
description: Aspose.Tasks を使用して、残業時間、残存コスト、および Java プロジェクトでの作業を監視する方法を学びます。効果的なプロジェクト管理のための簡単なステップ。
weight: 18
url: /ja/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での超過時間、残存コスト、作業の監視

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用して、プロジェクトの超過時間、残存コスト、および作業を監視する方法を学びます。これは、プロジェクト マネージャーやチーム リーダーにとって、プロジェクトが順調に予算内に収まるようにするために非常に貴重です。
## 前提条件
始める前に、以下のものがあることを確認してください。
1. Java Development Kit (JDK): Aspose.Tasks for Java には Java SE 6 以降が必要です。
2.  Aspose.Tasks for Java ライブラリ: からライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/java/).
3. 統合開発環境 (IDE): Eclipse、IntelliJ IDEA、NetBeans などの任意の Java IDE。

## パッケージのインポート
まず、必要なパッケージを Java ファイルにインポートします。
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## ステップ 1: データ ディレクトリをセットアップする
プロジェクト ファイルが配置されるディレクトリを定義します。
```java
String dataDir = "Your Data Directory";
```
交換する`"Your Data Directory"`プロジェクト ファイルへのパスを置き換えます。
## ステップ 2: プロジェクトをロードする
インスタンス化する`Project`オブジェクトを作成し、プロジェクト ファイルをロードします。
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
交換する`"ResourceAssignmentOvertimes.mpp"`プロジェクトファイルの名前に置き換えます。
## ステップ 3: リソース割り当てを繰り返す
プロジェクト内の各リソース割り当てをループします。
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## ステップ 4: 超過勤務コストと作業時間を印刷する
各リソース割り当ての超過勤務コストと作業時間を取得して出力します。
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## ステップ 5: 残りのコストと作業を印刷する
各リソース割り当ての残りのコストと作業時間を取得して出力します。
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## ステップ 6: 残りの残業代と作業時間を印刷する
各リソース割り当ての残りの超過コストと作業時間を取得して出力します。
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## 結論
プロジェクト管理を成功させるには、超過時間、残りのコスト、およびプロジェクトの作業を監視することが重要です。 Aspose.Tasks for Java を使用すると、この情報に簡単にアクセスして追跡でき、プロジェクトがスケジュールどおりに予算内に収まるように確保できます。
## よくある質問
### Aspose.Tasks for Java を他の Java ライブラリと一緒に使用できますか?
はい、Aspose.Tasks for Java は他の Java ライブラリおよびフレームワークと互換性があります。
### Aspose.Tasks はさまざまなプロジェクト ファイル形式をサポートしていますか?
はい、Aspose.Tasks は、MPP、XML などを含むさまざまなプロジェクト ファイル形式をサポートしています。
### 試用版はありますか?
はい、以下から無料試用版をダウンロードできます。[ここ](https://releases.aspose.com/).
### 問題が発生した場合はどこでサポートを受けられますか?
 Aspose.Tasks フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tasks/15)サポートのための。
### Aspose.Tasks のライセンスを購入するにはどうすればよいですか?
からライセンスを購入できます[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
