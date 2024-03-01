---
title: บันทึกตัวเลือกโครงการ MS สำหรับ Aspose.Tasks ได้อย่างง่ายดาย
linktitle: ตัวเลือกการบันทึก MPP สำหรับ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีบันทึกตัวเลือก MS Project ได้อย่างง่ายดายด้วย Aspose.Tasks for .NET เพิ่มประสิทธิภาพการจัดการโครงการของคุณ
type: docs
weight: 12
url: /th/net/saving-options/mpp-save-options/
---
## การแนะนำ
ในโลกของการพัฒนา .NET การจัดการและการจัดการไฟล์โครงการอย่างมีประสิทธิภาพเป็นสิ่งสำคัญสำหรับความสำเร็จ Aspose.Tasks for .NET นำเสนอโซลูชันอันทรงพลังในการจัดการไฟล์ Microsoft Project (MPP) ได้อย่างง่ายดาย ในบรรดาคุณสมบัติมากมาย Aspose.Tasks ช่วยให้ผู้ใช้สามารถบันทึกตัวเลือก MS Project ได้อย่างราบรื่น ปรับปรุงขั้นตอนการทำงานและรับประกันความสมบูรณ์ของโครงการ ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการบันทึกตัวเลือก MS Project โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio
3. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เป็นสิ่งจำเป็นสำหรับการนำตัวอย่างไปใช้

## นำเข้าเนมสเปซ
ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ เนมสเปซเหล่านี้ให้การเข้าถึงฟังก์ชันการทำงานของ Aspose.Tasks สำหรับ .NET

```csharp
using Aspose.Tasks;
using System;
using System.IO;

using Aspose.Tasks.Saving;
```

ตอนนี้ เรามาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอนเพื่อทำความเข้าใจโดยละเอียด
## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร
```csharp
String DataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: เริ่มต้น FileStream
```csharp
using Aspose.Tasks;
using (var stream = new FileStream(DataDir + "EmptyProjectSaveStream_out.xml", FileMode.Create, FileAccess.Write))
{
```
## ขั้นตอนที่ 3: โหลดไฟล์โครงการ
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## ขั้นตอนที่ 4: สร้างตัวเลือกการบันทึก
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
	RemoveInvalidAssignments = true
};
```
## ขั้นตอนที่ 5: บันทึกโครงการด้วยตัวเลือก
```csharp
project.Save(stream, options);
```

## บทสรุป
การเรียนรู้ศิลปะในการบันทึกตัวเลือก MS Project โดยใช้ Aspose.Tasks สำหรับ .NET จะช่วยเพิ่มความสามารถในการจัดการโครงการของคุณได้อย่างมาก ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณจะสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น เพื่อให้มั่นใจถึงประสิทธิภาพและความแม่นยำในการจัดการไฟล์โปรเจ็กต์

## คำถามที่พบบ่อย
### Aspose.Tasks สำหรับ .NET เข้ากันได้กับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่
ใช่ Aspose.Tasks สำหรับ .NET รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึง MPP, MPT, XML และอื่นๆ
### ฉันสามารถลองใช้ Aspose.Tasks สำหรับ .NET ก่อนซื้อได้หรือไม่
 แน่นอน! คุณสามารถดาวน์โหลด Aspose.Tasks สำหรับ .NET รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนด้านเทคนิคสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
หากต้องการความช่วยเหลือด้านเทคนิค คุณสามารถไปที่ฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ใบอนุญาตชั่วคราวคืออะไร และฉันจะขอรับใบอนุญาตได้อย่างไร
 ใบอนุญาตชั่วคราวช่วยให้คุณสามารถประเมิน Aspose.Tasks สำหรับ .NET ได้โดยไม่มีข้อจำกัดใดๆ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.Tasks สำหรับ .NET เวอร์ชันลิขสิทธิ์ได้ที่ไหน
 คุณสามารถซื้อ Aspose.Tasks สำหรับ .NET เวอร์ชันลิขสิทธิ์ได้จาก[ที่นี่](https://purchase.aspose.com/buy).