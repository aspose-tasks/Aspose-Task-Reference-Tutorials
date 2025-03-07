---
title: 在 Aspose.Tasks 中管理專案集合
linktitle: 在 Aspose.Tasks 中管理群組集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效地管理 MS Project 集合。請遵循我們的逐步指南。
weight: 26
url: /zh-hant/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理專案集合

## 介紹
在本教學中，我們將探討如何使用 Aspose.Tasks for .NET 管理群組 MS Project 集合。管理組集合對於在專案中有效地組織和操作任務和資源至關重要。
## 先決條件
在繼續本教學之前，請確保您符合以下先決條件：
1.  Aspose.Tasks for .NET 函式庫：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[下載連結](https://releases.aspose.com/tasks/net/).
2. C# 基礎知識：熟悉 C# 程式語言基礎知識，因為本教學涉及 C# 編碼。
3. 開發環境：設定開發環境，例如 Visual Studio 或任何其他支援 .NET 開發的 IDE。

## 導入命名空間
首先，我們導入必要的命名空間，以便在 C# 程式碼中使用 Aspose.Tasks 功能。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 第 1 步：載入項目
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
此步驟涉及將 MS Project 檔案載入到 Aspose.Tasks 專案物件中，以便我們對其執行操作。
## 第 2 步：迭代任務組
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
在這裡，我們迭代專案中的任務群組，列印每個群組選單中的索引、名稱和可見性等詳細資訊。
## 第 3 步：迭代資源組
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
同樣，此步驟迭代資源組，在選單中顯示它們的索引、名稱和可見性。
## 步驟 4：清除群組並將其複製到另一個項目
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
//清除其他項目組
otherProject.TaskGroups.Clear();
//將群組複製到其他項目
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
在這裡，我們清除另一個項目的群組，然後將群組從原始項目複製到它。
## 步驟 5：新增自訂任務群組
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
在此步驟中，我們建立一個自訂任務群組，並將其新增至其他項目（如果尚不存在）。
## 第 6 步：刪除所有群組
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
最後，我們從其他項目中刪除所有群組。

## 結論
在 Aspose.Tasks for .NET 中管理群組 MS Project 集合對於有效組織和操作項目資料至關重要。透過遵循本教學中概述的步驟，您可以有效地處理專案中的任務和資源群組，從而改善整體專案管理。
## 常見問題解答
### Aspose.Tasks for .NET 是否與所有版本的 MS Project 相容？
Aspose.Tasks for .NET支援各種版本的Microsoft Project，包括2003、2007、2010、2013、2016和2019。
### 我可以使用 Aspose.Tasks for .NET 自訂群組屬性嗎？
是的，您可以使用 Aspose.Tasks for .NET 自訂群組屬性，例如名稱和可見性。
### Aspose.Tasks for .NET 是否提供跨平台相容性？
Aspose.Tasks for .NET 主要針對 .NET 框架，但它可以用於 .NET Core 和 .NET Standard 的跨平台場景。
### 如何獲得 Aspose.Tasks for .NET 支援？
您可以透過以下方式獲得對 Aspose.Tasks for .NET 的支持[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for .NET 有沒有試用版？
是的，您可以從以下位置下載 Aspose.Tasks for .NET 的免費試用版：[網站](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
