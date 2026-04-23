---
date: 2026-02-20
description: 學習如何使用 Aspose.Tasks 在 Java 中計算專案成本變異並管理工作成本。請依照我們的逐步指南設定成本與控制預算。
linktitle: Manage Task Costs in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 計算專案成本差異
url: /zh-hant/java/task-properties/manage-task-cost/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 計算專案成本差異

## 簡介
在本完整教學中，您將了解 **如何計算專案成本差異**，並在 Java 應用程式中使用 Aspose.Tasks 高效管理工作成本。無論您是追蹤小型內部專案或大型企業部署，了解成本差異都有助於保持預算在軌道上，並及早發現超支情況。

## 快速解答
- **什麼是成本差異？** 計畫（固定）成本與實際（剩餘）成本之間的差異。  
- **哪個 API 方法設定工作成本？** `task.set(Tsk.COST, BigDecimal.valueOf(...))`。  
- **開發是否需要授權？** 免費試用可用於測試；正式環境需購買商業授權。  
- **能否取得專案層級的成本資料？** 可以，透過存取根工作（root task）的成本屬性。  
- **支援哪個 Java 版本？** Aspose.Tasks 支援 Java 8 及更新版本。

## 什麼是「計算專案成本差異」？
計算專案成本差異是指將您最初為工作或專案規劃的 **固定成本**，與反映尚未完成工作的 **剩餘成本** 進行比較。差異可告訴您是否低於或超出預算，從而進行主動調整。

## 為何使用 Aspose.Tasks 計算專案成本差異？
- **完整的純 Java API**（無需 .NET）— 不需要本機函式庫。  
- **豐富的成本管理屬性** (`COST`, `FIXED_COST`, `REMAINING_COST`, `COST_VARIANCE`)。  
- **輕鬆整合** 至現有的 Maven/Gradle 專案。  
- **精確的報告**，可匯出為 MS Project® 檔案。

## 先決條件
在開始之前，請確保您已具備以下條件：

1. **Java Development Kit (JDK)** — 已安裝 Java 8 或更新版本。  
2. **Aspose.Tasks for Java 程式庫** — 從官方網站 **[此處](https://releases.aspose.com/tasks/java/)** 下載。  
3. 一個 IDE 或建置工具（IntelliJ、Eclipse、Maven、Gradle）以編譯與執行範例程式碼。

## 匯入套件
將所需的 Aspose.Tasks 類別加入您的 Java 原始檔，以便操作專案與工作。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Import Aspose.Tasks classes
```

## 逐步指南

### 步驟 1：設定您的專案
首先，建立新的 `Project` 實例，並指向您可能儲存產生檔案的資料夾。

```java
// Set the path to your document directory
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project();
```

### 步驟 2：新增工作
在根工作下新增一個工作，我們將在此指派成本。

```java
// Add a new task to the root task
Task task = project.getRootTask().getChildren().add("Task");
```

### 步驟 3：設定工作成本 – **如何設定成本**
為工作指派計畫成本。在實際情況中，這可能來自預算試算表。

```java
// Set the task cost to 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```

### 步驟 4：取得並顯示成本資訊 – **如何管理成本**
現在我們將讀取各種成本屬性，包括計算出的成本差異。

```java
// Retrieve and print task information
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Retrieve and print project-level cost information
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```

**您將看到：**  
- `Remaining Cost` 代表尚未完成的工作。  
- `Fixed Cost` 為您設定的基準成本（本例為 800）。  
- `Cost Variance` 會自動計算為 **Fixed – Remaining**。  
- 相同的數值在專案（根工作）層級也可取得，讓您能 **計算所有工作之專案成本差異**。

### 步驟 5：為其他工作重複上述步驟（可選）
若您的專案有多個階段，請對每個工作重複步驟 2‑4。將各個差異相加即可得到整體專案成本差異。

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方式 |
|------|----------|----------|
| `NullPointerException` 在存取工作屬性時發生 | 工作未加入專案層級結構。 | 確保在設定成本前呼叫 `project.getRootTask().getChildren().add(...)`。 |
| 成本值顯示為 `0` | 使用 `int` 而非 `BigDecimal`。 | 如範例所示，請始終使用 `BigDecimal.valueOf(...)`。 |
| 出現意外的差異（負值） | `REMAINING_COST` 超過 `FIXED_COST`。 | 確認在工作進行時更新剩餘成本。 |

## 常見問題

**問：在哪裡可以找到 Aspose.Tasks for Java 的文件說明？**  
答：您可於 **[此處](https://reference.aspose.com/tasks/java/)** 存取文件說明。

**問：如何下載 Aspose.Tasks for Java 程式庫？**  
答：請於 **[此處](https://releases.aspose.com/tasks/java/)** 下載程式庫。

**問：在哪裡可以購買 Aspose.Tasks for Java？**  
答：您可於 **[此處](https://purchase.aspose.com/buy)** 購買。

**問：Aspose.Tasks for Java 是否提供免費試用？**  
答：是的，您可於 **[此處](https://releases.aspose.com/)** 取得免費試用。

**問：在哪裡可以取得 Aspose.Tasks for Java 的支援？**  
答：請前往支援論壇 **[此處](https://forum.aspose.com/c/tasks/15)**。

---

**最後更新：** 2026-02-20  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}