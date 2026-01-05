---
date: 2026-01-05
description: Aspose.Tasks for Java を使用してプロジェクトの開始日を設定し、MS Project XML を保存する方法を学びましょう。Java
  開発者向けのステップバイステップガイドです。
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Javaでプロジェクト開始日を設定する
url: /ja/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用したプロジェクト開始日の設定

## はじめに
このチュートリアルでは、Microsoft Project ファイルの **プロジェクト開始日を設定**し、Aspose.Tasks ライブラリ for Java を使用して **MS Project XML を保存**する方法を学びます。レポート パイプラインの自動化やカスタム プロジェクト管理ツールの構築など、これらのタスクをマスターすれば、時間を節約でき、手作業によるエラーを排除できます。

## クイック回答
- **開始日を設定する主なメソッドは何ですか？** `project.set(Prj.START_DATE, …)` を使用します。  
- **ファイルをエクスポートする際の形式は？** `SaveFileFormat.Xml` で XML として保存します。  
- **この操作にライセンスは必要ですか？** トライアルでも動作しますが、フル ライセンスを取得すると透かしが除去されます。  
- **タスク作成後に開始日を変更できますか？** はい、タスクを追加する前にプロジェクト プロパティを更新すれば変更可能です。  
- **すべての MS Project バージョンと互換性がありますか？** Aspose.Tasks は XML、MPP など多数の形式をサポートしています。

## 「プロジェクト開始日の設定」とは？
プロジェクト開始日を設定すると、すべてのタスク スケジューリング計算が開始される基準カレンダーが決まります。信頼性の高いプロジェクト スケジュールをプログラムで構築する第一歩です。

## なぜ Aspose.Tasks for Java を選ぶのか？
Aspose.Tasks は純粋な Java API を提供し、Microsoft Project のインストールが不要で、あらゆるプラットフォームで動作します。プロジェクト データの作成、変更、エクスポートを高速に行えるため、サーバー側の自動化に最適です。

## 前提条件
1. **Java Development Kit (JDK)** – 任意の最新 JDK バージョン。  
2. **Aspose.Tasks for Java** – [こちら](https://releases.aspose.com/tasks/java/) からダウンロード。  
3. **IDE** – IntelliJ IDEA、Eclipse、またはお好みの Java IDE。

## パッケージのインポート
まず、必要なクラスをインポートします。

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### 手順 1: データ ディレクトリの設定
生成されたファイルを保存する場所を定義します。

```java
String dataDir = "Your Data Directory";
```

### 手順 2: Project インスタンスの作成
新しい空のプロジェクトをインスタンス化します。

```java
Project project = new Project();
```

### 手順 3: プロジェクト情報プロパティの設定
ここで **プロジェクト開始日** と関連するスケジュール プロパティを設定します。

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 手順 4: MS Project XML の保存
設定したプロジェクトを XML ファイルとしてエクスポートします。

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## よくある問題と対策
- **日付形式が正しくない:** `java.util.Calendar` を使用し、代入前に `getTime()` を呼び出すことを確認してください。  
- **ファイルが保存されない:** `dataDir` が既存の書き込み可能なフォルダーを指しているか確認してください。  
- **ライセンス警告:** トライアル版は透かしが付加されます。有効なライセンスを適用すれば除去できます。

## FAQ

### Q: Aspose.Tasks for Java で MS Project ファイルを読み取れますか？  
**A:** はい、Aspose.Tasks for Java は MS Project ファイルの読み取りと書き込みの両方に対応した強力な機能を提供します。

### Q: Aspose.Tasks for Java はさまざまなバージョンの MS Project と互換性がありますか？  
**A:** もちろんです。Aspose.Tasks for Java は多数の MS Project フォーマットをサポートしており、広範な互換性を実現しています。

### Q: Aspose.Tasks for Java のトライアル版には制限がありますか？  
**A:** トライアル版ではライブラリを試用できますが、出力ファイルに透かしが付加されます。

### Q: Aspose.Tasks for Java のサポートはどこで受けられますか？  
**A:** Aspose.Tasks コミュニティ フォーラム [here](https://forum.aspose.com/c/tasks/15) で支援を受けられます。

### Q: Aspose.Tasks for Java の一時ライセンスは購入できますか？  
**A:** はい、短期利用向けの一時ライセンスが用意されています。取得は [here](https://purchase.aspose.com/temporary-license/) から。

### Q: XML 形式で保存するとカスタム フィールドは保持されますか？  
**A:** はい、`SaveFileFormat.Xml` で保存すると、すべてのカスタム属性と拡張フィールドが保持されます。

### Q: タスクを追加した後でも開始日を変更できますか？  
**A:** 保存前であればいつでも開始日を更新できます。再度 `project.set(Prj.START_DATE, …)` を呼び出してください。

---

**最終更新日:** 2026-01-05  
**テスト環境:** Aspose.Tasks for Java 24.12  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}