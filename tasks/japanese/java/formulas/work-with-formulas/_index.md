---
title: Aspose.Tasks for Java を使用した MS Project の数式
linktitle: Aspose.Tasks での数式の操作
second_title: Aspose.Tasks Java API
description: Aspose.Tasks ライブラリを使用して Java で MS Project ファイルを操作する方法を学びます。属性を簡単に作成、変更、計算できます。
weight: 11
url: /ja/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java を使用した MS Project の数式

## 導入
このチュートリアルでは、Aspose.Tasks for Java を使用した MS Project Formulas の操作について詳しく説明します。 Aspose.Tasks は、開発者が Microsoft Project ファイルをプログラムで操作できるようにする強力なライブラリです。その広範な機能により、Java アプリケーションでプロジェクト ファイルを簡単に作成、読み取り、変更、変換できます。
## 前提条件
始める前に、次の前提条件が設定されていることを確認してください。
### Java開発環境
システムに Java Development Kit (JDK) がインストールされていることを確認してください。 Oracle Web サイトから最新の JDK をダウンロードしてインストールできます。
### Aspose.Task ライブラリ
Aspose.Tasks ライブラリを Java プロジェクトに追加する必要があります。ライブラリはからダウンロードできます。[Aspose.Tasks for Java のダウンロード ページ](https://releases.aspose.com/tasks/java/)そしてそれをプロジェクトの依存関係に含めます。

## パッケージのインポート
例に入る前に、必要なパッケージを Java コードにインポートします。
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

提供された例を複数のステップに分けてみましょう。
## ステップ 1: カスタム フィールドを使用してテスト プロジェクトを作成する
```java
Project project = CreateTestProjectWithCustomField();
```
まず、カスタム フィールドを使用してテスト プロジェクトを作成します。`CreateTestProjectWithCustomField()`方法。このメソッドは、新しく作成されたプロジェクトを表す Project オブジェクトを返します。
## ステップ 2: 拡張属性定義を定義する
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
プロジェクトから拡張属性定義を取得し、そのエイリアスと式を設定します。この例では、終了日から締め切りまでの日数を計算する属性を定義しています。
## ステップ 3: タスクの期限を設定する
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Calendar オブジェクトを作成し、期限日を設定します。次に、プロジェクトからタスクを取得し、Calendar オブジェクトを使用して期限を設定します。
## ステップ 4: プロジェクトを保存する
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
最後に、指定した名前と形式でプロジェクトをファイルに保存します。この場合、MPP ファイルとして保存します。

## 結論
このチュートリアルでは、Aspose.Tasks for Java を使用して MS Project の数式を操作する方法を学びました。これらの手順に従うことで、プロジェクト ファイルをプログラムで効果的に操作し、カスタム フィールドを追加したり、数式に基づいて属性を計算したりすることができます。

## よくある質問
### Q: Aspose.Tasks を他のプログラミング言語で使用できますか?
A: はい、Aspose.Tasks は Java、.NET などを含むさまざまなプログラミング言語をサポートしています。
### Q: Aspose.Tasks に利用できる無料トライアルはありますか?
 A: はい、Aspose.Tasks の無料トライアルを次のサイトからダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks のドキュメントはどこで見つけられますか?
 A: Aspose.Tasks のドキュメントを見つけることができます。[ここ](https://reference.aspose.com/tasks/java/).
### Q: Aspose.Tasks のサポートを受けるにはどうすればよいですか?
 A: サポートが必要な場合は、次のサイトにアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks を使用するには一時ライセンスが必要ですか?
A: 追加機能が必要な場合は、次のサイトから一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
