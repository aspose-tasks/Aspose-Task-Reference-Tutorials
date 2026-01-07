---
date: 2026-01-07
description: 學習如何使用 Aspose.Tasks for Java 為專案新增資源，並處理資源指派的平衡延遲屬性。
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中向專案新增資源並處理平衡延遲屬性
url: /zh-hant/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中將資源新增至專案並處理平衡延遲屬性

## 介紹
在本教學中，您將學習 **how to add resource to project**，同時使用 Aspose.Tasks for Java 管理資源指派的平衡延遲屬性。無論您是建立排程引擎或自動化專案更新，掌握這些步驟即可在不安裝 Microsoft Project 的情況下，保持專案資料的正確性。

## 快速解答
- **「add resource to project」是什麼意思？** 它會建立一個可指派給工作的新資源項目。  
- **指派後可以設定平衡延遲嗎？** 可以，使用 `Asn.DELAY` 或 `Asn.LEVELING_DELAY` 欄位。  
- **執行此程式碼需要授權嗎？** 開發階段可使用免費試用版；正式環境需購買授權。  
- **支援哪個 Java 版本？** 支援 Java 8 或更新版本。  
- **是否相容所有 MS Project 檔案格式？** Aspose.Tasks 支援 .MPP、.XML、.XER 等多種格式。

## 在 Aspose.Tasks 中什麼是 “add resource to project”？
將資源新增至專案即是在 `Project` 模型內建立一個 `Resource` 物件。之後可透過 `ResourceAssignment` 與工作連結，讓您追蹤工作量、成本與平衡設定。

## 為什麼要處理平衡延遲屬性？
平衡延遲可協助排程器在資源過度分配時分散工作。設定延遲即告訴引擎推遲指派的開始時間，避免衝突並使專案更貼近實際情況。

## 前置條件
在開始之前，請確保您已具備以下條件：
1. Java Development Kit (JDK)：確保系統已安裝 Java JDK，可從 [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) 下載並安裝。  
2. Aspose.Tasks for Java Library：從 [download page](https://releases.aspose.com/tasks/java/) 下載 Aspose.Tasks for Java 程式庫。

## 匯入套件
首先，將必要的套件匯入您的 Java 專案，以使用 Aspose.Tasks 功能：
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

## 步驟 1：建立 Project 物件
實例化一個 `Project` 物件，作為所有工作、資源與指派的容器：
```java
Project prj = new Project();
```

## 步驟 2：建立工作
將工作新增至專案，示範 **how to add task** 的程式寫法：
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## 步驟 3：設定工作開始日期與持續時間
定義工作何時開始以及持續多久：
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## 步驟 4：新增資源
現在我們 **add resource to project**，透過建立新的 `Resource` 項目來新增資源：
```java
Resource resource = prj.getResources().add("Resource 1");
```

## 步驟 5：建立資源指派
將工作與剛剛新增的資源連結起來：
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## 步驟 6：設定平衡延遲
為指派設定平衡延遲。設定為 0 表示不額外延遲，您可以依需求調整數值：
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## 步驟 7：顯示結果
列印重要屬性以驗證所有設定是否正確：
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## 常見陷阱與提示
- **陷阱：** 忘記設定工作開始日期會導致指派預設為專案開始日。  
- **提示：** 使用 `prj.getDuration(value, TimeUnitType.Day)` 來控制延遲的粒度。  
- **提示：** 新增多個資源後，呼叫 `prj.updateResourceAssignments()` 讓排程器重新計算平衡。

## 結論
透過上述步驟，您現在已了解 **how to add resource to project**、將其指派給工作，並使用 Aspose.Tasks for Java 管理平衡延遲屬性。此知識可協助您打造符合實際資源限制的強大專案自動化解決方案。

## 常見問答
### Q: 我可以將 Aspose.Tasks 與其他 Java 函式庫一起使用嗎？

A: 可以，Aspose.Tasks 能與其他 Java 函式庫整合，以增強專案管理功能。

### Q: Aspose.Tasks 是否相容於不同版本的 Microsoft Project 檔案？

A: 是的，Aspose.Tasks 支援多種 Microsoft Project 檔案版本，確保在不同環境下的相容性。

### Q: 我可以在哪裡找到 Aspose.Tasks 的其他支援？

A: 您可以在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 上取得支援與資源。

### Q: 我可以在購買前試用 Aspose.Tasks 嗎？

A: 可以，您可從 [releases page](https://releases.aspose.com/) 取得 Aspose.Tasks 的免費試用版。

### Q: 我該如何取得 Aspose.Tasks 的臨時授權？

A: 您可前往 [temporary license page](https://purchase.aspose.com/temporary-license/) 申請臨時授權以供評估使用。

## 其他常見問題

**Q: 若設定非零的平衡延遲會發生什麼事？**  
**A:** 排程器會依指定的時長推遲指派的開始時間，協助解決資源過度分配的問題。

**Q: 儲存專案後，我能取得平衡延遲嗎？**  
**A:** 可以，重新開啟專案檔後即可從指派的 `Asn.DELAY` 屬性讀取該值。

**Q: 有沒有辦法一次對所有指派套用平衡延遲？**  
**A:** 您可以遍歷 `prj.getResourceAssignments()`，在迴圈中為每個指派設定延遲。

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}