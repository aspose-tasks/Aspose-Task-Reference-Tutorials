---
date: 2026-03-29
description: 了解如何在 Aspose.Tasks for Java 中更改每月天數並管理其他工作日屬性。自訂每週起始日期、修改專案行事曆，並將專案儲存為
  XML。
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 工作日屬性更改每月天數
url: /zh-hant/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 工作日屬性變更每月天數

## 介紹
Aspose.Tasks for Java 讓您 **變更每月天數**，並在不需要安裝 Microsoft Project 的情況下微調其他工作日設定。無論是將專案行事曆對齊至非標準會計月份，或只是需要調整一週的起始日，本教學將帶您了解最常見的情境——取得目前的週起始日、客製化週起始日期、修改專案行事曆，並將專案儲存為 XML。

## 快速答覆
- **可以變更每月天數嗎？** 可以，於 `Project` 物件上使用 `Prj.DAYS_PER_MONTH`。  
- **如何客製化週起始日期？** 將 `Prj.WEEK_START_DAY` 設為 `DayType` 值（例如 `DayType.Monday`）。  
- **可以使用什麼格式匯出專案？** 範例使用 `SaveFileFormat.Xml` 將檔案儲存為 XML。  
- **正式環境需要授權嗎？** 需要有效的 Aspose.Tasks 授權才能在非評估部署中使用。  
- **支援哪些 IDE？** 任何 Java IDE，如 IntelliJ IDEA、Eclipse 或 NetBeans，都可使用。

## 什麼是 Aspose.Tasks 中的「變更每月天數」？
變更每月天數即是更新 `Project` 實例的 `Prj.DAYS_PER_MONTH` 屬性。此屬性告訴引擎每個月應視為多少個工作天，直接影響工作排程與成本計算。

## 為什麼要修改專案行事曆屬性？
客製化專案行事曆（例如設定不同的週起始日或調整每日分鐘數）可協助您：

- 與區域性工作週同步排程。  
- 模擬非標準工作模式（例如 4 天工作週）。  
- 為使用自訂行事曆的合約提供精確報表。

## 前置條件
- **Java Development Kit (JDK)** – 從 Oracle 下載並安裝最新的 JDK。  
- **Aspose.Tasks for Java 套件** – 從官方網站[此處](https://releases.aspose.com/tasks/java/)下載。  
- **您慣用的 IDE** – IntelliJ IDEA、Eclipse 或 NetBeans。

## 匯入套件
首先匯入必要的 Aspose.Tasks 類別：

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步驟 1：載入專案檔案
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
此程式碼會從您指定的資料夾載入現有的 Microsoft Project 檔案 (`project.mpp`)。

## 步驟 2：顯示工作日屬性
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
在此取得並列印目前的工作日設定，包括 **週起始日** 與 **每月天數**。

## 步驟 3：設定工作日屬性
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
此步驟將 **每月天數** 變更為 24，將週起始日設為 Monday，並調整每日/每週的分鐘數。示範如何以程式方式 **修改專案行事曆**。

## 步驟 4：儲存專案
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
使用 **以 XML 格式儲存專案** 的方式將修改後的專案寫入檔案，方便與其他工具整合或進行版本控制。

## 步驟 5：顯示結果
```java
System.out.println("Process completed Successfully");
```
簡單的確認訊息，表示所有操作已順利完成且未發生錯誤。

## 如何客製化週起始日期
如果貴公司採用「星期日為首」的行事曆，只需將 `DayType.Monday` 改為 `DayType.Sunday`。同樣使用 `Prj.WEEK_START_DAY` 屬性，變更相當直接。

## 如何取得週起始日
您可以在任何時點呼叫 `project.get(Prj.WEEK_START_DAY)` 來 **取得週起始日** 資訊，如步驟 2 所示。

## 如何修改專案行事曆
除了週起始日外，您亦可調整 `Prj.MINUTES_PER_DAY` 與 `Prj.MINUTES_PER_WEEK`，以符合自訂的工作時數或輪班模式。

## 常見問題與解決方案
- **DayType 值不正確** – 請確保使用 `DayType` 列舉（例如 `DayType.Monday`）。  
- **檔案路徑錯誤** – 請確認 `dataDir` 以正確的檔案分隔符結尾（`/` 或 `\`）。  
- **未設定授權** – 若出現授權警告，請在建立 `Project` 物件前先註冊 Aspose.Tasks 授權。

## 常見問答

**Q: Aspose.Tasks for Java 能處理複雜的專案結構嗎？**  
A: 能，Aspose.Tasks for Java 提供完整支援，讓您輕鬆處理複雜的專案結構。

**Q: Aspose.Tasks for Java 是否相容於不同版本的 Microsoft Project 檔案？**  
A: 當然，Aspose.Tasks for Java 支援多種版本的 Microsoft Project 檔案，確保跨平台相容性。

**Q: 我可以將 Aspose.Tasks for Java 整合到現有的 Java 應用程式中嗎？**  
A: 可以，Aspose.Tasks for Java 提供無縫整合功能，讓您在 Java 應用程式中加入強大的專案管理功能。

**Q: Aspose.Tasks for Java 有提供文件與支援嗎？**  
A: 有，您可在他們的[網站](https://releases.aspose.com/)上取得完整文件與社群支援。

**Q: 是否有免費試用版可供下載？**  
A: 有，您可從他們的[網站](https://reference.aspose.com/tasks/java/)下載 Aspose.Tasks for Java 的免費試用版，先行體驗功能再決定購買。

---

**最後更新：** 2026-03-29  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}