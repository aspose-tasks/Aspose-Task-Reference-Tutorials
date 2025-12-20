---
date: 2025-12-20
description: 學習如何使用 Aspose.Tasks for Java 以程式方式取得 MS Project 大綱代碼，提升您的專案管理能力。
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中檢索 MS Project 大綱代碼
url: /zh-hant/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 以 Aspose.Tasks 取得 MS Project 大綱代碼

## 介紹
在本教學中，您將學習 **如何使用 Aspose.Tasks for Java 取得 MS Project 大綱代碼**。MS Project 的大綱代碼提供了一種強大的方式來對工作、資源與指派進行分類，程式化存取這些代碼可讓您建立自訂報表、自動化或整合解決方案。我們將一步一步示範完整範例，您可以直接複製到自己的專案中。

## 快速回答
- **程式碼的功能是什麼？** 載入專案檔並列印每個大綱代碼的定義、遮罩與值。  
- **需要哪個函式庫？** Aspose.Tasks for Java（任意近期版本）。  
- **需要授權嗎？** 開發階段可使用試用版；正式環境需購買正式授權。  
- **支援哪個 Java 版本？** Java 8 以上。  
- **取得後可以修改代碼嗎？** 可以——相同的 API 允許您新增、編輯或刪除大綱代碼。

## 什麼是 MS Project 大綱代碼？
大綱代碼是自訂欄位，讓專案經理在預設階層之外對工作進行分組與篩選。它們可以是簡單的數值、字串，甚至是企業層級在組織中定義的自訂代碼。透過讀取這些代碼，您可以驅動儀表板、匯出資料，或自動執行命名規則。

## 為什麼要使用 Aspose.Tasks 取得 MS Project 大綱代碼？
- **自動化：** 在不需手動匯出的情況下產生報表或觸發工作流程。  
- **整合：** 將大綱代碼同步至 ERP、PPM 或 BI 工具。  
- **客製化：** 根據代碼值套用業務規則（例如成本分配）。  
- **跨平台：** 可在 Windows、Linux、macOS 上執行，與 Microsoft Project UI 無關。

## 前置條件
在開始之前，請確保已完成以下前置作業：

### 1. Java 開發環境
請確認您的系統已安裝 Java Development Kit (JDK)。可從 Oracle 官方網站下載並安裝 JDK。

### 2. Aspose.Tasks 函式庫
下載並將 Aspose.Tasks 函式庫加入您的 Java 專案。可從 [Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/) 取得。

## 匯入套件
首先，在 Java 程式碼中匯入 Aspose.Tasks 所需的套件：
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

接下來，我們將提供的範例程式碼分成多個步驟說明：

## 步驟 1：載入專案
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
此步驟會使用提供的檔名將 Microsoft Project 檔載入 `Project` 物件。

## 步驟 2：取得大綱代碼
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
我們會遍歷專案中的每個大綱代碼定義。

## 步驟 3：存取大綱代碼屬性
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
取得並列印大綱代碼定義的各種屬性，例如別名 (Alias)、欄位 ID 與欄位名稱。

## 步驟 4：檢查企業自訂代碼
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
判斷此大綱代碼是否為企業自訂代碼，並相應列印結果。

## 步驟 5：顯示大綱代碼遮罩
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
遍歷與大綱代碼相關的每個遮罩，列印其層級與遮罩值。

## 步驟 6：顯示大綱代碼值
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
遍歷每個大綱代碼值，列印其說明、值 ID、值本身與類型。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **沒有輸出** | 專案檔路徑不正確 | 確認 `projectName` 指向有效的 `.mpp` 檔案。 |
| **值為 null** | 檔案中未定義大綱代碼 | 確認專案檔實際包含大綱代碼（可在 MS Project UI 中檢查）。 |
| **LicenseException** | 使用試用版未正確啟用 | 透過 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 套用臨時或正式授權。 |

## 常見問答

**Q: 可以使用 Aspose.Tasks for Java 在專案檔中修改大綱代碼嗎？**  
A: 可以，Aspose.Tasks for Java 提供 API 讓您以程式方式修改大綱代碼。您可以使用相同的 `Project` 物件新增、編輯或刪除定義。

**Q: Aspose.Tasks for Java 有提供試用版嗎？**  
A: 有，您可從 [Aspose.Tasks 官方網站](https://releases.aspose.com/) 下載免費試用版。

**Q: 如何取得 Aspose.Tasks for Java 的技術支援？**  
A: 可前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 發問取得技術支援。

**Q: 可以購買臨時授權嗎？**  
A: 可以，請至 [購買頁面](https://purchase.aspose.com/temporary-license/) 購買 Aspose.Tasks for Java 的臨時授權。

**Q: 哪裡可以找到 Aspose.Tasks for Java 的完整文件？**  
A: 請參考 [文件說明](https://reference.aspose.com/tasks/java/) 取得詳細使用資訊。

## 結論
本教學說明了如何使用 Aspose.Tasks for Java 取得 **MS Project 大綱代碼**。依循上述步驟，您即可在 Java 應用程式中有效存取與操作大綱代碼，從而實現自訂報表、自動化以及與其他企業系統的整合等進階專案管理功能。

---

**最後更新：** 2025-12-20  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}