---
title: ปรับแต่งคอลัมน์มุมมองทรัพยากรโครงการ MS ใน Aspose.Tasks
linktitle: การปรับแต่งคอลัมน์มุมมองทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีปรับแต่งคอลัมน์มุมมองทรัพยากร MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET สร้างมุมมองที่ปรับแต่งเพื่อการจัดการโครงการที่ดีขึ้น
type: docs
weight: 17
url: /th/net/resource-risk-analysis/resource-view-columns/
---
## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็น API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรม งานทั่วไปอย่างหนึ่งในการจัดการโครงการคือการปรับแต่งมุมมองเพื่อแสดงข้อมูลเฉพาะ ในบทช่วยสอนนี้ เราจะสำรวจวิธีปรับแต่งคอลัมน์มุมมองทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET Library: คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ไฟล์โครงการ Microsoft: เตรียมไฟล์ MS Project ตัวอย่างไว้เพื่อการทดสอบ
3. สภาพแวดล้อมการพัฒนา: สภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วย. NET Framework
## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นให้กับโปรเจ็กต์ของเรา:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
โหลดไฟล์ MS Project โดยใช้ Aspose.Tasks API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## ขั้นตอนที่ 2: รับทรัพยากรและกำหนดตัวเลือก
ถัดไป รับทรัพยากรที่มีคอลัมน์มุมมองที่คุณต้องการปรับแต่งและกำหนดตัวเลือกการบันทึก PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## ขั้นตอนที่ 3: กำหนดคอลัมน์ที่กำหนดเอง
ตอนนี้ ให้กำหนดคอลัมน์ที่กำหนดเองสำหรับมุมมองทรัพยากร คุณสามารถระบุฟิลด์ต่างๆ และใช้ผู้รับมอบสิทธิ์สำหรับการคำนวณแบบกำหนดเองได้:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## ขั้นตอนที่ 4: วนซ้ำคอลัมน์
วนซ้ำคอลัมน์ที่กำหนดและแสดงคุณสมบัติ:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## ขั้นตอนที่ 5: บันทึกมุมมองที่กำหนดเอง
สุดท้าย ให้ตั้งค่ามุมมองแบบกำหนดเองและบันทึกเป็นไฟล์ PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับแต่งคอลัมน์มุมมองทรัพยากร MS Project ได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET
## บทสรุป
การปรับแต่งคอลัมน์มุมมองทรัพยากรโครงการ MS เป็นสิ่งจำเป็นสำหรับการแสดงข้อมูลที่เกี่ยวข้องซึ่งปรับให้เหมาะกับความต้องการของโครงการของคุณ ด้วย Aspose.Tasks สำหรับ .NET งานนี้ตรงไปตรงมาและมีประสิทธิภาพ ช่วยให้คุณสร้างมุมมองที่กำหนดเองได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งมุมมองสำหรับองค์ประกอบอื่นๆ นอกเหนือจากทรัพยากรได้หรือไม่
ใช่ Aspose.Tasks ช่วยให้สามารถปรับแต่งงาน การมอบหมาย และองค์ประกอบโปรเจ็กต์อื่นๆ ได้เช่นกัน
### Aspose.Tasks รองรับการบันทึกมุมมองในรูปแบบอื่นที่ไม่ใช่ PDF หรือไม่
ได้ คุณสามารถบันทึกมุมมองในรูปแบบต่างๆ เช่น XLSX, HTML และรูปภาพได้
### เป็นไปได้ไหมที่จะใช้การจัดรูปแบบกับมุมมองแบบกำหนดเอง
แน่นอนว่า Aspose.Tasks มีตัวเลือกการจัดรูปแบบที่หลากหลายเพื่อปรับปรุงรูปลักษณ์ของมุมมองที่คุณกำหนดเอง
### ฉันสามารถอัปเดตมุมมองที่กำหนดเองแบบไดนามิกตามการเปลี่ยนแปลงข้อมูลโปรเจ็กต์ได้หรือไม่
ได้ คุณสามารถอัปเดตและสร้างมุมมองที่กำหนดเองใหม่ได้ทุกครั้งที่ข้อมูลโปรเจ็กต์พื้นฐานมีการเปลี่ยนแปลง
### Aspose.Tasks รองรับการพัฒนาข้ามแพลตฟอร์มหรือไม่
Aspose.Tasks สำหรับ .NET มีเป้าหมายหลักคือแพลตฟอร์ม .NET แต่ก็มีเวอร์ชันสำหรับ Java และแพลตฟอร์มอื่นๆ ด้วย