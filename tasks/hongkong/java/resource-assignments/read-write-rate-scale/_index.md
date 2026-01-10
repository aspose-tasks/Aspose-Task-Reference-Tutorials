---
date: 2026-01-10
description: 學習如何閱讀費率比例並管理 Aspose.Tasks for Java 中的資源指派。定義物料資源、如何設定比例，以及將資源指派給工作。
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中如何讀取與寫入資源指派的費率比例
url: /zh-hant/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中讀取與寫入資源指派的費率比例 (Rate Scale)

在本教學中，您將了解 **如何讀取費率** 比例設定，並使用 Aspose.Tasks for Java 為資源指派進行調整。無論您是在構建排程器、報表工具，或僅需自動化專案更新，精通費率比例的操作都能讓您對物料與工作資源實現細緻的控制。

## 快速解答
- **處理費率的主要類別是什麼？** `ResourceAssignment` 搭配 `Asn.RATE_SCALE` 屬性。  
- **哪個列舉定義了比例選項？** `RateScaleType`（Day、Week、Month 等）。  
- **執行範例是否需要授權？** 免費評估授權可用於測試；正式環境需商業授權。  
- **儲存後可以變更比例嗎？** 可以 – 重新載入專案後依照示例修改 `Asn.RATE_SCALE`。  
- **支援的 IDE？** 任何 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）皆可編譯此程式碼。

## 什麼是費率比例？
費率比例決定資源成本費率所套用的時間單位（天、週、月等）。調整比例可讓您精確地模擬物料消耗或勞務工作量。

## 為什麼要讀取與寫入費率比例？
讀取目前的比例可協助您稽核既有排程，而寫入新比例則能使資源符合專案的計費或消耗政策。這在 **定義物料資源** 成本或需要為非標準工作行事曆 **設定比例** 時特別有用。

## 前置條件
在開始之前，請確保您已具備以下前置條件：

1. **Java 開發環境** – 已安裝 JDK 8 或以上版本。  
2. **Aspose.Tasks for Java 程式庫** – 從 [此處](https://releases.aspose.com/tasks/java/) 下載並安裝。

## 匯入套件
首先，匯入必要的 Aspose.Tasks 類別。

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## 步驟 1：設定 Java 專案
建立 Maven 或 Gradle 專案，並將 Aspose.Tasks JAR 加入 classpath。此步驟可確保編譯器能找到匯入的類別。

## 步驟 2：載入專案檔案
載入您欲處理的現有 Microsoft Project 檔案。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 步驟 3：新增工作項目
建立一個新工作項目，稍後將接收資源指派。

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## 步驟 4：定義資源
此處我們 **定義物料資源** 以及一般工作資源。請留意對於物料型資源使用了 `ResourceType.Material`。

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## 步驟 5：指派資源至工作項目
現在我們 **指派資源至工作項目**，並透過 `RateScaleType.Week` 指定 **如何設定比例**。此範例同時示範了讀取與寫入費率比例。

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## 步驟 6：儲存專案
將變更持久化至新檔案，以便稍後驗證已儲存的費率比例。

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## 步驟 7：取得資源指派
重新載入已儲存的專案，並 **讀取費率** 比例以確認寫入正確。

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## 常見陷阱與技巧
- **UID 不匹配** – 依 UID 取得指派時，請確保 UID 值與建立時分配的相符。  
- **資源類型錯誤** – 為工作資源使用 `ResourceType.Material` 會導致費率計算出現異常。  
- **儲存格式** – 必須使用 `SaveFileFormat.Mpp`（或其他支援的格式）儲存，以保留費率比例等自訂欄位。

## 結論
只要了解相關類別與屬性，在 Aspose.Tasks for Java 中管理與檢查資源指派的費率比例即相當簡單。依循本指南，您即可自信地 **讀取費率** 資訊、 **定義物料資源** 物件、 **設定比例**，以及 **指派資源至工作項目**。

## 常見問題

**Q: 我可以在任何 Java IDE 中使用 Aspose.Tasks for Java 嗎？**  
A: 可以，Aspose.Tasks for Java 相容於所有主流 Java IDE，包括 IntelliJ IDEA、Eclipse 與 NetBeans。

**Q: Aspose.Tasks 是否支援除 MPP 之外的其他檔案格式？**  
A: 支援，Aspose.Tasks 支援多種檔案格式，包括 MPP、XML 與 HTML。

**Q: Aspose.Tasks 是否適合企業級專案管理？**  
A: 絕對適合，Aspose.Tasks 提供完整功能，能管理任何規模的專案，適用於企業級專案管理。

**Q: 我可以在費率比例之外進一步自訂資源指派嗎？**  
A: 可以，Aspose.Tasks 提供廣泛的功能，可自訂資源指派，包括成本、工作量與工期的調整。

**Q: 是否有 Aspose.Tasks 的社群論壇可供支援？**  
A: 有，您可在 Aspose.Tasks 論壇取得支援並與其他使用者互動，連結在 [此處](https://forum.aspose.com/c/tasks/15)。

**最後更新：** 2026-01-10  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}