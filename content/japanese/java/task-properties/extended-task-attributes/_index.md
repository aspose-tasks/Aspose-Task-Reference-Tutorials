---
title: Aspose.Tasks の拡張タスク属性
linktitle: Aspose.Tasks の拡張タスク属性
second_title: Aspose.Tasks Java API
description: Aspose.Tasks for Java の拡張タスク属性を調べてください。ステップバイステップのガイド、よくある質問、サポート。今すぐプロジェクト管理を最適化しましょう!
type: docs
weight: 16
url: /ja/java/task-properties/extended-task-attributes/
---
## 導入
Aspose.Tasks for Java の拡張タスク属性の活用に関する包括的なガイドへようこそ。 Aspose.Tasks は、Microsoft Project ドキュメントをシームレスに操作できるようにする強力な Java ライブラリです。このチュートリアルでは、拡張タスク属性を詳しく説明し、それらを活用してプロジェクト管理機能を強化する方法を示します。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
- Java プログラミングの基本的な知識。
- マシンに Java Development Kit (JDK) がインストールされていること。
- IntelliJ や Eclipse などの統合開発環境 (IDE)。
## パッケージのインポート
まず、Aspose.Tasks プロジェクトを開始するために必要なパッケージをインポートします。
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
ここで、プロセスをガイドするために例を複数のステップに分けてみましょう。
## ステップ 1: タスクと拡張属性へのアクセス
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## ステップ 2: フィールド ID と値 GUID の取得
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## ステップ 3: さまざまな属性タイプの処理
```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```
プロジェクト内のタスクごとにこれらの手順を繰り返して、拡張タスク属性を調べて操作します。
## 結論
結論として、Aspose.Tasks for Java の拡張タスク属性を理解して利用することで、プロジェクト管理機能を大幅に向上させることができます。このガイドは、この旅を始めるための強固な基盤を提供します。
## よくある質問
### 拡張タスク属性をプログラムで変更できますか?
はい、Aspose.Tasks for Java を使用して拡張タスク属性を変更できます。詳細な手順については、ドキュメントを参照してください。
### 試用版はありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Tasks for Java のサポートはどこで見つけられますか?
サポートについては、次のサイトにアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).
### 仮免許はどうやって取得できますか?
仮免許を取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Tasks for Java のフルバージョンはどこで購入できますか?
フルバージョンを購入できます[ここ](https://purchase.aspose.com/buy).