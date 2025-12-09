---
date: 2025-12-09
description: เรียนรู้วิธีอ่านไฟล์ MS Project และจัดการรหัสสกุลเงินอย่างมีประสิทธิภาพด้วย
  Aspose.Tasks for Java ทำให้การจัดการโครงการของคุณเป็นเรื่องง่ายโดยไม่ต้องเสียเวลา.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีอ่านไฟล์ MS Project และจัดการรหัสสกุลเงินด้วย Aspose.Tasks
url: /th/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านไฟล์ MS Project และจัดการรหัสสกุลเงินด้วย Aspose.Tasks

## Introduction
ยินดีต้อนรับ! ในบทแนะนำนี้คุณจะค้นพบ **วิธีอ่านข้อมูลไฟล์ MS Project** และโดยเฉพาะ **การจัดการรหัสสกุลเงิน** ด้วย Aspose.Tasks Java API ไม่ว่าคุณจะสร้างรายงาน, รวมโครงการหลายสกุลเงิน, หรือเพียงต้องการให้สัญลักษณ์การเงินที่ถูกต้องปรากฏ, คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการดึงรหัสสกุลเงินแบบโปรแกรมเมติก เมื่อเสร็จสิ้นคุณจะสามารถอ่านไฟล์ MS Project และสกัดข้อมูลสกุลเงินที่ต้องการได้อย่างมั่นใจ.

## Quick Answers
- **API ทำอะไร?** มันอ่านไฟล์ MS Project และเปิดเผยคุณสมบัติเช่นรหัสสกุลเงิน.  
- **ใช้ภาษาอะไร?** Java ผ่านไลบรารี Aspose.Tasks for Java.  
- **ต้องการไลเซนส์หรือไม่?** ทดลองใช้ฟรีสำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **สามารถดึงรหัสได้ในบรรทัดเดียวหรือไม่?** ได้—`prj.get(Prj.CURRENCY_CODE)` จะคืนค่ารหัสสกุลเงินเป็นสตริง.  
- **รองรับเวอร์ชัน Project ทั้งหมดหรือไม่?** Aspose.Tasks รองรับทั้งรูปแบบเก่า (MPP) และใหม่ (XML, XER).

## What is **read ms project file**?
การอ่านไฟล์ MS Project หมายถึงการเปิดไฟล์โปรเจกต์ *.mpp* (หรือไฟล์ที่รองรับอื่น) อย่างโปรแกรมเมติกและเข้าถึงโครงสร้างข้อมูลของมัน—งาน, ทรัพยากร, ปฏิทิน, และการตั้งค่าการเงิน—โดยไม่ต้องโต้ตอบด้วย Microsoft Project ด้วยตนเอง.

## Why use Aspose.Tasks to **read msproject** files?
- **รองรับรูปแบบเต็ม** – ทำงานกับไฟล์ตั้งแต่ Project 98 จนถึงรุ่น Office ล่าสุด.  
- **ไม่ต้องการ COM หรือการติดตั้ง Office** – เป็น Java แท้, เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์.  
- **API ครบถ้วน** – ให้การเข้าถึงโดยตรงต่อคุณสมบัติเช่น `Prj.CURRENCY_CODE`, ทำให้คุณ **วิธีดึงข้อมูลสกุลเงิน** ได้ทันที.  
- **ประสิทธิภาพ** – การแยกข้อมูลที่เบา, เหมาะสำหรับการประมวลผลเป็นชุดของหลายโครงการ.

## Prerequisites
ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### Java Development Kit (JDK) Installed
ตรวจสอบให้แน่ใจว่ามี JDK เวอร์ชันล่าสุดติดตั้งบนเครื่องของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK ล่าสุดได้จาก [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java Library
ดาวน์โหลดและตั้งค่าไลบรารี Aspose.Tasks for Java เอกสารรายละเอียดและไบนารีล่าสุดพร้อมให้ดาวน์โหลดได้ที่ [here](https://reference.aspose.com/tasks/java/).

## Import Packages
เพื่อเริ่มต้น, ให้นำเข้าแพ็กเกจที่จำเป็นในโปรเจกต์ Java ของคุณ:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Step 1: Set Up Data Directory
กำหนดโฟลเดอร์ที่บรรจุไฟล์ *.mpp* ของคุณ ปรับเส้นทางให้ตรงกับสภาพแวดล้อมของคุณ.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ MS Project นี่คือจุดที่คุณ **อ่านข้อมูล msproject** เข้าสู่หน่วยความจำ.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Currency Code
เมื่อโปรเจกต์โหลดแล้ว, คุณสามารถ **วิธีดึงสกุลเงิน** ด้วยการเรียกครั้งเดียว นี้เป็นการสาธิตการใช้ **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
ผลลัพธ์จะเป็นรหัสสกุลเงิน ISO แบบสามตัวอักษร (เช่น `USD`, `EUR`, `GBP`) ที่โครงการตั้งค่าไว้.

### Step 4: (Optional) Use the Currency Code
คุณอาจต้องการใช้รหัสที่ดึงมาในที่อื่น—เช่นการจัดรูปแบบค่าต้นทุนในรายงานที่กำหนดเองหรือส่งต่อให้ API การเงิน นี่คือตัวอย่างสั้น (ไม่ต้องมีบล็อกโค้ดเพิ่มเติม):
- เก็บรหัสไว้ในตัวแปร.  
- ใช้รหัสเมื่อสร้างสตริงเงิน.  
- ส่งต่อให้บริการต่อเนื่องที่ต้องการตัวระบุสกุลเงิน.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **ผลลัพธ์เป็น Null** | ไฟล์โปรเจกต์ไม่ได้กำหนดสกุลเงิน (ค่าเริ่มต้นเป็นค่าว่าง) | ตั้งค่าสกุลเงินใน Microsoft Project หรือกำหนดผ่าน `prj.set(Prj.CURRENCY_CODE, "USD");` ก่อนอ่าน. |
| **ไฟล์ไม่พบ** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบเส้นทางและให้แน่ใจว่าชื่อไฟล์ตรงกันอย่างแม่นยำ รวมถึงความแตกต่างตัวพิมพ์ใหญ่/เล็ก. |
| **เวอร์ชันไฟล์ไม่รองรับ** | ไฟล์ *.mpp* เก่าเกินไปหรือเสียหาย | ใช้เวอร์ชัน Aspose.Tasks ล่าสุดหรือแปลงไฟล์เป็นรูปแบบใหม่ใน Microsoft Project ก่อน. |

## Frequently Asked Questions

**Q: Aspose.Tasks สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?**  
A: ได้, API สามารถอ่านและจัดการลำดับชั้นงานหลายระดับ, กลุ่มทรัพยากร, และฟิลด์กำหนดเองได้โดยไม่มีปัญหา.

**Q: Aspose.Tasks รองรับเวอร์ชันไฟล์ MS Project ต่าง ๆ หรือไม่?**  
A: แน่นอน. รองรับ MPP, XML, XER, และรูปแบบอื่น ๆ มากมายจากหลายรุ่นของ Microsoft Project.

**Q: Aspose.Tasks มีเอกสารและการสนับสนุนหรือไม่?**  
A: มีเอกสารครบถ้วน, ตัวอย่างโค้ด, และทีมสนับสนุนเฉพาะบนเว็บไซต์ Aspose.

**Q: สามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: มีการให้ทดลองใช้ฟรีเพื่อให้คุณประเมินคุณสมบัติทั้งหมด, รวมถึงการอ่านรหัสสกุลเงิน.

**Q: จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
A: สามารถขอรับไลเซนส์ชั่วคราวได้จาก [website](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินผลระยะสั้น.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-09  
**ทดสอบด้วย:** Aspose.Tasks for Java (latest version)  
**ผู้เขียน:** Aspose