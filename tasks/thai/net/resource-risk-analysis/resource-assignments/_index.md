---
title: การจัดการการกำหนดทรัพยากรโครงการ MS ใน Aspose.Tasks
linktitle: การจัดการการกำหนดทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการการมอบหมายทรัพยากร MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET คำแนะนำที่ครอบคลุมนี้ให้คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา
weight: 11
url: /th/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการการกำหนดทรัพยากรโครงการ MS ใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกวิธีจัดการการมอบหมายทรัพยากร Microsoft Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรม ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะได้เรียนรู้วิธีจัดการการกำหนดทรัพยากรอย่างมีประสิทธิภาพภายในแอปพลิเคชัน .NET ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Tasks ในโปรเจ็กต์ .NET ของคุณ ซึ่งรวมถึง:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
ตอนนี้เรามาดูตัวอย่างที่ให้ไว้เป็นหลายขั้นตอนเพื่อให้เข้าใจอย่างครอบคลุมถึงวิธีจัดการการมอบหมายทรัพยากร MS Project โดยใช้ Aspose.Tasks
## ขั้นตอนที่ 1: ตั้งค่าโครงการและการตั้งค่าปฏิทิน
ในการเริ่มต้น ให้สร้างอินสแตนซ์โครงการใหม่และตั้งค่าปฏิทินของโครงการ:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## ขั้นตอนที่ 2: เพิ่มงานในโครงการ
ถัดไป เพิ่มงานใหม่ให้กับงานรูทของโปรเจ็กต์:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## ขั้นตอนที่ 3: สร้างการมอบหมายทรัพยากรและสร้างข้อมูลตามช่วงเวลา
ตอนนี้ ให้สร้างการมอบหมายทรัพยากรใหม่สำหรับงานและสร้างข้อมูลตามช่วงเวลา:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## ขั้นตอนที่ 4: แบ่งงาน
แบ่งงานออกเป็นหลายส่วนโดยระบุวันที่เริ่มต้นและสิ้นสุด:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## ขั้นตอนที่ 5: ตั้งค่า Contour การทำงาน
ตั้งค่าประเภทโครงร่างงานสำหรับการมอบหมาย:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## ขั้นตอนที่ 6: บันทึกโครงการ
สุดท้าย ให้บันทึกไฟล์โครงการพร้อมกับการเปลี่ยนแปลง:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## บทสรุป
โดยสรุป การจัดการการมอบหมายทรัพยากร Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET นั้นเป็นกระบวนการที่ไม่ซับซ้อน ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการการกำหนดทรัพยากรภายในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.Tasks สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ใช่ Aspose.Tasks มีฟังก์ชันที่ครอบคลุมเพื่อจัดการโครงสร้างโครงการที่ซับซ้อนได้อย่างมีประสิทธิภาพ
### Aspose.Tasks เข้ากันได้กับ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ฉันสามารถปรับแต่งการมอบหมายทรัพยากรตามความต้องการเฉพาะได้หรือไม่
แน่นอนว่า Aspose.Tasks นำเสนอตัวเลือกการปรับแต่งที่หลากหลายสำหรับการกำหนดทรัพยากรเพื่อตอบสนองความต้องการเฉพาะของโครงการ
### Aspose.Tasks รองรับการส่งออกข้อมูลโปรเจ็กต์เป็นรูปแบบอื่นหรือไม่
ใช่ Aspose.Tasks อนุญาตให้ส่งออกข้อมูลโครงการเป็นรูปแบบต่างๆ เช่น XML, PDF และ HTML และอื่นๆ อีกมากมาย
### มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่
ใช่ Aspose ให้การสนับสนุนทางเทคนิคโดยเฉพาะผ่านทางฟอรัมและช่องทางอื่นๆ เพื่อช่วยเหลือผู้ใช้ในการสอบถามหรือปัญหาใดๆ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
