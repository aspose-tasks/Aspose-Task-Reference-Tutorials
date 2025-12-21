---
date: 2025-12-21
description: 了解如何將專案儲存為範本、將 MPP 匯出為 CSV，以及使用 Aspose.Tasks for Java 將 MPP 轉換為文字。
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 將專案另存為範本、CSV 與文字檔
url: /zh-hant/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspise.Tasks 將專案另存為範本、CSV 與文字

## 簡介
在本教學中，您將了解 **如何將專案另存為範本**，以及如何使用 Aspose.Tasks for Java 將 Microsoft Project (MPP) 檔案匯出為 CSV 與純文字格式。無論您是需要建立可重複使用的專案範本、產生 CSV 報表以供分析，或是產出簡易文字擷取以進行整合，這些步驟都能快速且有效地指引您完成整個流程。

## 快速答覆
- **我可以將 MPP 匯出為 CSV 嗎？** 是的 – 使用 `project.save(..., SaveFileFormat.CSV)`。  
- **如何匯出文字？** 使用 `SaveFileFormat.TEXT` 進行儲存。  
- **「將專案另存為範本」的作用是什麼？** 它會產生一個 `.mpt` 檔案，會移除實際的開始/結束日期與基線資料，供日後重複使用。  
- **我需要授權嗎？** 提供試用版；正式環境需購買商業授權。  
- **需要哪個版本的 Java？** 支援 Java 8 以上。

## 什麼是「將專案另存為範本」？
將專案另存為範本（`.mpt`）會保留專案的結構、工作階層與資源指派，同時移除實際的開始/結束日期與基線資料。此範本非常適合在多個新專案中重複使用標準的專案版面配置。

## 為什麼使用 Aspose.Tasks for Java？
Aspose.Tasks 讓您在不安裝 Microsoft Project 本身的情況下操作 Microsoft Project 檔案。它支援 **如何匯出 MPP**、**如何匯出文字** 以及 **將 MPP 轉換為 CSV**，全部以純 Java 程式碼完成，非常適合伺服器端自動化、CI 流程或桌面工具。

## 先決條件
在開始之前，請確保您已具備以下條件：

1. 已安裝 Java Development Kit (JDK) 8 或更新版本。  
2. 已將 Aspose.Tasks for Java 函式庫加入您的專案。可從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. 具備 Java 語法的基本認識，以及 Maven/Gradle 專案設定的經驗。

## 匯入套件
首先，在您的 Java 原始檔案中匯入所需的類別：

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## 將專案另存為 CSV（將 MPP 匯出為 CSV）
將 MPP 檔案匯出為 CSV 可方便於 Excel 或 BI 工具進行資料分析。

### 步驟 1：載入專案
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步驟 2：另存為 CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## 將專案另存為文字（如何匯出文字）
如果您需要任務、資源或指派的純文字表示，請將專案儲存為文字檔案。

### 步驟 1：載入專案
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步驟 2：另存為文字
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## 將專案另存為範本（建立 Java 專案範本）
建立可重複使用的範本會移除實際日期與基線，留下乾淨的骨架供新專案使用。

### 步驟 1：載入專案
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步驟 2：設定範本選項
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### 步驟 3：另存為範本
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## 常見問題與技巧
- **找不到檔案：** 請確認 `YourProject.mpp` 的路徑正確，或使用絕對路徑。  
- **授權例外：** 若未提供有效授權，函式庫會以評估模式執行，可能會加上浮水印。請在程式碼中盡早載入授權（`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`）。  
- **大型專案：** 若處理極大的 MPP 檔案，建議增加 JVM 堆積大小（例如 `-Xmx2g`），以避免 `OutOfMemoryError`。

## 結論
我們已說明 **如何將專案另存為範本**，以及如何使用 Aspose.Tasks for Java **將 MPP 匯出為 CSV** 與 **將 MPP 轉換為文字**。這些功能讓您能自動化專案資料處理、產生可重複使用的範本，並將專案資訊整合至其他系統，全部不需安裝 Microsoft Project。

## 常見問答
### Q: Aspose.Tasks for Java 能處理複雜的專案檔案嗎？
A: 當然可以！Aspose.Tasks for Java 能輕鬆處理不同複雜度的專案，並提供對 Microsoft Project 檔案格式的完整支援。  
### Q: 是否提供 Aspose.Tasks for Java 的試用版？
A: 是的，您可從 [here](https://releases.aspose.com/) 取得 Aspose.Tasks for Java 的免費試用版。  
### Q: 我可以在哪裡取得 Aspose.Tasks for Java 的支援？
A: 您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 尋求任何關於 Aspose.Tasks for Java 的協助或疑問。  
### Q: 我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
A: 是的，您可從 [here](https://purchase.aspose.com/temporary-license/) 購買臨時授權，以評估此函式庫的完整功能。  
### Q: Aspose.Tasks for Java 是否相容於不同作業系統？
A: 是的，Aspose.Tasks for Java 相容於多種作業系統，包括 Windows、macOS 與 Linux。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

---