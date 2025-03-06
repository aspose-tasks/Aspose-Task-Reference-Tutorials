---
title: Aspose.Tasks 中可用時段的集合
linktitle: Aspose.Tasks 中可用時段的集合
second_title: Aspose.Tasks .NET API
description: 了解如何管理 Aspose.Tasks for .NET 中資源的可用期限。本逐步教學將引導您新增、更新和刪除可用期，確保有效的專案資源規劃。
weight: 18
url: /zh-hant/net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中可用時段的集合

## 介紹

在本教程中，我們將探討如何在 Aspose.Tasks for .NET 中使用資源的可用期集合。管理可用期對於專案管理至關重要，它使我們能夠定義資源何時可用於專案內的任務。

## 先決條件

在我們開始之前，請確保您具備以下條件：

1. Visual Studio：確保您的系統上安裝了 Visual Studio。
2.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).
3. 基本了解：熟悉 C# 和 .NET 架構。

## 導入命名空間

首先，我們需要將必要的命名空間匯入到我們的專案中：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

讓我們將範例程式碼分解為多個步驟並理解每個部分：

## 第 1 步：初始化專案與資源

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

在這裡，我們載入一個專案文件並透過其 ID 取得特定資源。

## 第 2 步：清除現有的可用期限

```csharp
resource.AvailabilityPeriods.Clear();
```

我們清除與資源相關的所有現有可用期。

## 第 3 步：新增可用時段

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

我們迭代可用性週期的集合並將它們新增至資源。

## 第 4 步：插入新的可用期

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

我們為 2013 年創建一個新的可用期並將其插入集合中。

## 第 5 步：顯示可用期限

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

我們列印與資源相關的每個可用期的計數和詳細資訊。

## 步驟 6：將可用期複製到另一個資源

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

我們將可用性週期從一種資源複製到另一種資源。

## 第 7 步：更新和刪除可用期

```csharp
//更新特定期間的可用單位
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

//刪除特定時期
otherResource.AvailabilityPeriods.Remove(period2013);
```

我們更新某個時期的可用單位並從集合中刪除特定時期。

## 結論

在本教程中，我們學習如何在 Aspose.Tasks for .NET 中使用可用期集合。管理資源可用性對於有效的專案規劃和執行至關重要。

## 常見問題解答

### Q1：我可以在可用期限中新增自訂欄位嗎？

A1：不，Aspose.Tasks for .NET 中的可用期不支援自訂欄位。

### Q2：可用期限與特定任務有關嗎？

A2：不，可用期與資源相關聯，並定義資源何時可用於一般任務。

### Q3：我可以從外部來源匯入可用時段嗎？

A3：是的，您可以使用 Aspose.Tasks for .NET API 從各種資料來源匯入可用時段。

### Q4：如何處理重疊的可用期間？

A4：Aspose.Tasks for .NET 不提供內建機制來處理重疊週期。您可能需要實作自訂邏輯來管理此類場景。

### Q5：資源的可用期限有限制嗎？

A5：資源可以擁有的可用週期數沒有預先定義限制，但週期數過多可能會導致效能下降。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
