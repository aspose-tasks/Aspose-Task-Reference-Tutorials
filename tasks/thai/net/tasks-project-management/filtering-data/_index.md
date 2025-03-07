---
title: การกรองข้อมูลอย่างมีประสิทธิภาพด้วย Aspose.Tasks
linktitle: การกรองข้อมูลใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกรองข้อมูลในไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เพิ่มความสามารถในการผลิตและการวิเคราะห์ได้อย่างง่ายดาย
weight: 16
url: /th/net/tasks-project-management/filtering-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกรองข้อมูลอย่างมีประสิทธิภาพด้วย Aspose.Tasks

## การแนะนำ
Aspose.Tasks for .NET มีฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการกรองข้อมูลในไฟล์ Microsoft Project ช่วยให้ผู้ใช้สามารถจัดการและวิเคราะห์ข้อมูลโครงการได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจวิธีกรองข้อมูลโดยใช้ Aspose.Tasks ในรูปแบบคำแนะนำทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ติดตั้ง Aspose.Tasks สำหรับ .NET
 ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/net/). ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้เพื่อตั้งค่าไลบรารีในสภาพแวดล้อมการพัฒนาของคุณ
### 2. ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ
ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนาที่ใช้งานได้สำหรับการเขียนโปรแกรม .NET ซึ่งรวมถึง IDE ที่เข้ากันได้ เช่น Visual Studio และความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
### 3. เข้าถึงไฟล์ตัวอย่างโครงการ Microsoft
เตรียมไฟล์ Microsoft Project ตัวอย่าง (.mpp) ที่มีข้อมูลที่คุณต้องการกรอง ตรวจสอบให้แน่ใจว่าคุณสามารถเข้าถึงไฟล์ได้ในไดเร็กทอรีโปรเจ็กต์ของคุณ
## นำเข้าเนมสเปซ
ในไฟล์โค้ด C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Tasks

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
using System;
using System.Collections.Generic;

```
ตอนนี้เรามาแจกแจงขั้นตอนการกรองข้อมูลใน MS Project โดยใช้ Aspose.Tasks ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "SampleProject.mpp");
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Document Directory"`พร้อมพาธไปยังไดเร็กทอรีไฟล์โปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: ดึงข้อมูลตัวกรองงาน
```csharp
List<Filter> filters = project.TaskFilters.ToList();
```
รับรายการตัวกรองงานที่มีอยู่ในโปรเจ็กต์
## ขั้นตอนที่ 3: แสดงรายละเอียดตัวกรองงาน
```csharp
foreach (var filter in filters)
{
    Console.WriteLine("Uid: " + filter.Uid);
    Console.WriteLine("Index: " + filter.Index);
    Console.WriteLine("Name: " + filter.Name);
    Console.WriteLine("Type: " + filter.FilterType);
    Console.WriteLine("Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Show Related Summary Rows: " + filter.ShowRelatedSummaryRows);
}
```
วนซ้ำรายการตัวกรองงานและแสดงรายละเอียด เช่น Uid ดัชนี ชื่อ ประเภทตัวกรอง แสดงในเมนู และแสดงแถวสรุปที่เกี่ยวข้อง
## ขั้นตอนที่ 4: ตรวจสอบตัวกรองทรัพยากร
```csharp
List<Filter> resourceFilters = project.ResourceFilters.ToList();
```
รับรายการตัวกรองทรัพยากรที่มีอยู่ในโปรเจ็กต์
## ขั้นตอนที่ 5: แสดงรายละเอียดตัวกรองทรัพยากร
```csharp
Console.WriteLine("Project.ResourceFilters count: " + resourceFilters.Count);
Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + resourceFilters[0].FilterType);
Console.WriteLine("Resource filter ShowInMenu" + resourceFilters[0].ShowInMenu);
Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + resourceFilters[0].ShowRelatedSummaryRows);
```
แสดงรายละเอียดของตัวกรองทรัพยากร รวมถึงจำนวน ประเภทตัวกรอง แสดงในเมนู และแสดงแถวสรุปที่เกี่ยวข้อง
## บทสรุป
การกรองข้อมูลในไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เป็นกระบวนการที่ไม่ซับซ้อนซึ่งช่วยเพิ่มความสามารถในการผลิตและการวิเคราะห์ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการข้อมูลโครงการตามเกณฑ์เฉพาะได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สามารถกรองข้อมูลตามเกณฑ์ที่กำหนดเองได้หรือไม่
ตอบ: ได้ Aspose.Tasks อนุญาตให้กรองข้อมูลตามเกณฑ์ที่กำหนดเองซึ่งปรับให้เหมาะกับความต้องการของโครงการของคุณ
### ถาม: Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ถาม: ฉันสามารถรวมตัวกรองหลายตัวใน Aspose.Tasks ได้หรือไม่
ตอบ: แน่นอน คุณสามารถรวมตัวกรองหลายตัวเข้าด้วยกันเพื่อปรับแต่งการแยกและวิเคราะห์ข้อมูลใน Aspose.Tasks ได้
### ถาม: Aspose.Tasks มีเอกสารประกอบเพื่อขอความช่วยเหลือเพิ่มเติมหรือไม่
 ตอบ: ได้ คุณสามารถอ้างอิงถึงเนื้อหาที่ครอบคลุมได้[เอกสารประกอบ](https://reference.aspose.com/tasks/net/) จัดทำโดย Aspose.Tasks สำหรับคำแนะนำโดยละเอียด
### ถาม: มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึงการสนับสนุนด้านเทคนิคผ่านทาง[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับข้อสงสัยหรือปัญหาใด ๆ ที่คุณพบ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
