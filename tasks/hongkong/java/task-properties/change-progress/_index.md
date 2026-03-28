---
date: 2026-01-28
description: 學習如何使用 Aspose.Tasks——功能強大的 Java 專案管理函式庫，建立 MPP 專案 Java 並修改任務進度。立即跟隨逐步指南！
linktitle: Change Progress of Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 在 Java 中建立 MPP 專案 – 更改任務進度
url: /zh-hant/java/task-properties/change-progress/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 MPP 專案（Java） – 使用 Aspose.Tasks 變更工作進度

## 介紹
在現代的 **java project management** 中，能夠 **create mpp project java** 檔案並保持工作進度即時更新，對於按時交付至關重要。Aspose.Tasks for Java 作為一個強大的 **java project management library**，提供簡潔的 API 來建立、修改以及報告 Microsoft Project 檔案。在本教學中，我們將逐步說明建立 MPP 專案、加入工作以及更新其進度的完整流程——以清晰、口語化的方式說明。

## 快速解答
- **「create mpp project java」是什麼意思？**  
  它指的是使用 Java 程式碼以程式化方式產生 Microsoft Project（.mpp）檔案。  
- **哪個函式庫可以協助完成此工作？**  
  Aspose.Tasks for Java，一個專門的 **java project management library**。  
- **設定工作進度需要多少行程式碼？**  
  在建立專案後，少於 10 行程式碼即可完成。  
- **正式環境是否需要授權？**  
  是的，需購買商業授權；亦提供免費試用版。  
- **可以在任何 Java IDE 上執行嗎？**  
  當然可以——任何支援 Java 8 以上的 IDE 都能運作。  

## 「create mpp project java」是什麼？
在 Java 中建立 MPP 專案是指使用程式碼產生 Microsoft Project 檔案（`.mpp`），該檔案可於 Microsoft Project 或其他相容工具開啟。這使得排程自動產生、大量工作建立以及與其他業務系統的整合成為可能。

## 為何將 Aspose.Tasks 作為 java project management library 使用？
- **Full API coverage** – 從專案建立到詳細的工作操作皆涵蓋。  
- **No external dependencies** – 可直接使用標準 Java，無需額外相依。  
- **Cross‑platform** – 可在 Windows、Linux 與 macOS 上執行。  
- **Rich reporting** – 可匯出為 PDF、PNG 或 HTML，供利害關係人溝通使用。  

## 先決條件
在開始之前，請確保您具備以下條件：

1. **Java Development Environment** – 已安裝並設定 JDK 8 或以上。  
2. **Aspose.Tasks for Java Library** – 從官方網站下載：[link](https://releases.aspose.com/tasks/java/)。  
3. **Document Directory** – 您機器上用於儲存產生的 `.mpp` 檔案的資料夾。  

## 匯入套件
首先，匯入您需要的 Aspose.Tasks 類別。此程式碼片段會設定環境，稍後我們會加入一個 50 % 進度的工作。

```java
import com.aspose.tasks.*;
```

## 逐步指南

### 步驟 1：設定您的 Java 專案
建立一個新的 Maven 或 Gradle 專案，並將 Aspose.Tasks JAR 加入 classpath。如此即可使用 `Project`、`Task` 以及相關類別。

### 步驟 2：定義文件目錄
指定專案檔案的儲存位置。將佔位符替換為您機器上的實際路徑。

```java
String dataDir = "Your Document Directory";
```

### 步驟 3：建立新專案（create mpp project java）
實例化 `Project` 物件。若檔案不存在，Aspose.Tasks 會建立全新的 `.mpp` 檔案。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 4：向專案新增工作（add task project）
使用根工作（root task）的子集合插入新工作。此範例展示了函式庫的 **add task project** 功能。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

### 步驟 5：設定工作進度
更新工作完成百分比。`percent` 輔助方法會將整數轉換為函式庫內部的表示方式。

```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```

### 步驟 6：顯示更新後的進度
將目前的進度印出至主控台，以驗證變更已生效。

```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```

依照上述步驟，您已成功 **在 Java 中建立 MPP 專案**、新增工作，並變更其進度——全部皆透過 Aspose.Tasks 完成。

## 常見問題與疑難排解
- **FileNotFoundException** – 確認 `dataDir` 以檔案分隔符（`/` 或 `\`）結尾，且目錄已存在。  
- **LicenseException** – 正式環境使用時，請在建立 `Project` 物件前載入 Aspose.Tasks 授權。  
- **Incorrect Percent Value** – `percent` 方法需要 0 到 100 之間的值，超出此範圍會拋出例外。  

## 常見問與答

### Aspose.Tasks 是否相容所有 Java 開發環境？
請依照文件中的安裝說明，以確保相容性。

### 我可以在專案中追蹤多個工作進度嗎？
對每個想要監控的工作重複上述步驟即可。

### 是否提供 Aspose.Tasks for Java 的試用版？
可於此處取得免費試用版 [here](https://releases.aspose.com/).

### 哪裡可以找到 Aspose.Tasks for Java 的詳細文件？
請於此處查閱完整文件 [here](https://reference.aspose.com/tasks/java/).

### 如何取得 Aspose.Tasks for Java 的臨時授權？
請前往 [temporary license page](https://purchase.aspose.com/temporary-license/).

## 其他常見問答（AI 優化）

**Q: 建立 MPP 檔案需要哪個版本的 Aspose.Tasks？**  
A: 任何近期版本（2023‑2025）皆支援 `Project` 建立；建議使用最新版本以取得錯誤修正。

**Q: 更新進度後，我可以將專案匯出為 PDF 嗎？**  
A: 可以，於設定進度後使用 `project.save("output.pdf", SaveFileFormat.PDF);`。

**Q: 是否可以批次更新多個工作的進度？**  
A: 可遍歷 `project.getRootTask().getChildren()`，為每個工作設定 `Tsk.PERCENT_COMPLETE`。

**Q: 函式庫會自動處理資源指派嗎？**  
A: 必須手動加入資源；工作進度不會自動影響資源分配。

**Q: 如何以密碼保護產生的 MPP 檔案？**  
A: 在儲存檔案前使用 `project.setPassword("yourPassword");`。

## 結論
使用 Aspose.Tasks 這個專門的 **java project management library**，在 Java 中建立 MPP 專案並管理工作進度相當簡單。掌握這些步驟後，您即可自動化排程建立、讓利害關係人即時掌握資訊，並將專案資料整合至更大的企業工作流程中。

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}