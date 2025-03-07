---
title: 在 Aspose.Tasks 中產生時間分段數據
linktitle: 在 Aspose.Tasks 中產生資源分配的時間分段數據
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 產生資源分配的時間分段資料。透過這份綜合指南提升專案管理效率。
weight: 24
url: /zh-hant/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中產生時間分段數據

## 介紹
在本教程中，我們將逐步介紹使用 Aspose.Tasks for Java 產生資源分配的時間分段資料的過程。時間分段資料提供了有關專案內資源如何隨時間分配的寶貴見解，幫助專案經理做出明智的決策。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從以下位置下載並安裝 JDK[這裡](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java 函式庫：您需要有 Aspose.Tasks for Java 函式庫。您可以從[網站](https://releases.aspose.com/tasks/java/).

## 導入包
首先，讓我們匯入使用 Aspose.Tasks 所需的套件：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## 步驟1：讀取來源MPP文件
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
//讀取來源MPP文件
Project project = new Project(dataDir + "project.mpp");
```
## 第 2 步：獲取任務和資源分配
```java
//取得專案的第一個任務
Task task = project.getRootTask().getChildren().getById(1);
//取得專案的第一個資源分配
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## 步驟 3：產生具有平坦輪廓的時間分段數據
```java
//平坦輪廓是預設輪廓
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 步驟 4：將輪廓更改為海龜
```java
//將輪廓更改為海龜
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 5 步：將輪廓更改為 BackLoaded
```java
//將輪廓更改為 BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 6 步：將輪廓更改為 FrontLoaded
```java
//將輪廓變更為 FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 步驟7：將輪廓更改為鐘形
```java
//將輪廓更改為 Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 8 步：將等值線改為 EarlyPeak
```java
//將輪廓更改為 EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 9 步：將輪廓更改為 LatePeak
```java
//將輪廓更改為 LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 步驟 10：將等值線改為 DoublePeak
```java
//將輪廓更改為 DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 結論
在本教程中，我們介紹如何使用 Aspose.Tasks for Java 產生資源分配的時間分段資料。了解不同的工作輪廓可以幫助專案經理有效管理專案中的資源分配和調度。
## 常見問題解答
### 我可以將 Aspose.Tasks 與其他 Java 函式庫一起使用嗎？
是的，Aspose.Tasks 可以與其他 Java 程式庫整合以增強專案管理功能。
### Aspose.Tasks適合大型企業專案嗎？
當然，Aspose.Tasks 旨在處理各種規模的項目，包括大型企業項目。
### Aspose.Tasks 是否提供不同專案文件格式的支援？
是的，Aspose.Tasks 支援各種專案檔案格式，包括 MPP、XML 和 MPX。
### 我可以根據我的專案要求客製化工作輪廓嗎？
是的，Aspose.Tasks 允許使用者定義自訂工作輪廓以滿足其特定的專案需求。
### 是否有社群論壇可以讓我獲得有關 Aspose.Tasks 的幫助？
是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以尋求支持和討論。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
