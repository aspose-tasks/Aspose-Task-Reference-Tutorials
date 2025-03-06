---
title: การรวบรวมช่วงเวลาที่พร้อมใช้งานใน Aspose.Tasks
linktitle: การรวบรวมช่วงเวลาที่พร้อมใช้งานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการช่วงเวลาที่พร้อมใช้งานสำหรับทรัพยากรใน Aspose.Tasks for .NET บทช่วยสอนทีละขั้นตอนนี้จะแนะนำคุณในการเพิ่ม อัปเดต และลบช่วงเวลาที่พร้อมใช้งาน เพื่อให้มั่นใจว่าการวางแผนทรัพยากรโครงการมีประสิทธิผล
type: docs
weight: 18
url: /th/net/advanced-features/availability-period-collection/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับคอลเลกชันระยะเวลาความพร้อมใช้งานของทรัพยากรใน Aspose.Tasks สำหรับ .NET การจัดการระยะเวลาความพร้อมใช้งานเป็นสิ่งสำคัญสำหรับการจัดการโครงการ ช่วยให้เราสามารถกำหนดเวลาได้ว่าทรัพยากรจะพร้อมใช้งานสำหรับงานภายในโครงการเมื่อใด

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนระบบของคุณ
2.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐาน: ความคุ้นเคยกับกรอบงาน C# และ .NET

## นำเข้าเนมสเปซ

ขั้นแรก เราต้องนำเข้าเนมสเปซที่จำเป็นให้กับโปรเจ็กต์ของเรา:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

มาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอนและทำความเข้าใจแต่ละส่วน:

## ขั้นตอนที่ 1: เริ่มต้นโครงการและทรัพยากร

```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

ที่นี่ เรากำลังโหลดไฟล์โครงการและรับทรัพยากรเฉพาะตาม ID ของไฟล์

## ขั้นตอนที่ 2: ล้างช่วงเวลาที่พร้อมใช้งานที่มีอยู่

```csharp
resource.AvailabilityPeriods.Clear();
```

เราล้างช่วงเวลาที่พร้อมใช้งานที่เกี่ยวข้องกับทรัพยากร

## ขั้นตอนที่ 3: เพิ่มช่วงเวลาที่พร้อมใช้งาน

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

เราวนซ้ำคอลเลกชันช่วงเวลาที่พร้อมใช้งานและเพิ่มลงในทรัพยากร

## ขั้นตอนที่ 4: ใส่ระยะเวลาความพร้อมใช้งานใหม่

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

เราสร้างช่วงเวลาที่พร้อมใช้งานใหม่สำหรับปี 2013 และแทรกลงในคอลเลกชัน

## ขั้นตอนที่ 5: แสดงช่วงเวลาที่มีจำหน่าย

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

เราพิมพ์จำนวนและรายละเอียดของแต่ละช่วงเวลาที่พร้อมใช้งานที่เกี่ยวข้องกับทรัพยากร

## ขั้นตอนที่ 6: คัดลอกระยะเวลาความพร้อมใช้งานไปยังทรัพยากรอื่น

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

เราคัดลอกช่วงเวลาที่พร้อมใช้งานจากแหล่งข้อมูลหนึ่งไปยังอีกแหล่งข้อมูลหนึ่ง

## ขั้นตอนที่ 7: อัปเดตและลบช่วงเวลาที่พร้อมใช้งาน

```csharp
// อัพเดทยูนิตว่างในช่วงเวลาที่กำหนด
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// ลบช่วงเวลาที่เฉพาะเจาะจง
otherResource.AvailabilityPeriods.Remove(period2013);
```

เราอัปเดตหน่วยที่มีอยู่ในช่วงเวลาหนึ่งและลบช่วงเวลาเฉพาะออกจากคอลเลกชัน

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีทำงานกับคอลเลกชันช่วงเวลาที่พร้อมใช้งานใน Aspose.Tasks สำหรับ .NET การจัดการความพร้อมของทรัพยากรถือเป็นสิ่งสำคัญสำหรับการวางแผนและการดำเนินโครงการอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถเพิ่มฟิลด์ที่กำหนดเองในช่วงเวลาที่พร้อมใช้งานได้หรือไม่

A1: ไม่ รอบระยะเวลาความพร้อมใช้งานใน Aspose.Tasks สำหรับ .NET ไม่สนับสนุนเขตข้อมูลแบบกำหนดเอง

### คำถามที่ 2: ระยะเวลาว่างเชื่อมโยงกับงานเฉพาะหรือไม่

A2: ไม่ ช่วงเวลาที่พร้อมใช้งานจะเชื่อมโยงกับทรัพยากรและกำหนดเวลาที่พร้อมใช้งานสำหรับงานทั่วไป

### คำถามที่ 3: ฉันสามารถนำเข้าช่วงเวลาที่พร้อมใช้งานจากแหล่งภายนอกได้หรือไม่

ตอบ 3: ได้ คุณสามารถนำเข้าช่วงเวลาที่พร้อมใช้งานจากแหล่งข้อมูลต่างๆ ได้โดยใช้ Aspose.Tasks สำหรับ .NET API

### คำถามที่ 4: ฉันจะจัดการกับช่วงเวลาที่พร้อมใช้งานที่ทับซ้อนกันได้อย่างไร

A4: Aspose.Tasks สำหรับ .NET ไม่มีกลไกในตัวเพื่อจัดการรอบระยะเวลาที่ทับซ้อนกัน คุณอาจจำเป็นต้องใช้ตรรกะแบบกำหนดเองเพื่อจัดการสถานการณ์ดังกล่าว

### คำถามที่ 5: มีการจำกัดจำนวนช่วงเวลาที่พร้อมใช้งานที่ทรัพยากรสามารถมีได้หรือไม่

A5: ไม่มีการจำกัดที่กำหนดไว้ล่วงหน้าเกี่ยวกับจำนวนช่วงเวลาที่พร้อมใช้งานที่ทรัพยากรสามารถมีได้ แต่ประสิทธิภาพอาจลดลงเมื่อมีระยะเวลาจำนวนมาก