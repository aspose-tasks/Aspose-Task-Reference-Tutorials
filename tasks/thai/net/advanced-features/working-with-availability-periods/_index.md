---
title: การทำงานกับระยะเวลาความพร้อมใช้งานใน Aspose.Tasks
linktitle: การทำงานกับระยะเวลาความพร้อมใช้งานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการระยะเวลาความพร้อมใช้งานของทรัพยากรอย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนสำหรับการทำงานกับช่วงเวลาที่พร้อมใช้งานในโปรเจ็กต์ .NET ของคุณ
weight: 17
url: /th/net/advanced-features/working-with-availability-periods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การทำงานกับระยะเวลาความพร้อมใช้งานใน Aspose.Tasks

## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับช่วงเวลาที่พร้อมใช้งานใน Aspose.Tasks สำหรับ .NET ระยะเวลาความพร้อมใช้งานมีความสำคัญอย่างยิ่งต่อการจัดการทรัพยากรอย่างมีประสิทธิภาพในสถานการณ์การจัดการโครงการ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Visual Studio: ติดตั้ง Visual Studio หรือ IDE ที่ต้องการอื่นๆ สำหรับการพัฒนา .NET
2.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐานของการเขียนโปรแกรม C#: ความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ

ก่อนที่จะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

มาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: สร้างอินสแตนซ์โครงการใหม่

```csharp
var project = new Project();
```

บรรทัดนี้เตรียมใช้งานอินสแตนซ์ใหม่ของคลาส Project ซึ่งแสดงถึงโปรเจ็กต์ใน Aspose.Tasks

## ขั้นตอนที่ 2: เพิ่มทรัพยากร

```csharp
var resource = project.Resources.Add("Work Resource");
```

ที่นี่ เราได้เพิ่มทรัพยากรใหม่ให้กับโครงการโดยใช้ชื่อ "ทรัพยากรงาน"

## ขั้นตอนที่ 3: กำหนดระยะเวลาความพร้อมใช้งาน

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 เราเรียกว่า`GetPeriods()` วิธีดึงข้อมูลการรวบรวมช่วงเวลาที่พร้อมใช้งาน

## ขั้นตอนที่ 4: เพิ่มระยะเวลาความพร้อมใช้งานให้กับทรัพยากร

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

เราวนซ้ำการรวบรวมช่วงเวลาที่พร้อมใช้งานที่ได้รับในขั้นตอนก่อนหน้า และเพิ่มลงในทรัพยากร

## ขั้นตอนที่ 5: แสดงรายละเอียดช่วงเวลาที่มีจำหน่าย

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

สุดท้าย เราจะวนดูช่วงเวลาที่พร้อมใช้งานที่เกี่ยวข้องกับทรัพยากรและพิมพ์รายละเอียด รวมถึงวันที่เริ่มต้น วันที่สิ้นสุด และหน่วยที่พร้อมใช้งาน

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีทำงานกับช่วงเวลาที่พร้อมใช้งานใน Aspose.Tasks สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถจัดการความพร้อมใช้งานของทรัพยากรในแอปพลิเคชันการจัดการโครงการของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET ในโครงการเชิงพาณิชย์ได้หรือไม่

 A1: ได้ Aspose.Tasks สำหรับ .NET สามารถใช้ในโครงการเชิงพาณิชย์ได้ คุณสามารถซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).

### คำถามที่ 2: Aspose.Tasks สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

A2: ได้ คุณสามารถขอรับ Aspose.Tasks for .NET รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะหาเอกสารสำหรับ Aspose.Tasks for .NET ได้ที่ไหน

 A3: คุณสามารถค้นหาเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/tasks/net/).

### คำถามที่ 4: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร

 A4: คุณสามารถรับการสนับสนุนจากฟอรัมชุมชนได้[ที่นี่](https://forum.aspose.com/c/tasks/15).

### คำถามที่ 5: คุณเสนอใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ .NET หรือไม่

 A5: ใช่ มีใบอนุญาตชั่วคราวให้ใช้งาน[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
