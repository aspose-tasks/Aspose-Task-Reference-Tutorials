---
date: 2026-06-05
description: 了解如何使用 Aspose.Tasks for Java 建立資源指派、將資源新增至專案，以及管理平衡延遲屬性。
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: 在 Aspose.Tasks 中處理資源指派的平衡延遲屬性
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 建立資源指派
url: /zh-hant/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 建立資源指派

在本完整指南中，您將學習 **如何建立資源指派 aspotasks**，使用 Aspose.Tasks for Java 函式庫。無論您是構建自訂排程引擎、批量自動化專案更新，或僅需在未安裝桌面應用程式的情況下操作 Microsoft Project 檔案，掌握這些步驟即可確保專案資料的正確性與完整控制。

## 快速解答
- **「add resource to project」是什麼意思？** 它會建立一個新的資源項目，之後可指派給工作。  
- **指派後我可以設定平衡延遲嗎？** 可以，使用 `Asn.DELAY` 或 `Asn.LEVELING_DELAY` 欄位。  
- **執行此程式碼是否需要授權？** 免費試用版可用於開發；正式環境需付費授權。  
- **支援哪個 Java 版本？** Java 8 或更新版本。  
- **此功能是否相容所有 MS Project 檔案格式？** Aspose.Tasks 支援超過 12 種格式，包括 .MPP、.XML、.XER、.CSV、.PDF 等。

## 「add resource to project」在 Aspose.Tasks 中是什麼？
將資源新增至專案即是在 `Project` 模型內建立一個 `Resource` 物件。之後可透過 `ResourceAssignment` 將其指派給工作，以追蹤工作量、成本與平衡設定。新增資源即為排程器提供可分配的對象，之後您可以查詢或修改其可用性、費率與行事曆指派等屬性。

## 為何要處理平衡延遲屬性？
平衡延遲告訴排程器延後超額指派的開始時間，將工作更均勻地分佈於時間軸上。設定此延遲可避免不切實際的開始日期、減少超額警告，並產生符合實際資源限制的排程。調整延遲亦提供細緻的控制，讓您在滿足專案期限的同時尊重資源上限。

## 如何建立資源指派 aspotasks？
載入 `Project` 物件、加入工作、建立資源，然後以 `ResourceAssignment` 連結它們。此端對端流程讓您以程式方式建構完整的專案結構，並立即在指派上控制平衡延遲。此過程示範了核心工作流程：專案初始化、工作定義、資源建立、指派連結，最後套用排程參數（如平衡延遲）。

## 前置條件
1. Java Development Kit (JDK)：確保系統已安裝 Java JDK。您可從 [官方網站](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) 下載並安裝。  
2. Aspose.Tasks for Java 函式庫：從 [下載頁面](https://releases.aspose.com/tasks/java/) 下載 Aspose.Tasks for Java 函式庫。

## 匯入套件
以下的匯入語句提供了操作專案所需的核心 Aspose.Tasks 類別。  
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 如何建立資源指派 aspotasks？
載入 `Project` 物件、加入工作、建立資源，然後以 `ResourceAssignment` 連結它們。此端對端流程讓您以程式方式建構完整的專案結構，並立即在指派上控制平衡延遲。此過程示範了核心工作流程：專案初始化、工作定義、資源建立、指派連結，最後套用排程參數（如平衡延遲）。

## 步驟 1：建立 Project 物件
`Project` 類別是 Aspose.Tasks 的最高層容器，代表整個專案檔案於記憶體中的模型。實例化它即可得到一個乾淨的起點，以加入工作、資源與指派。  
```java
Project prj = new Project();
```

## 步驟 2：建立 Task
`Task` 類別代表排程中的單一工作項目。加入工作示範了 **如何新增工作**，同時為即將到來的資源指派提供目標。  
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## 步驟 3：設定 Task 開始日期與持續時間
定義工作何時開始以及持續多久。正確的開始日期相當重要，因為平衡計算會以此為基礎，套用之後您指定的任何延遲。  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## 步驟 4：新增資源
現在我們 **add resource to project** 透過建立新的 `Resource` 項目來新增資源。`Resource` 類別代表可指派給工作之人員、設備或材料。  
```java
Resource resource = prj.getResources().add("Resource 1");
```

## 步驟 5：建立 Resource Assignment
`ResourceAssignment` 連結 `Task` 與 `Resource`。此關聯讓您能為特定資源在特定工作上記錄工作量、成本與平衡細節。  
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## 步驟 6：設定平衡延遲
為指派配置平衡延遲。設定為 0 表示不額外延遲，但您可以依需求調整數值。`Asn.DELAY` 欄位以分鐘為單位保存延遲；`Asn.LEVELING_DELAY` 為同等別名。  
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## 步驟 7：顯示結果
列印重要屬性以驗證所有設定是否正確。此步驟協助您在儲存檔案前，確認資源、工作與延遲值皆符合預期。  
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## 常見陷阱與技巧
- **陷阱：** 忘記設定 Task 開始日期會導致指派預設為專案開始日。  
- **技巧：** 使用 `prj.getDuration(value, TimeUnitType.Day)` 來控制延遲的粒度。  
- **技巧：** 新增多個資源後，呼叫 `prj.updateResourceAssignments()` 讓排程器重新計算平衡。  
- **專業技巧：** 對於大型專案（10,000+ 工作）在批次更新前啟用 `prj.setAutoCalculate(false)`，最後一次性呼叫 `prj.calculate()` 以提升效能。

## 常見問與答

**Q: 我可以將 Aspose.Tasks 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Tasks 能順利整合如 Jackson（用於 JSON 處理）或 Apache POI（用於額外的試算表操作）等函式庫，讓您構建更完整的專案管理解決方案。

**Q: Aspose.Tasks 是否相容不同版本的 Microsoft Project 檔案？**  
A: Aspose.Tasks 支援超過 12 種檔案格式，包括 .MPP（2003‑2021）、.XML、.XER、.CSV、.PDF、.HTML 以及 .MPP12，確保在所有主要 Project 版本間無縫往返編輯。

**Q: 我可以在哪裡取得 Aspose.Tasks 的額外支援？**  
A: 您可以在 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 上找到支援與社群討論。

**Q: 我可以在購買前試用 Aspose.Tasks 嗎？**  
A: 可以，完整功能的免費試用版可從 [發佈頁面](https://releases.aspose.com/) 取得。

**Q: 我如何取得評估用的臨時授權？**  
A: 可從 [臨時授權頁面](https://purchase.aspose.com/temporary-license/) 申請臨時授權，以在無評估限制的情況下執行函式庫。

**最後更新：** 2026-06-05  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose

## 相關教學

- [在 Aspose.Tasks 中建立資源指派](/tasks/java/resource-assignments/create-resource-assignments/)
- [使用 Aspose.Tasks 管理指派預算 (Java)](/tasks/java/resource-assignments/assignment-budget/)
- [如何在 Aspose.Tasks 中停止指派並恢復資源指派](/tasks/java/resource-assignments/stop-resume-assignment/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}