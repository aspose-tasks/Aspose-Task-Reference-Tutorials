---
date: 2026-09-25
description: เรียนรู้วิธีดึงรหัสสกุลเงินจากไฟล์ MS Project ด้วย Aspose.Tasks for Java
  – วิธีที่รวดเร็วในการรับรหัสสกุลเงินที่นักพัฒนา Java ต้องการ
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: จัดการรหัสสกุลเงินใน Aspose.Tasks
og_description: ดึงรหัสสกุลเงิน java จากไฟล์ MS Project ด้วย Aspose.Tasks คู่มือนี้จะแสดงวิธีอ่านโปรเจกต์,
  แยก ISO currency identifier, และนำไปใช้ในแอปพลิเคชัน Java
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: ดึงรหัสสกุลเงิน java จาก MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: ดึงรหัสสกุลเงิน java จาก MS Project ด้วย Aspose.Tasks
url: /th/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงรหัสสกุลเงิน java จาก MS Project ด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีดึงรหัสสกุลเงิน java** จากไฟล์ MS Project โดยใช้ Aspose.Tasks Java API ไม่ว่าคุณจะต้องการสร้างรายงานการเงินหลายสกุลเงิน, รวมโครงการจากหลายภูมิภาค, หรือเพียงแค่แสดงสัญลักษณ์เงินที่ถูกต้องในระบบ downstream ขั้นตอนต่อไปนี้จะพาคุณจากการตั้งค่าสภาพแวดล้อมจนถึงการเรียกใช้บรรทัดเดียวที่คืนค่า identifier ของสกุลเงินตามมาตรฐาน ISO. เมื่อจบคู่มือคุณจะสามารถโหลดไฟล์ Project ที่รองรับรูปแบบใดก็ได้และดึงรหัสสกุลเงินสามตัวอักษร เช่น `USD`, `EUR`, หรือ `GBP`.

## คำตอบอย่างรวดเร็ว
- **API ทำอะไร?** มันอ่านไฟล์ MS Project และเปิดเผยคุณสมบัติต่าง ๆ เช่น รหัสสกุลเงิน.  
- **ใช้ภาษาอะไร?** Java, ผ่านไลบรารี Aspose.Tasks for Java.  
- **ต้องการใบอนุญาตหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; ต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการผลิต.  
- **สามารถดึงรหัสในบรรทัดเดียวได้หรือไม่?** ได้—`prj.get(Prj.CURRENCY_CODE)` คืนสตริงรหัสสกุลเงินทันที.  
- **เข้ากันได้กับทุกเวอร์ชันของ Project หรือไม่?** Aspose.Tasks รองรับรูปแบบอินพุตมากกว่า 20 แบบ รวมถึง MPP รุ่นเก่า, XML, และไฟล์ XER.

## การอ่านไฟล์ MS Project คืออะไร?
การอ่านไฟล์ MS Project หมายถึงการเปิดไฟล์ *.mpp* (หรือรูปแบบที่รองรับอื่น ๆ เช่น XML หรือ XER) อย่างโปรแกรมและเข้าถึงโครงสร้างข้อมูลภายในของมัน โครงสร้างเหล่านี้รวมถึงงาน, ทรัพยากร, ปฏิทิน, ตารางค่าใช้จ่ายและการตั้งค่าการเงิน โดยการวิเคราะห์ไฟล์คุณสามารถดึงข้อมูลโดยไม่ต้องเปิด Microsoft Project ทำให้สามารถสร้างรายงานอัตโนมัติ, การย้ายข้อมูล, และกระบวนการบูรณาการได้.

## ทำไมต้องใช้ Aspose.Tasks เพื่ออ่านไฟล์ msproject?
Aspose.Tasks ให้โซลูชัน pure‑Java ที่ไม่ต้องพึ่งพา COM interop หรือการติดตั้ง Microsoft Project บนเครื่อง รองรับรูปแบบไฟล์มากกว่า 20 แบบ, สามารถจัดการโครงการที่มีงานหลายพันรายการโดยใช้หน่วยความจำต่ำกว่า 100 MB, และมอบโมเดลอ็อบเจ็กต์ที่ครบถ้วน การเข้าถึงคอนสแตนท์โดยตรงเช่น `Prj.CURRENCY_CODE` ทำให้คุณดึงข้อมูลสกุลเงินได้อย่างทันทีและเชื่อถือได้.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### ติดตั้ง Java Development Kit (JDK)
จำเป็นต้องใช้ JDK รุ่นล่าสุด (เวอร์ชัน 11 หรือใหม่กว่า) ดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Oracle: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### ไลบรารี Aspose.Tasks for Java
รับไฟล์ไบนารี Aspose.Tasks for Java เวอร์ชันล่าสุดและเพิ่มลงใน classpath ของโปรเจกต์ของคุณ เอกสารเต็มรูปแบบและลิงก์ดาวน์โหลดพร้อมให้บริการ [here](https://reference.aspose.com/tasks/java/).

## นำเข้าแพ็กเกจ
คลาส `Project` และคอนสแตนท์ `Prj` อยู่ในเนมสเปซ `com.aspose.tasks` ให้นำเข้าที่ส่วนหัวของไฟล์ซอร์ส Java ของคุณ:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดโฟลเดอร์ที่บรรจุไฟล์ *.mpp* ของคุณ ปรับเส้นทางให้ตรงกับสภาพแวดล้อมของคุณเพื่อให้ runtime สามารถค้นหาไฟล์โปรเจกต์ได้.

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์โปรเจกต์
คลาส `Project` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Tasks ที่แทนไฟล์ MS Project หนึ่งไฟล์ในหน่วยความจำ การสร้างอินสแตนซ์จะอ่านไฟล์และสร้างโมเดลในหน่วยความจำที่คุณสามารถสอบถามได้.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 3: ดึงรหัสสกุลเงิน
คอนสแตนท์ `Prj.CURRENCY_CODE` ระบุคุณสมบัติที่เก็บตัวระบุสกุลเงินตามมาตรฐาน ISO การเรียก `prj.get(Prj.CURRENCY_CODE)` จะคืนค่ารหัสสามตัวอักษรในหนึ่งการดำเนินการ.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
ผลลัพธ์จะเป็นรหัส ISO สามตัวอักษร (เช่น `USD`, `EUR`, `GBP`) ที่โครงการได้ตั้งค่าให้ใช้.

### ขั้นตอนที่ 4: วิธีดึงรหัสสกุลเงินใน Java (บริบทเพิ่มเติม)
โหลดโครงการของคุณ, เรียก `prj.get(Prj.CURRENCY_CODE)`, และเก็บผลลัพธ์ใน `String` จากนั้นคุณสามารถส่งค่าดังกล่าวไปยังบริการการเงินใด ๆ, เครื่องมือรายงาน, หรือคอมโพเนนต์ UI ที่ต้องการตัวระบุสกุลเงิน.

### ขั้นตอนที่ 5: (ทางเลือก) ใช้รหัสสกุลเงิน
สถานการณ์ downstream ที่พบบ่อยรวมถึง:

- **การสร้างรายงาน** – นำรหัสไปต่อหน้าคอลัมน์ค่าใช้จ่าย (`USD 1,200`).  
- **การบูรณาการ API** – ส่งรหัส ISO ไปยังเกตเวย์การชำระเงินที่ต้องการพารามิเตอร์สกุลเงิน.  
- **การรวมข้อมูล** – จัดกลุ่มหลายโครงการตามสกุลเงินเพื่อการวิเคราะห์ระดับพอร์ตโฟลิโอ.

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ผลลัพธ์เป็น Null** | ไฟล์โครงการไม่ได้กำหนดสกุลเงิน (ค่าเริ่มต้นเป็นค่าว่าง). | ตั้งค่าสกุลเงินใน Microsoft Project หรือกำหนดผ่าน `prj.set(Prj.CURRENCY_CODE, "USD");` ก่อนอ่าน. |
| **ไฟล์ไม่พบ** | เส้นทาง `dataDir` ไม่ถูกต้อง. | ตรวจสอบเส้นทางและให้แน่ใจว่าชื่อไฟล์ตรงกันอย่างสมบูรณ์ รวมถึงความแตกต่างของตัวพิมพ์ใหญ่/เล็ก. |
| **เวอร์ชันไฟล์ที่ไม่รองรับ** | ไฟล์ *.mpp* เก่าเกินไปหรือเสียหาย. | อัปเกรดเป็นเวอร์ชันล่าสุดของ Aspose.Tasks หรือแปลงไฟล์เป็นรูปแบบใหม่ใน Microsoft Project ก่อน. |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?**  
A: ใช่, API สามารถอ่านโครงสร้างงานหลายระดับ, พูลทรัพยากร, ฟิลด์กำหนดเอง, และปฏิทินได้โดยไม่มีข้อจำกัด.

**Q: Aspose.Tasks เข้ากันได้กับเวอร์ชันต่าง ๆ ของไฟล์ MS Project หรือไม่?**  
A: แน่นอน. รองรับ MPP, XML, XER และรูปแบบอื่น ๆ ตั้งแต่ Project 98 จนถึงรุ่น Office ล่าสุด.

**Q: Aspose.Tasks มีเอกสารและการสนับสนุนหรือไม่?**  
A: มีเอกสารอ้างอิง API อย่างครบถ้วน, ตัวอย่างโค้ด, และการสนับสนุนทางเทคนิคเฉพาะบนเว็บไซต์ของ Aspose.

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: มีการทดลองใช้ฟรีเพื่อให้คุณประเมินคุณสมบัติทั้งหมด รวมถึงการดึงรหัสสกุลเงิน.

**Q: ฉันสามารถรับใบอนุญาตชั่วคราวสำหรับการประเมินได้จากที่ไหน?**  
A: ใบอนุญาตชั่วคราวมีให้ที่ [website](https://purchase.aspose.com/temporary-license/).

---

**อัปเดตล่าสุด:** 2026-09-25  
**ทดสอบด้วย:** Aspose.Tasks for Java (latest version)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [คุณสมบัติโครงการ Java – อ่าน Metadata ด้วย Aspose.Tasks](/tasks/java/project-properties/)
- [วิธีอ่านข้อมูลโครงการจาก Microsoft Project ด้วย Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [ดึงรหัส Outline ของ MS Project ใน Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}