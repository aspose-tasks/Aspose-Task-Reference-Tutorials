---
date: 2026-08-24
description: เรียนรู้วิธีดึงข้อยกเว้นของปฏิทินใน Java จากไฟล์ MS Project และวิธีอ่านปฏิทิน
  mpp ด้วย Aspose.Tasks for Java คำแนะนำนี้มีตัวอย่างโค้ดทีละขั้นตอน
keywords:
- retrieve calendar exceptions java
- how to read mpp calendar
- Aspose.Tasks Java
- MS Project calendar API
lastmod: 2026-08-24
linktitle: วิธีดึงข้อยกเว้นของปฏิทินใน Java ด้วย Aspose.Tasks
og_description: เรียนรู้วิธีดึงข้อยกเว้นของปฏิทินใน Java จากไฟล์ MS Project และวิธีอ่านปฏิทิน
  mpp ด้วย Aspose.Tasks for Java คู่มือทีละขั้นตอนนี้ช่วยให้คุณเพิ่มการจัดการปฏิทินที่แม่นยำให้กับแอป
  Java ของคุณ
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: วิธีดึงข้อยกเว้นของปฏิทินใน Java ด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  headline: How to retrieve calendar exceptions java with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  name: How to retrieve calendar exceptions java with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
    text: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
    text: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
  type: HowTo
- questions:
  - answer: Retrieving calendar exceptions from an MPP file using Aspose.Tasks for
      Java.
    question: What does this tutorial cover?
  - answer: About 10‑15 minutes for a basic setup.
    question: How long does implementation take?
  - answer: JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).
    question: Prerequisites?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: All major MS Project formats (MPP, MPT, XML).
    question: Supported Project versions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project scheduling
- calendar exceptions
- MS Project integration
- developer tutorial
title: วิธีดึงข้อยกเว้นของปฏิทินใน Java ด้วย Aspose.Tasks
url: /th/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีดึงข้อมูลข้อยกเว้นปฏิทินใน Java ด้วย Aspose.Tasks

## บทนำ
ใน **asp tasks java tutorial** นี้คุณจะได้เรียนรู้วิธีดึงข้อยกเว้นปฏิทินจากไฟล์ Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java. ข้อยกเว้นปฏิทินแสดงช่วงเวลาที่ไม่ทำงาน เช่น วันหยุดหรือกฎเวลาทำงานที่กำหนดเอง และการอ่านข้อมูลเหล่านี้ด้วยโปรแกรมเป็นสิ่งสำคัญสำหรับการปรับระดับทรัพยากร, การรายงาน, และตรรกะการจัดตารางที่กำหนดเอง เราจะเดินผ่านกระบวนการทั้งหมดแบบขั้นตอนต่อขั้นตอน เพื่อให้คุณสามารถรวมความสามารถนี้เข้าไปในแอปพลิเคชัน Java ของคุณได้อย่างมั่นใจ.

## คำตอบสั้น
- **What does this tutorial cover?** **บทเรียนนี้ครอบคลุมอะไร?** การดึงข้อยกเว้นปฏิทินจากไฟล์ MPP โดยใช้ Aspose.Tasks สำหรับ Java.  
- **How long does implementation take?** **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ประมาณ 10‑15 นาทีสำหรับการตั้งค่าเบื้องต้น.  
- **Prerequisites?** **ข้อกำหนดเบื้องต้น?** JDK, Aspose.Tasks for Java, และ IDE (IntelliJ IDEA หรือ Eclipse).  
- **Do I need a license?** **ต้องการใบอนุญาตหรือไม่?** การทดลองใช้ฟรีสามารถใช้สำหรับการพัฒนา; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Supported Project versions?** **เวอร์ชัน Project ที่รองรับ?** ทุกฟอร์แมตหลักของ MS Project (MPP, MPT, XML).

## asp tasks java tutorial คืออะไร?
**asp tasks java tutorial** อธิบายวิธีใช้ Aspose.Tasks API ภายในโครงการ Java. มันให้ตัวอย่างโค้ดที่เป็นรูปธรรม, คำอธิบายแนวปฏิบัติที่ดีที่สุด, และสถานการณ์จริงเพื่อให้นักพัฒนาสามารถจัดการไฟล์ Project โดยไม่ต้องติดตั้ง Microsoft Project. การทำตามบทเรียนเช่นนี้ช่วยให้นักพัฒนามีความเข้าใจเชิงปฏิบัติเกี่ยวกับโครงสร้าง API, รูปแบบการใช้งานทั่วไป, และวิธีรวมความสามารถของมันเข้าสู่แอปพลิเคชันระดับองค์กรที่ใหญ่ขึ้น.

## ทำไมต้องดึงข้อยกเว้นปฏิทิน?
การดึงข้อยกเว้นปฏิทินทำให้คุณสร้างไทม์ไลน์โครงการที่แม่นยำโดยคำนึงถึงวันหยุดและตารางทำงานที่กำหนดเอง, สร้างเครื่องมือรายงานที่เน้นวันไม่ทำงาน, และซิงโครไนซ์ปฏิทิน Project กับระบบภายนอกเช่น ERP หรือ HR. Aspose.Tasks สามารถอ่านข้อยกเว้นจาก **30+** ประเภทของปฏิทินและรองรับ **3** ฟอร์แมตไฟล์ MS Project หลัก (MPP, MPT, XML) โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ทำให้ประมวลผลโครงการหลายร้อยหน้าได้อย่างมีประสิทธิภาพ.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

1. **Java Development Kit (JDK)** – ตรวจสอบว่าคุณมี JDK 8 หรือใหม่กว่าติดตั้งอยู่.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดและติดตั้ง Aspose.Tasks for Java จาก **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE)** – คุณสามารถใช้ IDE ใดก็ได้ที่คุณชอบ, เช่น IntelliJ IDEA หรือ Eclipse.

## นำเข้าแพ็กเกจ
คำสั่ง import จะนำคลาสของ Aspose.Tasks เข้ามาในไฟล์ซอร์ส Java ของคุณ, ทำให้คุณสามารถทำงานกับโครงการ, ปฏิทิน, และข้อยกเว้นได้.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูลของคุณ
กำหนดโฟลเดอร์ที่บรรจุไฟล์ Project ที่คุณต้องการวิเคราะห์. การใช้พาธแบบเต็มหรือพาธที่สัมพันธ์กับโฟลเดอร์ resources ของโครงการจะช่วยป้องกัน `FileNotFoundException`.

```java
String dataDir = "C:/Projects/Data/";
```

> **Pro tip:** เก็บไฟล์ Project ของคุณในโฟลเดอร์ resources แยกเฉพาะและอ้างอิงด้วย `Paths.get(...)` เพื่อให้พาธทำงานได้บนทุกแพลตฟอร์ม.

## ขั้นตอนที่ 2: โหลดไฟล์ MS Project
คลาส `Project` แทนไฟล์ MS Project และให้การเข้าถึงปฏิทิน, งาน, ทรัพยากร, และข้อมูลโครงการอื่น ๆ. โหลดไฟล์ Project ลงในอ็อบเจ็กต์ `Project`. อ็อบเจ็กต์นี้แทนไฟล์ MS Project ทั้งหมดในหน่วยความจำและให้การเข้าถึงปฏิทิน, งาน, ทรัพยากร, และอื่น ๆ.

```java
Project project = new Project(dataDir + "project.mpp");
```

## ขั้นตอนที่ 3: ดึงข้อยกเว้นปฏิทิน
วนลูปผ่านแต่ละปฏิทินในโครงการและจากนั้นผ่านแต่ละข้อยกเว้นในปฏิทินนั้น. พิมพ์วันที่เริ่มต้นและสิ้นสุดของแต่ละข้อยกเว้น.

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **No output printed** | ไฟล์ Project ไม่มีข้อยกเว้นปฏิทินใด ๆ. | ตรวจสอบให้แน่ใจว่าปฏิทินใน MS Project มีการกำหนดข้อยกเว้น (เช่น วันหยุด). |
| **`NullPointerException`** | พาธ `dataDir` ไม่ถูกต้องหรือไฟล์ไม่พบ. | ตรวจสอบพาธไดเรกทอรีอีกครั้งและยืนยันว่า `project.mpp` มีอยู่. |
| **Time zone mismatch** | วันที่แสดงเป็น UTC. | ใช้ `calExc.getFromDate().toLocalDateTime()` เพื่อแปลงเป็นเวลาท้องถิ่นหากจำเป็น. |

## คำถามที่พบบ่อย
### Aspose.Tasks สามารถจัดการกับเวอร์ชันต่าง ๆ ของไฟล์ MS Project ได้หรือไม่?
ใช่, Aspose.Tasks รองรับ **ทุกฟอร์แมตหลัก** ของ MS Project, รวมถึง MPP, MPT, และ XML, สำหรับเวอร์ชันตั้งแต่ปี 2000 จนถึงรุ่นล่าสุด.

### มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks หรือไม่?
ใช่, คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีของ Aspose.Tasks ได้จาก **[Aspose free trial download page](https://releases.aspose.com/)**.

### ฉันสามารถหาเอกสารสำหรับ Aspose.Tasks for Java ได้ที่ไหน?
คุณสามารถอ้างอิงเอกสาร **[Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)**.

### ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร?
คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน **[Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)**.

### มีตัวเลือกสำหรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks หรือไม่?
ใช่, คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก **[temporary license purchase page](https://purchase.aspose.com/temporary-license/)**.

**คำถามเพิ่มเติม**

**Q:** *Can I modify calendar exceptions after retrieving them?*  
**A:** แน่นอน. ใช้ `CalendarException.setFromDate()` และ `setToDate()` เพื่อปรับวันที่, จากนั้นบันทึกโครงการด้วย `project.save(...)`.

**Q:** *Does Aspose.Tasks preserve custom fields on calendars?*  
**A:** ใช่, ฟิลด์กำหนดเองและแอตทริบิวต์ขยายทั้งหมดจะถูกเก็บรักษาไว้เมื่อโหลดและบันทึกโครงการ.

## สรุป
ใน **asp tasks java tutorial** นี้เราได้เรียนรู้วิธีดึงข้อยกเว้นปฏิทินจาก MS Project ด้วย Aspose.Tasks สำหรับ Java. ด้วยการทำตามขั้นตอนง่าย ๆ เหล่านี้, คุณสามารถผสานฟังก์ชันนี้เข้าไปในแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น, เพิ่มคุณสมบัติการจัดตารางที่หลากหลายและการวิเคราะห์โครงการที่แม่นยำยิ่งขึ้น.

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  








```java
import com.aspose.tasks.*;
```

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

```java
Project project = new Project(dataDir + "project.mpp");
```

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

## บทเรียนที่เกี่ยวข้อง

- [สร้างข้อยกเว้นปฏิทินแบบกำหนดเองด้วย Aspose.Tasks สำหรับ Java](/tasks/java/calendar-exceptions/)
- [วิธีใช้ Aspose.Tasks เพื่อดึงข้อมูลปฏิทินของ MS Project](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [วิธีอ่านสัปดาห์ทำงานใน Java จากปฏิทิน MS Project ด้วย Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}