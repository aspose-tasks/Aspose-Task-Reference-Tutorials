---
title: การเรียนรู้มุมมองไทม์ไลน์ของโปรเจ็กต์ใน Aspose.Tasks
linktitle: การปรับแต่งมุมมองไทม์ไลน์ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Master Aspose.Tasks สำหรับ .NET ในการปรับแต่งมุมมองไทม์ไลน์ ปรับปรุงการจัดการโครงการของคุณด้วยไทม์ไลน์ที่ดึงดูดสายตาซึ่งปรับให้เหมาะกับความต้องการของโครงการของคุณ
weight: 13
url: /th/net/text-view-configuration/timeline-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้มุมมองไทม์ไลน์ของโปรเจ็กต์ใน Aspose.Tasks

## การแนะนำ
การสร้างมุมมองไทม์ไลน์ที่ดึงดูดสายตาและให้ข้อมูลเป็นสิ่งสำคัญสำหรับการจัดการโครงการที่มีประสิทธิภาพ Aspose.Tasks for .NET มอบโซลูชันที่แข็งแกร่งสำหรับการปรับแต่งมุมมองไทม์ไลน์ ซึ่งช่วยให้คุณปรับแต่งการแสดงงานตามความต้องการเฉพาะของโปรเจ็กต์ของคุณได้ ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีใช้ Aspose.Tasks เพื่อสร้างและปรับแต่งมุมมองไทม์ไลน์ได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และ .NET
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว ถ้าไม่เช่นนั้นให้ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tasks/net/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio
## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นในรหัส C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## ขั้นตอนที่ 1: เริ่มต้นโครงการและมุมมองไทม์ไลน์
เริ่มต้นด้วยการเริ่มต้นโครงการใหม่และมุมมองไทม์ไลน์:
```csharp
var project = new Project();
var view = new TimelineView();
```
## ขั้นตอนที่ 2: ตั้งค่าคุณสมบัติมุมมองไทม์ไลน์
ปรับแต่งมุมมองไทม์ไลน์โดยการตั้งค่าคุณสมบัติต่างๆ:
```csharp
view.DateFormat = DateFormat.DateDddDd;
view.DisplayOverlapped = true;
view.ShowPanZoom = true;
view.ShowTimescale = true;
view.ShowToday = true;
view.TextLinesCount = 2;
```
## ขั้นตอนที่ 3: แสดงรายละเอียดการดูรายละเอียดไทม์ไลน์
รับข้อมูลเกี่ยวกับมุมมองไทม์ไลน์:
```csharp
Console.WriteLine("Show Dates: " + view.ShowDates);
```
## ขั้นตอนที่ 4: เพิ่มมุมมองให้กับโครงการ
เพิ่มมุมมองไทม์ไลน์ที่กำหนดเองให้กับโปรเจ็กต์:
```csharp
project.Views.Add(view);
```
## ขั้นตอนที่ 5: เพิ่มข้อมูลการทดสอบลงในโครงการ
เติมโปรเจ็กต์ด้วยงานตัวอย่าง:
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task1.Set(Tsk.Duration, task1.ParentProject.GetDuration(24, TimeUnitType.Hour));
var task2 = project.RootTask.Children.Add("Task 2");
task2.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task2.Set(Tsk.Duration, task1.ParentProject.GetDuration(40, TimeUnitType.Hour));
```
## ขั้นตอนที่ 6: บันทึกโครงการเป็น PDF
บันทึกโปรเจ็กต์ด้วยมุมมองไทม์ไลน์ที่กำหนดเองเป็นไฟล์ PDF:
```csharp
project.Save("Your Document Directory/SetTimeScaleCount_out.pdf", SaveFileFormat.Pdf);
```
## บทสรุป
ยินดีด้วย! คุณปรับแต่งมุมมองไทม์ไลน์ได้สำเร็จโดยใช้ Aspose.Tasks สำหรับ .NET ไลบรารีอันทรงพลังนี้ช่วยลดความซับซ้อนของกระบวนการสร้างไทม์ไลน์ของโปรเจ็กต์ที่ดึงดูดสายตา เพิ่มความสามารถในการจัดการโปรเจ็กต์ของคุณ
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับเฟรมเวิร์ก .NET อื่นหรือไม่
ใช่ Aspose.Tasks รองรับเฟรมเวิร์ก .NET ที่หลากหลาย เพื่อให้มั่นใจว่าสามารถเข้ากันได้กับสภาพแวดล้อมการพัฒนาของคุณ
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของงานแต่ละงานในมุมมองไทม์ไลน์ได้หรือไม่
อย่างแน่นอน! Aspose.Tasks ให้ความยืดหยุ่นในการปรับแต่งลักษณะที่ปรากฏของแต่ละงานในมุมมองไทม์ไลน์
### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 เยี่ยมชม[เอกสารประกอบ Aspose.Tasks](https://reference.aspose.com/tasks/net/)สำหรับคำแนะนำที่ครอบคลุมและ[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือ.
### Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
