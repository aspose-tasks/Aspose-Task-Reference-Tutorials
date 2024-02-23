---
title: กำหนดค่าลายเซ็นดิจิทัล MS Project PDF ด้วย Aspose.Tasks
linktitle: กำหนดค่ารายละเอียดลายเซ็นดิจิทัล PDF ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดค่ารายละเอียดลายเซ็นดิจิทัล Microsoft Project PDF โดยใช้ Aspose.Tasks สำหรับ .NET รับประกันความปลอดภัยและความถูกต้องของไฟล์โครงการของคุณ
type: docs
weight: 10
url: /th/net/pdf-security-configuration/pdf-digital-signature-details/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการกำหนดค่ารายละเอียดลายเซ็นดิจิทัล Microsoft Project PDF โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถรวมลายเซ็นดิจิทัลเข้ากับไฟล์ MS Project ของคุณได้อย่างราบรื่น มั่นใจในความปลอดภัยและความถูกต้อง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Tasks for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks for .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ไฟล์โครงการ Microsoft: เตรียมไฟล์โครงการ Microsoft ที่คุณต้องการใช้งานและตรวจสอบให้แน่ใจว่าสามารถเข้าถึงได้ภายในไดเรกทอรีโครงการของคุณ
3. ใบรับรอง X.509: รับใบรับรอง X.509 ที่จะใช้สำหรับการเซ็นชื่อดิจิทัล หากคุณไม่มี คุณสามารถสร้างใบรับรองที่ลงนามด้วยตนเองเพื่อการทดสอบได้
## การนำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ .NET ของคุณเพื่อเข้าถึงคลาสและวิธีการที่จำเป็นจาก Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;
using System.Security.Cryptography;
using System.Security.Cryptography.X509Certificates;

using Aspose.Tasks.Saving;
```
ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ Microsoft
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```
## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการบันทึก PDF
```csharp
var options = new PdfSaveOptions();
```
## ขั้นตอนที่ 3: ระบุใบรับรอง X.509
```csharp
var certificate = new X509Certificate2();
```
## ขั้นตอนที่ 4: สร้างรายละเอียดลายเซ็น PDF
```csharp
var signatureDetails = new PdfDigitalSignatureDetails(
    // ระบุใบรับรอง
    certificate,
    // ระบุเหตุผลในการลงนาม
    "reason",
    // ระบุสถานที่ลงนาม
    "location",
    // ระบุวันที่ลงนาม
    new DateTime(2019, 1, 1),
    // ระบุอัลกอริทึมแฮชของการลงนาม
    PdfDigitalSignatureHashAlgorithm.Sha1);
```
## ขั้นตอนที่ 5: แสดงรายละเอียดลายเซ็น
```csharp
Console.WriteLine("Certificate: " + signatureDetails.Certificate);
Console.WriteLine("Reason: " + signatureDetails.Reason);
Console.WriteLine("Location: " + signatureDetails.Location);
Console.WriteLine("Signature Date: " + signatureDetails.SignatureDate);
Console.WriteLine("Hash Algorithm: " + signatureDetails.HashAlgorithm);
```
## ขั้นตอนที่ 6: ตั้งค่ารายละเอียดลายเซ็นดิจิทัล
```csharp
// ตั้งค่ารายละเอียดลายเซ็นดิจิทัล
options.DigitalSignatureDetails = signatureDetails;
```
## ขั้นตอนที่ 7: บันทึกโครงการพร้อมรายละเอียดการเข้ารหัส
```csharp
// บันทึกโครงการพร้อมรายละเอียดการเข้ารหัสที่ระบุ
project.Save(DataDir + "WorkWithPdfEncryptionDetails_out.pdf", options);
```
## บทสรุป
ยินดีด้วย! คุณได้กำหนดค่ารายละเอียดลายเซ็นดิจิทัล Microsoft Project PDF โดยใช้ Aspose.Tasks สำหรับ .NET เรียบร้อยแล้ว เมื่อทำตามขั้นตอนเหล่านี้ คุณจะมั่นใจได้ในความปลอดภัยและความถูกต้องของไฟล์ MS Project ของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ใบรับรองที่ลงนามด้วยตนเองสำหรับการลงนามดิจิทัลได้หรือไม่
ตอบ: ได้ คุณสามารถใช้ใบรับรองที่ลงนามด้วยตนเองเพื่อการทดสอบได้ อย่างไรก็ตาม สำหรับสภาพแวดล้อมการใช้งานจริง ขอแนะนำให้ใช้ใบรับรองที่เชื่อถือได้ซึ่งออกโดยผู้ออกใบรับรอง
### ถาม: Aspose.Tasks รองรับอัลกอริธึมแฮชอื่นๆ สำหรับการเซ็นชื่อดิจิทัลหรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับอัลกอริธึมแฮชที่หลากหลายสำหรับการเซ็นชื่อดิจิทัล รวมถึง SHA-1, SHA-256 และ SHA-512
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นดิจิทัลใน PDF ได้หรือไม่
ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นดิจิทัลได้ รวมถึงข้อความ แบบอักษร สี และตำแหน่ง ตามความต้องการของคุณ
### ถาม: เป็นไปได้ไหมที่จะลบหรืออัปเดตลายเซ็นดิจิทัลเมื่อนำไปใช้แล้ว
ตอบ: ไม่ได้ เมื่อใช้ลายเซ็นดิจิทัลกับ PDF แล้ว จะไม่สามารถลบหรืออัปเดตได้ อย่างไรก็ตาม คุณสามารถเพิ่มลายเซ็นเพิ่มเติมได้หากจำเป็น
### ถาม: มีข้อจำกัดเกี่ยวกับขนาดหรือความซับซ้อนของไฟล์ Microsoft Project หรือไม่
ตอบ: Aspose.Tasks สามารถจัดการไฟล์ Microsoft Project ในขนาดและความซับซ้อนต่างๆ ได้โดยไม่มีข้อจำกัด อย่างไรก็ตาม ประสิทธิภาพอาจแตกต่างกันไปขึ้นอยู่กับฮาร์ดแวร์และทรัพยากรที่มีอยู่