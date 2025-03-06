---
title: 使用 Aspose.Tasks 配置 MS Project PDF 數位簽名
linktitle: 在 Aspose.Tasks 中配置 PDF 數位簽名詳細信息
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 設定 Microsoft Project PDF 數位簽章詳細資料。確保專案文件的安全性和真實性。
weight: 10
url: /zh-hant/net/pdf-security-configuration/pdf-digital-signature-details/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 配置 MS Project PDF 數位簽名

## 介紹
在本教學中，我們將引導您完成使用 Aspose.Tasks for .NET 設定 Microsoft Project PDF 數位簽章詳細資料的流程。透過執行這些步驟，您將能夠將數位簽章無縫整合到您的 MS Project 檔案中，從而確保安全性和真實性。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1.  Aspose.Tasks for .NET：請確定您的開發環境中安裝了 Aspose.Tasks for .NET。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 文件：準備要使用的 Microsoft Project 文件，並確保可以在專案目錄中存取它。
3. X.509 憑證：取得將用於數位簽章的 X.509 憑證。如果您沒有，您可以產生一個自簽名憑證用於測試目的。
## 導入命名空間
首先，您需要在 .NET 專案中匯入必要的命名空間，以從 Aspose.Tasks 存取所需的類別和方法。
```csharp
using Aspose.Tasks;
using System;
using System.Security.Cryptography;
using System.Security.Cryptography.X509Certificates;

using Aspose.Tasks.Saving;
```
現在，讓我們將範例分解為多個步驟：
## 第 1 步：載入 Microsoft Project 文件
```csharp
//文檔目錄的路徑。
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```
## 步驟 2：設定 PDF 儲存選項
```csharp
var options = new PdfSaveOptions();
```
## 步驟 3：指定 X.509 證書
```csharp
var certificate = new X509Certificate2();
```
## 第 4 步：建立 PDF 簽名詳細信息
```csharp
var signatureDetails = new PdfDigitalSignatureDetails(
    //指定證書
    certificate,
    //指定簽名的原因
    "reason",
    //指定簽名地點
    "location",
    //指定簽署日期
    new DateTime(2019, 1, 1),
    //指定簽署的哈希演算法
    PdfDigitalSignatureHashAlgorithm.Sha1);
```
## 第 5 步：顯示簽名詳細信息
```csharp
Console.WriteLine("Certificate: " + signatureDetails.Certificate);
Console.WriteLine("Reason: " + signatureDetails.Reason);
Console.WriteLine("Location: " + signatureDetails.Location);
Console.WriteLine("Signature Date: " + signatureDetails.SignatureDate);
Console.WriteLine("Hash Algorithm: " + signatureDetails.HashAlgorithm);
```
## 第 6 步：設定數位簽名詳細信息
```csharp
//設定數位簽名詳細信息
options.DigitalSignatureDetails = signatureDetails;
```
## 第 7 步：使用加密詳細資料儲存項目
```csharp
//使用指定的加密詳細資訊儲存項目
project.Save(DataDir + "WorkWithPdfEncryptionDetails_out.pdf", options);
```
## 結論
恭喜！您已使用 Aspose.Tasks for .NET 成功配置了 Microsoft Project PDF 數位簽章詳細資料。透過執行以下步驟，您可以確保 MS Project 檔案的安全性和真實性。
## 常見問題解答
### Q：我可以使用自簽名憑證進行數位簽章嗎？
答：是的，您可以使用自簽名憑證進行測試。但是，對於生產環境，建議使用由憑證授權單位頒發的受信任憑證。
### Q：Aspose.Tasks 是否支援其他雜湊演算法進行數位簽章？
答：是的，Aspose.Tasks 支援各種數位簽章雜湊演算法，包括 SHA-1、SHA-256 和 SHA-512。
### Q：我可以自訂 PDF 中數位簽章的外觀嗎？
答：是的，您可以根據您的要求自訂數位簽名的外觀，包括文字、字體、顏色和位置。
### Q：數位簽章應用程式後是否可以刪除或更新？
答：不可以，數位簽章一旦套用於 PDF，就無法刪除或更新。但是，如果需要，您可以新增其他簽名。
### Q：Microsoft Project 檔案的大小或複雜性是否有任何限制？
答：Aspose.Tasks 可以無限制地處理各種大小和複雜程度的 Microsoft Project 檔案。但是，效能可能會因可用的硬體和資源而異。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
