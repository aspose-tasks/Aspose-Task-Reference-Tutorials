---
date: 2026-02-10
description: เรียนรู้วิธีดึงรหัสสกุลเงินจากไฟล์ MS Project ด้วย Aspose.Tasks for Java
  – วิธีที่รวดเร็วในการรับรหัสสกุลเงินที่นักพัฒนา Java ต้องการ.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีดึงสกุลเงินจาก MS Project ด้วย Aspose.Tasks
url: /th/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีดึงข้อมูลสกุลเงินจาก MS Project ด้วย Aspise.Tasks

## บทนำ
ยินดีต้อนรับ! ในบทแนะนำนี้คุณจะค้นพบ **วิธีดึงสกุลเงิน** จากไฟล์ MS Project โดยใช้ Aspose.Tasks Java API ไม่ว่าคุณจะสร้างรายงานการเงินหลายสกุลเงิน, รวมโครงการจากหลายภูมิภาค, หรือเพียงต้องการสัญลักษณ์เงินที่ถูกต้องสำหรับการประมวลผลต่อไป คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การตั้งค่าสภาพแวดล้อมของคุณจนถึงการดึงรหัสสกุลเงินโดยโปรแกรมเมติกส์. เมื่อเสร็จสิ้นคุณจะสามารถอ่านไฟล์ MS Project และใช้คำสั่ง **get currency code java** เพื่อรับตัวระบุสกุลเงิน ISO.

## คำตอบอย่างรวดเร็ว
- **API ทำอะไร?** มันอ่านไฟล์ MS Project และเปิดเผยคุณสมบัติเช่นรหัสสกุลเงิน.  
- **ใช้ภาษาอะไร?** Java, via the Aspose.Tasks for Java library.  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **สามารถดึงรหัสในบรรทัดเดียวได้หรือไม่?** ได้—`prj.get(Prj.CURRENCY_CODE)` จะคืนค่ารหัสสกุลเงินเป็นสตริง.  
- **รองรับเวอร์ชันของ Project ทั้งหมดหรือไม่?** Aspose.Tasks รองรับทั้งรูปแบบเก่า (MPP) และรูปแบบใหม่ (XML, XER).

## อะไรคือ **read ms project file**?
การอ่านไฟล์ MS Project หมายถึงการเปิดไฟล์โปรเจกต์ *.mpp* (หรือรูปแบบที่รองรับอื่น) ด้วยโปรแกรมและเข้าถึงโครงสร้างข้อมูล—งาน, ทรัพยากร, ปฏิทิน, และการตั้งค่าการเงิน—โดยไม่ต้องมีการโต้ตอบด้วยมือกับ Microsoft Project เอง.

## ทำไมต้องใช้ Aspose.Tasks เพื่อ **read msproject** files?
- **การสนับสนุนรูปแบบเต็ม** – works with files from Project 98 through the latest Office releases.  
- **ไม่ต้องการ COM หรือการติดตั้ง Office** – pure Java, perfect for server‑side automation.  
- **API ครบถ้วน** – ให้เข้าถึงคุณสมบัติโดยตรงเช่น `Prj.CURRENCY_CODE` ทำให้คุณสามารถ **วิธีดึงสกุลเงิน** ได้ทันที.  
- **ประสิทธิภาพ** – lightweight parsing, ideal for batch processing of many projects.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### ติดตั้ง Java Development Kit (JDK)
ตรวจสอบให้แน่ใจว่ามี JDK เวอร์ชันล่าสุดบนเครื่องของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK เวอร์ชันล่าสุดได้จาก [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### ไลบรารี Aspose.Tasks สำหรับ Java
ดาวน์โหลดและตั้งค่าไลบรารี Aspose.Tasks สำหรับ Java เอกสารโดยละเอียดและไบนารีล่าสุดพร้อมให้บริการ [here](https://reference.aspose.com/tasks/java/).

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น, ให้เรานำเข้าแพ็กเกจที่จำเป็นในโครงการ Java ของคุณ:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดโฟลเดอร์ที่มีไฟล์ *.mpp* ของคุณ ปรับเส้นทางให้ตรงกับสภาพแวดล้อมของคุณ
```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์โปรเจกต์
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ MS Project นี้ นี่คือจุดที่คุณ **read msproject** ข้อมูลเข้าสู่หน่วยความจำ
```java
Project prj = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 3: ดึงรหัสสกุลเงิน
ตอนนี้โปรเจกต์โหลดแล้ว คุณสามารถ **วิธีดึงสกุลเงิน** ด้วยการเรียกครั้งเดียว นี้เป็นการสาธิตการใช้ **get currency code java**
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
ผลลัพธ์จะเป็นรหัสสกุลเงิน ISO แบบสามตัวอักษร (เช่น `USD`, `EUR`, `GBP`) ที่โปรเจกต์กำหนดให้ใช้

### ขั้นตอนที่ 4: วิธีดึงรหัสสกุลเงินใน Java (บริบทเพิ่มเติม)
หากคุณต้องการเก็บค่าดังกล่าวไว้ใช้ในภายหลัง เพียงกำหนดให้กับตัวแปร:

*No extra code block is required* – เพียงเก็บสตริงที่ `prj.get(Prj.CURRENCY_CODE)` คืนค่าไว้และส่งต่อให้บริการการเงิน, เครื่องมือรายงาน, หรือคอมโพเนนต์ UI ใด ๆ

### ขั้นตอนที่ 5: (ทางเลือก) ใช้รหัสสกุลเงิน
คุณอาจต้องการนำรหัสที่ดึงมาใช้ในที่อื่น—เช่น การจัดรูปแบบค่าใช้จ่ายในรายงานแบบกำหนดเองหรือส่งต่อให้ API การเงิน สถานการณ์ทั่วไปได้แก่:

- **Report generation** – prepend the code to cost columns (`USD 1,200`).  
- **API integration** – send the ISO code to payment gateways that require a currency identifier.  
- **Data consolidation** – group multiple projects by currency for portfolio analysis.

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ผลลัพธ์เป็น Null** | Project file does not define a currency (default is empty). | ตั้งค่าสกุลเงินใน Microsoft Project หรือกำหนดโดยใช้ `prj.set(Prj.CURRENCY_CODE, "USD");` ก่อนอ่าน. |
| **ไม่พบไฟล์** | Incorrect `dataDir` path. | ตรวจสอบเส้นทางและให้แน่ใจว่าชื่อไฟล์ตรงกันอย่างแม่นยำ รวมถึงความแตกต่างของตัวอักษรใหญ่‑เล็ก. |
| **เวอร์ชันไฟล์ไม่รองรับ** | Very old or corrupted *.mpp* file. | ใช้เวอร์ชันล่าสุดของ Aspose.Tasks หรือแปลงไฟล์เป็นรูปแบบใหม่ใน Microsoft Project ก่อน. |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?**  
A: ได้, API สามารถอ่านและจัดการลำดับชั้นงานหลายระดับ, กลุ่มทรัพยากร, และฟิลด์กำหนดเองโดยไม่มีปัญหา.

**Q: Aspose.Tasks รองรับเวอร์ชันต่าง ๆ ของไฟล์ MS Project หรือไม่?**  
A: แน่นอน. รองรับ MPP, XML, XER, และรูปแบบอื่น ๆ ในหลายรุ่นของ Microsoft Project.

**Q: Aspose.Tasks มีเอกสารและการสนับสนุนหรือไม่?**  
A: มีเอกสารครบถ้วน, ตัวอย่างโค้ด, และการสนับสนุนเฉพาะจากเว็บไซต์ Aspose.

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: มีการทดลองใช้ฟรีเพื่อให้คุณประเมินคุณสมบัติต่าง ๆ รวมถึงการอ่านรหัสสกุลเงิน.

**Q: จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
A: สามารถรับไลเซนส์ชั่วคราวได้จาก [website](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินระยะสั้น.

---

**อัปเดตล่าสุด:** 2026-02-10  
**ทดสอบด้วย:** Aspose.Tasks for Java (latest version)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}