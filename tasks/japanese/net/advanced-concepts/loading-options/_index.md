---
date: 2026-03-08
description: Aspose.Tasks for .NET を使用してプロジェクト ファイルをインポートする方法を学びます。ファイル エンコーディングの指定方法や
  Microsoft Project ファイルを効率的に読み込む方法も含まれます。
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: プロジェクト ファイルのインポート – Aspose.Tasks の読み込みオプション
url: /ja/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクト ファイルのインポート – Aspose.Tasks のロード オプション

## はじめに

Aspose.Tasks for .NET は、Microsoft Project、Primavera、その他の形式から **プロジェクト ファイル** データを簡単にインポートできるようにします。パスワードで保護されたファイルを読み取る必要がある場合や、カスタムエンコーディングを設定する場合、またはパースエラーを処理する場合でも、ライブラリはロード オプションを通じて細かな制御を提供します。このチュートリアルでは、最も一般的なシナリオを順に説明し、.NET アプリケーションで **Microsoft Project ファイル** オブジェクトを自信を持って **ロード** できるようにします。

## クイック回答
- **プロジェクト ファイルをインポートする主な方法は何ですか？** `Project` コンストラクタに `LoadOptions` インスタンスを渡す方法です。  
- **パスワードで保護されたファイルを開くことはできますか？** はい—`LoadOptions` の `Password` プロパティを設定します。  
- **ファイルのエンコーディングはどう指定しますか？** `LoadOptions.Encoding` に `Encoding` オブジェクトを割り当てます。  
- **エラーハンドリングはカスタマイズできますか？** もちろんです—`LoadOptions.ErrorHandler` にデリゲートを提供します。  
- **これらのオプションは Primavera ファイルでも機能しますか？** はい、`LoadOptions` 内の `PrimaveraReadOptions` を使用します。

## 前提条件

始める前に、以下が揃っていることを確認してください：

1. **Visual Studio**（または好みの .NET IDE）。  
2. **Aspose.Tasks for .NET** – [ウェブサイト](https://releases.aspose.com/tasks/net/) からダウンロードしてください。  
3. **C#** の構文とプロジェクト構造の基本的な理解。

これで準備が整ったので、必要な名前空間をインポートしましょう。

## 名前空間のインポート

C# プロジェクトで、以下の `using` ステートメントを追加して API クラスを利用できるようにします：

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## ロード オプションを使用したプロジェクト ファイルのインポート方法

以下に、最も頻繁に使用されるロード シナリオをカバーする 4 つの実用的な例を示します。

### ステップ 1: パスワードで保護されたプロジェクトのロード

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### ステップ 2: カスタム オプションで Primavera プロジェクトをロード

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### ステップ 3: XER ファイルをインポートする際の **ファイル エンコーディングの指定**

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### ステップ 4: カスタム エラーハンドリングで Primavera プロジェクトをロード

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

これらの手順に従うことで、**プロジェクト ファイル** データを正確にインポートし、ロード プロセスをニーズに合わせて調整し、アプリケーションを堅牢に保つことができます。

## 一般的な問題とヒント

- **パスワードが間違っている** – `Password` プロパティは例外をスローします。ロード前に資格情報を確認してください。  
- **サポートされていないエンコーディング** – 指定したコードページが対象マシンに存在することを確認してください（例: `Encoding.GetEncoding(1251)` はキリル文字用に機能します）。  
- **Primavera オプションが欠如** – タスク UID を保持する必要がある場合は `PreserveUids = true` を設定してください。設定しないと重複 ID が発生する可能性があります。  
- **エラーハンドラが null を返す** – `null` を返すとパーサーは問題のある要素をスキップします。必要に応じてカスタマイズしてください。

## よくある質問

**Q: Aspose.Tasks for .NET はすべてのバージョンの Microsoft Project と互換性がありますか？**  
A: はい、幅広い Microsoft Project バージョンをサポートしているため、古い MPP ファイルから最新の形式まで、**Microsoft Project ファイル** を **ロード** できます。

**Q: Aspose.Tasks for .NET を他のサードパーティ ライブラリと統合できますか？**  
A: もちろんです。このライブラリは他の .NET パッケージとシームレスに連携し、レポーティング、UI、データアクセス フレームワークと組み合わせて使用できます。

**Q: Aspose.Tasks for .NET はドキュメントやサポートリソースを提供していますか？**  
A: はい、包括的な [documentation](https://reference.aspose.com/tasks/net/) を参照でき、[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) からサポートを受けられます。

**Q: Aspose.Tasks for .NET のライセンスオプションはありますか？**  
A: はい、[Aspose.Tasks website](https://purchase.aspose.com/buy) で無料トライアルや一時ライセンスを含むさまざまなライセンスオプションを確認できます。

**Q: Aspose.Tasks for .NET の更新や新機能はどのくらいの頻度でリリースされますか？**  
A: Aspose.Tasks は定期的に更新され、新機能の追加、パフォーマンスの向上、最新の Microsoft Project リリースとの互換性が保たれます。

---

**最終更新日:** 2026-03-08  
**テスト対象:** Aspose.Tasks 24.11 for .NET  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}