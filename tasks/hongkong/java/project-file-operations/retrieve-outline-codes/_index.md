---
title: 在 Aspose.Tasks 中檢索 MS 專案大綱程式碼
linktitle: 檢索 Aspose.Tasks 中的大綱程式碼
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 以程式設計方式擷取 Microsoft Project 大綱程式碼。增強您的專案管理能力。
weight: 15
url: /zh-hant/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中檢索 MS 專案大綱程式碼

## 介紹
在本教程中，我們將學習如何使用 Aspose.Tasks for Java 檢索 Microsoft Project 大綱程式碼。 MS Project 中的大綱程式碼提供了一種結構化的方法來分類和組織專案任務、資源和分配。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓開發人員以程式設計方式操作和管理 Microsoft Project 檔案。
## 先決條件
在我們開始之前，請確保您已設定以下先決條件：
### 1.Java開發環境
確保您的系統上安裝了 Java 開發工具包 (JDK)。您可以從 Oracle 網站下載並安裝 JDK。
### 2.Aspose.Tasks庫
下載 Aspose.Tasks 庫並將其包含在您的 Java 專案中。您可以從以下位置下載該程式庫[Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/).
## 導入包
首先，從 Java 程式碼中的 Aspose.Tasks 匯入必要的套件：
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
現在讓我們將提供的範例程式碼分解為多個步驟：
## 第 1 步：載入項目
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
在此步驟中，我們將 Microsoft Project 檔案載入到`Project`使用提供的檔案名稱的物件。
## 第 2 步：擷取大綱程式碼
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
我們迭代專案中的每個大綱程式碼定義。
## 第 3 步：存取大綱程式碼屬性
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
我們檢索並列印大綱程式碼定義的各種屬性，例如別名、欄位 ID 和欄位名稱。
## 第四步：檢查企業自訂程式碼
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
我們檢查大綱程式碼是否為企業自訂程式碼並相應列印結果。
## 第 5 步：顯示輪廓代碼遮罩
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
我們迭代與大綱程式碼關聯的每個遮罩並列印其層級和遮罩值。
## 步驟 6：顯示輪廓代碼值
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
我們迭代每個大綱程式碼值並列印其描述、值 ID、值和類型。
## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 檢索 MS Project 大綱程式碼。透過遵循提供的步驟，您可以有效地存取和操作 Java 應用程式中的大綱程式碼，從而實現高階專案管理功能。
## 常見問題解答
### Q1: 我可以使用Aspose.Tasks for Java修改Project檔案中的大綱程式碼嗎？
答：是的，Aspose.Tasks for Java 提供 API 以程式方式修改 MS Project 檔案中的大綱程式碼。
### Q2：Aspose.Tasks for Java 有試用版嗎？
答：是的，您可以從 Aspose.Tasks for Java 下載免費試用版[Aspose.Tasks 網站](https://releases.aspose.com/).
### Q3：如何獲得 Aspose.Tasks for Java 的技術支援？
答：您可以透過造訪網站獲得技術支持[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)並在那裡發布您的疑問。
### Q4：我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
答：是的，您可以從 Aspose.Tasks for Java 購買臨時許可證[購買頁面](https://purchase.aspose.com/temporary-license/).
### Q5：在哪裡可以找到 Aspose.Tasks for Java 的完整文件？
答：您可以參考[文件](https://reference.aspose.com/tasks/java/)有關使用 Aspose.Tasks for Java 的詳細資訊。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
