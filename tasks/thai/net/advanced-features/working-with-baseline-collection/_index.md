---
title: การทำงานกับ Baseline Collection ใน Aspose.Tasks
linktitle: การทำงานกับ Baseline Collection ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการพื้นฐานใน Aspose.Tasks สำหรับ .NET อย่างมีประสิทธิภาพ ปฏิบัติตามบทช่วยสอนที่ครอบคลุมของเราเพื่อรับคำแนะนำทีละขั้นตอน
weight: 20
url: /th/net/advanced-features/working-with-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การทำงานกับ Baseline Collection ใน Aspose.Tasks

## การแนะนำ

Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ในแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ในบรรดาคุณสมบัติต่างๆ มากมาย มันให้การสนับสนุนที่มีประสิทธิภาพสำหรับการจัดการพื้นฐานภายในโครงการ เส้นพื้นฐานถือเป็นสิ่งสำคัญสำหรับการจัดการโครงการ เนื่องจากช่วยให้คุณสามารถเปรียบเทียบแผนโครงการเดิมกับสถานะปัจจุบัน ทำให้สามารถติดตามและวิเคราะห์ความคืบหน้าของโครงการได้ดียิ่งขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกในการทำงานกับคอลเลกชันพื้นฐานใน Aspose.Tasks ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Visual Studio: ติดตั้ง Visual Studio IDE บนระบบของคุณ
2.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐานของ C#: ทำความคุ้นเคยกับภาษาการเขียนโปรแกรม C#
4. ไฟล์ Microsoft Project: เตรียมไฟล์ Microsoft Project (.mpp) ให้พร้อมสำหรับการทดสอบ

## นำเข้าเนมสเปซ

หากต้องการเริ่มทำงานกับคอลเลกชันพื้นฐานใน Aspose.Tasks คุณต้องนำเข้าเนมสเปซต่อไปนี้:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

ขั้นแรก ให้โหลดไฟล์ Microsoft Project โดยใช้ Aspose.Tasks:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## ขั้นตอนที่ 2: รับทรัพยากร

ถัดไป ดึงทรัพยากรที่ต้องการจากโปรเจ็กต์:

```csharp
var resource = project.Resources.GetByUid(1);
```

## ขั้นตอนที่ 3: แสดงข้อมูลพื้นฐาน

ตอนนี้ แสดงข้อมูลเกี่ยวกับข้อมูลพื้นฐานที่เกี่ยวข้องกับทรัพยากร:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## ขั้นตอนที่ 4: ทำซ้ำผ่านเส้นพื้นฐาน

วนซ้ำแต่ละบรรทัดพื้นฐานที่เกี่ยวข้องกับทรัพยากรและพิมพ์ข้อมูลที่เกี่ยวข้อง:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## ขั้นตอนที่ 5: ลบเส้นพื้นฐาน

ลบข้อมูลพื้นฐานทั้งหมดที่เกี่ยวข้องกับทรัพยากร:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการทำงานกับคอลเลกชันพื้นฐานใน Aspose.Tasks สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถจัดการพื้นฐานภายในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย ช่วยให้ติดตามและวิเคราะห์โครงการได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สามารถจัดการไฟล์โปรเจ็กต์ขนาดใหญ่ได้หรือไม่

ตอบ 1: ใช่ Aspose.Tasks ได้รับการปรับให้เหมาะสมเพื่อจัดการไฟล์โปรเจ็กต์ขนาดใหญ่อย่างมีประสิทธิภาพ และรับประกันประสิทธิภาพที่ราบรื่น

### คำถามที่ 2: Aspose.Tasks เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่

ตอบ 2: Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน

### คำถามที่ 3: ฉันสามารถปรับแต่งเส้นพื้นฐานใน Aspose.Tasks ได้หรือไม่

ตอบ 3: ได้ คุณสามารถปรับแต่งพื้นฐานตามความต้องการของโปรเจ็กต์ของคุณได้โดยใช้ Aspose.Tasks for .NET

### คำถามที่ 4: Aspose.Tasks รองรับแพลตฟอร์มคลาวด์หรือไม่

ตอบ 4: ใช่ Aspose.Tasks ให้การสนับสนุนสำหรับการผสานรวมกับแพลตฟอร์มคลาวด์ยอดนิยม โดยให้ความยืดหยุ่นในการปรับใช้

### คำถามที่ 5: มีฟอรัมชุมชนสำหรับผู้ใช้ Aspose.Tasks เพื่อขอความช่วยเหลือและแบ่งปันความรู้หรือไม่

 A5: ใช่ คุณสามารถเยี่ยมชมได้[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อมีส่วนร่วมกับชุมชนและรับความช่วยเหลือจากผู้เชี่ยวชาญ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
