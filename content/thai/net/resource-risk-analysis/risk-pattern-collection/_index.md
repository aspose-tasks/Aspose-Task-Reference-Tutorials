---
title: จัดการรูปแบบความเสี่ยงใน MS Project ด้วย Aspose.Tasks
linktitle: การรวบรวมรูปแบบความเสี่ยงใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีการวิเคราะห์และจัดการรูปแบบความเสี่ยงอย่างมีประสิทธิภาพในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET
type: docs
weight: 24
url: /th/net/resource-risk-analysis/risk-pattern-collection/
---
## การแนะนำ
Aspose.Tasks for .NET มอบโซลูชันที่ครอบคลุมสำหรับการจัดการและวิเคราะห์รูปแบบความเสี่ยงภายในไฟล์ Microsoft Project ในบทช่วยสอนนี้ เราจะเจาะลึกวิธีการใช้ Aspose.Tasks เพื่อทำงานกับรูปแบบความเสี่ยงในโครงการของคุณอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET SDK: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET SDK จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ความรู้การทำงานของการพัฒนา .NET โดยใช้ C#
3. ไฟล์โครงการ Microsoft: เตรียมไฟล์โครงการ Microsoft พร้อมที่จะใช้งาน

## นำเข้าเนมสเปซ
ประการแรก ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks ในโปรเจ็กต์ C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.RiskAnalysis;
```
## ขั้นตอนที่ 1: เริ่มต้นการตั้งค่า RiskAnalysis
 เริ่มต้น`RiskAnalysisSettings` วัตถุที่มีพารามิเตอร์ที่ต้องการ เช่น จำนวนการวนซ้ำสำหรับการจำลองมอนติคาร์โล
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
 โหลดไฟล์ Microsoft Project ของคุณโดยใช้นามสกุล`Project` ระดับ:
```csharp
var project = new Project("Your_Project_File.mpp");
```
## ขั้นตอนที่ 3: เข้าถึงงานและสร้างรูปแบบความเสี่ยง
เข้าถึงงานภายในโครงการของคุณและสร้างรูปแบบความเสี่ยงสำหรับพวกเขา กำหนดพารามิเตอร์ เช่น ประเภทการกระจาย ค่าในแง่ดี ค่าในแง่ร้าย และระดับความเชื่อมั่น
```csharp
var task1 = project.RootTask.Children.GetById(17);
var task2 = project.RootTask.Children.GetById(18);
var pattern1 = new RiskPattern(task1)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 60,
    Pessimistic = 140,
    ConfidenceLevel = ConfidenceLevel.CL75
};
var pattern2 = new RiskPattern(task2)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
```
## ขั้นตอนที่ 4: เพิ่มรูปแบบในการตั้งค่า
เพิ่มรูปแบบความเสี่ยงที่สร้างขึ้นในการตั้งค่า:
```csharp
settings.Patterns.Add(pattern1);
settings.Patterns.Add(pattern2);
```
## ขั้นตอนที่ 5: ทำซ้ำรูปแบบ
ทำซ้ำรูปแบบความเสี่ยงที่เพิ่มเข้ามาเพื่อดูรายละเอียด:
```csharp
foreach (var pattern in settings.Patterns)
{
    Console.WriteLine("Task: " + pattern.Task);
    Console.WriteLine("Distribution: " + pattern.Distribution);
    Console.WriteLine("Optimistic: " + pattern.Optimistic);
    Console.WriteLine("Pessimistic: " + pattern.Pessimistic);
    Console.WriteLine("Confidence Level: " + pattern.ConfidenceLevel);
    Console.WriteLine();
}
```
## ขั้นตอนที่ 6: แก้ไขรูปแบบ
แก้ไขรูปแบบตามต้องการโดยใช้การเข้าถึงดัชนี:
```csharp
settings.Patterns[task1].Optimistic = 70;
settings.Patterns[task1].Pessimistic = 140;
```
## ขั้นตอนที่ 7: ลบรูปแบบ
ลบรูปแบบที่ไม่ต้องการออกจากคอลเลกชัน:
```csharp
settings.Patterns.Remove(pattern1);
```
## ขั้นตอนที่ 8: ล้างรูปแบบ
ล้างคอลเลกชันรูปแบบทีละรายการหรือทั้งหมด:
```csharp
// การกำจัดส่วนบุคคล
settings.Patterns.Clear();
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีจัดการรูปแบบความเสี่ยงในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถวิเคราะห์และจัดการรูปแบบความเสี่ยงภายในโครงการของคุณได้อย่างมีประสิทธิภาพ และเพิ่มขีดความสามารถในการจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สามารถจัดการไฟล์ Microsoft Project ขนาดใหญ่ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks ได้รับการปรับให้เหมาะกับการจัดการไฟล์โปรเจ็กต์ขนาดใหญ่อย่างมีประสิทธิภาพ จึงรับประกันประสิทธิภาพที่ราบรื่นแม้จะมีข้อมูลจำนวนมากก็ตาม
### ถาม: Aspose.Tasks รองรับการแจกแจงความน่าจะเป็นที่แตกต่างกันสำหรับการวิเคราะห์ความเสี่ยงหรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks นำเสนอการแจกแจงความน่าจะเป็นที่หลากหลาย เช่น แบบปกติ แบบสม่ำเสมอ และอื่นๆ อีกมากมาย เพื่อตอบสนองความต้องการในการวิเคราะห์ความเสี่ยงที่หลากหลาย
### ถาม: ฉันสามารถรวม Aspose.Tasks เข้ากับเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่
ตอบ: แน่นอน Aspose.Tasks ทำงานร่วมกับเฟรมเวิร์ก .NET อื่นๆ ได้อย่างราบรื่น ช่วยให้คุณสามารถใช้ประโยชน์จากความสามารถบนแพลตฟอร์มและแอปพลิเคชันต่างๆ ได้
### ถาม: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึง Aspose.Tasks รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/)ทำให้คุณสำรวจฟีเจอร์ต่างๆ ก่อนตัดสินใจซื้อได้
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถดูการสนับสนุนและความช่วยเหลือที่ครอบคลุมได้ในฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15)ซึ่งคุณสามารถโต้ตอบกับผู้เชี่ยวชาญและเพื่อนผู้ใช้เพื่อแก้ไขข้อสงสัยและปัญหาต่างๆ