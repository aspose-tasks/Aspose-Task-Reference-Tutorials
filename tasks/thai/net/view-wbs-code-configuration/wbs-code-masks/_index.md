---
title: การกำหนดค่ารหัส WBS ทีละขั้นตอนใน Aspose.Tasks .NET
linktitle: การกำหนดค่ามาสก์รหัส WBS ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจการกำหนดค่า WBS Code Masks ทีละขั้นตอนในโครงการ .NET โดยใช้ Aspose.Tasks ปรับปรุงความสามารถในการจัดการโครงการได้อย่างง่ายดาย
weight: 14
url: /th/net/view-wbs-code-configuration/wbs-code-masks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดค่ารหัส WBS ทีละขั้นตอนใน Aspose.Tasks .NET

## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาจัดการข้อมูลการจัดการโครงการในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจกระบวนการกำหนดค่ามาสก์โค้ดโครงสร้างการแบ่งงาน (WBS) โดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Tasks สำหรับเอกสาร .NET](https://reference.aspose.com/tasks/net/).
- สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้
- ไดเร็กทอรีเอกสาร: เลือกไดเร็กทอรีในระบบของคุณเพื่อจัดเก็บไฟล์โปรเจ็กต์
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์โปรเจ็กต์
เริ่มต้นด้วยการสร้างอินสแตนซ์โครงการใหม่:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## ขั้นตอนที่ 2: กำหนดคำจำกัดความรหัส WBS
ตั้งค่าคำจำกัดความรหัส WBS สำหรับโครงการของคุณ:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## ขั้นตอนที่ 3: เพิ่มมาสก์รหัส WBS
กำหนด WBS Code Masks และเพิ่มลงในโปรเจ็กต์:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## ขั้นตอนที่ 4: สร้างงาน
เพิ่มงานในโครงการ:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## ขั้นตอนที่ 5: คำนวณใหม่
คำนวณโครงการใหม่เพื่อให้แน่ใจว่ามีการใช้รหัส WBS อย่างถูกต้อง:
```csharp
project.Recalculate();
```
## ขั้นตอนที่ 6: แสดงข้อมูลมาสก์ WBS
ข้อมูลเอาต์พุตเกี่ยวกับมาสก์ WBS ไปยังคอนโซล:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## ขั้นตอนที่ 7: บันทึกโครงการ
บันทึกโครงการด้วยรหัส WBS ที่เพิ่มเข้ามา:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
ยินดีด้วย! คุณได้กำหนดค่า WBS Code Masks ในโปรเจ็กต์ Aspose.Tasks เรียบร้อยแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการทีละขั้นตอนในการกำหนดค่า WBS Code Mask โดยใช้ Aspose.Tasks สำหรับ .NET ไลบรารี่อันทรงพลังนี้ช่วยให้นักพัฒนามีวิธีที่ราบรื่นในการปรับปรุงความสามารถในการจัดการโครงการภายในแอปพลิเคชัน .NET ของตน

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks ได้ฟรีหรือไม่
 Aspose.Tasks ให้ทดลองใช้ฟรีซึ่งคุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาการสนับสนุนเพิ่มเติมได้จากที่ไหน?
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อสนับสนุนชุมชน
### ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### มีเอกสารรายละเอียดไหม?
 ใช่ มีเอกสารประกอบครบถ้วน[ที่นี่](https://reference.aspose.com/tasks/net/).
### ฉันจะซื้อ Aspose.Tasks ได้ที่ไหน
 ซื้อ Aspose.Tasks[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
