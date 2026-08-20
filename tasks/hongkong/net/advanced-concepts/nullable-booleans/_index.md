---
date: 2026-03-14
description: 學習如何在 Aspose.Tasks for .NET 中使用可空布林值，包括轉換可空布林值以及設定可空布林屬性。
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中使用可空布林值
url: /zh-hant/net/advanced-concepts/nullable-booleans/
weight: 21
---

 produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中使用可空布林值

在本教學中，我們將展示 **如何使用可空** 布林值，當使用 Aspose.Tasks .NET API 時。可空布林值提供三種可能的狀態——`true`、`false` 或 *未定義*——這在可能未明確指定的專案層級設定中特別方便。您將看到如何建立、轉換，以及 **設定可空布林值**，以及正確處理可空布林值如何防止排程應用程式出現意外行為。

## 快速解答
- **什麼是可空布林值？** 一種可以容納 `true`、`false` 或未定義的類型。  
- **為什麼在 Aspose.Tasks 中使用可空布林值？** 它們讓您能表示可選的專案屬性，而不必猜測預設值。  
- **如何將可空布林值轉換為一般 bool？** 使用隱式轉換或先檢查 `IsDefined`。  
- **主要的類別是什麼？** 位於 `Aspose.Tasks` 命名空間的 `NullableBool`。  
- **我需要授權嗎？** 是的，正式使用時需要有效的 Aspose.Tasks 授權。

## 什麼是可空布林值？

可空布林值（`NullableBool`）透過加入 *IsDefined* 標誌，擴充了普通的 `bool` 型別。當 `IsDefined` 為 `false` 時，該值被視為未定義，讓您能區分「false」與「未設定」。

## 為什麼在專案設定中處理可空布林值？

許多專案選項——例如 **ActualsInSync** 或 **HonorConstraints**——都是可選的。使用普通的 `bool` 會迫使您選擇 `true` 或 `false`，可能會無意間覆寫使用者的意圖。透過 **處理可空布林值**，您可以保留原始狀態，避免意外的設定變更。

## 前置條件

1. **Visual Studio**（或任何相容 .NET 的 IDE）。  
2. **Aspose.Tasks for .NET** – 從 [here](https://releases.aspose.com/tasks/net/) 下載。

## 匯入命名空間

首先，匯入所需的命名空間：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

現在讓我們一步一步走過每個範例。

## 使用 `NullableBool`

### 步驟 1：建立新的 `Project` 實例。

```csharp
var project = new Project();
```

### 步驟 2：以指定的值實例化 `NullableBool` 物件。

```csharp
var actualsInSync = new NullableBool(false, false);
```

### 步驟 3：檢查 `NullableBool` 物件的值與已定義狀態。

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### 步驟 4：在專案上 **設定可空布林值**。

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### 步驟 5：以單一值實例化另一個 `NullableBool` 物件。

```csharp
var honorConstraints = new NullableBool(true);
```

### 步驟 6：顯示 `NullableBool` 物件的字串表示。

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### 步驟 7：透過在專案中設定來使用 `NullableBool` 實例。

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## 比較 `NullableBool` 實例

### 步驟 1：實例化兩個 `NullableBool` 物件。

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### 步驟 2：檢查每個 `NullableBool` 物件的字串表示。

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### 步驟 3：隱式轉換為 `bool` 並印出結果。

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### 步驟 4：比較兩個 `NullableBool` 物件的相等性。

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## 取得 `NullableBool` 的雜湊碼

### 步驟 1：實例化兩個 `NullableBool` 物件。

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### 步驟 2：印出每個 `NullableBool` 物件的雜湊碼。

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## 常見陷阱與技巧

- **永遠不要假設可空布林值已定義。** 在使用 `Value` 前，請務必先檢查 `IsDefined`。  
- **在未檢查的情況下轉換為一般 bool**，若值未定義會拋出例外。僅在確定已定義時才使用隱式轉換。  
- **設定專案屬性時**，使用帶有 `NullableBool` 的 `Set` 方法，以在需要時保留未定義狀態。

## 常見問與答

**Q: 什麼是可空布林值？**  
A: 可空布林值可以表示 `true`、`false` 或未定義的狀態，提供三種不同的結果。

**Q: 如何安全地將可空布林值轉換為一般 bool？**  
A: 先檢查 `IsDefined`，然後使用 `Value` 屬性，或在確定已定義時依賴隱式轉換。

**Q: 為什麼在 Aspose.Tasks 中要使用可空布林值而不是普通 bool？**  
A: 它們讓您保持可選的專案設定不被改動，防止意外的覆寫。

**Q: 我可以將可空布林值設定為未定義嗎？**  
A: 可以——使用只接受已定義旗標的建構子，例如 `new NullableBool(false, false)`。

**Q: 在哪裡可以找到 Aspose.Tasks for .NET 的進一步文件？**  
A: 您可以在 [here](https://reference.aspose.com/tasks/net/) 找到詳細文件。

---

**最後更新：** 2026-03-14  
**測試環境：** Aspose.Tasks for .NET（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}