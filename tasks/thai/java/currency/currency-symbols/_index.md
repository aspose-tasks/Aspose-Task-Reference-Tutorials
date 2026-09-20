---
date: 2026-09-20
description: เรียนรู้วิธีดึงสัญลักษณ์สกุลเงิน mpp และอัปเดตคุณสมบัติโครงการโดยใช้
  Aspose.Tasks สำหรับ Java. เปลี่ยนและดึงสัญลักษณ์ได้ในไม่กี่บรรทัดของโค้ด.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: ดึงสัญลักษณ์สกุลเงิน mpp ด้วย Aspose.Tasks สำหรับ Java
og_description: เรียนรู้วิธีดึงสัญลักษณ์สกุลเงิน mpp และอัปเดตคุณสมบัติโครงการโดยใช้
  Aspose.Tasks สำหรับ Java. รวดเร็ว เชื่อถือได้ และพร้อมใช้งานในผลิตภัณฑ์.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: วิธีดึงสัญลักษณ์สกุลเงิน mpp ด้วย Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: วิธีดึงสัญลักษณ์สกุลเงิน mpp ด้วย Aspose.Tasks Java
url: /th/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงสัญลักษณ์สกุลเงินจากไฟล์ mpp ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีการทำงานกับ **java project properties** — โดยเฉพาะวิธี **extract currency symbol mpp** จากไฟล์ Microsoft Project (MPP) และวิธี **change currency symbol java** หรือ **retrieve currency symbol java** ด้วยไลบรารี Aspose.Tasks ไม่ว่าคุณจะกำลังสร้างเครื่องมือรายงานการเงิน, ผสานข้อมูล Project เข้ากับระบบ ERP, หรือเพียงต้องการแสดงสัญลักษณ์สกุลเงินที่ถูกต้องใน UI ของคุณ การเชี่ยวชาญงานเล็ก ๆ แต่สำคัญนี้จะทำให้แอปพลิเคชัน Java ของคุณแข็งแรงและเป็นมิตรต่อผู้ใช้มากขึ้น.

## คำตอบอย่างรวดเร็ว
- **อะไรคือ “extract currency symbol mpp”?** หมายความว่าการอ่านสัญลักษณ์สกุลเงินที่เก็บไว้ในไฟล์ MPP (Microsoft Project).
- **ไลบรารีใดจัดการเรื่องนี้?** Aspose.Tasks for Java มี API ที่ง่ายต่อการทำงานนี้.
- **ฉันต้องการไลเซนส์หรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.
- **ใช้เวลานานเท่าไหร่?** ด้วยโค้ดด้านล่าง คุณสามารถดึงสัญลักษณ์ได้ภายในไม่ถึงหนึ่งนาที.
- **ฉันสามารถเปลี่ยนสัญลักษณ์ได้หรือไม่?** ได้ – คุณสามารถตั้งค่าตัวใหม่โดยใช้ property `Prj.CURRENCY_SYMBOL` เดียวกัน.

## “extract currency symbol mpp” คืออะไร?
การดึงสัญลักษณ์สกุลเงินจากไฟล์ MPP หมายถึงการอ่านสตริงตัวอักษรเดียวที่ Microsoft Project เก็บไว้ในส่วนหัวของไฟล์เพื่อแสดงหน่วยเงินของโครงการ การดำเนินการนี้ทำให้คุณสามารถแสดงสัญลักษณ์ที่ถูกต้อง (เช่น $, €, £) ในแอปพลิเคชันของคุณโดยไม่ต้องกำหนดค่าตายตัว.

## ทำไมต้องอัปเดตสัญลักษณ์สกุลเงินใน java project properties?
การอัปเดตสัญลักษณ์สกุลเงินทำให้คุณสามารถทำให้รายงาน, ใบแจ้งหนี้, และแดชบอร์ดเป็นภาษาท้องถิ่นได้อย่างรวดเร็ว บริษัทที่ดำเนินโครงการในหลายภูมิภาคสามารถสลับสัญลักษณ์ได้ในขั้นตอนเดียว ลดความจำเป็นในการทำสำเนาไฟล์โครงการทั้งหมด Aspose.Tasks สามารถแก้ไข property ในหน่วยความจำและบันทึกไฟล์กลับได้ รองรับโครงการที่มีงานสูงสุด 2,000 งานโดยไม่ทำให้ประสิทธิภาพลดลงอย่างเห็นได้ชัด.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือสูงกว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. ไฟล์ **project.mpp** ที่ถูกต้องซึ่งวางไว้ในโฟลเดอร์ที่คุณสามารถอ้างอิงจากโค้ดของคุณ.

## นำเข้าแพคเกจ
ก่อนอื่น ให้นำเข้าคลาสที่เราต้องการใช้ทำงานกับไฟล์ Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
บอกแอปพลิเคชันว่าที่อยู่ของไฟล์ *.mpp* ของคุณอยู่ที่ไหน.

```java
String dataDir = "Your Data Directory";
```

> **เคล็ดลับ:** ใช้ `System.getProperty("user.dir")` เพื่อสร้างเส้นทางแบบ absolute ที่ทำงานได้บนเครื่องใดก็ได้.

## ขั้นตอนที่ 2: โหลดไฟล์ MS Project
`Project` คืออ็อบเจ็กต์ระดับบนของ Aspose.Tasks ที่แทนไฟล์ Microsoft Project หนึ่งไฟล์ในหน่วยความจำ การสร้างอ็อบเจ็กต์นี้จะโหลดโครงสร้างไฟล์โดยไม่ต้องติดตั้ง Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

## ขั้นตอนที่ 3: ดึง (และเปลี่ยนได้ตามต้องการ) สัญลักษณ์สกุลเงิน
`Prj.CURRENCY_SYMBOL` คือคีย์ของ property ที่เก็บสัญลักษณ์สกุลเงิน การอ่านค่าจะคืนสัญลักษณ์ปัจจุบัน; การกำหนดสตริงใหม่จะอัปเดตการกำหนดสกุลเงินของโครงการ.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

คำสั่ง `System.out.println` จะพิมพ์สัญลักษณ์ (เช่น `$`) ไปยังคอนโซล เพื่อยืนยันว่าการดึงสำเร็จ.

## ปัญหาทั่วไป & วิธีแก้ไข
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | เส้นทางไฟล์ไม่ถูกต้องหรือไม่พบไฟล์ | ตรวจสอบ `dataDir` และชื่อไฟล์; ใช้ `new File(dataDir).exists()` เพื่อตรวจสอบ |
| สัญลักษณ์ไม่คาดคิด (เช่น `?`) | โครงการสร้างด้วย locale ที่ไม่มาตรฐาน | ตรวจสอบให้แน่ใจว่าไฟล์ MPP ต้นทางกำหนดสัญลักษณ์สกุลเงิน; คุณสามารถตั้งค่าได้โดยโปรแกรมตามที่แสดงด้านบน |
| ข้อผิดพลาดไลเซนส์ | ใช้รุ่นทดลองโดยไม่มีไฟล์ไลเซนส์ที่ถูกต้อง | โหลดไลเซนส์ของคุณด้วย `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` ก่อนสร้างอ็อบเจ็กต์ `Project` |

## คำถามที่พบบ่อย

**Q: ฉันสามารถจัดการคุณสมบัติอื่นของโครงการนอกจากสัญลักษณ์สกุลเงินโดยใช้ Aspose.Tasks ได้หรือไม่?**  
**A:** ใช่, Aspose.Tasks ให้คุณแก้ไขงาน, ทรัพยากร, การมอบหมาย, ปฏิทิน, และคุณสมบัติโครงการอื่น ๆ อีกมากมาย.

**Q: Aspose.Tasks รองรับไฟล์ MS Project เวอร์ชันต่าง ๆ หรือไม่?**  
**A:** แน่นอน. รองรับรูปแบบ MPP, MPT, และ XML ตั้งแต่ Project 98 จนถึงรุ่นล่าสุด.

**Q: Aspose.Tasks มีเอกสารและการสนับสนุนสำหรับนักพัฒนาหรือไม่?**  
**A:** มีเอกสาร API ครบถ้วน, ตัวอย่างโค้ด, และฟอรั่มสนับสนุนเฉพาะบนเว็บไซต์ Aspose.Tasks.

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
**A:** ใช่ – สามารถดาวน์โหลดรุ่นทดลองฟรีที่ทำงานเต็มรูปแบบจาก [Aspose website](https://purchase.aspose.com/buy).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร?**  
**A:** ไลเซนส์ชั่วคราวมีให้บน [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) เพื่อการประเมินผล.

---

**อัปเดตล่าสุด:** 2026-09-20  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [Project Properties Java – อ่าน Metadata ด้วย Aspose.Tasks](/tasks/java/project-properties/)
- [วิธีดึงสกุลเงินจาก MS Project ด้วย Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [ตั้งค่า Project Start Date ใน MS Project ด้วย Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}