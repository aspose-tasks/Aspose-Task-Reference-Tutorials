---
date: 2026-03-21
description: เรียนรู้วิธีจัดการช่วงเวลาการพร้อมใช้งานของทรัพยากรและบรรลุการพร้อมใช้งานของทรัพยากรโครงการอย่างมีประสิทธิภาพด้วย
  Aspose.Tasks สำหรับ .NET คู่มือขั้นตอนต่อขั้นตอนนี้แสดงวิธีเพิ่ม, ปรับปรุงและลบช่วงเวลาการพร้อมใช้งาน.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: ความพร้อมของทรัพยากรโครงการ – การจัดการช่วงเวลาความพร้อมใน Aspose.Tasks
url: /th/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ความพร้อมของทรัพยากรโครงการ: การรวบรวมช่วงเวลาความพร้อมใน Aspose.Tasks

การจัดการ **ความพร้อมของทรัพยากรโครงการ** เป็นส่วนสำคัญของการวางแผนโครงการที่ประสบความสำเร็จ. ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีจัดการความพร้อม** ของทรัพยากรโดยใช้ Aspose.Tasks for .NET API ทีละขั้นตอน ตั้งแต่การโหลดโครงการจนถึงการคัดลอกช่วงเวลาระหว่างทรัพยากร.

## คำตอบด่วน
- **คลาสหลักสำหรับช่วงเวลาความพร้อมคืออะไร?** `AvailabilityPeriod` in the `Aspose.Tasks` namespace.  
- **ฉันสามารถลบช่วงเวลาที่มีอยู่ได้หรือไม่?** Yes, call `resource.AvailabilityPeriods.Clear()`.  
- **ฉันจะเพิ่มช่วงเวลาใหม่อย่างไร?** Create an `AvailabilityPeriod` object and use `Add` or `Insert`.  
- **สามารถคัดลอกช่วงเวลาไปยังทรัพยากรอื่นได้หรือไม่?** Absolutely – use `CopyTo` and then add each item to the target resource.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** Yes, a commercial Aspose.Tasks license is required for non‑trial deployments.

## ความพร้อมของทรัพยากรโครงการคืออะไร?
ความพร้อมของทรัพยากรโครงการกำหนดวันที่และหน่วย (เปอร์เซ็นต์ของความจุ) ที่ทรัพยากรสามารถถูกมอบหมายให้กับงานได้ การควบคุมช่วงเวลาเหล่านี้ช่วยป้องกันการจัดสรรเกินและปรับปรุงความแม่นยำของกำหนดเวลา.

## ทำไมต้องใช้ Aspose.Tasks เพื่อจัดการช่วงเวลาความพร้อม?
- **การบูรณาการเต็มรูปแบบกับ .NET** – ไม่มี COM interop, โค้ดที่จัดการโดย .NET อย่างเดียว.  
- **การควบคุมระดับละเอียด** – ตั้งค่าวันเริ่มต้น/สิ้นสุดที่แม่นยำและหน่วยเศษส่วน.  
- **คัดลอกง่าย** – ย้ายข้อมูลความพร้อมระหว่างทรัพยากรโดยไม่ต้องทำการแยกวิเคราะห์ด้วยตนเอง.  
- **ปรับประสิทธิภาพการทำงาน** – ทำงานกับไฟล์ MPP ขนาดใหญ่ได้อย่างมีประสิทธิภาพ.

## ข้อกำหนดเบื้องต้น
1. **Visual Studio** – เวอร์ชันล่าสุดใดก็ได้ (2019, 2022 หรือใหม่กว่า).  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดจาก [here](https://releases.aspose.com/tasks/net/).  
3. **ความรู้พื้นฐาน C#** – คุณควรคุ้นเคยกับคลาส, คอลเลกชัน, และ LINQ.

## นำเข้า Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

เรานำเข้า namespace หลักของ Aspose.Tasks พร้อมกับคอลเลกชันมาตรฐานของ .NET ที่เราจะต้องใช้ในภายหลัง.

## ขั้นตอนที่ 1: เริ่มต้นโครงการและทรัพยากร

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

ที่นี่เราจะโหลดไฟล์ MPP ที่มีอยู่และดึงทรัพยากรที่ต้องการแก้ไขความพร้อม (ID = 1).

## ขั้นตอนที่ 2: ลบช่วงเวลาความพร้อมที่มีอยู่

```csharp
resource.AvailabilityPeriods.Clear();
```

การลบจะทำให้ช่วงเวลาที่กำหนดไว้ก่อนหน้านี้หายไป ทำให้เราได้พื้นที่ว่างใหม่.

## ขั้นตอนที่ 3: เพิ่มช่วงเวลาความพร้อม

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

เราดึงคอลเลกชันของอ็อบเจ็กต์ `AvailabilityPeriod` (สมมติว่า helper `GetPeriods` ถูกกำหนดไว้ในที่อื่น) และเพิ่มแต่ละอันโดยตรวจสอบว่าคอลเลกชันสามารถเขียนได้.

## ขั้นตอนที่ 4: แทรกช่วงเวลาความพร้อมใหม่

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

ส่วนนี้สร้างช่วงเวลาที่กำหนดเองสำหรับปี 2013 และแทรกที่ตำแหน่ง 1 (ช่องที่สอง) หากยังไม่มีอยู่.

## ขั้นตอนที่ 5: แสดงช่วงเวลาความพร้อม

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

การพิมพ์ข้อมูลสั้น ๆ บนคอนโซลจะแสดงจำนวนทั้งหมดและรายละเอียดของแต่ละช่วง – มีประโยชน์สำหรับการดีบักหรือยืนยัน.

## ขั้นตอนที่ 6: คัดลอกช่วงเวลาความพร้อมไปยังทรัพยากรอื่น

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

เราคัดลอกคอลเลกชันทั้งหมดเป็นอาเรย์, ลบช่วงเวลาของทรัพยากรเป้าหมาย, แล้วเติมข้อมูลใหม่ นี่แสดงวิธีทำสำเนาข้อมูลความพร้อมระหว่างทรัพยากร.

## ขั้นตอนที่ 7: ปรับปรุงและลบช่วงเวลาความพร้อม

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

ที่นี่เราปรับ `AvailableUnits` ของช่วงเวลาที่เป็นอันดับก่อนสุดท้าย แล้วลบช่วงปี 2013 ที่เราเพิ่มไว้ก่อนหน้านี้.

## ปัญหาที่พบบ่อยและวิธีแก้
- **ข้อผิดพลาดคอลเลกชันแบบอ่านอย่างเดียว** – ตรวจสอบว่าโครงการไม่ได้เปิดในโหมดอ่านอย่างเดียวหรือคุณได้เรียก `resource.AvailabilityPeriods.Clear()` ก่อนเพิ่มรายการใหม่.  
- **ช่วงเวลาที่ทับซ้อน** – Aspose.Tasks ไม่ได้รวมช่วงที่ทับซ้อนโดยอัตโนมัติ; คุณอาจต้องเขียนตรรกะกำหนดเองเพื่อค้นหาและแก้ไข.  
- **รูปแบบวันที่ไม่ถูกต้อง** – ควรใช้วัตถุ `DateTime` เสมอ; การแปลงสตริงอาจทำให้เกิดบั๊กตามภาษาท้องถิ่น.

## คำถามที่พบบ่อย

**Q: ฉันสามารถเพิ่มฟิลด์กำหนดเองให้กับช่วงเวลาความพร้อมได้หรือไม่?**  
A: No, availability periods in Aspose.Tasks for .NET do not support custom fields.

**Q: ช่วงเวลาความพร้อมเชื่อมโยงกับงานเฉพาะหรือไม่?**  
A: No, they are associated with resources and define when the resource is generally available for tasks.

**Q: ฉันสามารถนำเข้าช่วงเวลาความพร้อมจากแหล่งภายนอกได้หรือไม่?**  
A: Yes, you can import periods from CSV, XML, or a database by creating `AvailabilityPeriod` objects and adding them to the collection.

**Q: ฉันจะจัดการกับช่วงเวลาความพร้อมที่ทับซ้อนอย่างไร?**  
A: Overlaps are not resolved automatically; you need to implement custom validation to merge or reject conflicting periods.

**Q: มีขีดจำกัดจำนวนช่วงเวลาความพร้อมที่ทรัพยากรหนึ่งสามารถมีได้หรือไม่?**  
A: There is no hard‑coded limit, but very large collections may affect performance; consider consolidating periods where possible.

## สรุป

ในคู่มือนี้เราได้ครอบคลุมทุกสิ่งที่คุณต้องรู้เพื่อจัดการ **ความพร้อมของทรัพยากรโครงการ** ด้วย Aspose.Tasks for .NET—from initializing a project and clearing old data, to adding, inserting, copying, updating, and removing availability periods. การเชี่ยวชาญขั้นตอนเหล่านี้ช่วยให้คุณรักษาปฏิทินทรัพยากรให้แม่นยำและทำให้กำหนดเวลาโครงการเป็นจริงได้.

---

**อัปเดตล่าสุด:** 2026-03-21  
**ทดสอบด้วย:** Aspose.Tasks for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}