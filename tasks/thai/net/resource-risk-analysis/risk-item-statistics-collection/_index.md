---
title: รวบรวมสถิติรายการความเสี่ยงของโครงการ MS ใน Aspose.Tasks
linktitle: การรวบรวมสถิติรายการความเสี่ยงใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีรวบรวมสถิติรายการความเสี่ยงจากไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ปรับปรุงความสามารถในการจัดการโครงการของคุณ
weight: 22
url: /th/net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รวบรวมสถิติรายการความเสี่ยงของโครงการ MS ใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการรวบรวมสถิติรายการความเสี่ยงจากไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ไลบรารีนี้มีฟังก์ชันที่มีประสิทธิภาพในการวิเคราะห์ข้อมูลโครงการ รวมถึงการประเมินความเสี่ยงและการวิเคราะห์ทางสถิติ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks คุณสามารถรับได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาสำหรับการเขียนโปรแกรม .NET

## นำเข้าเนมสเปซ
ก่อนที่คุณจะเริ่มเขียนโค้ด ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณแล้ว:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
ขั้นแรก คุณต้องโหลดไฟล์ MS Project ลงในแอปพลิเคชันของคุณ นี่คือวิธีที่คุณสามารถบรรลุเป้าหมายได้:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## ขั้นตอนที่ 2: กำหนดการตั้งค่าการวิเคราะห์ความเสี่ยง
เริ่มต้นการตั้งค่าการวิเคราะห์ความเสี่ยง รวมถึงจำนวนการวนซ้ำ ดังที่แสดงด้านล่าง:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## ขั้นตอนที่ 3: เริ่มต้นรูปแบบความเสี่ยง
กำหนดรูปแบบความเสี่ยงสำหรับการวิเคราะห์ ระบุประเภทการกระจาย เปอร์เซ็นต์ในแง่ดีและแง่ร้าย และระดับความเชื่อมั่น:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## ขั้นตอนที่ 4: ทำการวิเคราะห์ความเสี่ยง
 ยกตัวอย่าง`RiskAnalyzer` ชั้นเรียนและวิเคราะห์โครงการ:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## ขั้นตอนที่ 5: ดึงข้อมูลสถิติ
รับสถิติรายการความเสี่ยง เช่น การเสร็จเร็ว จากผลการวิเคราะห์:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## ขั้นตอนที่ 6: พิมพ์สถิติ
ทำซ้ำสถิติและพิมพ์รายละเอียด:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //พิมพ์สถิติอื่นๆ ที่เกี่ยวข้อง...
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.Tasks สำหรับ .NET เพื่อรวบรวมสถิติรายการความเสี่ยงจากไฟล์ MS Project เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถวิเคราะห์ข้อมูลโครงการและประเมินความเสี่ยงที่อาจเกิดขึ้นได้อย่างมีประสิทธิภาพ ช่วยในการตัดสินใจและการจัดการโครงการได้ดียิ่งขึ้น

## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สามารถจัดการไฟล์ MS Project ขนาดใหญ่ได้หรือไม่
ตอบ: ได้ Aspose.Tasks สามารถจัดการไฟล์ MS Project ขนาดใหญ่ได้อย่างมีประสิทธิภาพ โดยให้ประสิทธิภาพที่เชื่อถือได้และความสามารถในการปรับขนาดได้
### ถาม: Aspose.Tasks รองรับไฟล์โปรเจ็กต์รูปแบบอื่นนอกเหนือจาก .mpp หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์โปรเจ็กต์หลากหลายรูปแบบ รวมถึง XML และ MPT
### ถาม: Aspose.Tasks เหมาะสำหรับแอปพลิเคชันการจัดการโครงการระดับองค์กรหรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks ได้รับการออกแบบมาเพื่อตอบสนองความต้องการของแอปพลิเคชันการจัดการโครงการระดับองค์กร โดยมีฟีเจอร์ที่แข็งแกร่งและเอกสารประกอบที่ครอบคลุม
### ถาม: ฉันสามารถปรับแต่งการตั้งค่าการวิเคราะห์ความเสี่ยงใน Aspose.Tasks ได้หรือไม่
ตอบ: ได้ Aspose.Tasks มอบความยืดหยุ่นในการกำหนดการตั้งค่าการวิเคราะห์ความเสี่ยงเพื่อให้เหมาะกับความต้องการและสถานการณ์เฉพาะของโครงการของคุณ
### ถาม: มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่
 ตอบ: ได้ ผู้ใช้ Aspose.Tasks สามารถเข้าถึงการสนับสนุนด้านเทคนิคผ่าน Aspose[ฟอรั่ม](https://forum.aspose.com/c/tasks/15)ซึ่งพวกเขาสามารถถามคำถาม รายงานปัญหา และโต้ตอบกับชุมชนได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
