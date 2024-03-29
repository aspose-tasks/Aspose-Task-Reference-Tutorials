---
title: รูปภาพบันทึกตัวเลือกโครงการ MS สำหรับ Aspose.Tasks
linktitle: ตัวเลือกการบันทึกรูปภาพสำหรับ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีบันทึกตัวเลือก MS Project เป็นรูปภาพโดยใช้ Aspose.Tasks สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
type: docs
weight: 11
url: /th/net/saving-options/image-save-options/
---

## การแนะนำ
ในโลกของการพัฒนาซอฟต์แวร์ การจัดการงานโครงการอย่างมีประสิทธิภาพเป็นสิ่งสำคัญสำหรับการจัดการโครงการที่ประสบความสำเร็จ Aspose.Tasks for .NET นำเสนอโซลูชันอันทรงพลังสำหรับนักพัฒนาที่ทำงานกับไฟล์ Microsoft Project ช่วยให้พวกเขาสามารถจัดการ แปลง และจัดการงานของโครงการได้อย่างราบรื่นภายในแอปพลิเคชัน .NET ของตน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ Aspose.Tasks สำหรับ .NET เพื่อบันทึกตัวเลือก MS Project เป็นรูปภาพ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ติดตั้ง Aspose.Tasks สำหรับ .NET
ในการเริ่มต้น คุณจะต้องติดตั้ง Aspose.Tasks for .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[เว็บไซต์](https://releases.aspose.com/tasks/net/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้
### 2. รับใบอนุญาต (ไม่บังคับ)
 แม้ว่า Aspose.Tasks สำหรับ .NET สามารถใช้งานได้โดยไม่ต้องมีใบอนุญาตในโหมดการประเมินผล แต่ขอแนะนำให้ขอรับใบอนุญาตสำหรับการใช้งานเต็มรูปแบบและเพื่อลบข้อจำกัดในการประเมิน คุณสามารถขอรับใบอนุญาตได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy) หรือเลือกใช้ก[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ
### 3. ความรู้พื้นฐานเกี่ยวกับการพัฒนา C# และ .NET
ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# และเฟรมเวิร์ก .NET เป็นสิ่งจำเป็นในการปฏิบัติตามตัวอย่างและรวมฟังก์ชัน Aspose.Tasks เข้ากับแอปพลิเคชันของคุณอย่างมีประสิทธิภาพ
## นำเข้าเนมสเปซ
ก่อนที่เราจะเริ่มบันทึกตัวเลือก MS Project เป็นอิมเมจโดยใช้ Aspose.Tasks สำหรับ .NET เราต้องแน่ใจว่าเรานำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ C# ของเรา:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร
ตรวจสอบให้แน่ใจว่าคุณมีไดเร็กทอรีที่กำหนดสำหรับเอกสารของคุณและตั้งค่าเส้นทางตาม:
```csharp
String DataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ MS
 เริ่มต้นใหม่`Project` วัตถุโดยการโหลดไฟล์ MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## ขั้นตอนที่ 3: กำหนดตัวเลือกการบันทึกรูปภาพ
 สร้างอินสแตนซ์ของ`ImageSaveOptions`และระบุการตั้งค่าที่ต้องการ:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## ขั้นตอนที่ 4: ระบุหน้าที่จะบันทึก
หากจำเป็น ให้ระบุหน้าที่จะบันทึก ในตัวอย่างนี้ เรากำลังเพิ่มหน้าที่ 2:
```csharp
options.Pages.Add(2);
```
## ขั้นตอนที่ 5: บันทึกรูปภาพ
สุดท้าย ให้บันทึกหน้าที่เลือกเป็นรูปภาพพร้อมตัวเลือกที่ระบุ:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## บทสรุป
Aspose.Tasks สำหรับ .NET ช่วยให้กระบวนการทำงานกับไฟล์ MS Project ง่ายขึ้น ช่วยให้นักพัฒนาจัดการงานของโครงการได้อย่างง่ายดาย ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถบันทึกตัวเลือก MS Project เป็นรูปภาพภายในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET โดยไม่มีใบอนุญาตได้หรือไม่
ตอบ: ได้ คุณสามารถใช้ Aspose.Tasks สำหรับ .NET ได้โดยไม่ต้องมีใบอนุญาตในโหมดการประเมินผล อย่างไรก็ตาม ขอแนะนำให้ขอรับใบอนุญาตสำหรับการใช้งานเต็มรูปแบบและนำข้อจำกัดในการประเมินออก
### คำถามที่ 2: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับการทดสอบได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
### คำถามที่ 3: Aspose.Tasks สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET อื่นๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ รวมถึง .NET Core และ .NET Standard
### คำถามที่ 4: ฉันสามารถปรับแต่งตัวเลือกการบันทึกรูปภาพเพิ่มเติมได้หรือไม่
ตอบ: ได้ คุณสามารถปรับแต่งตัวเลือกการบันทึกรูปภาพได้ตามความต้องการเฉพาะของคุณ เช่น การปรับขนาดหน้า ความละเอียด หรือรูปแบบเอาต์พุต
### คำถามที่ 5: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือสำหรับ Aspose.Tasks สำหรับ .NET ได้จาก[ฟอรั่ม](https://forum.aspose.com/c/tasks/15).