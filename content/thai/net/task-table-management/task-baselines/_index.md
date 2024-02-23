---
title: การเรียนรู้พื้นฐานงานใน Aspose.Tasks สำหรับ .NET
linktitle: การจัดการงานพื้นฐานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการงานพื้นฐานใน Aspose.Tasks for .NET ด้วยบทช่วยสอนที่ครอบคลุมนี้ พัฒนาทักษะการจัดการโครงการของคุณวันนี้!
type: docs
weight: 16
url: /th/net/task-table-management/task-baselines/
---
## การแนะนำ
ในโลกที่มีการเปลี่ยนแปลงตลอดเวลาของการจัดการโครงการ การจัดระเบียบและรับทราบข้อมูลเป็นสิ่งสำคัญ Aspose.Tasks สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพสำหรับการจัดการบรรทัดฐานของงาน ช่วยให้คุณเข้าถึงข้อมูลพื้นฐานอันมีค่าได้อย่างมีประสิทธิภาพ คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ เพื่อให้มั่นใจว่าคุณจะเข้าใจแต่ละแนวคิดได้ชัดเจน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  การตั้งค่าสภาพแวดล้อม: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[เอกสารประกอบ Aspose.Tasks](https://reference.aspose.com/tasks/net/).
- ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C# เนื่องจากบทช่วยสอนนี้ถือเป็นความเข้าใจพื้นฐาน
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE ที่ต้องการ เช่น Visual Studio เพื่อติดตามได้อย่างราบรื่น
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงฟังก์ชัน Aspose.Tasks ได้:
```csharp
    using Aspose.Tasks;
    using System;
```
ตอนนี้ เราจะแจกแจงตัวอย่างที่ให้ไว้เป็นหลายขั้นตอนเพื่อแนะนำคุณเกี่ยวกับการจัดการงานพื้นฐานใน Aspose.Tasks
## ขั้นตอนที่ 1: สร้างโครงการ
```csharp
var project = new Project();
```
 เริ่มต้นด้วยการเริ่มต้นโครงการใหม่โดยใช้`Project` ระดับ.
## ขั้นตอนที่ 2: สร้างงานและตั้งค่าพื้นฐาน
```csharp
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
```
 เพิ่มงานในโครงการและตั้งค่าพื้นฐานโดยใช้`SetBaseline` วิธี.
## ขั้นตอนที่ 3: แสดงข้อมูลพื้นฐานของงาน
```csharp
var baseline = task.Baselines.ToList()[0];
Console.WriteLine("Baseline Start: {0}", baseline.Start);
Console.WriteLine("Baseline duration: {0}", baseline.Duration);
Console.WriteLine("Baseline duration format: {0}", baseline.Duration.TimeUnit);
Console.WriteLine("Is it estimated duration?: {0}", baseline.EstimatedDuration);
Console.WriteLine("Baseline Finish: {0}", baseline.Finish);
```
ดึงและแสดงข้อมูลสำคัญเกี่ยวกับงานพื้นฐาน เช่น เวลาเริ่มต้น ระยะเวลา และเวลาสิ้นสุด
## ขั้นตอนที่ 4: รายละเอียดพื้นฐานเพิ่มเติม
```csharp
Console.WriteLine("Interim: {0}", baseline.Interim);
Console.WriteLine("Fixed Cost: {0}", baseline.FixedCost);
```
สำรวจรายละเอียดเพิ่มเติม รวมถึงว่าข้อมูลพื้นฐานเป็นข้อมูลพื้นฐานชั่วคราวหรือไม่ และต้นทุนคงที่ที่เกี่ยวข้อง
## ขั้นตอนที่ 5: พิมพ์ข้อมูลตามช่วงเวลา
```csharp
Console.WriteLine("Number of timephased items: " + baseline.TimephasedData.Count);
foreach (var data in baseline.TimephasedData)
{
    Console.WriteLine(" Uid: " + data.Uid);
    Console.WriteLine(" Start: " + data.Start);
    Console.WriteLine(" Finish: " + data.Finish);
}
```
ทำความเข้าใจข้อมูลตามช่วงเวลาที่เกี่ยวข้องกับเส้นพื้นฐานของงาน โดยให้ข้อมูลเชิงลึกเกี่ยวกับเส้นเวลาของโครงการต่างๆ
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีจัดการงานพื้นฐานใน Aspose.Tasks for .NET เรียบร้อยแล้ว ความรู้นี้จะช่วยเพิ่มความสามารถในการจัดการโครงการของคุณ ทำให้มั่นใจในการติดตามและการวางแผนที่แม่นยำ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่
ตอบ: Aspose.Tasks เข้ากันได้กับเฟรมเวิร์ก .NET หลายเฟรม ซึ่งให้ความยืดหยุ่นในสภาพแวดล้อมการพัฒนาของคุณ
### ถาม: มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่
ตอบ: ได้ คุณสามารถรับการสนับสนุนและมีส่วนร่วมกับชุมชนได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: เยี่ยมชม[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks
### ถาม: มีบทช่วยสอนใดๆ นอกเหนือจากพื้นฐานงานหรือไม่
 ตอบ: สำรวจ[เอกสารประกอบ](https://reference.aspose.com/tasks/net/) สำหรับบทช่วยสอนที่หลากหลายเกี่ยวกับคุณสมบัติ Aspose.Tasks
### ถาม: ฉันจะซื้อ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
 ตอบ: คุณสามารถซื้อ Aspose.Tasks ได้อย่างสะดวก[ที่นี่](https://purchase.aspose.com/buy).