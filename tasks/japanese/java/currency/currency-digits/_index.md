---
date: 2026-02-10
description: Aspose.Tasks を使用して通貨値の取得方法、MS Project ファイルの読み取り、Java でのプロジェクトファイル変換を学びます。通貨の桁数を抽出するステップバイステップガイド。
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks を使用して MS Project から通貨を取得する方法
url: /ja/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用して MS Project から通貨情報を取得する方法

## はじめに
Microsoft Project ファイルから **通貨情報** を取得したいとお考えですか？この包括的なチュートリアルでは、Aspose.Tasks ライブラリ for Java を使って **ms project currency** の値を扱う方法をご紹介します。レポートツールの構築、マイグレーションユーティリティの作成、あるいは **java project file** から通貨設定を読み取るだけでも、本ガイドは *.mpp* ファイルの読み込みから通貨桁数の抽出までのすべての手順を解説します。最後まで読めば、独自のアプリケーションで ms project currency データを自在に扱えるようになります。

## クイック回答
- **MS Project ファイルを読み取るライブラリは？** Aspose.Tasks for Java。  
- **通貨桁数を取得するコードは何行？** プロジェクトをロードした後はたった 3 行です。  
- **開発時にライセンスは必要？** テスト目的なら無料トライアルで可。商用環境では正式ライセンスが必要です。  
- **対応 Java バージョンは？** Java 8 以上（Aspose.Tasks が動作する JDK であれば可）。  
- **他の Project プロパティも取得できる？** はい – Aspose.Tasks は開始日、コストレートなど、豊富な Project フィールドを提供します。

## ms project currency とは？
`ms project currency` は、Microsoft Project が金額を表示する際の小数点以下の桁数（精度）を指します。プロジェクト ファイル内では **CURRENCY_DIGITS** プロパティとして保存され、金額が整数、1 桁小数、2 桁小数などで表示されるかを決定します。

## Aspose.Tasks で ms project currency を扱うメリット
- **Microsoft Project のインストール不要** – 任意の Java 対応プラットフォームで *.mpp* ファイルを直接操作可能。  
- **強力な型安全性** – API が強く型付けされた値を返すため、パースエラーが減少します。  
- **パフォーマンス最適化** – 大規模プロジェクトのロードが高速で、必要なフィールドだけを抽出できます。  
- **クロスプラットフォーム** – Windows、Linux、macOS で変更なしに実行可能。

## 前提条件
作業を始める前に、以下を用意してください。

1. **Java 開発環境** – JDK 8 以上がインストールされ、設定済みであること。  
2. **Aspose.Tasks for Java** – 公式サイトから最新の JAR をダウンロード: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)。  
3. **基本的な Java 知識** – Java プロジェクトの作成、外部ライブラリの追加、`main` メソッドの実行に慣れていること。  

## パッケージのインポート
まず、必要なクラスをインポートします。  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 手順 1: データ ディレクトリの定義
**java project file**（`*.mpp`）が格納されているフォルダーを指定します。  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` を `project.mpp` が存在する絶対パスまたは相対パスに置き換えてください。

## 手順 2: MPP ファイルのロード  
次に、Aspose.Tasks を使用して **mpp** ファイルをロードする方法を示します。  
```java
Project project = new Project(dataDir + "project.mpp");
```
ファイル名が正確に一致しない場合、`IOException` がスローされます。

## 手順 3: 通貨桁数の取得  
プロジェクトがロードされたら、**ms project currency** の桁数はワンライナーで取得できます。  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
この呼び出しは小数点以下の桁数を表す `Integer` を返します（例: セントの場合は `2`）。結果はコンソールに出力されますが、変数に格納してさらに処理することも可能です。

## よくある問題とヒント
- **ファイルが見つからない** – `dataDir` のパスとファイル名（拡張子 `.mpp` を含む）を再確認してください。  
- **サポート外のファイル バージョン** – Aspose.Tasks は Project 2000‑2024 形式をサポートしています。古いバージョンや破損したファイルは変換が必要な場合があります。  
- **ライセンスが設定されていない** – 開発時はトライアルで動作しますが、本番環境では評価ウォーターマークを回避するために有効なライセンスを適用する必要があります。

## FAQ

**Q: Aspose.Tasks は通貨桁数以外の Project 属性も扱えますか？**  
A: はい、タスク、リソース、カスタム フィールドなど、Project ファイルのさまざまな側面を操作する豊富な機能を提供します。

**Q: Aspose.Tasks はエンタープライズ向けアプリケーションに適していますか？**  
A: もちろんです。Aspose.Tasks はエンタープライズ グレードのプロジェクト要件に応えるよう設計されており、高いパフォーマンスとスケーラビリティを備えています。

**Q: クロスプラットフォーム開発は可能ですか？**  
A: はい、Java Runtime Environment が動作する Windows、Linux、macOS で Aspose.Tasks for Java を使用できます。

**Q: 購入前に Aspose.Tasks を試せますか？**  
A: はい、[こちら](https://releases.aspose.com/) から無料トライアル版をダウンロードできます。

**Q: Aspose.Tasks のサポートはどこで受けられますか？**  
A: [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) でサポートをご利用いただけます。

## 結論
これで Aspose.Tasks for Java を使って MS Project ファイルから **通貨桁数** を取得する方法が分かりました。手順はシンプルです: プロジェクトをロードし、`project.get(Prj.CURRENCY_DIGITS)` を呼び出して結果をアプリケーションで利用します。同様のパターンで他のプロパティも取得できるので、レポートやマイグレーション ソリューションに組み込んでみてください。

---

**最終更新日:** 2026-02-10  
**テスト環境:** Aspose.Tasks for Java（執筆時点の最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}