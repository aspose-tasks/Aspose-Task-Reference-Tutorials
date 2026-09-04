---
date: 2026-06-10
description: 了解如何使用 Aspose.Tasks for Java 讀取費率以及寫入資源指派的費率比例。支援物料資源、多種格式及大型專案。
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: 在 Aspose.Tasks 中讀取與寫入資源指派的費率比例
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中讀取與寫入資源指派的費率比例
url: /zh-hant/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中讀取與寫入資源指派的費率比例

在本教學中，您將了解 **如何讀取費率** 比例設定，並使用 Aspose.Tasks for Java 調整資源指派的費率比例。無論您是建立排程器、報表工具，或僅需自動化專案更新，精通費率比例的操作都能讓您對物料與工作資源進行細緻的控制。

## 快速解答
`ResourceAssignment` 連結任務與資源，並保存指派專屬的資料。  
`Asn` 包含指派欄位的常數，包含 `RATE_SCALE`。  
`RateScaleType` 列舉提供費率比例可能的時間單位。  

- **主要用於費率處理的類別是什麼？** `ResourceAssignment` 搭配 `Asn.RATE_SCALE` 屬性。  
- **哪個列舉定義了比例選項？** `RateScaleType`（Day、Week、Month 等）。  
- **執行範例是否需要授權？** 免費評估授權可用於測試；正式環境需商業授權。  
- **儲存後可以變更比例嗎？** 可以 – 重新載入專案並如範例所示修改 `Asn.RATE_SCALE`。  
- **支援的 IDE 為何？** 任何 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）皆可編譯此程式碼。

## 如何讀取資源指派的費率比例？

載入專案，找到目標的 `ResourceAssignment`，然後呼叫 `getRateScale()` – 這會回傳 `RateScaleType` 值，告訴您費率是以每日、每週、每月或其他單位套用。此回傳即時且僅需兩次 API 呼叫，非常適合稽核腳本或 UI 顯示。

## 如何寫入資源指派的費率比例？

建立或取得 `ResourceAssignment` 物件，將其 `Asn.RATE_SCALE` 屬性設定為所需的 `RateScaleType`（例如 `RateScaleType.Week`），然後儲存專案。此單一屬性的變更會自動更新成本計算，且會在所有支援的檔案格式中保留。設定比例後，您可能還需要調整資源的標準費率或加班費率，以符合新的時間單位，確保成本計算的準確性。

## 什麼是費率比例？

費率比例決定資源成本費率所套用的時間單位（日、週、月等）。調整比例可讓您精確地模擬物料消耗或勞動投入。例如，將比例設定為 Week 表示費率被視為每週成本，任務的總成本則依據資源指派的週數計算。

## 為何要讀取與寫入費率比例？

讀取目前的比例可協助您稽核既有排程，而寫入新比例則能讓資源符合專案的計費或消耗政策。這在 **定義物料資源** 成本或需要 **設定比例** 給非標準工作行事曆時特別有用。

## 前置條件
在開始之前，請確保您具備以下前置條件：
1. **Java 開發環境** – 已安裝 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java 程式庫** – 從 [此處](https://releases.aspose.com/tasks/java/) 下載並安裝程式庫。

## 匯入套件
The `ResourceAssignment` 類別代表任務與資源之間的連結，而 `RateScaleType` 列舉費率可能的時間單位。請在開始編寫程式碼前匯入必要的 Aspose.Tasks 類別。  

`Project` 是用來載入與儲存 Microsoft Project 檔案的主要物件。  
`Resource` 定義專案資源，例如工作或物料。  
`ResourceType` 列舉指定資源是工作還是物料。  
`Task` 代表專案排程中的工作項目。  
`SaveFileFormat` 列舉定義儲存專案的輸出格式。

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

## 步驟 1：設定您的 Java 專案
建立 Maven 或 Gradle 專案，並將 Aspose.Tasks JAR 加入 classpath。此步驟可確保編譯器能找到已匯入的類別。

## 步驟 2：載入專案檔案
載入您欲處理的現有 Microsoft Project 檔案。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 步驟 3：新增工作項目
建立一個新工作項目，稍後將指派資源給它。

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## 步驟 4：定義資源
此處我們 **定義物料資源** 與一般工作資源。請注意對於物料型資源使用 `ResourceType.Material`。

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## 步驟 5：指派資源給工作項目
現在我們 **指派資源給工作項目**，並透過使用 `RateScaleType.Week` 來說明 **如何設定比例**。此範例同時展示讀取與寫入費率比例。

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

## 常見陷阱與提示
- **UID 不匹配** – 依 UID 取得指派時，請確保 UID 值與建立時指派的相符。  
- **資源類型錯誤** – 為工作資源使用 `ResourceType.Material` 會導致費率計算異常。  
- **儲存格式** – 必須使用 `SaveFileFormat.Mpp`（或其他支援格式）儲存，以保留自訂欄位如費率比例。  
- **大型專案** – Aspose.Tasks 能在不將整個文件載入記憶體的情況下處理 **500+ 頁** 的檔案，得益於其串流架構。

## 常見問答

**Q: 我可以在任何 Java IDE 中使用 Aspose.Tasks for Java 嗎？**  
A: 可以，Aspose.Tasks for Java 相容於所有主流 Java IDE，包括 IntelliJ IDEA、Eclipse 與 NetBeans。

**Q: Aspose.Tasks 是否支援除 MPP 之外的其他檔案格式？**  
A: 支援，Aspose.Tasks 可處理多種檔案格式，包括 MPP、XML 與 HTML。

**Q: Aspose.Tasks 是否適用於企業級專案管理？**  
A: 絕對適用，Aspose.Tasks 提供完整功能以管理任何規模的專案，適合企業級專案管理。

**Q: 我可以在費率比例之外進一步自訂資源指派嗎？**  
A: 可以，Aspose.Tasks 提供廣泛的功能，可自訂資源指派，包括成本、工作與工期的調整。

**Q: 是否有 Aspose.Tasks 的社群論壇可供支援？**  
A: 有，您可在 Aspose.Tasks 論壇 [此處](https://forum.aspose.com/c/tasks/15) 獲得支援並與其他使用者互動。

---

**最後更新：** 2026-06-10  
**測試環境：** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**作者：** Aspose

## 相關教學

- [在 Aspose.Tasks 中建立資源指派](/tasks/java/resource-assignments/create-resource-assignments/)
- [如何修改指派 – 使用 Aspose 讀取共享資源](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [如何在 Aspose.Tasks 中為資源指派新增備註](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}