---
title: การจัดการความคืบหน้าของโครงการ MS ด้วย Aspose.Tasks
linktitle: การจัดการเส้นความคืบหน้าใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการบรรทัดความคืบหน้าในไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ซึ่งช่วยเพิ่มการแสดงภาพและการจัดการโครงการ
type: docs
weight: 15
url: /th/net/project-management-integration/progress-lines/
---
## การแนะนำ
Microsoft Project (MS Project) เป็นเครื่องมือที่มีประสิทธิภาพสำหรับการจัดการโครงการ ช่วยให้ผู้ใช้สามารถติดตามแง่มุมต่างๆ ของโครงการของตนได้ คุณลักษณะที่สำคัญอย่างหนึ่งของ MS Project คือความสามารถในการเห็นภาพเส้นความคืบหน้า ซึ่งช่วยให้ผู้มีส่วนได้ส่วนเสียเข้าใจสถานะและวิถีของโครงการ ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการกับบรรทัดความคืบหน้าใน MS Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Visual Studio: ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET อื่นที่ต้องการ
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## การนำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
ตอนนี้ เรามาดูรายละเอียดแต่ละขั้นตอนในการจัดการกับบรรทัดความคืบหน้า:
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 ที่นี่เราโหลดไฟล์ MS Project`Project2.mpp` และกำหนดวันที่สถานะ
## ขั้นตอนที่ 2: กำหนดมุมมองแผนภูมิแกนต์
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
เราส่งมุมมองของโปรเจ็กต์ไปยังมุมมองแผนภูมิแกนต์เพื่อการจัดการเพิ่มเติม
## ขั้นตอนที่ 3: กำหนดเส้นความคืบหน้า
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
เราเริ่มต้นเส้นความคืบหน้าสำหรับมุมมองแผนภูมิแกนต์
## ขั้นตอนที่ 4: กำหนดการตั้งค่าเส้นความคืบหน้า
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
ที่นี่ เราตั้งค่าคุณสมบัติต่างๆ สำหรับบรรทัดความคืบหน้า เช่น สีของเส้น รูปแบบ แบบอักษร ฯลฯ
## ขั้นตอนที่ 5: ตรวจสอบการกำหนดค่าเส้นความคืบหน้า
```csharp
// การตั้งค่าบรรทัดความคืบหน้าเอาท์พุต
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// ส่งออกการตั้งค่าอื่นๆ...
```
เราส่งออกการตั้งค่าบรรทัดความคืบหน้าที่กำหนดไว้สำหรับการตรวจสอบ
## ขั้นตอนที่ 6: บันทึกไฟล์โครงการ
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
สุดท้าย เราจะบันทึกไฟล์โครงการที่แก้ไขพร้อมกับเส้นความคืบหน้า

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดการบรรทัดความคืบหน้าของ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับแต่งและแสดงภาพเส้นความคืบหน้าในไฟล์ MS Project ของคุณได้อย่างมีประสิทธิภาพโดยทางโปรแกรม
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเส้นความคืบหน้าเพิ่มเติมได้หรือไม่?
ตอบ: ได้ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ได้ เช่น สีเส้น รูปแบบ และแบบอักษรให้เหมาะกับความต้องการของคุณ
### ถาม: Aspose.Tasks รองรับคุณสมบัติการจัดการโครงการอื่นๆ หรือไม่
ตอบ: ได้ Aspose.Tasks ให้การสนับสนุนอย่างกว้างขวางสำหรับการจัดการแง่มุมต่างๆ ของไฟล์ MS Project รวมถึงงาน ทรัพยากร และปฏิทิน
### ถาม: ฉันสามารถผสานรวม Aspose.Tasks เข้ากับไลบรารี .NET อื่นๆ ได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks ได้รับการออกแบบมาเพื่อผสานรวมกับไลบรารี .NET อื่นๆ ได้อย่างราบรื่น ช่วยให้คุณสามารถปรับปรุงแอปพลิเคชันการจัดการโครงการของคุณให้ดียิ่งขึ้นได้
### ถาม: มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่
 ตอบ: ได้ คุณสามารถค้นหาแหล่งข้อมูลที่เป็นประโยชน์และขอความช่วยเหลือได้ที่ฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: Aspose.Tasks เสนอสิทธิ์การใช้งานชั่วคราวเพื่อวัตถุประสงค์ในการประเมินหรือไม่
 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับการประเมินได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).