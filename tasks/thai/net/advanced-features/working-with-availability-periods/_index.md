---
date: 2026-04-06
description: เรียนรู้วิธีเพิ่มทรัพยากรลงในโครงการและกำหนดช่วงเวลาการพร้อมใช้งานของทรัพยากรโดยใช้
  Aspose.Tasks สำหรับ .NET คู่มือแบบขั้นตอนต่อขั้นตอนสำหรับการจัดการปฏิทินทรัพยากร
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: การทำงานกับช่วงเวลาความพร้อมใช้งานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: เพิ่มทรัพยากรลงในโครงการและตั้งค่าความพร้อมใช้งานใน Aspose.Tasks
url: /th/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มทรัพยากรไปยังโครงการและตั้งค่าความพร้อมใช้งานใน Aspose.Tasks

## บทนำ

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีเพิ่มทรัพยากรไปยังโครงการ** และจากนั้นกำหนดช่วงเวลาความพร้อมใช้งานโดยใช้ไลบรารี Aspose.Tasks .NET การจัดการปฏิทินทรัพยากรเป็นสิ่งสำคัญสำหรับตารางโครงการที่เป็นจริง และขั้นตอนต่อไปนี้จะพาคุณผ่านกระบวนการทั้งหมด — ตั้งแต่การสร้างอินสแตนซ์ของโครงการจนถึงการพิมพ์รายละเอียดของแต่ละช่วงเวลา

## คำตอบด่วน
- **เป้าหมายหลักคืออะไร?** เพื่อเพิ่มทรัพยากรไปยังโครงการและกำหนดช่วงเวลาความพร้อมใช้งาน.  
- **ต้องการไลบรารีใด?** Aspose.Tasks for .NET.  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** ใช่ จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **เวลาในการดำเนินการ?** โดยทั่วไปใช้เวลาน้อยกว่า 15 minutes สำหรับสถานการณ์พื้นฐาน.

## อะไรคือ “add resource to project”?

การเพิ่มทรัพยากรไปยังโครงการสร้างตำแหน่งสำหรับบุคคล, อุปกรณ์ หรือวัสดุที่สามารถมอบหมายให้กับงานได้ เมื่อทรัพยากรมีอยู่แล้วคุณสามารถ **ตั้งค่าความพร้อมใช้งานของทรัพยากร**, กำหนดปฏิทินการทำงาน, และให้ตัวจัดตารางเวลาปฏิบัติตามข้อจำกัดเหล่านั้น

## ทำไมต้องกำหนดกำหนดการทำงานและช่วงเวลาความพร้อมใช้งาน?

- **การวางแผนที่แม่นยำ:** งานจะถูกกำหนดเวลาเฉพาะเมื่อทรัพยากรว่างจริง.  
- **การควบคุมต้นทุน:** หน่วยความพร้อมใช้งานสะท้อนการทำงานแบบพาร์ทไทม์ ช่วยให้คุณคำนวณค่าแรงได้อย่างถูกต้อง.  
- **การปรับระดับทรัพยากร:** ระบบสามารถปรับระดับการจัดสรรเกินได้โดยอัตโนมัติเมื่อรู้ปฏิทินของแต่ละทรัพยากร.

## ข้อกำหนดเบื้องต้น

1. Visual Studio (หรือ IDE ที่รองรับ .NET ใดก็ได้).  
2. Aspose.Tasks for .NET – ดาวน์โหลดจาก [here](https://releases.aspose.com/tasks/net/).  
3. ความรู้พื้นฐานของ C#.

## นำเข้า Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## วิธีเพิ่มทรัพยากรไปยังโครงการ?

### ขั้นตอน 1: สร้างอินสแตนซ์ `Project` ใหม่

```csharp
var project = new Project();
```

อ็อบเจ็กต์นี้แสดงถึงไฟล์โครงการทั้งหมดในหน่วยความจำ

### ขั้นตอน 2: เพิ่มทรัพยากรไปยังโครงการ

```csharp
var resource = project.Resources.Add("Work Resource");
```

การเรียกนี้สร้าง **resource** ชื่อ *Work Resource* ที่คุณสามารถแนบไปยังงานในภายหลัง

### ขั้นตอน 3: กำหนดช่วงเวลาความพร้อมใช้งาน

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` เป็นเมธอดช่วยเหลือ (ไม่ได้แสดงการทำงาน) ที่คืนคอลเลกชันของอ็อบเจ็กต์ `AvailabilityPeriod` แต่ละช่วงระบุวันที่เริ่มต้น, วันที่สิ้นสุด, และหน่วย (เปอร์เซ็นต์ของความพยายามเต็มเวลา) ที่ทรัพยากรพร้อมใช้งาน

### ขั้นตอน 4: เพิ่มช่วงเวลาไปยัง resource

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

ที่นี่เรา **ตั้งค่าความพร้อมใช้งานของทรัพยากร** โดยวนลูปผ่านคอลเลกชันและเพิ่มแต่ละช่วงเวลาไปยังปฏิทินของทรัพยากร

### ขั้นตอน 5: แสดงรายละเอียดความพร้อมใช้งาน

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

ผลลัพธ์บนคอนโซลช่วยให้คุณตรวจสอบว่าช่วงเวลาถูกจัดเก็บอย่างถูกต้อง

## ข้อผิดพลาดทั่วไปและเคล็ดลับ

- **ความแม่นยำของวันที่:** `AvailableFrom` และ `AvailableTo` เป็นค่า `DateTime`; ตรวจสอบให้แน่ใจว่าตั้งเป็นเที่ยงคืนหากต้องการช่วงเวลาเต็มวัน.  
- **ช่วงค่าหน่วย:** ค่าที่ถูกต้องอยู่ระหว่าง 0‑100 %; ค่าที่อยู่นอกช่วงนี้จะทำให้เกิดข้อยกเว้น.  
- **ช่วงเวลาที่ทับซ้อน:** ช่วงเวลาที่ทับซ้อนจะถูกรวมโดยอัตโนมัติ, แต่การแยกให้ชัดเจนจะทำให้เข้าใจง่ายกว่า.

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้ Aspose.Tasks for .NET ในโครงการเชิงพาณิชย์ได้หรือไม่?
A1: ใช่, Aspose.Tasks for .NET สามารถใช้ในโครงการเชิงพาณิชย์ได้ คุณสามารถซื้อใบอนุญาตได้จาก [here](https://purchase.aspose.com/buy).

### Q2: มีการทดลองใช้งานฟรีสำหรับ Aspose.Tasks for .NET หรือไม่?
A2: ใช่, คุณสามารถรับการทดลองใช้งานฟรีของ Aspose.Tasks for .NET ได้จาก [here](https://releases.aspose.com/).

### Q3: ฉันจะหาเอกสารสำหรับ Aspose.Tasks for .NET ได้ที่ไหน?
A3: คุณสามารถหาเอกสารได้จาก [here](https://reference.aspose.com/tasks/net/).

### Q4: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks for .NET ได้อย่างไร?
A4: คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชนได้ที่ [here](https://forum.aspose.com/c/tasks/15).

### Q5: คุณมีใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks for .NET หรือไม่?
A5: มี, ใบอนุญาตชั่วคราวพร้อมให้บริการที่ [here](https://purchase.aspose.com/temporary-license/).

---

**อัปเดตล่าสุด:** 2026-04-06  
**ทดสอบด้วย:** Aspose.Tasks for .NET (latest stable release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}