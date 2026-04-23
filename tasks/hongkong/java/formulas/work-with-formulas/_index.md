---
date: 2026-02-13
description: 學習如何計算日期之間的天數、建立測試專案，並在使用 Aspose.Tasks for Java 操作 Microsoft Project
  檔案時新增自訂欄位。
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 計算日期之間的天數
url: /zh-hant/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 計算日期之間的天數

## 簡介
在本教學中，您將 **計算日期之間的天數**，方法是建立測試專案、加入自訂欄位，並透過 Aspose.Tasks for Java 函式庫使用 Microsoft Project 公式。無論是產生排程、計算截止日期，或自動化報表，Aspose.Tasks 都能在不需桌面安裝的情況下以程式方式操作 Project 資料。完成本指南後，您將擁有一個可執行的範例，定義延伸屬性、為工作設定截止日期，並將專案儲存為 MPP 檔案。

## 快速答覆
- **本教學涵蓋什麼內容？** 建立測試專案、加入自訂欄位、定義延伸屬性，並使用公式設定工作任務的截止日期以計算日期之間的天數。  
- **需要哪個函式庫？** Aspose.Tasks for Java（最新版本）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買授權。  
- **可以使用哪種 IDE？** 任何支援 JDK 8+ 的 Java IDE（如 IntelliJ IDEA、Eclipse、VS Code）。  
- **實作大約需要多久？** 複製程式碼並執行，大約 10‑15 分鐘。

## 什麼是 Aspose.Tasks 中的「計算日期之間的天數」？
計算日期之間的天數是指使用 Project 公式，將一個日期欄位（例如 **Finish**）減去另一個日期欄位（例如 **Deadline**），並回傳以天數為單位的數值差異。此功能可用於追蹤排程延遲、測量緩衝時間，或產生自訂報表。

## 為什麼使用 Aspose.Tasks 計算日期之間的天數？
- **完整 API 覆蓋** – 可存取每個 Project、Task 與 Resource 的屬性。  
- **不需安裝 Office** – 可在伺服器、CI 流程與 Docker 容器上執行。  
- **跨平台** – 使用相同的 Java 程式碼即可在 Windows、Linux 與 macOS 上執行。  
- **強大的公式引擎** – 允許直接在專案檔內定義如 `[Deadline] - [Finish]` 的計算。

## 如何為工作設定截止日期
設定截止日期是計算間隔的第一步。截止日期儲存在工作任務的 `Tsk.DEADLINE` 欄位，可透過 `java.util.Calendar` 例項指派。

## 如何定義延伸屬性
延伸屬性是用來保存公式結果的自訂欄位。您只需定義一次，為其設定易讀的別名，然後附加執行日期相減的公式。

## 先決條件
在開始之前，請確保您已具備以下條件：

- **Java Development Kit (JDK) 8+** – 可從 Oracle 官方網站或 AdoptOpenJDK 下載。  
- **Aspose.Tasks for Java** – 從 [Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/) 取得最新 JAR，並加入專案的 classpath 或 Maven/Gradle 相依性中。

## 匯入套件
首先，匯入我們需要的類別：

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 逐步指南

### 步驟 1：建立帶有自訂欄位的測試專案
我們首先 **建立測試專案**，並加入一個稍後將保存公式結果的自訂欄位。

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` 是一個協助方法，用於建立最小排程並註冊可供公式指派的延伸屬性。

### 步驟 2：定義延伸屬性（加入自訂欄位）
接著，我們 **定義延伸屬性**——即自訂欄位——並為其設定易讀的別名。這裡就是我們 **加入自訂欄位** 邏輯的地方。

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** 讓欄位在 Project 中易於閱讀。  
- **Formula** 計算工作任務的 *Finish* 日期與 *Deadline* 之間的天數——即 *計算日期之間的天數* 的核心。

### 步驟 3：為工作設定截止日期（新增截止日期工作與設定工作截止日期）
現在，我們透過在特定工作任務上設定 *Deadline* 屬性，**加入截止日期工作** 資料。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` 例項定義了精確的截止時間。  
- `set(Tsk.DEADLINE, …)` **設定所選工作任務的截止日期**。

### 步驟 4：儲存專案（操作 Microsoft Project 檔案）
最後，我們透過將變更寫入 MPP 檔案，**操作 Microsoft Project**。

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

您可以在 Microsoft Project 中開啟 `SaveFile.mpp`，查看自訂欄位、公式結果與截止日期在排程中的呈現。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **公式未評估** | 確保屬性的 `Formula` 字串使用正確的欄位名稱（例如 `[Deadline]`、`[Finish]`）。 |
| **找不到工作** | 確認範例中的工作 ID（`1`）是否存在；可使用 `project.getRootTask().getChildren().size()` 進行除錯。 |
| **授權例外** | 在呼叫任何 API 方法前先套用有效的 Aspose.Tasks 授權（`License license = new License(); license.setLicense("Aspose.Tasks.lic");`）。 |

## 常見問答

**Q: 我可以在其他程式語言中使用 Aspose.Tasks 嗎？**  
A: 可以，Aspose.Tasks 提供 .NET、Java 以及其他平台的 API，讓您能以自己選擇的語言 **操作 Microsoft Project** 檔案。

**Q: Aspose.Tasks 有提供免費試用嗎？**  
A: 當然有。可從 [Aspose.Tasks 下載頁面](https://releases.aspose.com/) 下載完整功能的試用版。

**Q: 我在哪裡可以找到 Aspose.Tasks 的詳細文件？**  
A: 官方文件位於 [Aspose.Tasks Java API 參考文件](https://reference.aspose.com/tasks/java/)。

**Q: 我該如何取得 Aspose.Tasks 的支援？**  
A: 前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 提問並與社群分享使用經驗。

**Q: 評估時需要臨時授權嗎？**  
A: 可取得短期測試用的臨時授權，請於此處 [申請](https://purchase.aspose.com/temporary-license/)。

---

**最後更新：** 2026-02-13  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}