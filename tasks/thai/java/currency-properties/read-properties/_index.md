---
date: 2026-02-07
description: เรียนรู้วิธีอ่านคุณสมบัติสกุลเงินใน Java และดึงสัญลักษณ์สกุลเงินใน Java
  จากไฟล์ MS Project ด้วย Aspose.Tasks for Java ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อดึงรหัสสกุลเงิน,
  สัญลักษณ์, จำนวนหลักและตำแหน่งของสกุลเงินโดยอัตโนมัติ
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: อ่านคุณสมบัติสกุลเงินใน Java ด้วยโครงการ Aspose.Tasks
url: /th/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านคุณสมบัติสกุลเงิน Java ด้วย Aspose.Tasks Projects

## Introduction
ในบทแนะนำนี้คุณจะ **อ่านคุณสมบัติสกุลเงิน java** จากไฟล์ Microsoft Project ด้วย Aspose.Tasks for Java API. Aspose.Tasks ช่วยให้คุณทำงานกับไฟล์ .mpp ได้โดยไม่ต้องติดตั้ง Microsoft Project ทำให้เหมาะสำหรับการสร้างรายงานอัตโนมัติ, การย้ายข้อมูล, หรือการรวมเข้ากับแอปพลิเคชันระดับองค์กรที่ใช้ Java. เมื่อจบคู่มือคุณจะสามารถดึงรหัสสกุลเงิน, สัญลักษณ์, จำนวนทศนิยม, และตำแหน่งสัญลักษณ์โดยตรงจากไฟล์โปรเจกต์ได้.

## Quick Answers
- **“read currency properties java” หมายถึงอะไร?** หมายถึงการดึงข้อมูลเมตาดาต้าสกุลเงิน (รหัส, สัญลักษณ์, จำนวนทศนิยม, ตำแหน่ง) จากไฟล์ MS Project ด้วยโค้ด Java.  
- **ต้องมีลิขสิทธิ์เพื่อทดลองหรือไม่?** มีรุ่นทดลองฟรีของ Aspose.Tasks; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์จริง.  
- **ต้องใช้ JDK เวอร์ชันใด?** Java 8 หรือใหม่กว่า.  
- **สามารถแก้ไขการตั้งค่าสกุลเงินหลังจากอ่านได้หรือไม่?** ได้, Aspose.Tasks รองรับการอ่านและเขียนคุณสมบัติสกุลเงิน.  
- **รองรับไฟล์ .mpp ทุกเวอร์ชันหรือไม่?** API รองรับไฟล์ที่สร้างด้วย Microsoft Project 2003‑2021.

## What is read currency properties java?
การอ่านคุณสมบัติสกุลเงินใน Java หมายถึงการเข้าถึงการตั้งค่าระดับโปรเจกต์ที่กำหนดวิธีการแสดงค่าการเงินในไฟล์ Microsoft Project. การตั้งค่าเหล่านี้รวมถึงรหัสสกุลเงินตามมาตรฐาน ISO (เช่น **USD**), สัญลักษณ์ (**$**), จำนวนทศนิยม, และว่าตำแหน่งสัญลักษณ์จะอยู่ก่อนหรือหลังจำนวน.

## Why read currency properties java with Aspose.Tasks?
- **ไม่ต้องติดตั้ง Microsoft Project** – API ทำงานบนแพลตฟอร์มใดก็ได้ที่รองรับ Java.  
- **การสกัดข้อมูลเร็วใน‑process** – เหมาะสำหรับการประมวลผลเป็นชุดของไฟล์โปรเจกต์จำนวนมาก.  
- **ควบคุมเต็มรูปแบบ** – สามารถนำค่าที่ดึงมาใช้ร่วมกับการรายงานแบบกำหนดเองหรือรวมเข้ากับระบบ ERP.  
- **รองรับหลายเวอร์ชัน** – ทำงานกับไฟล์ .mpp ตั้งแต่ Project 2003 จนถึงรุ่นล่าสุด 2021.

## Prerequisites
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

1. **Java Development Kit (JDK)** – Java 8 หรือใหม่กว่า ติดตั้งและกำหนดค่าใน `PATH` ของคุณ.  
2. **Aspose.Tasks for Java JAR** – ดาวน์โหลดไลบรารีล่าสุดจาก [here](https://releases.aspose.com/tasks/java/) แล้วเพิ่มลงใน classpath ของโปรเจกต์.

## Import Packages
เริ่มต้นด้วยการนำเข้า namespace ของ Aspose.Tasks ที่จำเป็นสำหรับการจัดการโปรเจกต์:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
กำหนดโฟลเดอร์ที่บรรจุไฟล์ `.mpp` ที่คุณต้องการวิเคราะห์. การเก็บพาธไว้ในตัวแปรทำให้โค้ดสามารถนำกลับมาใช้ใหม่ได้:

```java
String dataDir = "Your Data Directory";
```

*เปลี่ยน `"Your Data Directory"` ให้เป็นพาธแบบ absolute หรือ relative ที่ชี้ไปยังโฟลเดอร์ที่มี `project.mpp` อยู่.*

## Step 2: Create a Project Reader Instance
โหลดไฟล์ Microsoft Project เข้าไปในอ็อบเจกต์ `Project`. อ็อบเจกต์นี้ให้คุณเข้าถึงคุณสมบัติโปรเจกต์ทั้งหมดรวมถึงการตั้งค่าสกุลเงิน:

```java
Project project = new Project(dataDir + "project.mpp");
```

*หากไฟล์ของคุณมีชื่อแตกต่างกัน ให้เปลี่ยน `"project.mpp"` ให้ตรงกับชื่อไฟล์ของคุณ.*

## Step 3: Display Currency Properties
ดึงคุณลักษณะสกุลเงินแต่ละรายการโดยใช้ enumeration `Prj` แล้วพิมพ์ผลลัพธ์ไปยังคอนโซล. API จะคืนค่าเป็นอ็อบเจกต์ที่คุณสามารถแปลงเป็นสตริงเพื่อแสดงผล:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**สิ่งที่คุณจะเห็น:**  
- **Currency Code** – รหัส ISO‑4217 เช่น `USD`, `EUR`, `JPY`.  
- **Currency Digits** – ปกติเป็น `2` สำหรับสกุลเงินส่วนใหญ่, `0` สำหรับเยนญี่ปุ่น.  
- **Currency Symbol** – ตัวอักษรที่แสดงในรายงาน (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` หมายถึง **ก่อน** จำนวน, `1` หมายถึง **หลัง** จำนวน.

## How to extract currency symbol java?
หากคุณสนใจเฉพาะสัญลักษณ์เท่านั้น สามารถโฟกัสที่ property `Prj.CURRENCY_SYMBOL`. การเรียก `project.get(...)` เดียวกันจะคืนค่าสัญลักษณ์ ซึ่งคุณสามารถเก็บ, บันทึก, หรือส่งต่อให้บริการอื่นเพื่อการประมวลผลต่อได้. วิธีนี้มีประโยชน์เมื่อต้อง **extract currency symbol java** สำหรับแดชบอร์ดการเงินหรือคอมโพเนนต์ UI ที่ต้องการการแสดงผลตามภาษาท้องถิ่น.

## Step 4: Process Completion
ส่งสัญญาณว่า การสกัดข้อมูลเสร็จสมบูรณ์. ข้อความง่าย ๆ นี้มีประโยชน์เมื่อโค้ดทำงานเป็นส่วนหนึ่งของงานแบตช์ขนาดใหญ่:

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | พาธ `dataDir` ไม่ถูกต้องหรือชื่อไฟล์สะกดผิด. | ตรวจสอบสตริงของไดเรกทอรีและยืนยันว่าไฟล์ `.mpp` มีอยู่ในตำแหน่งที่ระบุ. |
| **NullPointerException on `project.get(...)`** | ไฟล์โปรเจกต์ไม่มีข้อมูลสกุลเงิน (เป็นไปได้น้อย) หรือคีย์ property ผิด. | ใช้ `project.contains(Prj.CURRENCY_CODE)` เพื่อตรวจสอบว่ามีค่าก่อนอ่าน. |
| **LicenseException** | รันโดยไม่มีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องในสภาพแวดล้อมการผลิต. | ใส่ไฟล์ลิขสิทธิ์ด้วย `License license = new License(); license.setLicense("Aspose.Tasks.lic");` ก่อนสร้างอ็อบเจกต์ `Project`. |

## Frequently Asked Questions

**Q: Aspose.Tasks รองรับเวอร์ชันของ Microsoft Project ทุกเวอร์ชันหรือไม่?**  
A: Aspose.Tasks รองรับไฟล์ .mpp ที่สร้างโดย Microsoft Project 2003‑2021, ครอบคลุมทั้งรูปแบบเก่าและใหม่ล่าสุด.

**Q: สามารถแก้ไขคุณสมบัติสกุลเงินด้วย Aspose.Tasks ได้หรือไม่?**  
A: ได้, คุณสามารถอ่านและเขียนการตั้งค่าสกุลเงินได้. ใช้ `project.set(Prj.CURRENCY_CODE, "EUR");` แล้วบันทึกโปรเจกต์.

**Q: Aspose.Tasks เหมาะสำหรับการใช้งานเชิงพาณิชย์หรือไม่?**  
A: แน่นอน. เป็นไลบรารีเชิงพาณิชย์; คุณสามารถซื้อไลเซนส์ได้จาก [here](https://purchase.aspose.com/buy).

**Q: Aspose.Tasks มีรุ่นทดลองฟรีหรือไม่?**  
A: มี, รุ่นทดลองเต็มรูปแบบพร้อมใช้งานจาก [here](https://releases.aspose.com/).

**Q: จะหาความช่วยเหลือหรือสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
A: ฟอรั่มอย่างเป็นทางการของ Aspose.Tasks เป็นแหล่งที่ดีที่สุดสำหรับการขอความช่วยเหลือ – เยี่ยมชมได้ที่ [here](https://forum.aspose.com/c/tasks/15).

## Additional FAQ (AI‑Optimized)

**Q: จะดึงสัญลักษณ์สกุลเงินเพียงอย่างเดียวใน Java อย่างโปรแกรมเมติกได้อย่างไร?**  
A: เรียก `project.get(Prj.CURRENCY_SYMBOL)` แล้วแคสต์ผลลัพธ์เป็น `String`. ค่าที่ได้คือสัญลักษณ์ที่ใช้ในไฟล์โปรเจกต์นั้น.

**Q: สามารถอ่านคุณสมบัติสกุลเงินจากไฟล์ .mpp ที่มีการป้องกันด้วยรหัสผ่านได้หรือไม่?**  
A: ได้. โหลดไฟล์ด้วย overload ของคอนสตรัคเตอร์ `Project` ที่รับพารามิเตอร์รหัสผ่าน, แล้วอ่านคุณสมบัติตามที่แสดง.

**Q: ประสิทธิภาพการประมวลผลไฟล์โปรเจกต์จำนวนมากเป็นอย่างไร?**  
A: Aspose.Tasks ทำงานใน‑process และโดยทั่วไปอ่านไฟล์ .mpp มาตรฐานในไม่กี่มิลลิวินาที. สำหรับการประมวลผลเป็นชุดใหญ่ ควรพิจารณาใช้ `Project` อินสแตนซ์เดียวกันซ้ำหลายครั้งเมื่อเป็นไปได้.

## Conclusion
คุณได้เรียนรู้วิธี **read currency properties java** และ **extract currency symbol java** จากไฟล์ MS Project ด้วย Aspose.Tasks for Java. ความสามารถนี้ช่วยให้คุณนำเมตาดาต้าสกุลเงินไปใช้ในรายงานแบบกำหนดเอง, การวิเคราะห์การเงิน, หรือการรวมระบบโดยไม่ต้องพึ่งพา Microsoft Project เอง. อย่าลังเลที่จะทดลองแก้ไขคุณสมบัติต่าง ๆ หรือผสานข้อมูลนี้กับแอตทริบิวต์อื่นของโปรเจกต์เพื่อสร้างโซลูชันที่สมบูรณ์ยิ่งขึ้น.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}