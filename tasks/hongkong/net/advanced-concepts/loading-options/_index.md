---
title: Aspose.Tasks 中的載入選項
linktitle: Aspose.Tasks 中的載入選項
second_title: Aspose.Tasks .NET API
description: 透過逐步指導，了解如何利用 Aspose.Tasks for .NET 的強大功能來有效管理 Microsoft Project 文件。
weight: 16
url: /zh-hant/net/advanced-concepts/loading-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的載入選項

## 介紹

Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式操作 Microsoft Project 文件。無論您需要建立、讀取、寫入或轉換專案文件，Aspose.Tasks 都提供了廣泛的功能來簡化您的任務。在本教程中，我們將深入研究使用 Aspose.Tasks for .NET 的基本知識，將關鍵流程分解為簡單、可操作的步驟。

## 先決條件

在深入研究 Aspose.Tasks for .NET 之前，請確保您已設定以下先決條件：

1. Visual Studio：安裝 Visual Studio 或您選擇的任何其他 IDE。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[網站](https://releases.aspose.com/tasks/net/).
3. C# 的基本了解：熟悉 C# 程式語言基礎。

現在我們已經滿足了先決條件，讓我們探索基本的命名空間並深入了解逐步指南。

## 導入命名空間

在您的 C# 專案中，匯入必要的命名空間以存取 Aspose.Tasks 功能：

1. Aspose.Tasks：此命名空間提供用於處理專案文件的核心類別和介面。

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

現在，讓我們將不同的任務分解為逐步指南。

## 第 1 步：載入受密碼保護的項目

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    //初始化FileStream載入專案文件
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        //建立 LoadOptions 實例
        var options = new LoadOptions
        {
            Password = "password" //設定密碼
        };

        //使用指定選項載入項目
        var project = new Project(stream, options);

        //顯示項目名稱
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## 第 2 步：使用自訂選項載入 Primavera 項目

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    //建立 LoadOptions 實例
    var loadOptions = new LoadOptions();

    //配置 Primavera 閱讀選項
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, //設定項目 UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    //設定 Primavera 閱讀選項
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //使用指定選項載入 Primavera 項目
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    //顯示項目名稱
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    //對載入的項目執行進一步操作
}
```

## 步驟 3：指定文件編碼

```csharp
public void SpecifyFileEncoding()
{
    //建立 LoadOptions 實例
    LoadOptions lo = new LoadOptions();

    //從 Primavera XER 檔案開啟專案時指定編碼
    lo.Encoding = Encoding.GetEncoding(1251);

    //載入指定編碼的項目
    var project = new Project("encoding1251.xer", lo);

    //對載入的項目執行進一步操作
}
```

## 步驟 4：載入帶有錯誤處理的 Primavera 項目

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    //建立 LoadOptions 實例
    var loadOptions = new LoadOptions();

    //配置 Primavera 閱讀選項
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 //設定項目 UID
    };

    //設定 Primavera 閱讀選項
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //設定自訂錯誤處理
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    //載入具有指定選項和錯誤處理的 Primavera 項目
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    //對載入的項目執行進一步操作
}

//自訂錯誤處理方法
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    //實作自訂錯誤處理邏輯
}
```

透過執行這些步驟，您可以有效地利用 Aspose.Tasks for .NET 中的載入選項根據您的要求操作項目文件。

## 結論

在本教程中，我們探討了在 Aspose.Tasks for .NET 中使用載入選項的基礎知識。從載入受密碼保護的項目到指定自訂錯誤處理，掌握這些技術將使您能夠有效地管理 .NET 應用程式中的專案檔案。

## 常見問題解答

### Q1：Aspose.Tasks for .NET 是否與所有版本的 Microsoft Project 相容？

A1：是的，Aspose.Tasks for .NET 支援各種版本的 Microsoft Project，確保不同環境之間的相容性。

### Q2：我可以將 Aspose.Tasks for .NET 與其他第三方函式庫整合嗎？

A2：當然，Aspose.Tasks for .NET 與其他 .NET 函式庫無縫集成，提供增強的功能和靈活性。

### Q3：Aspose.Tasks for .NET 是否提供文件和支援資源？

 A3：是的，您可以參考綜合[文件](https://reference.aspose.com/tasks/net/)並透過以下方式獲得支持[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).

### 問題 4：Aspose.Tasks for .NET 有可用的授權選項嗎？

 A4：是的，您可以探索不同的授權選項，包括免費試用和臨時授權。[Aspose.Tasks 網站](https://purchase.aspose.com/buy).

### 問題 5：Aspose.Tasks for .NET 的更新和新功能發佈的頻率如何？

A5：Aspose.Tasks for .NET 會定期更新和功能增強，以確保最佳效能以及與不斷發展的技術的兼容性。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
