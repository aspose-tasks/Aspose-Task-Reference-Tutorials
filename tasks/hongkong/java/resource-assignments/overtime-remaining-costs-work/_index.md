---
date: 2026-01-07
description: 學習如何在 Java 專案中使用 Aspose.Tasks 進行專案成本監控、追蹤加班、計算剩餘工作量以及管理成本。簡單步驟，助您有效管理專案。
linktitle: 'Project Cost Monitoring with Aspose.Tasks: Overtime & Work'
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 監控項目成本：加班與工作
url: /zh-hant/java/resource-assignments/overtime-remaining-costs-work/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 進行專案成本監控：加班與工作

## 介紹
在本教學中，您將學會如何使用 Aspose.Tasks for Java 進行 **專案成本監控**。我們將逐步說明如何追蹤加班、剩餘成本與工作量，讓您的專案能夠按時完成且不超出預算。無論您是專案經理或是團隊領導，這些步驟都能協助您清晰掌握財務與資源指標。

## 快速回答
- **我可以監控什麼？** 加班成本、加班工作、剩餘成本、剩餘工作以及剩餘加班成本。  
- **需要哪個函式庫？** Aspose.Tasks for Java。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式環境需要授權。  
- **可以載入現有的 .mpp 檔案嗎？** 可以，只需提供檔案路徑。  
- **Java 6 足夠嗎？** 此 API 支援 Java SE 6 及以上版本。

## 什麼是專案成本監控？
專案成本監控是持續追蹤專案所有財務面向的做法——包括預算成本、實際支出以及預測的剩餘成本。結合資源指派後，您可即時了解加班費用與工作進度。

## 為什麼要監控加班與剩餘工作？
- **控制預算：** 加班常會導致意外的成本超支。  
- **改善預測：** 瞭解剩餘工作量可讓您主動調整排程。  
- **提升透明度：** 利害關係人能清楚看到資源的使用情況。

## 前置條件
在開始之前，請確保您已具備以下條件：
1. **Java Development Kit (JDK)：** Aspose.Tasks for Java 需要 Java SE 6 或更新版本。  
2. **Aspose.Tasks for Java 函式庫：** 從 [here](https://releases.aspose.com/tasks/java/) 下載並安裝。  
3. **整合開發環境 (IDE)：** 任意 Java IDE，例如 Eclipse、IntelliJ IDEA 或 NetBeans。

## 匯入套件
先在 Java 檔案中匯入必要的套件：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## 步驟 1：設定資料目錄
定義專案檔案所在的目錄：
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為您的專案檔案路徑。

## 步驟 2：載入專案
建立 `Project` 物件並載入專案檔案：
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
將 `"ResourceAssignmentOvertimes.mpp"` 替換為您的 MPP 檔案名稱，此步驟示範 **載入 mpp 檔案** 的用法。

## 步驟 3：遍歷資源指派
對專案中的每個資源指派進行迴圈：
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```

## 步驟 4：列印加班成本與工作
取得並列印每個資源指派的加班成本與工作量：
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```

## 步驟 5：列印剩餘成本與工作
取得並列印每個資源指派的剩餘成本與工作量：
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```

## 步驟 6：列印剩餘加班成本與工作
取得並列印每個資源指派的剩餘加班成本與工作量：
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## 常見問題與解決方案
- **找不到檔案：** 請再次確認 `dataDir` 路徑並確保 MPP 檔名正確。  
- **空值：** 某些指派可能沒有加班資料，列印時需檢查 `null`。  
- **版本不匹配：** 請使用與 MPP 檔案格式相符的函式庫版本（例如較新的 Microsoft Project 版本）。

## 常見問答

**Q: 可以將 Aspose.Tasks for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Tasks for Java 與其他 Java 函式庫與框架相容。

**Q: Aspose.Tasks 支援不同的專案檔案格式嗎？**  
A: 支援，Aspose.Tasks 可處理多種格式，包括 MPP、XML 等。

**Q: 有提供試用版嗎？**  
A: 有，您可從 [here](https://releases.aspose.com/) 下載免費試用版。

**Q: 若遇到問題，該去哪裡取得支援？**  
A: 您可前往 Aspose.Tasks 論壇 [here](https://forum.aspose.com/c/tasks/15) 尋求協助。

**Q: 要如何購買 Aspose.Tasks 的授權？**  
A: 您可在 [here](https://purchase.aspose.com/buy) 購買授權。

## 結論
監控加班、剩餘成本與工作量是有效 **專案成本監控** 的關鍵。透過 Aspose.Tasks for Java，您可以程式化地擷取這些指標，取得保持專案進度與避免預算驚喜所需的資料。探索更多 Aspose.Tasks 功能，進一步強化您的專案管理工具箱。

---

**最後更新：** 2026-01-07  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}