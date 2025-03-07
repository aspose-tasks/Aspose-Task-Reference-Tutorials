---
title: การเรียนรู้มาสก์โค้ด WBS ด้วย Aspose.Tasks สำหรับ .NET
linktitle: คอลเลกชันของ WBS Code Masks ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: ปรับปรุงการจัดการโครงการด้วย Aspose.Tasks สำหรับ .NET เรียนรู้การสร้าง จัดการ และถ่ายโอน WBS Code Masks ได้อย่างง่ายดายในบทช่วยสอนที่ครอบคลุมนี้
weight: 15
url: /th/net/view-wbs-code-configuration/wbs-code-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้มาสก์โค้ด WBS ด้วย Aspose.Tasks สำหรับ .NET

## การแนะนำ
ในโลกที่มีการเปลี่ยนแปลงตลอดเวลาของการจัดการโครงการ การจัดระเบียบงานอย่างมีประสิทธิภาพเป็นสิ่งสำคัญ Aspose.Tasks สำหรับ .NET มอบโซลูชันอันทรงพลังในการจัดการโค้ดโครงสร้างการแบ่งงานโครงการ (WBS) ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเจาะลึกคอลเลกชั่นของ WBS Code Masks โดยสำรวจวิธีการนำไปใช้และจัดการมาสก์เหล่านั้นโดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มการเดินทางเขียนโค้ดนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
-  Aspose.Tasks สำหรับ .NET ที่ติดตั้งในสภาพแวดล้อมการพัฒนาของคุณ ถ้าไม่เช่นนั้นให้ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tasks/net/).
- โปรแกรมแก้ไขโค้ดเช่น Visual Studio เพื่อประสบการณ์การเขียนโค้ดที่ราบรื่น
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็น:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. เริ่มต้นโครงการและคำจำกัดความรหัส WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. กำหนดมาสก์รหัส WBS
ล้างโค้ดมาสก์ที่มีอยู่และเพิ่มอันใหม่:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. แสดงข้อมูลโค้ดมาสก์
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. เพิ่มงานในโครงการ
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. ดึงข้อมูลงาน
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. จัดการโค้ดมาสก์
ลบโค้ดมาสก์และตรวจสอบให้แน่ใจว่าได้ลบออกแล้ว:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. คัดลอกโค้ดมาสก์ไปยังโปรเจ็กต์อื่น
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. แสดงโค้ดมาสก์ในอีกโปรเจ็กต์
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. เพิ่มงานในโครงการอื่น
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. แสดงรหัส WBS ในโครงการอื่น
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## บทสรุป
ด้วย Aspose.Tasks สำหรับ .NET การจัดการรหัส WBS จะกลายเป็นงานที่ง่ายดาย บทช่วยสอนนี้ครอบคลุมถึงการสร้าง การปรับแต่ง และการถ่ายโอน WBS Code Masks โดยให้คำแนะนำที่ครอบคลุมเพื่อปรับปรุงประสบการณ์การจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่
ตอบ: Aspose.Tasks รองรับภาษา .NET เป็นหลัก แต่คุณสามารถสำรวจตัวเลือกความสามารถในการทำงานร่วมกันกับภาษาอื่นได้
### ถาม: Aspose.Tasks สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดเวอร์ชันทดลองได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะขอความช่วยเหลือหรือรายงานปัญหาเกี่ยวกับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปราย
### ถาม: วัตถุประสงค์ของรหัส WBS ในการจัดการโครงการคืออะไร
ตอบ: รหัส WBS ช่วยจัดระเบียบและจัดโครงสร้างงานโครงการตามลำดับชั้น ซึ่งเป็นแนวทางที่เป็นระบบในการวางแผนโครงการ
### ถาม: ฉันสามารถปรับแต่งรูปแบบของรหัส WBS ใน Aspose.Tasks สำหรับ .NET ได้หรือไม่
ตอบ: แน่นอน คุณสามารถควบคุมรูปแบบและโครงสร้างของโค้ด WBS ได้อย่างสมบูรณ์โดยใช้ Aspose.Tasks สำหรับ .NET
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
