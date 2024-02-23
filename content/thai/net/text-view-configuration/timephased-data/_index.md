---
title: การจัดการข้อมูลตามระยะเวลาหลักด้วย Aspose.Tasks สำหรับ .NET
linktitle: การจัดการข้อมูลตามช่วงเวลาใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจ Aspose.Tasks สำหรับ .NET เพื่อจัดการข้อมูลที่แบ่งตามช่วงเวลา เพิ่มประสิทธิภาพการวางแผนโครงการ และเพิ่มประสิทธิภาพการจัดการทรัพยากร #Aspose #งาน #โครงการ MS
type: docs
weight: 14
url: /th/net/text-view-configuration/timephased-data/
---
## การแนะนำ
ในโลกของการจัดการโครงการ การจัดการข้อมูลตามช่วงเวลาอย่างมีประสิทธิผลถือเป็นสิ่งสำคัญสำหรับการจัดสรรทรัพยากร การประมาณต้นทุน และการวางแผนโครงการโดยรวม Aspose.Tasks สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพในการทำงานกับข้อมูลตามช่วงเวลาที่กำหนดเองได้อย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการจัดการข้อมูลตามช่วงเวลาโดยใช้ Aspose.Tasks ซึ่งช่วยให้คุณเพิ่มประสิทธิภาพการจัดการทรัพยากรในโปรเจ็กต์ของคุณได้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการจัดการโครงการ
-  ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- โปรแกรมแก้ไขโค้ด เช่น Visual Studio สำหรับการนำตัวอย่างที่ให้มาไปใช้
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชัน Aspose.Tasks เพิ่มบรรทัดต่อไปนี้ที่จุดเริ่มต้นของไฟล์โค้ดของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
```
ตอนนี้ เราจะแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อแนะนำคุณเกี่ยวกับการจัดการข้อมูลตามช่วงเวลาโดยใช้ Aspose.Tasks:
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
ที่นี่ เราจะเริ่มต้นโปรเจ็กต์ใหม่และตั้งค่าโหมดการคำนวณ
## ขั้นตอนที่ 2: กำหนดทรัพยากรและงาน
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
สร้างทรัพยากรงานและต้นทุน รวมถึงงาน เพื่อจำลองโครงสร้างโครงการ
## ขั้นตอนที่ 3: กำหนดทรัพยากรให้กับงาน
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
มอบหมายทรัพยากรงานและต้นทุนให้กับงาน
## ขั้นตอนที่ 4: เพิ่มข้อมูลตามระยะเวลาที่กำหนดเอง
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// ขั้นตอนที่คล้ายกันสำหรับการกำหนดต้นทุน
costAssignment.TimephasedData.Clear();
```
เพิ่มข้อมูลตามระยะเวลาที่กำหนดเองสำหรับทั้งงานและการกำหนดต้นทุน
## ขั้นตอนที่ 5: แสดงข้อมูลตามช่วงเวลา
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // แสดงข้อมูลที่เกี่ยวข้องเกี่ยวกับการป้อนข้อมูลตามช่วงเวลาแต่ละครั้ง
    }
}
```
สุดท้าย แสดงข้อมูลตามช่วงเวลาสำหรับแต่ละงาน
#
## บทสรุป
การจัดการข้อมูลตามช่วงเวลาอย่างมีประสิทธิภาพใน Aspose.Tasks เปิดโอกาสใหม่ๆ สำหรับการวางแผนโครงการโดยละเอียดและการจัดการทรัพยากร ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะได้เรียนรู้วิธีจัดการข้อมูลตามระยะเพื่อตอบสนองความต้องการเฉพาะของโครงการของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับเครื่องมือการจัดการโครงการอื่นๆ ได้หรือไม่
Aspose.Tasks ได้รับการออกแบบมาเพื่อการพัฒนา .NET เป็นหลัก อย่างไรก็ตาม ฟังก์ชันการทำงานของมันสามารถเสริมเครื่องมือการจัดการโครงการต่างๆ ได้
### มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
 ใช่ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)เพื่อสนับสนุนชุมชน
### ใบอนุญาตชั่วคราวคืออะไร และฉันจะขอรับใบอนุญาตได้อย่างไร
 เรียนรู้เกี่ยวกับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาเอกสารสำหรับ Aspose.Tasks for .NET ได้ที่ไหน
 อ้างถึงที่ครอบคลุม[เอกสารประกอบ](https://reference.aspose.com/tasks/net/) สำหรับข้อมูลโดยละเอียด