---
title: การเรียนรู้ตัวเลือกการบันทึกโครงการ MS สำหรับ Aspose.Tasks
linktitle: ตัวเลือกการบันทึกทั่วไปสำหรับ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้การบันทึกไฟล์ MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET ปรับแต่งตัวเลือกเอาท์พุตสำหรับโปรเจ็กต์ของคุณได้อย่างง่ายดาย
weight: 17
url: /th/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้ตัวเลือกการบันทึกโครงการ MS สำหรับ Aspose.Tasks

## การแนะนำ
Aspose.Tasks สำหรับ .NET นำเสนอคุณสมบัติที่มีประสิทธิภาพสำหรับการจัดการไฟล์ Microsoft Project โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะเจาะลึกความซับซ้อนของการบันทึกไฟล์ MS Project โดยใช้ตัวเลือกต่างๆ ที่ Aspose.Tasks มอบให้ โดยเฉพาะอย่างยิ่ง เราจะมุ่งเน้นไปที่ตัวเลือกการบันทึกทั่วไปสำหรับ Aspose.Tasks ซึ่งช่วยให้คุณปรับแต่งผลลัพธ์ตามความต้องการเฉพาะของคุณได้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).
2. ความเข้าใจพื้นฐานของ .NET Framework: ความคุ้นเคยกับแนวคิดการเขียนโปรแกรม .NET จะเป็นประโยชน์

## การนำเข้าเนมสเปซ
ก่อนที่จะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
ขั้นแรก คุณต้องโหลดไฟล์ MS Project โดยใช้ Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## ขั้นตอนที่ 2: กำหนดตัวเลือกการบันทึก
 กำหนดตัวเลือกการบันทึกตามความต้องการของคุณ ในตัวอย่างนี้ เรากำลังใช้`Spreadsheet2003SaveOptions`: :
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## ขั้นตอนที่ 3: ปรับแต่งคอลัมน์มุมมอง
คุณสามารถปรับแต่งคอลัมน์มุมมอง เช่น แผนภูมิแกนต์ มุมมองทรัพยากร และมุมมองการมอบหมายได้ ต่อไปนี้เป็นวิธีเพิ่มคอลัมน์ลงในแต่ละคอลัมน์:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## ขั้นตอนที่ 4: บันทึกโครงการด้วยตัวเลือก
สุดท้าย ให้บันทึกโครงการด้วยตัวเลือกที่ระบุ:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## บทสรุป
การเรียนรู้ตัวเลือกการบันทึก MS Project ทั่วไปด้วย Aspose.Tasks สำหรับ .NET ช่วยให้คุณสามารถปรับแต่งรูปแบบเอาต์พุตได้อย่างมีประสิทธิภาพตามความต้องการของโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับไฟล์ MS Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์ MS Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่
 ตอบ: ได้ คุณสามารถสำรวจ Aspose.Tasks พร้อมให้ทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: สามารถดูเอกสารโดยละเอียดได้[ที่นี่](https://reference.aspose.com/tasks/net/)ซึ่งให้คำแนะนำที่ครอบคลุมเกี่ยวกับการใช้ฟีเจอร์ Aspose.Tasks
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: ใบอนุญาตชั่วคราวมีไว้เพื่อวัตถุประสงค์ในการประเมิน[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะขอรับการสนับสนุนสำหรับคำถามที่เกี่ยวข้องกับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถเข้าร่วมฟอรัมชุมชน Aspose.Tasks ได้[ที่นี่](https://forum.aspose.com/c/tasks/15)เพื่อรับความช่วยเหลือจากผู้เชี่ยวชาญและเพื่อนนักพัฒนา
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
