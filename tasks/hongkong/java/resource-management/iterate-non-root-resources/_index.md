---
date: 2026-01-13
description: 學習如何使用 Aspose.Tasks for Java 在 Microsoft Project 檔案中遍歷非根資源。
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 迭代非根資源
url: /zh-hant/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 迭代非根資源

## 介紹
Aspose.Tasks for Java 是一套功能強大的函式庫，讓開發者以乾淨、物件導向的方式操作 Microsoft Project 檔案。在本教學中，你將學會 **如何迭代非根資源**，以便在不處理根佔位節點的情況下讀取、修改或分析資源資料。無論你是在建立報表工具、遷移腳本，或是自訂排程器，掌握此技巧都能讓程式碼更精確且效能更佳。

## 快速回答
- **「非根資源」是什麼意思？** 指的不是預設的「Project」佔位節點（根節點）的資源。  
- **為什麼要過濾掉根資源？** 根資源沒有實際的排程資料，會讓報表變得雜亂。  
- **哪個 Aspose.Tasks 類別提供資源集合？** `Project.getResources()`。  
- **這段程式碼需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以在 Java 17 上使用嗎？** 可以 – Aspose.Tasks 支援 Java 8 以上版本。

## 前置條件
在開始撰寫程式碼之前，請先確認已具備以下環境：

1. **Java Development Kit (JDK)** – 從 [Oracle 官方網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載並安裝最新的 JDK。  
2. **Aspose.Tasks for Java 函式庫** – 從 [下載頁面](https://releases.aspose.com/tasks/java/) 取得最新的 JAR 檔。

## 匯入套件
在 Java 專案中匯入必要的 Aspose.Tasks 類別：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 步驟 1：設定資料目錄
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為存放 `.mpp` 檔案的絕對路徑。

## 步驟 2：載入專案檔案
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
此程式會從先前指定的資料夾載入 **ResourceCosts.mpp**，並建立 `Project` 例項。

## 步驟 3：迭代非根資源
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
此迴圈會走訪專案中的每個 `Resource` 物件。`isRoot()` 檢查會跳過內建的根資源，而 `System.out.println` 會印出每個 **非根資源** 的名稱。

## 如何迭代非根資源
上述程式碼展示了核心模式：

1. 使用 `prj.getResources()` 取得完整集合。  
2. 以 `isRoot()` 篩選掉佔位根資源。  
3. 依需求存取任意資源欄位（例如 `Rsc.NAME`、`Rsc.COST`）。

你可以在此基礎上加入成本彙總、匯出 CSV，或套用自訂商業規則。

## 常見陷阱與技巧
- **空值檢查** – 某些資源的欄位可能為 `null`，呼叫 `get()` 前務必做好防護。  
- **效能** – 面對極大型專案時，考慮使用基於索引的迴圈，以避免產生中間集合。  
- **授權** – 未載入有效授權時，匯出檔案會加上浮水印；請務必在應用程式啟動時盡早激活授權。

## 結論
透過上述步驟，你現在已掌握 **如何使用 Aspose.Tasks for Java 迭代非根資源**。此技巧可協助你聚焦於實際的專案資源、清理資料抽取，並打造更可靠的專案管理解決方案。

## 常見問題
### 我可以使用 Aspose.Tasks for Java 建立新的專案檔案嗎？
可以，Aspose.Tasks 提供完整的 CRUD（建立、讀取、更新、刪除）功能，支援 MPP、MPT 與 XML 等專案格式。

### Aspose.Tasks 支援所有版本的 Microsoft Project 檔案嗎？
絕對支援。它能處理 Project 2003‑2019 的檔案，包含最新的 MPP 規格。

### Aspose.Tasks 能與 Spring 等 Java 框架相容嗎？
可以，你可以將函式庫注入 Spring Bean，或在任何標準的 Java 應用程式中使用。

### 我能使用 Aspose.Tasks 自訂專案資料欄位嗎？
當然可以。API 允許你新增、修改或刪除任務、資源與指派的自訂欄位。

### Aspose.Tasks 為開發者提供支援與文件嗎？
產品內含完整的 API 文件、程式碼範例，以及專屬的支援論壇，讓你快速取得協助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-13  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

---