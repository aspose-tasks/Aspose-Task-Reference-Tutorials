---
title: การจัดการมุมมองโครงการ MS ได้อย่างง่ายดายด้วย Aspose.Tasks .NET
linktitle: การรวบรวมมุมมองใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจ Aspose.Tasks สำหรับ .NET และฝึกฝนศิลปะในการจัดการ MS Project Views ได้อย่างง่ายดาย ดาวน์โหลดตอนนี้เพื่อรับประสบการณ์การจัดการโครงการที่ราบรื่น
type: docs
weight: 11
url: /th/net/view-wbs-code-configuration/view-collection/
---
## การแนะนำ
ยินดีต้อนรับสู่โลกของ Aspose.Tasks สำหรับ .NET ไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการ Microsoft Project Views ในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะเจาะลึกถึงสิ่งสำคัญในการจัดการ MS Project Views โดยใช้ Aspose.Tasks ซึ่งจะให้คำแนะนำแบบทีละขั้นตอนเพื่อปรับปรุงความสามารถในการจัดการโครงการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางครั้งนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Tasks Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
- .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนเครื่องพัฒนาของคุณ
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการเริ่มต้นโปรเจ็กต์ของคุณโดยใช้ไลบรารี Aspose.Tasks
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
## ขั้นตอนที่ 2: แก้ไขมุมมองที่มีอยู่
วนซ้ำรายการมุมมองและทำการแก้ไขตามความจำเป็น ในตัวอย่างนี้ เราจะเปลี่ยนข้อความส่วนหัวของแต่ละมุมมอง
```csharp
List<View> list = project.Views.ToList();
for (var index = 0; index < list.Count; index++)
{
    var viewToChange = list[index];
    viewToChange.PageInfo.Header.CenteredText = "Header " + index;
}
```
## ขั้นตอนที่ 3: เพิ่มมุมมองใหม่
ขยายโครงการของคุณโดยการเพิ่มมุมมองใหม่ เช่น แผนภูมิแกนต์
```csharp
var view = new GanttChartView();
if (!project.Views.IsReadOnly)
{
    project.Views.Add(view);
}
```
## ขั้นตอนที่ 4: วนซ้ำการดู
แสดงข้อมูลเกี่ยวกับมุมมองที่มีอยู่ภายในโครงการ
```csharp
Console.WriteLine("Iterate over views of " + project.Views.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Project view count: " + project.Views.Count);
Console.WriteLine();
foreach (var projectView in project.Views)
{
    Console.WriteLine("Name: " + projectView.Name);
}
```
## ขั้นตอนที่ 5: ลบมุมมอง
เรียนรู้วิธีลบมุมมองทั้งหมดพร้อมกันหรือทีละรายการ
### แนวทางที่ 1:
```csharp
List<View> listToDelete = project.Views.ToList();
foreach (var v in listToDelete)
{
    if (project.Views.Contains(v))
    {
        project.Views.Remove(v);
    }
}
```
### แนวทางที่ 2:
```csharp
var array = new View[project.Views.Count];
project.Views.CopyTo(array, 0);
foreach (var v in array)
{
    if (project.Views.Contains(v))
    {
        project.Views.Remove(v);
    }
}
```
## บทสรุป
ยินดีด้วย! คุณได้สำรวจภูมิทัศน์ Aspose.Tasks สำหรับ .NET สำเร็จแล้ว โดยเชี่ยวชาญศิลปะการจัดการ MS Project Views ตอนนี้ ปลดปล่อยศักยภาพสูงสุดของไลบรารีนี้ในโครงการของคุณเพื่อการจัดการโครงการที่ราบรื่น
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ .NET Framework เวอร์ชันล่าสุดหรือไม่
Aspose.Tasks ได้รับการออกแบบให้เข้ากันได้กับ .NET Framework เวอร์ชันต่างๆ ตรวจสอบเอกสารประกอบเพื่อดูรายละเอียดเฉพาะ
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของมุมมองแผนภูมิแกนต์ได้หรือไม่
อย่างแน่นอน! Aspose.Tasks มีตัวเลือกมากมายในการปรับแต่งรูปลักษณ์ของมุมมองแผนภูมิแกนต์ให้เหมาะกับความต้องการของโครงการของคุณ
### Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนจากชุมชนสำหรับ Aspose.Tasks ได้อย่างไร
 มีส่วนร่วมกับชุมชน Aspose.Tasks บน[ฟอรั่ม](https://forum.aspose.com/c/tasks/15) หากมีข้อสงสัยหรือความช่วยเหลือ
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks หรือไม่
 ใช่ สำรวจใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).