---
title: จัดการตัวกรองโครงการ MS อย่างมีประสิทธิภาพด้วย Aspose.Tasks
linktitle: การจัดการคอลเลกชันตัวกรองใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการตัวกรองคอลเลกชัน MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET
weight: 17
url: /th/net/tasks-project-management/filter-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการตัวกรองโครงการ MS อย่างมีประสิทธิภาพด้วย Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการตัวกรองคอลเลกชัน MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET การจัดการตัวกรองเป็นสิ่งสำคัญสำหรับการจัดระเบียบและวิเคราะห์ข้อมูลโครงการอย่างมีประสิทธิภาพ Aspose.Tasks มีฟังก์ชันการทำงานที่มีประสิทธิภาพเพื่อจัดการงานและตัวกรองทรัพยากรได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).
2. การเข้าถึงสภาพแวดล้อมการพัฒนา .NET: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนา .NET ที่ตั้งค่าให้ทำงานกับ Aspose.Tasks

## นำเข้าเนมสเปซ
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## ขั้นตอนที่ 2: ทำซ้ำตัวกรองงาน
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## ขั้นตอนที่ 3: วนซ้ำตัวกรองทรัพยากร
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## ขั้นตอนที่ 4: ล้างและคัดลอกตัวกรอง
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// ล้างตัวกรองของโครงการอื่น
otherProject.TaskFilters.Clear();
// คัดลอกตัวกรองไปยังโครงการอื่น
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## ขั้นตอนที่ 5: เพิ่มตัวกรองงานแบบกำหนดเอง
```csharp
// เพิ่มตัวกรองงานที่กำหนดเอง
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## ขั้นตอนที่ 6: ลบตัวกรองทั้งหมด
```csharp
// ลบตัวกรองทั้งหมด
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการตัวกรองคอลเลกชัน MS Project ได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET

## บทสรุป
การจัดการตัวกรองอย่างมีประสิทธิภาพในคอลเลกชัน MS Project ถือเป็นสิ่งสำคัญสำหรับการจัดระเบียบและวิเคราะห์ข้อมูลโครงการ Aspose.Tasks สำหรับ .NET มอบฟังก์ชันการทำงานที่ครอบคลุมเพื่อจัดการงานและตัวกรองทรัพยากรได้อย่างราบรื่น ช่วยให้นักพัฒนาปรับปรุงงานการจัดการโครงการได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ตอบ: Aspose.Tasks นำเสนอฟีเจอร์ที่มีประสิทธิภาพในการจัดการโครงสร้างโปรเจ็กต์ต่างๆ รวมถึงโครงสร้างที่ซับซ้อน เพื่อให้มั่นใจถึงความสามารถในการจัดการโปรเจ็กต์ที่ครอบคลุม
### ถาม: Aspose.Tasks เข้ากันได้กับไฟล์ MS Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับรูปแบบไฟล์ MS Project ที่หลากหลาย จึงรับประกันความเข้ากันได้ในเวอร์ชันต่างๆ
### ถาม: ฉันสามารถปรับแต่งตัวกรองตามความต้องการเฉพาะของโครงการได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks ช่วยให้นักพัฒนาสามารถสร้างตัวกรองแบบกำหนดเองที่ปรับแต่งตามความต้องการของโปรเจ็กต์เฉพาะ ช่วยเพิ่มความยืดหยุ่นและประสิทธิภาพ
### ถาม: Aspose.Tasks มีเอกสารประกอบและทรัพยากรสนับสนุนหรือไม่
ตอบ: ใช่ Aspose.Tasks มีเอกสารประกอบ บทช่วยสอน และฟอรัมการสนับสนุนเฉพาะเพื่อช่วยเหลือนักพัฒนาในทุกขั้นตอนของการดำเนินโครงการ
### ถาม: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่
ตอบ: ได้ นักพัฒนาสามารถเข้าถึง Aspose.Tasks เวอร์ชันทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์ต่างๆ ก่อนตัดสินใจซื้อ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
