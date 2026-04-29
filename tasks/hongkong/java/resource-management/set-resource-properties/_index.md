---
date: 2026-01-18
description: 學習如何使用 Aspose.Tasks for Java 在 MS Project 中設定標準費率及其他資源屬性，包括如何新增資源至 MS
  Project 以及有效管理資源。
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中設定資源的標準費率
url: /zh-hant/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中設定資源的標準費率

## Introduction
如果您正在開發需要與 Microsoft Project 檔案互動的 Java 應用程式，為資源 **設定標準費率** 是最常見的工作之一。在本教學中，您將學習如何使用 Aspose.Tasks for Java **設定標準費率** 以及其他資源屬性。完成本指南後，您將能夠建立專案物件、將資源新增至 MS Project 檔案，並自信地管理 MS Project 資源。

## Quick Answers
- **主要用於處理 Project 檔案的類別是什麼？** `Project`
- **哪個方法可新增資源？** `project.getResources().add()`
- **如何設定標準費率？** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **生產環境是否需要授權？** 是，需要有效的 Aspose.Tasks 授權。
- **支援哪個 Java 版本？** Java 8 以上（建議使用最新的 JDK）。

## What is “set standard rate”?
什麼是「設定標準費率」？

*設定標準費率* 操作會為資源指派預設的每小時成本。專案經理會使用此數值來計算人工成本、產生成本報表，並預測預算。

## Why set rates with Aspose.Tasks?
- **不需要安裝 Microsoft Project** – 可直接從 Java 操作檔案。
- **完整保真** – 所有資源欄位，包括加班與成本費率，都會被保留。
- **跨平台** – 可在 Windows、Linux 與 macOS 上執行。
- **自動化友好** – 適合批次處理或整合至 CI 流程。

## Prerequisites
在開始之前，請確保您已具備以下項目：

### Java Development Environment Setup
1. **安裝 JDK**：確保您的系統已安裝 Java Development Kit（JDK）。您可從 [Oracle 網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載。
2. **IDE 設定**：選擇如 IntelliJ IDEA、Eclipse 或 NetBeans 等整合開發環境（IDE），並在您的機器上完成設定。

### Aspose.Tasks for Java Installation
1. **下載 Aspose.Tasks for Java**：前往 [下載頁面](https://releases.aspose.com/tasks/java/) 取得最新版本的 Aspose.Tasks for Java。
2. **整合至專案**：將 Aspose.Tasks for Java 程式庫加入您的 Java 專案，作為相依性。

## Import Packages
匯入套件

為了開始，您需要將 Aspose.Tasks for Java 所需的套件匯入您的專案。此步驟可確保您能使用所需的功能。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Step 1: Create a Project Object
步驟 1：建立 Project 物件

建立 **project 物件** 是任何 MS Project 操作的第一步。它在記憶體中代表整個專案檔案。

```java
Project project = new Project();
```

## Step 2: Add a Resource (add resource ms project)
步驟 2：新增資源（add resource ms project）

現在，我們將使用 Resources 集合 **新增 MS Project 資源**。資源名稱可以是任何符合您排程的名稱。

```java
Resource rsc = project.getResources().add("Rsc");
```

## Step 3: Set Resource Properties (how to set rates)
步驟 3：設定資源屬性（how to set rates）

在此，我們 **設定標準費率**，並示範如何設定加班費率。這些費率以 `BigDecimal` 值儲存，以保留精度。

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Common Issues and Solutions
常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| `NullPointerException` 在呼叫 `set` 時 | 資源未正確新增。 | 確保 `project.getResources().add()` 回傳非 null 的 `Resource`。 |
| 儲存的檔案中費率顯示為 0 | 使用 `int` 而非 `BigDecimal`。 | 金額請始終使用 `BigDecimal.valueOf()`。 |
| 找不到授權 | 在建立 `Project` 之前未載入授權檔。 | 在程式開始時載入授權（`License license = new License(); license.setLicense("Aspose.Tasks.lic");`）。 |

## Conclusion
結論

透過上述步驟，您已學會如何 **建立 project 物件**、**新增 MS Project 資源**，以及 **設定標準費率** 與其他資源屬性。這使您能自動化成本計算、產生自訂報表，並從 Java 完全管理 MS Project 資源。

## FAQ's
### Aspose.Tasks for Java 能處理複雜的 MS Project 檔案嗎？
是，Aspose.Tasks for Java 能處理各種 MS Project 檔案格式，包括具有大量任務層級的複雜檔案。

### 是否提供 Aspose.Tasks for Java 的免費試用？
是，您可從 [此處](https://releases.aspose.com/) 取得 Aspose.Tasks for Java 的免費試用。

### 哪裡可以找到 Aspose.Tasks for Java 的支援？
您可在 [支援論壇](https://forum.aspose.com/c/tasks/15) 尋求協助並參與 Aspose.Tasks for Java 相關討論。

### 如何取得 Aspose.Tasks for Java 的臨時授權？
您可從 [臨時授權頁面](https://purchase.aspose.com/temporary-license/) 取得臨時授權以供評估。

### 哪裡可以購買 Aspose.Tasks for Java 的授權版本？
您可在 [購買頁面](https://purchase.aspose.com/buy) 購買 Aspose.Tasks for Java 的授權版本。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-18  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose