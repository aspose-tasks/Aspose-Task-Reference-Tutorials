---
title: การวัดการใช้งานโครงการ MS ด้วย Aspose.Tasks สำหรับ .NET
linktitle: การใช้การวัดแสงใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีการตรวจสอบและเพิ่มประสิทธิภาพการใช้งาน MS Project ของคุณด้วย Aspose.Tasks for .NET ได้อย่างมีประสิทธิภาพ คำแนะนำทีละขั้นตอนเพื่อการจัดการโครงการที่มีประสิทธิภาพ
type: docs
weight: 17
url: /th/net/license-management/metering-usage/
---
## การแนะนำ
คุณต้องการจัดการและตรวจสอบการใช้งาน MS Project ของคุณด้วย Aspose.Tasks อย่างมีประสิทธิภาพหรือไม่? ด้วยพลังของการวัด คุณสามารถติดตามการใช้งานและเพิ่มประสิทธิภาพการจัดการโครงการของคุณได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการวัดการใช้งาน MS Project ทีละขั้นตอนโดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกการใช้งาน MS Project การวัดผล ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/net/), ปฏิบัติตามคำแนะนำในการติดตั้งเพื่อตั้งค่าไลบรารีในสภาพแวดล้อมการพัฒนาของคุณ
2.  กุญแจสาธารณะและกุญแจส่วนตัว: รับกุญแจสาธารณะและกุญแจส่วนตัวของคุณจาก Aspose ปุ่มเหล่านี้จำเป็นสำหรับการใช้งานการวัดแสง หากคุณยังไม่มีกุญแจ คุณสามารถขอได้จาก Aspose ผ่านทาง[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) หน้าหนังสือ.

## นำเข้าเนมสเปซ
ก่อนดำเนินการต่อ ให้นำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ของคุณ:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Net;

```
## ขั้นตอนที่ 1: ตั้งค่าการวัดแสง
หากต้องการเริ่มวัดการใช้งาน MS Project ให้ตั้งค่าสภาพแวดล้อมแบบวัดแสงโดยระบุกุญแจสาธารณะและกุญแจส่วนตัวของคุณ:
```csharp
String DataDir = "Your Document Directory";
var metered = new Metered();
metered.SetMeteredKey("<public key>", "<private key>");
```
 แทนที่`"Your Document Directory"` ด้วยเส้นทางไปยังไดเร็กทอรีเอกสารของคุณและทดแทน`<public key>` และ`<private key>` ด้วยกุญแจจริงของคุณที่ได้รับจาก Aspose
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ MS
จากนั้น โหลดไฟล์ MS Project ของคุณโดยใช้ Aspose.Tasks:
```csharp
var project = new Project(DataDir + "Project2.mpp");
Console.WriteLine("Project Name: " + project.Get(Prj.Name));
```
ขั้นตอนนี้จะโหลดไฟล์ MS Project ชื่อ "Project2.mpp" จากไดเร็กทอรีที่ระบุ คุณสามารถเปลี่ยนชื่อไฟล์ด้วยไฟล์ MS Project ของคุณเองได้
## ขั้นตอนที่ 3: ทำงานกับโครงการ
เมื่อโหลดโครงการแล้ว คุณสามารถดำเนินการต่างๆ ได้ตามความต้องการสำหรับงานการจัดการโครงการของคุณ
```csharp
// ดำเนินงานการจัดการโครงการที่นี่
```
## ขั้นตอนที่ 4: ตรวจสอบเครดิตและการใช้ไบต์
คุณสามารถตรวจสอบเครดิตที่ใช้ไปและจำนวนไบต์ที่ใช้ไปในระหว่างช่วงการใช้งานของคุณ:
```csharp
try
{
    Console.WriteLine("Credits spent: {0}", Metered.GetConsumptionCredit());
    Console.WriteLine("Bytes consumed: {0}", Metered.GetConsumptionQuantity());
}
catch (WebException)
{
    // จัดการข้อยกเว้นที่นี่
}
```
ขั้นตอนนี้จะดึงและแสดงเครดิตที่ใช้ไปและจำนวนไบต์ที่ใช้โดยการดำเนินงานของคุณ จัดการกับข้อยกเว้นใด ๆ ที่อาจเกิดขึ้นระหว่างกระบวนการนี้
## ขั้นตอนที่ 5: รีเซ็ตคีย์แบบมิเตอร์
หรือคุณสามารถรีเซ็ตคีย์แบบมิเตอร์เพื่อหยุดนับไบต์ได้:
```csharp
metered.ResetMeteredKey();
```
ขั้นตอนนี้จะหยุดกระบวนการวัดแสงและรีเซ็ตปุ่มวัดแสง

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีวัดการใช้งาน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถตรวจสอบและเพิ่มประสิทธิภาพความพยายามในการจัดการโครงการของคุณได้อย่างมีประสิทธิภาพ ในขณะเดียวกันก็รับประกันการใช้ทรัพยากรอย่างมีประสิทธิภาพ
### คำถามที่พบบ่อย
### ถาม: ฉันสามารถวัดการใช้งานไฟล์ MS Project หลายไฟล์ได้หรือไม่
ตอบ: ได้ คุณสามารถวัดการใช้งานไฟล์ MS Project หลายไฟล์ได้โดยการโหลดแต่ละไฟล์แยกกัน และตรวจสอบการใช้งานตามนั้น
### ถาม: การใช้งานการวัดปริมาณ MS Project เข้ากันได้กับ Aspose.Tasks for .NET ทุกเวอร์ชันหรือไม่
ตอบ: ได้ รองรับการใช้งาน Metering MS Project ใน Aspose.Tasks สำหรับ .NET ทุกเวอร์ชัน
### ถาม: ฉันจำเป็นต้องเชื่อมต่ออินเทอร์เน็ตเพื่อใช้งานการตรวจวัดหรือไม่
ตอบ: ใช่ จำเป็นต้องมีการเชื่อมต่ออินเทอร์เน็ตเพื่อสื่อสารกับเซิร์ฟเวอร์ของ Aspose สำหรับการใช้งานการวัดแสง
### ถาม: ฉันสามารถติดตามการใช้งานแบบเรียลไทม์ได้หรือไม่
ตอบ: ได้ คุณสามารถติดตามการใช้งานแบบเรียลไทม์ได้โดยตรวจสอบเครดิตที่ใช้ไปและจำนวนไบต์ที่ใช้ไปเป็นระยะๆ
### ถาม: การใช้งาน Metering MS Project มีให้ใช้งานในเวอร์ชันทดลองใช้งานหรือไม่
ตอบ: ได้ การใช้งานการวัดปริมาณการใช้งาน MS Project มีให้บริการใน Aspose.Tasks สำหรับ .NET เวอร์ชันทดลองและเวอร์ชันลิขสิทธิ์