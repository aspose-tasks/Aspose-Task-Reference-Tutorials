---
title: กำหนดการตั้งค่าหน้าโครงการ MS ด้วย Aspose.Tasks
linktitle: การกำหนดการตั้งค่าเพจใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดการตั้งค่าหน้า MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ปรับแต่งการวางแนว ขนาด และอื่นๆ ด้วยขั้นตอนง่ายๆ
weight: 20
url: /th/net/outline-code-page-settings/page-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดการตั้งค่าหน้าโครงการ MS ด้วย Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการกำหนดการตั้งค่าหน้า Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วย Visual Studio หรือ IDE ที่ต้องการอื่นๆ สำหรับการพัฒนา .NET

## การนำเข้าเนมสเปซ
ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณ เนมสเปซเหล่านี้ให้การเข้าถึงคลาส Aspose.Tasks และวิธีการที่จำเป็นสำหรับการจัดการไฟล์ MS Project
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
ขั้นแรก คุณต้องโหลดไฟล์ MS Project ที่คุณต้องการกำหนดการตั้งค่าเพจ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## ขั้นตอนที่ 2: เข้าถึงการตั้งค่าเพจ
ต่อไป คุณจะเข้าถึงการตั้งค่าหน้าของไฟล์โครงการ
```csharp
// รับการตั้งค่า
var settings = project.DefaultView.PageInfo.PageSettings;
```
## ขั้นตอนที่ 3: กำหนดการตั้งค่าหน้า
ตอนนี้ มากำหนดค่าคุณสมบัติต่างๆ ของการตั้งค่าเพจตามความต้องการของคุณกัน
```csharp
// ตั้งค่าการวางแนวหน้าเป็นแนวตั้ง
settings.IsPortrait = true;
// กำหนดจำนวนหน้ากว้างที่จะพิมพ์
settings.PagesInWidth = 5;
// กำหนดจำนวนหน้าสูงที่จะพิมพ์
settings.PagesInHeight = 7;
// ตั้งค่าเปอร์เซ็นต์ของขนาดปกติเพื่อปรับการพิมพ์
settings.PercentOfNormalSize = 200;
// กำหนดขนาดกระดาษ
settings.PaperSize = PrinterPaperSize.PaperB4;
// ตั้งค่าหมายเลขหน้าแรกสำหรับการพิมพ์
settings.FirstPageNumber = 3;
```
## ขั้นตอนที่ 4: บันทึกไฟล์โครงการ
สุดท้าย ให้บันทึกไฟล์โครงการด้วยการตั้งค่าหน้าที่อัปเดต
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีกำหนดการตั้งค่าหน้า Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถปรับแต่งการวางแนวหน้า ขนาด และตัวเลือกการพิมพ์อื่น ๆ ตามความต้องการของคุณได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถกำหนดการตั้งค่าหน้าสำหรับไฟล์ MS Project หลายไฟล์พร้อมกันได้หรือไม่
ตอบ: ได้ คุณสามารถวนซ้ำไฟล์โปรเจ็กต์หลายไฟล์และใช้การตั้งค่าหน้าเดียวกันกับแต่ละไฟล์ได้
### ถาม: เป็นไปได้ไหมที่จะเปลี่ยนการตั้งค่าหน้ากลับเป็นค่าเริ่มต้น?
ตอบ: แน่นอน คุณสามารถละเว้นขั้นตอนการกำหนดค่าหรือรีเซ็ตการตั้งค่าเป็นค่าเริ่มต้นได้
### ถาม: มีข้อจำกัดเกี่ยวกับขนาดกระดาษที่รองรับหรือไม่
ตอบ: Aspose.Tasks รองรับขนาดกระดาษที่หลากหลาย รวมถึงขนาดมาตรฐานและขนาดที่กำหนดเอง
### ถาม: ฉันสามารถทำให้กระบวนการกำหนดการตั้งค่าเพจเป็นแบบอัตโนมัติได้หรือไม่
ตอบ: แน่นอน คุณสามารถรวมฟังก์ชันนี้เข้ากับขั้นตอนการทำงานของแอปพลิเคชันของคุณเพื่อทำให้การกำหนดค่าการตั้งค่าเพจเป็นแบบอัตโนมัติได้
### ถาม: Aspose.Tasks รองรับไฟล์รูปแบบต่างๆ นอกเหนือจาก .mpp หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์รูปแบบต่างๆ เช่น XML, MPT และ HTML และอื่นๆ อีกมากมาย
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
