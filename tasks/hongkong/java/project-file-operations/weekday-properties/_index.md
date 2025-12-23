---
date: 2025-12-23
description: 學習如何使用 Aspose.Tasks Java 來更新專案排程、設定每週起始日、變更每月天數，並有效地自訂專案行事曆。
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Java – 管理工作日屬性
url: /zh-hant/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – 管理工作日屬性

## 簡介
Aspose.Tasks for Java (aspose tasks java) 是一個功能強大的 API，讓 Java 開發人員在不需要安裝 Microsoft Project 的情況下操作 Microsoft Project 檔案。在本教學中，您將學習如何 **載入 MPP 檔案**、**設定週起始日**、**變更每月天數**，以及**自訂專案行事曆**——這些都是更新專案排程的必要步驟。完成後，您將能以程式方式調整工作日屬性，並以所需格式儲存變更。

## 快速答覆
- **什麼是處理專案的主要類別？** `Project` 來自 Aspose.Tasks 函式庫。  
- **如何變更週起始日？** 使用 `project.set(Prj.WEEK_START_DAY, DayType.Monday)`。  
- **我可以載入現有的 .mpp 檔案嗎？** 可以——使用檔案路徑實例化 `Project`。  
- **哪個方法可將專案儲存為 XML？** `project.save(path, SaveFileFormat.Xml)`。  
- **開發時需要授權嗎？** 免費試用版可用於評估；正式環境需購買授權。

## 先決條件
在開始之前，請確保您已具備以下項目：

- **Java Development Kit (JDK)** – 已安裝最新版本。  
- **Aspose.Tasks for Java 函式庫** – 在此下載 [here](https://releases.aspose.com/tasks/java/)。  
- **IDE**（如 IntelliJ IDEA、Eclipse 或 NetBeans）。

## 匯入套件
首先，匯入必要的 Aspose.Tasks 類別：

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

現在讓我們逐步說明如何管理工作日屬性。

## 步驟 1：載入 MPP 檔案
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*此處我們 **載入現有的 .mpp 檔案**（`load mpp file`），以便檢查並修改其行事曆設定。*

## 步驟 2：顯示目前工作日屬性
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
此程式碼會印出目前的 **週起始日**、**每月天數**、**每日分鐘數** 以及 **每週分鐘數**——這些是您常需要 **自訂專案行事曆** 的核心要素。

## 步驟 3：設定新工作日屬性
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
在此步驟中，我們 **將週起始日** 設為 Monday，**將每月天數** 改為 24，並調整每日與每週的分鐘數。當您需要 **更新專案排程** 以符合非標準工作行事曆時，這些設定相當常見。

## 步驟 4：儲存已更新的專案
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
修改後的專案會儲存為 XML 檔案，方便分享或匯入其他工具。

## 步驟 5：確認操作
```java
System.out.println("Process completed Successfully");
```
簡單的主控台訊息會告訴您工作流程已順利完成，且未發生錯誤。

## 常見問題與技巧
- **檔案路徑不正確** – 請確認 `dataDir` 以斜線結尾，或使用 `Paths.get(...)` 取得跨平台的路徑。  
- **未設定授權** – 在正式環境中，於建立 `Project` 前呼叫 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`。  
- **週起始日非預期** – 請確保使用正確的 `DayType` 列舉值（例如 `DayType.Sunday`）。

## 常見問答

**Q: Aspose.Tasks for Java 能處理複雜的專案結構嗎？**  
A: 可以，Aspose.Tasks for Java 提供完整支援，能輕鬆處理複雜的專案結構。

**Q: Aspose.Tasks for Java 是否相容於不同版本的 Microsoft Project 檔案？**  
A: 絕對相容，Aspose.Tasks for Java 支援多種 Microsoft Project 檔案版本，確保跨平台相容性。

**Q: 我可以將 Aspose.Tasks for Java 整合到現有的 Java 應用程式中嗎？**  
A: 可以，Aspose.Tasks for Java 提供無縫整合功能，讓您以強大的專案管理特性增強 Java 應用程式。

**Q: Aspose.Tasks for Java 是否提供文件與支援？**  
A: 有，您可在其[網站](https://releases.aspose.com/)上取得豐富的文件與社群支援。

**Q: 是否提供 Aspose.Tasks for Java 的免費試用版？**  
A: 有，您可從其[網站](https://reference.aspose.com/tasks/java/)下載免費試用版，以在購買前體驗功能。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}