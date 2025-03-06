---
title: 使用 Aspose.Tasks 有效率地管理 MS 專案屬性
linktitle: 處理 Aspose.Tasks 中的擴充資源屬性
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 有效處理擴充功能的 Microsoft Project 資源屬性。簡單的步驟和全面的指南。
type: docs
weight: 11
url: /zh-hant/java/resource-management/extended-resource-attributes/
---
## 介紹
在本教程中，我們將深入研究如何使用 Aspose.Tasks for Java 有效處理擴充功能的 Microsoft Project 資源屬性。 Aspose.Tasks 是一個功能強大的函式庫，使開發人員能夠以程式設計方式操作 Microsoft Project 文件，為任務和資源管理提供廣泛的功能。
## 先決條件
在繼續之前，請確保您具備以下先決條件：
1. Java 開發環境：在您的系統上設定 Java 開發工具包 (JDK)。
2.  Aspose.Tasks for Java：下載並安裝 Aspose.Tasks for Java 函式庫[這裡](https://releases.aspose.com/tasks/java/).
3. 整合開發環境 (IDE)：安裝用於 Java 開發的 IDE，例如 Eclipse 或 IntelliJ IDEA。

## 導入包
首先將必要的套件匯入到您的 Java 專案中。 
```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```
## 第 1 步：定義資料目錄
設定項目資料所在目錄的路徑。
```java
String dataDir = "Your Data Directory";
```
## 步驟2：載入專案文件
實例化一個`Project`透過載入 Microsoft Project 檔案來取得物件。
```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```
## 步驟 3：定義擴充屬性
定義資源的擴充屬性。
```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```
## 步驟4：建立擴展屬性並設定值
建立擴展屬性並為其指派數值。
```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```
## 步驟5：新增資源和擴充屬性
將新資源及其擴充屬性新增至專案。
```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```
## 第 6 步：儲存項目
將修改後的項目儲存到新文件中。
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
## 第7步：顯示結果
列印一條訊息，確認流程已完成。
```java
System.out.println("Process completed Successfully");
```
仔細遵循這些步驟，您可以使用 Aspose.Tasks for Java 無縫處理擴充的 MS Project 資源屬性。

## 結論
總之，Aspose.Tasks for Java 提供了管理 Microsoft Project 檔案的強大功能，包括處理擴充資源屬性。透過利用Aspose.Tasks提供的功能，開發人員可以有效地操作專案資料以滿足各種需求。
## 常見問題解答
### Aspose.Tasks 可以處理複雜的專案結構嗎？
是的，Aspose.Tasks 為複雜的專案結構提供全面的支持，允許使用者無縫地管理任務、資源和屬性。
### Aspose.Tasks 與最新版本的 Microsoft Project 相容嗎？
Aspose.Tasks定期更新，以確保與最新版本的Microsoft Project相容，為使用者提供可靠的專案管理解決方案。
### Aspose.Tasks支援跨平台開發嗎？
是的，開發人員可以跨不同平台使用 Aspose.Tasks for Java，使其成為專案管理應用程式的多功能選擇。
### 我可以將 Aspose.Tasks 與其他 Java 函式庫整合嗎？
當然，Aspose.Tasks 可以與其他 Java 程式庫無縫集成，以增強功能並簡化開發流程。
### Aspose.Tasks 用戶可以獲得技術支援嗎？
是的，用戶可以透過 Aspose.Tasks 論壇獲得技術支持，在那裡他們可以尋求幫助並與社群互動。