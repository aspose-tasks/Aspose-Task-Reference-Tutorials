---
title: การเรียนรู้มุมมองแผนภูมิ Gantt ใน Aspose.Tasks
linktitle: มุมมองแผนภูมิแกนต์ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีปรับแต่งมุมมองแผนภูมิแกนต์ในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET คำแนะนำทีละขั้นตอนเพื่อการจัดการโครงการที่มีประสิทธิภาพ
weight: 22
url: /th/net/tasks-project-management/gantt-chart-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้มุมมองแผนภูมิ Gantt ใน Aspose.Tasks

## การแนะนำ
แผนภูมิแกนต์เป็นเครื่องมืออันทรงพลังที่ใช้ในการจัดการโครงการเพื่อแสดงภาพงาน ไทม์ไลน์ และการขึ้นต่อกัน Aspose.Tasks for .NET มอบความสามารถที่แข็งแกร่งสำหรับการทำงานกับมุมมองแผนภูมิ Gantt ในไฟล์ Microsoft Project ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้ Aspose.Tasks เพื่อจัดการมุมมองแผนภูมิ Gantt ปรับแต่งรูปลักษณ์ และบันทึกเป็นไฟล์ PDF
## ข้อกำหนดเบื้องต้น
ก่อนดำเนินการต่อ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. การติดตั้ง Aspose.Tasks สำหรับ .NET
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tasks/net/).
### 2. ไฟล์โครงการไมโครซอฟต์
เตรียมไฟล์ Microsoft Project (`Project2.mpp`) ที่คุณจะใช้เพื่อทำงานกับมุมมองแผนภูมิแกนต์
### 3. ความรู้พื้นฐานเกี่ยวกับ C# และ .NET Framework
บทช่วยสอนนี้ถือว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# และกรอบงาน .NET
## นำเข้าเนมสเปซ
ก่อนที่คุณจะเริ่มทำงานกับมุมมองแผนภูมิ Gantt ใน Aspose.Tasks คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

มาแบ่งโค้ดตัวอย่างที่ให้มาออกเป็นหลายขั้นตอนและอธิบายแต่ละขั้นตอนโดยละเอียด:
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
ขั้นตอนนี้เกี่ยวข้องกับการโหลดไฟล์ Microsoft Project (`Project2.mpp` ) ในกรณีของ`Project` ระดับ.
## ขั้นตอนที่ 2: ตั้งค่าวันที่สถานะ
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
ที่นี่ เรากำหนดวันที่สถานะของโครงการเป็นวันที่เริ่มต้น
## ขั้นตอนที่ 3: เข้าถึงมุมมองแผนภูมิแกนต์
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
เราเข้าถึงมุมมองแผนภูมิแกนต์จากโครงการ Aspose.Tasks ช่วยให้สามารถเข้าถึงมุมมองต่างๆ เช่น แผนภูมิแกนต์ แผนภาพเครือข่าย และการใช้งาน
## ขั้นตอนที่ 4: ปรับแต่งมุมมองแผนภูมิแกนต์
ตอนนี้ มาปรับแต่งแง่มุมต่างๆ ของมุมมองแผนภูมิ Gantt กัน:
### ตั้งค่าการปัดเศษแถบ
```csharp
view.BarRounding = false;
```
การตั้งค่านี้จะกำหนดว่าแท่งบนแผนภูมิ Gantt จะปัดเศษเป็นวันที่ใกล้ที่สุดหรือไม่
### ตั้งค่าขนาดบาร์
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
ซึ่งจะกำหนดความสูงของแท่งแกนต์ในแผนภูมิ
### ซ่อนแถบโรลอัพ
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
ระบุว่าจะซ่อนแถบค่าสะสมเมื่อขยายงานสรุปหรือไม่
### ตั้งค่าสีเวลาที่ไม่ทำงาน
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
กำหนดสีสำหรับเวลาที่ไม่ทำงานบนแผนภูมิแกนต์
### โรลอัพแกนต์บาร์
```csharp
view.RollUpGanttBars = true;
```
ระบุว่าจะต้องม้วนแท่งบนแผนภูมิ Gantt ขึ้นหรือไม่
### แสดงแถบแยก
```csharp
view.ShowBarSplits = true;
```
กำหนดว่าต้องแสดงการแบ่งงานบนแผนภูมิแกนต์หรือไม่
### แสดงภาพวาด
```csharp
view.ShowDrawings = true;
```
ระบุว่าต้องแสดงภาพวาดบนแผนภูมิแกนต์หรือไม่
### เปอร์เซ็นต์ขนาดมาตราส่วนเวลา
```csharp
view.TimescaleSizePercentage = 10;
```
ตั้งค่าเปอร์เซ็นต์เพื่อปรับระยะห่างระหว่างหน่วยในระดับมาตราส่วนเวลา
## ขั้นตอนที่ 5: บันทึกมุมมองแผนภูมิแกนต์เป็น PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
สุดท้าย เราจะบันทึกมุมมองแผนภูมิ Gantt แบบกำหนดเองเป็นไฟล์ PDF
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีทำงานกับมุมมองแผนภูมิ Gantt ใน Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถจัดการและปรับแต่งแผนภูมิแกนต์ตามความต้องการของโครงการได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของแท่งแผนภูมิ Gantt เพิ่มเติมได้หรือไม่
ตอบ: ได้ Aspose.Tasks มีตัวเลือกมากมายในการปรับแต่งรูปลักษณ์ของแถบแผนภูมิ Gantt รวมถึงสี รูปร่าง และขนาด
### ถาม: Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP, MPT และ XML
### ถาม: ฉันสามารถส่งออกมุมมองแผนภูมิ Gantt เป็นรูปแบบอื่นที่ไม่ใช่ PDF ได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks รองรับการส่งออกมุมมองแผนภูมิ Gantt ไปเป็นหลายรูปแบบ รวมถึง PNG, JPEG และ XPS
### ถาม: Aspose.Tasks รองรับอัลกอริธึมการจัดกำหนดการโปรเจ็กต์ที่ซับซ้อนหรือไม่
ตอบ: ใช่ Aspose.Tasks มีอัลกอริธึมการจัดกำหนดการขั้นสูงเพื่อจัดการกำหนดการของโครงการที่ซับซ้อนได้อย่างมีประสิทธิภาพ
### ถาม: มีฟอรัมชุมชนที่ฉันสามารถขอความช่วยเหลือหรือแบ่งปันประสบการณ์กับ Aspose.Tasks ได้หรือไม่
 ตอบ: ได้ คุณสามารถเยี่ยมชมได้[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อมีส่วนร่วมกับผู้ใช้รายอื่น ถามคำถาม และค้นหาวิธีแก้ปัญหาสำหรับคำถามของคุณ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
