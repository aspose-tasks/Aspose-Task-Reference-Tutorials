---
date: 2026-04-30
description: เรียนรู้วิธีตั้งค่า baseline และจัดการ baseline ของโครงการอย่างมีประสิทธิภาพด้วย
  Aspose.Tasks สำหรับ .NET.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: ประเภทต่าง ๆ ของเส้นฐานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: วิธีตั้งค่า Baseline ใน Aspose.Tasks – ประเภท Baseline ต่าง ๆ
url: /th/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ประเภทต่าง ๆ ของ Baseline ใน Aspose.Tasks

## บทนำ

ในการจัดการโครงการ, **how to set baseline** อย่างถูกต้องสามารถทำให้โครงการอยู่ในเส้นทางหรือพังทลายได้อย่างแตกต่าง Aspose.Tasks for .NET ให้ API ที่ครบถ้วนสำหรับสร้าง, ปรับปรุง, และเปรียบเทียบ baseline, ช่วยให้คุณ **track project progress** เทียบกับแผนต้นฉบับ ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีตั้ง baseline, ทำงานกับหลายประเภทของ baseline, และใช้ข้อมูลเพื่อวิเคราะห์ **baseline vs actual schedule** ของโครงการของคุณ.

## คำตอบสั้น
- **What is a baseline?** ภาพสแนปช็อตของกำหนดการ, ค่าใช้จ่าย, และข้อมูลงานที่ถ่ายในช่วงเวลาหนึ่งของโครงการ.  
- **How many baselines can Aspose.Tasks store?** สามารถเก็บได้สูงสุด 11 baseline ที่แตกต่างกันต่อโครงการ.  
- **Why set a baseline?** เพื่อเปรียบเทียบประสิทธิภาพจริงกับแผนต้นฉบับและระบุความแตกต่าง.  
- **Do I need a license to try this?** มีการทดลองใช้ฟรี; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## อะไรคือ “how to set baseline” ใน Aspose.Tasks?
การตั้ง baseline หมายถึงการเรียกเมธอด `SetBaseline` บนวัตถุ `Project`. API ให้คุณเลือกจากหลายค่า `BaselineType` (Baseline, Baseline1 … Baseline10) เพื่อให้คุณสามารถเก็บภาพสแนปช็อตประวัติขณะโครงการพัฒนา.

## ทำไมต้องจัดการ baseline ของโครงการ?
- **Measure variance:** ตรวจสอบอย่างรวดเร็วว่าหน้าที่อยู่ล่วงหน้าหรือช้ากว่ากำหนดหรือไม่.  
- **Cost control:** เปรียบเทียบค่าใช้จ่าย baseline กับการใช้จ่ายจริง.  
- **Stakeholder reporting:** ส่งออกข้อมูล baseline ไปยัง PDF, XLSX หรือรูปแบบอื่นเพื่อการสื่อสารที่ชัดเจน.  
- **Scenario planning:** เก็บหลาย baseline เพื่อประเมินตาราง “what‑if”.

## ข้อกำหนดเบื้องต้น

### 1. ความคุ้นเคยกับ C# และ .NET Framework
ต้องมีความเข้าใจพื้นฐานเกี่ยวกับคลาส, เมธอด, และแนวคิดเชิงวัตถุของ C#.

### 2. การติดตั้ง Aspose.Tasks for .NET
ตรวจสอบให้แน่ใจว่ามีการเพิ่มไลบรารีนี้ในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก [Aspose.Tasks website](https://releases.aspose.com/tasks/net/) หรือทำการติดตั้งผ่าน NuGet.

### 3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE)
แนะนำให้ใช้ Visual Studio (หรือ IDE ที่เข้ากันได้) สำหรับการเขียน, คอมไพล์, และดีบักโค้ด C#.

## นำเข้า Namespaces
ก่อนที่เราจะเริ่มทำงานกับ Aspose.Tasks ในโครงการ C# ของเรา เราต้องนำเข้า namespaces ที่จำเป็นเพื่อเข้าถึงคลาสและเมธอดที่ต้องการ ทำตามขั้นตอนต่อไปนี้:

```csharp

```

เมื่อเราตั้งค่าข้อกำหนดเบื้องต้นและนำเข้า namespaces ที่จำเป็นแล้ว เรามาเริ่มตั้งค่าประเภทต่าง ๆ ของ baseline ด้วย Aspose.Tasks for .NET กันเถอะ เราจะแบ่งตัวอย่างแต่ละส่วนออกเป็นหลายขั้นตอนเพื่อความชัดเจนและง่ายต่อการเข้าใจ.

## วิธีตั้ง Baseline ใน Aspose.Tasks

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ
ก่อนอื่น เราต้องโหลดไฟล์โครงการที่เราตั้งใจจะตั้ง baseline ขั้นตอนนี้เกี่ยวข้องกับการสร้างอ็อบเจกต์ `Project` และโหลดไฟล์โครงการ นี่คือตัวอย่างวิธีทำ:

```csharp
var project = new Project("Project2.mpp");
```

### ขั้นตอนที่ 2: ตั้ง Baseline
เมื่อโหลดโครงการแล้ว เราสามารถดำเนินการตั้ง baseline ได้ Baseline ให้ภาพสแนปช็อตของกำหนดการเริ่มต้นของโครงการ ซึ่งทำหน้าที่เป็นจุดอ้างอิงสำหรับการเปรียบเทียบขณะโครงการดำเนินต่อไป ใช้เมธอด `SetBaseline` เพื่อกำหนด baseline ตัวอย่างเช่น เพื่อตั้ง baseline สำหรับโครงการทั้งหมด ให้ใช้ enumeration `BaselineType.Baseline`:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### ขั้นตอนที่ 3: ทำงานกับ Baseline ของโครงการ
หลังจากตั้ง baseline แล้ว คุณสามารถทำงานกับฟิลด์ baseline ต่าง ๆ ของโครงการเพื่อวิเคราะห์และติดตามความคืบหน้าของโครงการได้อย่างแม่นยำ ขั้นตอนนี้เกี่ยวข้องกับการเข้าถึงข้อมูล baseline เช่น วันที่เริ่ม, วันที่สิ้นสุด, ระยะเวลา, และค่าใช้จ่าย ที่นี่คุณสามารถใช้คุณลักษณะอันหลากหลายของ Aspose.Tasks เพื่อจัดการข้อมูล baseline ตามความต้องการของคุณ.

## ปัญหาทั่วไปและวิธีแก้
- **Baseline not applied:** ตรวจสอบให้แน่ใจว่าไฟล์โครงการถูกบันทึกหลังจากเรียก `SetBaseline`. ใช้ `project.Save("output.mpp");` หากต้องการบันทึกการเปลี่ยนแปลง.  
- **Multiple baselines conflict:** เมื่อกำหนดมากกว่าหนึ่ง baseline ให้ระบุ `BaselineType` ที่ถูกต้อง (เช่น `Baseline1`, `Baseline2`).  
- **Version mismatch:** ตรวจสอบว่าเวอร์ชันของ Aspose.Tasks DLL ตรงกับ .NET runtime ที่เป้าหมาย.

## คำถามที่พบบ่อย

**Q: ฉันสามารถตั้งหลาย baseline สำหรับโครงการเดียวโดยใช้ Aspose.Tasks for .NET ได้หรือไม่?**  
A: ได้, Aspose.Tasks อนุญาตให้ตั้งได้สูงสุด 11 baseline สำหรับโครงการหนึ่ง, ให้ความสามารถในการติดตามอย่างครบถ้วน.

**Q: Aspose.Tasks รองรับรูปแบบไฟล์โครงการต่าง ๆ หรือไม่?**  
A: แน่นอน! Aspose.Tasks รองรับรูปแบบไฟล์โครงการหลายประเภท เช่น MPP, XML, และ MPX, ทำให้เข้ากันได้กับหลายแพลตฟอร์ม.

**Q: ฉันจะทำให้ข้อมูล baseline แสดงผลในโครงการของฉันอย่างไร?**  
A: คุณสามารถใช้ Aspose.Tasks ส่งออกข้อมูลโครงการเป็นไฟล์รูปแบบยอดนิยม เช่น PDF หรือ XLSX เพื่อให้การแสดงผลและการแชร์ข้อมูล baseline ง่ายขึ้น.

**Q: Aspose.Tasks มีการสนับสนุนการผสานรวมกับเครื่องมือการจัดการโครงการหรือไม่?**  
A: Aspose.Tasks มีเอกสารและฟอรั่มสนับสนุนที่กว้างขวางเพื่อช่วยนักพัฒนาในการผสานคุณลักษณะของมันกับเครื่องมือและแพลตฟอร์มการจัดการโครงการที่นิยม.

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: ได้, คุณสามารถสำรวจ Aspose.Tasks ผ่านการทดลองใช้ฟรีที่เว็บไซต์, เพื่อสัมผัสความสามารถของมันโดยตรง.

---

**อัปเดตล่าสุด:** 2026-04-30  
**ทดสอบกับ:** Aspose.Tasks for .NET (latest stable release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}