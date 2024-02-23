---
title: Aspose.Tasks の MS プロジェクト アウトライン コード処理定義
linktitle: Aspose.Tasks でのアウトライン コード定義の処理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project のアウトライン コード定義を処理し、プロジェクト管理アプリケーションを強化する方法を学びます。
type: docs
weight: 12
url: /ja/net/outline-code-page-settings/outline-code-definitions/
---
## 導入
Microsoft Project はプロジェクトを管理するための強力なツールであり、Aspose.Tasks for .NET はプロジェクト ファイルをプログラムで操作するための包括的なサポートを提供します。プロジェクト管理の重要な側面の 1 つは、アウトライン コードを使用してタスクを整理することです。このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project のアウトライン コード定義を処理する方法を検討します。
## 前提条件
実装に入る前に、次の前提条件を満たしていることを確認してください。
### 1. Aspose.Tasks for .NET のインストール
開発環境に Aspose.Tasks for .NET がインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
### 2. C# と .NET Framework の基本的な理解
このチュートリアルでは中級レベルの C# 知識が必要となるため、C# プログラミング言語と .NET Framework についてよく理解してください。
### 3. 統合開発環境（IDE）
コーディングとデバッグのために、Visual Studio などの IDE をシステムにインストールします。
## 名前空間のインポート
コーディングを始める前に、Aspose.Tasks for .NET を操作するために必要な名前空間をインポートしましょう。
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
ここで、明確に理解できるように、提供された例を複数のステップに分けてみましょう。
## ステップ 1: プロジェクト ファイルをロードする
まず、MS Project ファイルをアプリケーションにロードする必要があります。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## ステップ 2: アウトライン コード定義を作成する
ここで、新しいアウトライン コード定義を作成しましょう。
```csharp
var outline = new OutlineCodeDefinition();
```
## ステップ 3: フィールド番号と名前を設定する
アウトラインコードのフィールド番号と名前を設定します。
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## ステップ 4: GUID およびその他のプロパティを設定する
アウトライン コードの GUID およびその他のプロパティを設定します。
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## ステップ 5: アウトライン マスクを追加する
アウトラインマスクをアウトラインコードに追加します。
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## ステップ 6: その他のプロパティを設定する
アウトライン コードの追加プロパティを設定します。
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## ステップ 7: アウトライン値を追加する
最後に、アウトラインコードにアウトライン値を追加しましょう。
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project のアウトライン コード定義を処理する方法を学習しました。ステップバイステップのガイドに従うことで、プロジェクト ファイル内のアウトライン コードをプログラムで効率的に操作できます。
## よくある質問
### Q1: Aspose.Tasks for .NET をさまざまなバージョンの MS Project ファイルで使用できますか?
A: はい、Aspose.Tasks for .NET は、MPP 形式や XML 形式など、さまざまなバージョンの MS Project ファイルをサポートしています。
### Q2: Aspose.Tasks for .NET は .NET Core と互換性がありますか?
A: はい、Aspose.Tasks for .NET は .NET Core と互換性があるため、クロスプラットフォーム アプリケーションを開発できます。
### Q3: Aspose.Tasks for .NET を使用してリソース割り当てを操作できますか?
A: はい、Aspose.Tasks for .NET は、割り当ての追加、更新、削除など、リソース割り当てを操作するための広範な機能を提供します。
### Q4: Aspose.Tasks for .NET は、MS Project ファイルからのカスタム フィールドの読み取りをサポートしていますか?
A: もちろん、Aspose.Tasks for .NET は、MS Project ファイルからのカスタム フィールド (アウトライン コードを含む) の読み取りと書き込みをサポートしています。
### Q5: Aspose.Tasks for .NET のコミュニティ フォーラムはありますか?
 A: はい、Aspose.Tasks for .NET のコミュニティ フォーラムに参加できます。[ここ](https://forum.aspose.com/c/tasks/15)質問したり、知識を共有したり、他の開発者と協力したりできます。