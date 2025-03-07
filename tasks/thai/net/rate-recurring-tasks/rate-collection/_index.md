---
title: อัตราโครงการ MS ต้นแบบด้วย Aspose.Tasks
linktitle: การรวบรวมอัตราใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการอัตราในไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET บทช่วยสอนทีละขั้นตอนสำหรับการจัดการทรัพยากรอย่างมีประสิทธิภาพ
weight: 11
url: /th/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อัตราโครงการ MS ต้นแบบด้วย Aspose.Tasks

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนของเราเกี่ยวกับการจัดการอัตราใน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET! ในคู่มือนี้ เราจะแนะนำคุณตลอดกระบวนการทำงานกับอัตราในไฟล์ MS Project ของคุณโดยใช้ Aspose.Tasks ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นพัฒนา .NET บทช่วยสอนนี้จะให้คำแนะนำทีละขั้นตอนเพื่อจัดการอัตราภายในโครงการของคุณอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### 1. ติดตั้ง Visual Studio แล้ว
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนระบบของคุณ คุณสามารถดาวน์โหลดได้จากเว็บไซต์หากยังไม่ได้ดาวน์โหลด
### 2. Aspose.Tasks สำหรับ .NET
 ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[เว็บไซต์](https://releases.aspose.com/tasks/net/).
### 3. ความรู้พื้นฐานเกี่ยวกับ C# และ .NET
ทำความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และพื้นฐานเฟรมเวิร์ก .NET เพื่อทำความเข้าใจตัวอย่างโค้ดที่ให้ไว้ในบทช่วยสอนนี้ให้ดียิ่งขึ้น
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ MS
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 ที่นี่เราสร้างใหม่`Project` วัตถุโดยการโหลดไฟล์ MS Project ที่มีอยู่
## ขั้นตอนที่ 2: เพิ่มทรัพยากรและตั้งค่างานและราคา
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
เราเพิ่มทรัพยากรใหม่ให้กับโครงการ กำหนดประเภทเป็นงาน จำนวนงาน และอัตรามาตรฐาน
## ขั้นตอนที่ 3: เพิ่มอัตราให้กับทรัพยากร
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
เราเพิ่มอัตราให้กับทรัพยากรโดยระบุวันที่เริ่มต้นและสิ้นสุด อัตรามาตรฐาน และรูปแบบอัตรา
## ขั้นตอนที่ 4: พิมพ์ข้อมูลอัตรา
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
ขั้นตอนนี้จะพิมพ์ข้อมูลเกี่ยวกับอัตราที่เกี่ยวข้องกับทรัพยากร
## ขั้นตอนที่ 5: อัปเดตอัตรา
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
เราอัปเดตวันที่สิ้นสุดของอัตราที่เฉพาะเจาะจง
## ขั้นตอนที่ 6: ลบอัตรา
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
ขั้นตอนนี้จะลบอัตราทั้งหมดสำหรับประเภทใดประเภทหนึ่ง
## ขั้นตอนที่ 7: วนซ้ำอัตราที่เหลือ
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
สุดท้ายนี้ เราจะวนซ้ำอัตราที่เหลือหลังจากการนำออก
## บทสรุป
โดยสรุป บทช่วยสอนนี้จะให้คำแนะนำที่ครอบคลุมเกี่ยวกับการจัดการอัตราในไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการอัตราภายในโปรเจ็กต์ของคุณได้อย่างมีประสิทธิภาพ และรับประกันการจัดการทรัพยากรที่แม่นยำ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับซอฟต์แวร์การจัดการโครงการอื่นๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับการทำงานร่วมกับซอฟต์แวร์การจัดการโครงการต่างๆ รวมถึง MS Project, Primavera และอื่นๆ อีกมากมาย
### ถาม: Aspose.Tasks สำหรับ .NET เข้ากันได้กับไฟล์ MS Project เวอร์ชันต่างๆ หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ .NET รองรับการทำงานกับไฟล์ MS Project ในเวอร์ชันต่างๆ ทำให้มั่นใจได้ถึงความยืดหยุ่นและความเข้ากันได้
### ถาม: Aspose.Tasks for .NET มีเอกสารประกอบและการสนับสนุนหรือไม่
 ตอบ: ได้ คุณสามารถค้นหาเอกสารที่ครอบคลุมและเข้าถึงฟอรัมสนับสนุนได้ที่ Aspose.Tasks[เว็บไซต์](https://reference.aspose.com/tasks/net/).
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks สำหรับ .NET ก่อนซื้อได้หรือไม่
ตอบ: ได้ คุณสามารถใช้ Aspose.Tasks สำหรับ .NET รุ่นทดลองใช้ฟรีเพื่อประเมินคุณสมบัติและความเข้ากันได้กับความต้องการของคุณ
### ถาม: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 ตอบ: คุณสามารถซื้อใบอนุญาตสำหรับ Aspose.Tasks สำหรับ .NET ได้จาก[เว็บไซต์](https://purchase.aspose.com/temporary-license/)ซึ่งมีตัวเลือกใบอนุญาตที่ยืดหยุ่นเพื่อให้เหมาะกับความต้องการของคุณ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
