---
title: การเรียนรู้ลำดับ WBS ด้วย Aspose.Tasks สำหรับ .NET
linktitle: การกำหนดลำดับ WBS ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เสริมศักยภาพการจัดการโครงการของคุณด้วย Aspose.Tasks สำหรับ .NET – กำหนดลำดับ WBS ได้อย่างราบรื่นและเพิ่มประสิทธิภาพได้อย่างง่ายดาย #Aspose #งาน #โครงการ MS
type: docs
weight: 16
url: /th/net/view-wbs-code-configuration/wbs-sequences/
---
## การแนะนำ
คุณกำลังทำงานกับแอปพลิเคชันการจัดการโครงการและต้องการเครื่องมือที่มีประสิทธิภาพในการจัดการลำดับโครงสร้างการแบ่งงาน (WBS) หรือไม่? ไม่ต้องมองหาที่ไหนนอกจาก Aspose.Tasks สำหรับ .NET ซึ่งเป็นไลบรารีอันทรงพลังที่ทำให้งานการจัดการโครงการง่ายขึ้น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการกำหนดลำดับ WBS ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- [ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET](https://releases.aspose.com/tasks/net/)
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
- สภาพแวดล้อมการพัฒนาที่ตั้งค่าสำหรับโครงการ .NET
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.Tasks เพิ่มสิ่งต่อไปนี้ที่จุดเริ่มต้นของสคริปต์ของคุณ:
```csharp
    
    using Aspose.Tasks.Saving;
```
## การกำหนดลำดับ WBS - คำแนะนำทีละขั้นตอน
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project();
```
## ขั้นตอนที่ 2: กำหนดค่าคำจำกัดความรหัส WBS
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## ขั้นตอนที่ 3: กำหนดมาสก์รหัส WBS
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
## ขั้นตอนที่ 4: เพิ่มงานในโครงการ
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
```
## ขั้นตอนที่ 5: คำนวณข้อมูลโครงการใหม่
```csharp
project.Recalculate();
```
## ขั้นตอนที่ 6: บันทึกโครงการ
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
ยินดีด้วย! คุณได้กำหนดลำดับ WBS ในโครงการของคุณสำเร็จแล้วโดยใช้ Aspose.Tasks สำหรับ .NET
## บทสรุป
การจัดการลำดับ WBS เป็นสิ่งสำคัญสำหรับการจัดการโครงการที่มีประสิทธิภาพ และ Aspose.Tasks สำหรับ .NET ทำให้งานนี้ราบรื่น ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถปรับปรุงฟังก์ชัน WBS ในแอปพลิเคชันการจัดการโครงการของคุณได้
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Tasks รองรับ .NET Core ทำให้คุณสามารถสร้างแอปพลิเคชันข้ามแพลตฟอร์มได้
### ฉันสามารถปรับแต่งรูปแบบโค้ด WBS เพิ่มเติมได้หรือไม่
อย่างแน่นอน! Aspose.Tasks ให้ความยืดหยุ่นในการกำหนดรหัส WBS ตามความต้องการของโครงการของคุณ
### มีรุ่นทดลองใช้งานหรือไม่?
 ใช่คุณสามารถ[ดาวน์โหลดรุ่นทดลองใช้ฟรี](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติก่อนตัดสินใจซื้อ
### ฉันจะรับการสนับสนุนจากชุมชนสำหรับ Aspose.Tasks ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อเชื่อมต่อกับชุมชนและขอความช่วยเหลือ
### มีใบอนุญาตชั่วคราวหรือไม่
 ใช่ คุณจะได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ