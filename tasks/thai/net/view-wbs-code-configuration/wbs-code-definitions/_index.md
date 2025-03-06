---
title: การกำหนดคำจำกัดความรหัส WBS ใน Aspose.Tasks
linktitle: การกำหนดคำจำกัดความรหัส WBS ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks สำหรับ .NET ช่วยให้การจัดการโครงการมีประสิทธิภาพ เชี่ยวชาญโค้ด WBS ได้อย่างง่ายดายด้วยบทช่วยสอนที่ครอบคลุมของเรา ปรับปรุงขั้นตอนการทำงานวันนี้!
weight: 13
url: /th/net/view-wbs-code-configuration/wbs-code-definitions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดคำจำกัดความรหัส WBS ใน Aspose.Tasks

## การแนะนำ
เมื่อการจัดการโครงการพัฒนาขึ้น ความต้องการเครื่องมืออันทรงพลังที่ช่วยปรับปรุงกระบวนการก็เช่นกัน ในขอบเขตของการพัฒนา .NET Aspose.Tasks มีความโดดเด่นในฐานะไลบรารีที่มีประสิทธิภาพสำหรับจัดการงานการจัดการโครงการ ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการกำหนดรหัสโครงสร้างการแบ่งงาน (WBS) โดยใช้ Aspose.Tasks สำหรับ .NET รหัส WBS ทำให้เกิดลำดับชั้นของโครงการ ช่วยให้สามารถติดตามและจัดระเบียบได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้ด้านการทำงานของการพัฒนา .NET
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- โปรแกรมแก้ไขโค้ด (แนะนำให้ใช้ Visual Studio)
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
    
    using Aspose.Tasks.Saving;
```
ตอนนี้ เรามาแจกแจงกระบวนการกำหนดรหัส WBS ให้เป็นขั้นตอนที่สามารถจัดการได้

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
String DataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ
## ขั้นตอนที่ 2: เริ่มต้นโครงการ
```csharp
var project = new Project();
```
สร้างอินสแตนซ์โครงการใหม่โดยใช้ Aspose.Tasks
## ขั้นตอนที่ 3: กำหนดค่าคำจำกัดความรหัส WBS
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
ตั้งค่าพารามิเตอร์ข้อกำหนดโค้ด WBS เช่น การสร้างโค้ด การตรวจสอบเอกลักษณ์ และคำนำหน้าโค้ด
## ขั้นตอนที่ 4: กำหนดมาสก์รหัส WBS
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
ระบุตัวพรางโค้ด WBS ให้กับโค้ดโครงสร้างตามความยาว ตัวคั่น และลำดับ
## ขั้นตอนที่ 5: สร้างงานและคำนวณใหม่
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
project.Recalculate();
```
เพิ่มงานลงในลำดับชั้นของโครงการและคำนวณใหม่เพื่ออัปเดตรหัส WBS
## ขั้นตอนที่ 6: บันทึกโครงการ
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
บันทึกโครงการด้วยรหัส WBS ที่กำหนดไว้ใหม่
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจพลังของ Aspose.Tasks สำหรับ .NET ในการกำหนดโค้ด WBS เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มความสามารถในการจัดการโครงการ โดยนำโครงสร้างและประสิทธิภาพมาสู่เวิร์กโฟลว์ของคุณ
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ .NET ทุกรุ่นหรือไม่
ใช่ Aspose.Tasks รองรับ .NET เวอร์ชันต่างๆ เพื่อให้มั่นใจว่าสามารถเข้ากันได้กับสภาพแวดล้อมการพัฒนาที่หลากหลาย
### ฉันสามารถปรับแต่งรูปแบบโค้ด WBS เพิ่มเติมได้หรือไม่
อย่างแน่นอน. Aspose.Tasks มอบความยืดหยุ่นอย่างกว้างขวาง ช่วยให้คุณปรับแต่งโค้ด WBS ให้ตรงตามความต้องการเฉพาะของโปรเจ็กต์ได้
### มีข้อจำกัดเกี่ยวกับจำนวนรหัส WBS ที่ฉันสามารถกำหนดได้หรือไม่
Aspose.Tasks นำเสนอความสามารถในการปรับขนาด และคุณสามารถกำหนดรหัส WBS ได้จำนวนมากตามความซับซ้อนของโปรเจ็กต์ของคุณ
### ฉันจะแก้ไขปัญหาที่เกี่ยวข้องกับโค้ด WBS ในโครงการของฉันได้อย่างไร
 ฟอรัม Aspose.Tasks (ลิงก์ไปยัง[สนับสนุน](https://forum.aspose.com/c/tasks/15)) เป็นทรัพยากรที่มีคุณค่าในการขอความช่วยเหลือและแก้ไขปัญหาข้อสงสัย
### มีเวอร์ชันทดลองใช้ก่อนที่จะซื้อ Aspose.Tasks หรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติและความสามารถของ Aspose.Tasks ได้โดยเข้าไปที่[ทดลองฟรี](https://releases.aspose.com/) รุ่น
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
