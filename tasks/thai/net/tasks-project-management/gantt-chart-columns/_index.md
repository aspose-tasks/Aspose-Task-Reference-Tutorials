---
title: ปรับแต่งคอลัมน์แผนภูมิแกนต์ด้วย Aspose.Tasks
linktitle: คอลัมน์แผนภูมิแกนต์ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีปรับแต่งคอลัมน์แผนภูมิ Gantt ใน Aspose.Tasks สำหรับ .NET เพื่อแสดงข้อมูลงานเฉพาะอย่างมีประสิทธิภาพ
weight: 21
url: /th/net/tasks-project-management/gantt-chart-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปรับแต่งคอลัมน์แผนภูมิแกนต์ด้วย Aspose.Tasks

## การแนะนำ
แผนภูมิแกนต์เป็นเครื่องมือพื้นฐานในการจัดการโครงการ โดยนำเสนองาน ลำดับเวลา และทรัพยากรด้วยภาพ Aspose.Tasks สำหรับ .NET นำเสนอความสามารถอันทรงพลังในการจัดการแผนภูมิ Gantt รวมถึงการปรับแต่งคอลัมน์เพื่อแสดงข้อมูลงานเฉพาะ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับคอลัมน์แผนภูมิแกนต์โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  การติดตั้ง: ติดตั้ง Aspose.Tasks สำหรับ .NET บนระบบของคุณ ถ้าไม่เช่นนั้น ให้ดาวน์โหลดและติดตั้งจาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. .NET Development Environment: ความรู้เกี่ยวกับการทำงานของ C# และ .NET Framework
3. ไฟล์โครงการตัวอย่าง: มีไฟล์โครงการ Microsoft ตัวอย่าง (`.mpp`) มีประโยชน์ในการทดลองด้วย หากคุณยังไม่มี คุณสามารถสร้างโครงการอย่างง่ายใน MS Project และบันทึกได้

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Tasks สำหรับ .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
 โหลดไฟล์โครงการโดยใช้`Project` คลาสที่จัดทำโดย Aspose.Tasks:
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## ขั้นตอนที่ 2: กำหนดคอลัมน์แผนภูมิแกนต์
กำหนดคอลัมน์ที่คุณต้องการแสดงในแผนภูมิแกนต์ คุณสามารถระบุฟิลด์ในตัวหรือสร้างฟิลด์ที่กำหนดเองได้:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## ขั้นตอนที่ 3: วนซ้ำคอลัมน์
วนซ้ำคอลัมน์ที่กำหนดเพื่อเข้าถึงคุณสมบัติและแสดงข้อมูล:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## ขั้นตอนที่ 4: บันทึกแผนภูมิแกนต์เป็น CSV
บันทึกแผนภูมิแกนต์ที่มีคอลัมน์ที่กำหนดลงในไฟล์ CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะทำงานกับคอลัมน์แผนภูมิ Gantt ใน Aspose.Tasks for .NET ได้อย่างมีประสิทธิภาพ ซึ่งช่วยให้คุณสามารถปรับแต่งและแสดงข้อมูลงานได้ตามต้องการ

## บทสรุป
การควบคุมคอลัมน์แผนภูมิ Gantt ใน Aspose.Tasks สำหรับ .NET ได้อย่างเชี่ยวชาญ เปิดโอกาสให้ปรับแต่งภาพการจัดการโครงการให้ตรงกับความต้องการเฉพาะของคุณได้ไม่รู้จบ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการข้อมูลงานได้อย่างมีประสิทธิภาพ และปรับปรุงความชัดเจนของโครงการและการจัดระเบียบ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถสร้างคอลัมน์แบบกำหนดเองใน Aspose.Tasks for .NET ได้หรือไม่
ตอบ: ได้ คุณสามารถกำหนดคอลัมน์แบบกำหนดเองเพื่อแสดงคุณลักษณะของงานเฉพาะตามความต้องการของโครงการของคุณได้
### ถาม: Aspose.Tasks สำหรับ .NET เข้ากันได้กับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks for .NET รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมของโปรเจ็กต์ที่แตกต่างกัน
### ถาม: ฉันจะจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนด้วย Aspose.Tasks สำหรับ .NET ได้อย่างไร
ตอบ: Aspose.Tasks for .NET มี API และคุณสมบัติที่ครอบคลุมเพื่อจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อน โดยให้ความยืดหยุ่นและความสามารถในการปรับขนาด
### ถาม: มีข้อจำกัดเกี่ยวกับจำนวนคอลัมน์ที่ฉันสามารถเพิ่มลงในแผนภูมิ Gantt ได้หรือไม่
ตอบ: Aspose.Tasks for .NET มีตัวเลือกการปรับแต่งที่หลากหลาย ซึ่งช่วยให้คุณสามารถเพิ่มคอลัมน์จำนวนมากลงในแผนภูมิ Gantt ได้โดยไม่มีข้อจำกัด
### ถาม: ฉันจะค้นหาการสนับสนุนและทรัพยากรเพิ่มเติมสำหรับ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
ตอบ: คุณสามารถสำรวจเอกสารประกอบ ฟอรัมชุมชน และช่องทางการสนับสนุนที่ Aspose.Tasks สำหรับ .NET มอบให้เพื่อเข้าถึงทรัพยากรและความช่วยเหลือที่ครอบคลุม
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
