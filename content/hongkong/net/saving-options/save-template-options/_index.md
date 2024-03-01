---
title: 使用 Aspose.Tasks 將 MS 專案檔案另存為模板
linktitle: 儲存 Aspose.Tasks 的範本選項
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 將 Microsoft Project 檔案儲存為範本。自訂範本設定以簡化專案管理。
type: docs
weight: 18
url: /zh-hant/net/saving-options/save-template-options/
---
## 介紹
在本教學中，我們將逐步介紹使用 Aspose.Tasks for .NET 儲存範本的過程。模板對於標準化項目結構和設定以供將來使用非常有用。我們將示範如何將項目另存為模板，並在此過程中調整其屬性。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1.  Aspose.Tasks for .NET 函式庫：確保您已安裝 Aspose.Tasks for .NET 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
2. C# 程式設計知識：需要具備 C# 程式設計基礎知識才能理解和實作所提供的程式碼片段。
3. Microsoft Project 檔案：準備好要儲存為範本的 Microsoft Project 檔案（MPP 格式）。

## 導入命名空間
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 第 1 步：載入項目
首先，我們需要載入要另存為模板的 Microsoft Project 檔案 (.mpp)。
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 步驟2：取得專案文件信息
檢索有關載入的項目文件的信息，例如其格式。
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## 步驟 3：配置儲存範本選項
建立模板保存選項並根據您的要求配置其屬性。這些選項可讓您自訂應從範本中刪除哪些資料。
```csharp
var options = new SaveTemplateOptions
{
	//從項目模板中刪除所有固定成本
	RemoveFixedCosts = true,
	//從項目模板中刪除所有實際值
	RemoveActualValues = true,
	//從項目模板中刪除資源費率
	RemoveResourceRates = true,
	//從項目模板中刪除所有基線值
	RemoveBaselineValues = true
};
```
## 第 4 步：將項目另存為模板
將項目儲存為具有指定選項的範本。
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## 步驟5：取得範本文件信息
檢索已儲存範本文件的信息，例如其格式。
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
恭喜！您已成功使用 Aspose.Tasks for .NET 儲存模板，並根據需要自訂其屬性。

## 結論
在本教學中，我們探討如何使用 Aspose.Tasks for .NET 將 Microsoft Project 檔案儲存為範本。模板對於標準化專案結構和設定、簡化未來的專案創建非常有價值。
## 常見問題解答
### Q：我可以自訂從模板中刪除哪些資料嗎？
答：是的，您可以配置「儲存範本選項」來刪除特定數據，例如固定成本、實際值、資源費率和基準值。
### Q：Aspose.Tasks for .NET 是否與所有版本的 Microsoft Project 相容？
答：Aspose.Tasks for .NET 提供與 Microsoft Project 各個版本的廣泛相容性，確保無縫整合和功能。
### Q：我可以將範本應用到現有專案嗎？
答：是的，您可以透過載入範本文件並根據需要將其與目前項目合併來將範本套用到現有項目。
### Q：Aspose.Tasks for .NET 支援跨平台開發嗎？
答：Aspose.Tasks for .NET 主要是為 Windows 平台上執行的 .NET 框架應用程式設計的。
### Q：Aspose.Tasks for .NET 是否提供技術支援？
答：是的，您可以向 Aspose.Tasks 社群尋求技術協助和指導[論壇](https://forum.aspose.com/c/tasks/15)或直接聯絡他們的支援團隊。