---
date: 2026-04-06
description: เรียนรู้วิธีลบบรรทัดฐานทั้งหมดและจัดการคอลเลกชันบรรทัดฐานใน Aspose.Tasks
  สำหรับ .NET พร้อมตัวอย่างโค้ดทีละขั้นตอน.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: ลบ Baselines ทั้งหมดด้วย Aspose.Tasks Baseline Collection
second_title: Aspose.Tasks .NET API
title: ลบ Baseline ทั้งหมดด้วย Aspose.Tasks Baseline Collection
url: /th/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ลบ Baselines ทั้งหมดด้วย Aspose.Tasks Baseline Collection

## บทนำ

Aspose.Tasks for .NET ให้คุณจัดการไฟล์ Microsoft Project โดยตรงจากแอปพลิเคชัน .NET ของคุณ หนึ่งในคุณสมบัติที่ทรงพลังที่สุดคือความสามารถในการ **ลบ Baselines ทั้งหมด** สำหรับทรัพยากร ซึ่งจำเป็นเมื่อคุณต้องรีเซ็ตข้อมูลการติดตามของโครงการหรือเริ่มช่วง Baseline ใหม่ ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมด—from การโหลดไฟล์โครงการไปจนถึงการลบ Baseline ทุกอันที่แนบกับทรัพยากรเฉพาะ—โดยใช้คำอธิบายที่เป็นกันเองและโค้ด C# ที่พร้อมรัน

## คำตอบอย่างรวดเร็ว
- **การ “delete all baselines” ทำอะไร?** มันลบบันทึก baseline ทั้งหมดที่เก็บไว้สำหรับทรัพยากรที่เลือก, ทำให้ข้อมูลต้นทุนและงานในอดีตถูกล้างออก.  
- **ทำไมฉันต้องการสิ่งนี้?** เพื่อรีเซ็ตการติดตามหลังจากการเปลี่ยนแปลงโครงการใหญ่หรือเมื่อ baseline ดั้งเดิมไม่เกี่ยวข้องอีกต่อไป.  
- **ไลบรารีใดที่ให้ความสามารถนี้?** Aspose.Tasks for .NET.  
- **ฉันต้องมีใบอนุญาตหรือไม่?** จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์; มีรุ่นทดลองฟรีให้ใช้.  
- **โค้ดนี้เข้ากันได้กับ .NET 6+ หรือไม่?** ใช่, API ทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6.

## Baseline คืออะไรและทำไมต้องลบ Baselines ทั้งหมด?

Baseline จับภาพแผนต้นฉบับของต้นทุน, งาน, และกำหนดเวลาในช่วงเวลาหนึ่ง ตลอดอายุโครงการคุณอาจสร้าง Baseline หลายชุด (Baseline 1, Baseline 2, ฯลฯ) เพื่อเปรียบเทียบความก้าวหน้าจริงกับภาพ snapshot ของการวางแผนต่าง ๆ อย่างไรก็ตาม มีสถานการณ์—เช่น การปรับขอบเขตโครงการใหม่หรือการเริ่มต้นใหม่—ที่การเก็บ Baseline เก่า ๆ ทำให้สับสน การลบ Baselines ทั้งหมดจะให้คุณเริ่มต้นใหม่อย่างสะอาด เพื่อกำหนด Baseline ใหม่ที่สะท้อนความเป็นจริงปัจจุบัน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในโค้ด, ตรวจสอบว่าคุณมี:

1. **Visual Studio** – รุ่นล่าสุดใดก็ได้ (Community, Professional, หรือ Enterprise).  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดได้จาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – คุณควรคุ้นเคยกับตัวแปร, ลูป, และการแสดงผลบนคอนโซล.  
4. **A Microsoft Project file** (`.mpp`) – ตัวอย่างไฟล์ชื่อ *WorkWithBaselineCollection.mpp* จะถูกใช้ในตัวอย่าง.

## นำเข้า Namespaces

ก่อนอื่นให้เพิ่ม Namespaces ที่จำเป็นเข้าสู่สโคปเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาสที่เราจะใช้จากที่ไหน

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## ขั้นตอนที่ 1: โหลดไฟล์ Project

เราจะเริ่มโดยการโหลดไฟล์ Project ที่มีอยู่แล้ว ปรับ `DataDir` ให้ชี้ไปยังโฟลเดอร์ที่มีไฟล์ `.mpp` ของคุณ

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## ขั้นตอนที่ 2: ดึง Resource เป้าหมาย

เพื่อการสาธิตเราจะดึง Resource ที่มี UID = 1 ในสถานการณ์จริงคุณอาจค้นหา Resource ตามชื่อหรือ identifier อื่น

```csharp
var resource = project.Resources.GetByUid(1);
```

## ขั้นตอนที่ 3: แสดงข้อมูล Baseline ที่มีอยู่

ก่อนลบอะไรเลย การดู Baseline ที่แนบอยู่กับ Resource ปัจจุบันจะช่วยให้คุณมั่นใจว่ากำลังลบข้อมูลที่ถูกต้อง

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## ขั้นตอนที่ 4: วนลูปผ่าน Baselines ทั้งหมด

ที่นี่เราจะวนลูปผ่านแต่ละ Baseline, พิมพ์ค่ามาตรฐานสำคัญเช่นต้นทุน, งาน, และมูลค่าที่ได้รับ (BCWP/BCWS) ขั้นตอนนี้เป็นทางเลือกแต่มีประโยชน์สำหรับการบันทึกหรือการตรวจสอบ

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

## ลบ Baselines ทั้งหมด

ตอนนี้เราจะทำการหลัก: **delete all baselines** สำหรับ Resource ที่เลือก เราจะคัดลอกคอลเลกชันไปเป็นรายการเพื่อหลีกเลี่ยงการแก้ไขคอลเลกชันขณะวนลูป, แล้วลบแต่ละ Baseline ทีละอัน

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

หลังจากบล็อกนี้ทำงานเสร็จ, `resource.Baselines.Count` จะเป็น `0`, ยืนยันว่าบันทึก Baseline ทั้งหมดถูกล้างออกแล้ว

## ปัญหาที่พบบ่อยและเคล็ดลับ

- **NullReferenceException** – ตรวจสอบให้แน่ใจว่าไฟล์โปรเจกต์มี Resource ที่คุณต้องการจริง; มิฉะนั้น `GetByUid` จะคืนค่า `null`.  
- **Licensing** – หากไม่มีใบอนุญาต Aspose.Tasks ที่ถูกต้อง คุณจะเห็นลายน้ำในผลลัพธ์และฟังก์ชันที่จำกัด.  
- **Performance** – สำหรับโครงการขนาดใหญ่มาก, พิจารณาใช้ `Parallel.ForEach` เพื่อเร่งกระบวนการลบ, แต่จำไว้ว่าคอลเลกชันพื้นฐานไม่ปลอดภัยต่อการทำงานหลายเธรด.

## คำถามที่พบบ่อย

**Q: Aspose.Tasks สามารถจัดการไฟล์โครงการขนาดใหญ่ได้หรือไม่?**  
A: ใช่, Aspose.Tasks ถูกปรับให้ทำงานอย่างมีประสิทธิภาพและสามารถประมวลผลไฟล์ `.mpp` ขนาดหลายกิกะไบต์ได้อย่างมีประสิทธิภาพ.

**Q: ไลบรารีนี้เข้ากันได้กับเวอร์ชัน Microsoft Project ทั้งหมดหรือไม่?**  
A: Aspose.Tasks รองรับ Project 2000 ถึง Project 2024, ครอบคลุมทั้งรูปแบบ `.mpp` เก่าและไฟล์ XML‑based ใหม่.

**Q: ฉันสามารถปรับแต่ง Baseline ก่อนลบได้หรือไม่?**  
A: แน่นอน. คุณสามารถอ่านหรือแก้ไขคุณสมบัติของ Baseline ใดก็ได้ (ต้นทุน, งาน, วันที่) ก่อนตัดสินใจลบ.

**Q: Aspose.Tasks ทำงานบนแพลตฟอร์มคลาวด์หรือไม่?**  
A: ใช่, API ทำงานบนสภาพแวดล้อมที่รองรับ .NET ใดก็ได้, รวมถึง Azure App Service, AWS Lambda (ผ่าน .NET Core), และคอนเทนเนอร์ Docker.

**Q: ฉันจะขอความช่วยเหลือจากชุมชนได้ที่ไหน?**  
A: เยี่ยมชม [ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อเชื่อมต่อกับนักพัฒนาอื่น ๆ และทีมงาน Aspose.

## สรุป

ในคู่มือนี้เราได้สาธิตวิธี **delete all baselines** จาก Resource ด้วย Aspose.Tasks for .NET โดยทำตามโค้ดขั้นตอน‑ขั้นตอน คุณสามารถรีเซ็ตข้อมูล Baseline, ทำให้การติดตามโครงการของคุณสะอาด และเตรียมกำหนดการสำหรับรอบการวางแผนใหม่ได้อย่างง่ายดาย อย่าลังเลที่จะทดลองสร้าง Baseline ใหม่หลังจากการลบเพื่อดูว่าห้องสมุดอัปเดตไฟล์โครงการอย่างไร

---

**อัปเดตล่าสุด:** 2026-04-06  
**ทดสอบกับ:** Aspose.Tasks 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}