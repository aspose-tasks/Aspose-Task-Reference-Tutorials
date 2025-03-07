---
title: 處理 Aspose.Tasks 中的調平延遲屬性
linktitle: 處理 Aspose.Tasks 中資源分配的調配延遲屬性
second_title: Aspose.Tasks Java API
description: 透過這個綜合教程，了解如何在 Aspose.Tasks for Java 中處理資源分配的調平延遲屬性。
weight: 17
url: /zh-hant/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 處理 Aspose.Tasks 中的調平延遲屬性

## 介紹
在本教程中，我們將逐步介紹在 Aspose.Tasks for Java 中處理資源分配的均衡延遲屬性的過程。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓您使用 Microsoft Project 文件，而無需在系統上安裝 Microsoft Project。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 Java JDK。您可以從以下位置下載並安裝它[網站](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java 函式庫：從下列位置下載 Aspose.Tasks for Java 函式庫：[下載頁面](https://releases.aspose.com/tasks/java/).

## 導入包
首先，將必要的套件匯入到您的 Java 專案中以使用 Aspose.Tasks 功能：
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

## 第 1 步：建立專案對象
實例化一個`Project`目的：
```java
Project prj = new Project();
```
## 第 2 步：建立任務
在專案中新增任務：
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## 步驟 3：設定任務開始日期和持續時間
設定任務的開始日期和持續時間：
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## 第 4 步：新增資源
為專案新增資源：
```java
Resource resource = prj.getResources().add("Resource 1");
```
## 步驟 5：建立資源分配
為任務和資源建立資源分配：
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## 第6步：設定調平延遲
設定分配的調平延遲：
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## 第 7 步：顯示結果
列印平層延遲及其他相關資訊：
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## 結論
在本教程中，我們學習如何處理 Aspose.Tasks for Java 中資源分配的均衡延遲屬性。透過執行下列步驟，您可以有效地管理 Java 專案中的資源分配。
## 常見問題解答
### Q：我可以將 Aspose.Tasks 與其他 Java 函式庫一起使用嗎？

答：是的，Aspose.Tasks 可以與其他 Java 庫集成，以增強專案管理能力。

### Q：Aspose.Tasks 是否與不同版本的 Microsoft Project 檔案相容？

答：是的，Aspose.Tasks 支援各種版本的 Microsoft Project 文件，確保不同環境之間的相容性。

### Q：在哪裡可以找到對 Aspose.Tasks 的額外支援？

答：您可以在以下位置找到支援和資源：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).

### Q：我可以在購買前試用 Aspose.Tasks 嗎？

答：是的，您可以從 Aspose.Tasks 取得免費試用版[發布頁面](https://releases.aspose.com/).

### Q：如何取得 Aspose.Tasks 的臨時許可證？

答：您可以向以下機構申請臨時許可證[臨時許可證頁面](https://purchase.aspose.com/temporary-license/)出於評估目的。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
