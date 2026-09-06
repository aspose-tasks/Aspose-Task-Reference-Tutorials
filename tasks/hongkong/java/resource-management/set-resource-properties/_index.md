---
date: 2026-08-24
description: 了解如何使用 Aspose.Tasks for Java 為 MS Project 添加資源、設定標準費率及其他資源屬性，並有效管理資源。
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: 在 Aspose.Tasks 中設定資源屬性
og_description: 使用 Aspose.Tasks for Java 為 MS Project 添加資源並設定標準費率。了解先決條件、逐步程式碼示例及故障排除技巧，快速上手。
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: 使用 Aspose.Tasks (Java) 為 MS Project 添加資源並設定費率
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: 如何使用 Aspose.Tasks 為 MS Project 添加資源
url: /zh-hant/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中新增資源 ms project 並設定費率

## 介紹
如果您正在開發需要讀寫 Microsoft Project 檔案的 Java 應用程式，**add resource ms project** 並設定其標準費率是一項常見但重要的工作。在本指南中，您將了解如何建立 `Project` 物件、加入資源，並使用 Aspose.Tasks for Java 設定標準與加班費率。完成後，您即可自動化成本計算，並在不需安裝 Microsoft Project 的情況下保持專案排程為最新狀態。

## 快速解答
- **哪個類別代表 Project 檔案？** `Project`
- **哪個呼叫會新增資源？** `project.getResources().add()`
- **如何設定標準費率？** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **生產環境是否需要授權？** 是，您必須載入有效的 Aspose.Tasks 授權。
- **支援哪些 Java 版本？** Java 8 及以上（建議使用 Java 17 以上）。

## 什麼是「設定標準費率」？
*設定標準費率* 操作會為資源指派預設的每小時成本。此費率供專案經理計算勞務支出、產生成本報表與預算預測，確保成本計算反映每個資源在整個專案生命週期中執行工作的預期價格。

## 為何使用 Aspose.Tasks 設定費率？
Aspose.Tasks 能處理 **超過 50 種輸入與輸出格式**，包括 MPP、MPX、XML 與 Primavera 檔案，且可在不將整個檔案載入記憶體的情況下處理數百頁的專案。這讓 Windows、Linux 或 macOS 伺服器上的高吞吐量批次處理成為可能，在一般自動化情境下可減少高達 90 % 的人工工作。

## 前置條件
在開始之前，請確保以下項目已備妥：

### Java 開發環境設定
1. 安裝 JDK 8 或更新版本。您可從 [Oracle 網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載。  
2. 選擇 IntelliJ IDEA、Eclipse 或 NetBeans 等 IDE，並將其設定為 Java 開發環境。

### Aspose.Tasks for Java 安裝
1. 從 [下載頁面](https://releases.aspose.com/tasks/java/) 下載最新的 Aspose.Tasks for Java 套件。  
2. 將 JAR 檔案加入專案的 classpath，或依產品文件說明宣告 Maven/Gradle 相依性。

## 匯入套件
匯入您需要的核心 Aspose.Tasks 類別。此步驟可讓您存取稍後會用到的 `Project`、`Resource` 與 `Rsc` 類型。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## 步驟 1：建立專案物件
`Project` 類別是代表整個 MS Project 檔案於記憶體中的最高層級物件。實例化它會產生一個空白專案，您可以在其中加入工作、資源與其他資料。

```java
Project project = new Project();
```

## 步驟 2：加入資源（add resource ms project）
`Resource` 類別模擬單一專案資源，例如人員、設備或材料。透過 `project.getResources().add()` 加入資源會回傳一個非 null 的 `Resource` 實例，供您設定屬性。

```java
Resource rsc = project.getResources().add("Rsc");
```

## 步驟 3：設定資源屬性（how to set rates）
`Rsc` 列舉包含資源欄位的常數，如 `STANDARD_RATE` 與 `OVERTIME_RATE`。  
您可透過在 `Resource` 物件上呼叫 `set`，並傳入相對應的 `Rsc` 列舉值，來設定標準與加班費率。費率以 `BigDecimal` 儲存，以保留金額精度。

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方式 |
|------|----------|----------|
| `set` 時拋出 `NullPointerException` | 資源未正確加入。 | 確保 `project.getResources().add()` 回傳非 null 的 `Resource`。 |
| 儲存的檔案中費率顯示為 0 | 使用 `int` 而非 `BigDecimal`。 | 金額值請始終使用 `BigDecimal.valueOf()`。 |
| 找不到授權 | 在建立 `Project` 前未載入授權檔案。 | 在程式啟動時載入授權（`License license = new License(); license.setLicense("Aspose.Tasks.lic");`）。 |

## 結論
現在您已了解如何 **add resource ms project**、建立 `Project` 物件，並使用 Aspose.Tasks for Java **設定標準與加班費率**。此功能讓您能自動化成本計算、產生自訂報表，並從任何 Java 應用程式完整管理 MS Project 資源。

## 常見問答
**Q: Aspose.Tasks for Java 能處理複雜的 MS Project 檔案嗎？**  
A: 是的，它支援所有主要的 Project 格式，包括包含數千個工作與資源的大型檔案，且能完整保留每個欄位而不遺失資料。

**Q: 是否提供免費試用？**  
A: 是的，您可從 [Aspose.Tasks 免費試用頁面](https://releases.aspose.com/) 取得 Aspose.Tasks for Java 的免費試用。

**Q: 在哪裡可以取得 Aspose.Tasks for Java 的支援？**  
A: 您可在 [支援論壇](https://forum.aspose.com/c/tasks/15) 尋求協助。

**Q: 如何取得評估用的臨時授權？**  
A: 可從 [臨時授權頁面](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 在哪裡可以購買授權版？**  
A: 請從 [購買頁面](https://purchase.aspose.com/buy) 購買完整授權。

---

**最後更新：** 2026-08-24  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose

## 相關教學

- [如何建立資源 – 使用 Aspose.Tasks for Java 進行資源管理](/tasks/java/resource-management/)
- [使用 Aspose.Tasks for Java 將資源加入專案](/tasks/java/resource-management/create-resources/)
- [如何在 Aspose.Tasks 中新增資源至專案並處理平衡延遲屬性](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}