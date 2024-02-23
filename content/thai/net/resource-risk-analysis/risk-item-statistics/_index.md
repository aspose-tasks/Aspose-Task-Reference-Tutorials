---
title: สถิติสำหรับรายการความเสี่ยงใน Aspose.Tasks
linktitle: สถิติสำหรับรายการความเสี่ยงใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: ปลดล็อกพลังของการวิเคราะห์ความเสี่ยงในไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET รับข้อมูลเชิงลึก ลดความไม่แน่นอน และขับเคลื่อนความสำเร็จของโครงการได้อย่างง่ายดาย
type: docs
weight: 21
url: /th/net/resource-risk-analysis/risk-item-statistics/
---
## การแนะนำ
คุณต้องการปรับปรุงความสามารถในการจัดการโครงการโดยใช้ Aspose.Tasks สำหรับ .NET หรือไม่? เจาะลึกขอบเขตของการวิเคราะห์ความเสี่ยงด้วยบทช่วยสอนทีละขั้นตอนของเราเกี่ยวกับการรับสถิติสำหรับรายการความเสี่ยงในไฟล์ MS Project ด้วยการใช้ประโยชน์จากความสามารถอันทรงพลังของ Aspose.Tasks คุณจะได้รับข้อมูลเชิงลึกอันล้ำค่าเกี่ยวกับความไม่แน่นอนของโครงการ และทำการตัดสินใจอย่างมีข้อมูลเพื่อลดความเสี่ยงได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางครั้งนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจากไฟล์[Aspose.Tasks สำหรับเอกสาร .NET](https://reference.aspose.com/tasks/net/), ไลบรารีนี้จัดเตรียมเครื่องมือที่มีประสิทธิภาพสำหรับการจัดการไฟล์ MS Project โดยทางโปรแกรม
2. สภาพแวดล้อมการพัฒนา .NET: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ของคุณ รวมถึง Visual Studio หรือ IDE อื่นๆ ที่คุณเลือก เพื่ออำนวยความสะดวกในการผสานรวม Aspose.Tasks ในโครงการของคุณได้อย่างราบรื่น

## นำเข้าเนมสเปซ
รวมเนมสเปซที่จำเป็นในโครงการของคุณเพื่อควบคุมฟังก์ชันการทำงานของ Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
```csharp
String DataDir = "Your Document Directory";
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Document Directory"`ด้วยเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีไฟล์ MS Project ของคุณอยู่
## ขั้นตอนที่ 2: กำหนดการตั้งค่าการวิเคราะห์ความเสี่ยง
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 ปรับ`IterationsCount` พารามิเตอร์ตามความต้องการโครงการของคุณเพื่อควบคุมความแม่นยำของการวิเคราะห์ความเสี่ยง
## ขั้นตอนที่ 3: โหลดไฟล์โครงการ MS
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 โหลดไฟล์ MS Project ที่ต้องการลงในไฟล์`project` วัตถุเพื่อการวิเคราะห์ต่อไป
## ขั้นตอนที่ 4: กำหนดงานและเริ่มต้นรูปแบบความเสี่ยง
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
ระบุงานสำหรับการวิเคราะห์ความเสี่ยงและกำหนดค่ารูปแบบความเสี่ยงด้วยพารามิเตอร์ที่เหมาะสม เช่น ประเภทการกระจาย ระยะเวลาในแง่ดีและแง่ร้าย และระดับความเชื่อมั่น
## ขั้นตอนที่ 5: วิเคราะห์ความเสี่ยงของโครงการ
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
เริ่มต้นกระบวนการวิเคราะห์ความเสี่ยงโดยใช้การตั้งค่าที่กำหนดไว้และข้อมูลโครงการ
## ขั้นตอนที่ 6: ดึงข้อมูลและแสดงสถิติ
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
เรียกค้นและแสดงตัวชี้วัดทางสถิติต่างๆ ที่เกี่ยวข้องกับรายการความเสี่ยงในไฟล์ MS Project รวมถึงค่าที่คาดหวัง ส่วนเบี่ยงเบนมาตรฐาน เปอร์เซ็นไทล์ ค่าต่ำสุด และค่าสูงสุด

## บทสรุป
โดยสรุป การเรียนรู้การวิเคราะห์ความเสี่ยงในไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET จะเปิดขอบเขตความเป็นไปได้สำหรับผู้จัดการโครงการและผู้มีส่วนได้ส่วนเสีย ด้วยการทำตามบทช่วยสอนที่ครอบคลุมของเรา คุณสามารถก้าวผ่านความไม่แน่นอนได้อย่างมั่นใจ และรับประกันผลลัพธ์ของโครงการที่ประสบความสำเร็จ
## คำถามที่พบบ่อย
### ฉันสามารถรวม Aspose.Tasks เข้ากับไลบรารี .NET อื่นๆ เพื่อขยายฟังก์ชันการทำงานได้หรือไม่
อย่างแน่นอน! Aspose.Tasks ผสานรวมกับไลบรารี .NET ต่างๆ ได้อย่างราบรื่น ช่วยให้คุณสามารถขยายขีดความสามารถของไลบรารีได้ตามความต้องการของโปรเจ็กต์ของคุณ
### มีรุ่นทดลองใช้สำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติของ Aspose.Tasks ได้โดยเข้าไปที่[ทดลองฟรี](https://releases.aspose.com/) ที่มีอยู่ในเว็บไซต์ของเรา
### มีการเผยแพร่การอัปเดตและการปรับปรุงสำหรับ Aspose.Tasks บ่อยเพียงใด
เรามุ่งมั่นที่จะปรับปรุง Aspose.Tasks อย่างต่อเนื่องโดยการปล่อยการอัปเดตและการปรับปรุงเป็นระยะ เพื่อให้มั่นใจว่าคุณจะสามารถเข้าถึงคุณสมบัติและการเพิ่มประสิทธิภาพล่าสุดได้ตลอดเวลา
### ฉันสามารถรับการสนับสนุนด้านเทคนิคสำหรับ Aspose.Tasks ได้หรือไม่
แน่นอน! ทีมสนับสนุนเฉพาะของเราพร้อมให้บริการบน[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อช่วยเหลือคุณในการสอบถามหรือความท้าทายใดๆ ที่คุณอาจพบในระหว่างเส้นทางการดำเนินงานของคุณ
### คุณมีใบอนุญาตชั่วคราวสำหรับโครงการระยะสั้นหรือไม่?
 ได้ หากคุณต้องการ Aspose.Tasks สำหรับโครงการระยะสั้น คุณสามารถใช้ประโยชน์จากเราได้อย่างสะดวก[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) ตัวเลือกเพื่อตอบสนองความต้องการด้านใบอนุญาตของคุณโดยไม่มีข้อผูกมัดระยะยาว