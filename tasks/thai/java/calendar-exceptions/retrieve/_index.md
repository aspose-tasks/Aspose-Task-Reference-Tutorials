---
date: 2026-11-19
description: เรียนรู้วิธีดึงข้อยกเว้นปฏิทิน Java จากไฟล์ MS Project และวิธีอ่านปฏิทิน
  MPP ด้วย Aspose.Tasks for Java คำแนะนำนี้มีตัวอย่างโค้ดแบบขั้นตอนต่อขั้นตอน
images:
- /java/calendar-exceptions/retrieve/og-image.png
keywords:
- retrieve calendar exceptions java
- Aspose.Tasks for Java
- MS Project calendar API
- read MPP calendar
- Java project scheduling
lastmod: 2026-11-19
linktitle: วิธีดึงข้อยกเว้นปฏิทิน Java ด้วย Aspose.Tasks
og_description: เรียนรู้วิธีดึงข้อยกเว้นปฏิทิน Java จากไฟล์ MS Project และอ่านปฏิทิน
  MPP ด้วย Aspose.Tasks for Java คู่มือนี้จะแสดงวิธีเพิ่มการจัดการปฏิทินที่แม่นยำให้กับแอป
  Java
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: วิธีดึงข้อยกเว้นปฏิทิน Java ด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
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
title: วิธีดึงข้อยกเว้นปฏิทิน Java ด้วย Aspose.Tasks
url: /th/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีดึงข้อมูลข้อยกเว้นของปฏิทินใน Java ด้วย Aspose.Tasks

## บทนำ
ใน **asp tasks java tutorial** นี้ คุณจะได้เรียนรู้วิธีดึงข้อยกเว้นของปฏิทินจากไฟล์ Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java. ข้อยกเว้นของปฏิทินหมายถึงช่วงเวลาที่ไม่ทำงาน เช่น วันหยุดหรือกฎเวลาทำงานที่กำหนดเอง และการอ่านข้อมูลเหล่านี้ด้วยโปรแกรมเป็นสิ่งสำคัญสำหรับการปรับระดับทรัพยากร การสร้างรายงาน และตรรกะการกำหนดเวลาที่กำหนดเอง เราจะเดินผ่านกระบวนการทั้งหมดทีละขั้นตอน เพื่อให้คุณสามารถผสานความสามารถนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างมั่นใจ.

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไร?** การดึงข้อยกเว้นของปฏิทินจากไฟล์ MPP โดยใช้ Aspose.Tasks สำหรับ Java.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับการตั้งค่าเบื้องต้น.  
- **ข้อกำหนดเบื้องต้น?** JDK, Aspose.Tasks for Java, และ IDE (IntelliJ IDEA หรือ Eclipse).  
- **ฉันต้องการไลเซนส์หรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน Project ที่รองรับ?** รูปแบบ MS Project หลักทั้งหมด (MPP, MPT, XML).

## asp tasks java tutorial คืออะไร?
**asp tasks java tutorial** อธิบายวิธีใช้ Aspose.Tasks API ภายในโครงการ Java มันให้ตัวอย่างโค้ดที่เป็นรูปธรรม, คำอธิบายแนวปฏิบัติที่ดีที่สุด, และสถานการณ์จากโลกจริง เพื่อให้นักพัฒนาสามารถจัดการไฟล์ Project ได้โดยไม่ต้องติดตั้ง Microsoft Project ด้วยการทำตามบทเรียนเช่นนี้ นักพัฒนาจะได้รับความเข้าใจที่ชัดเจนและเป็นมืออาชีพเกี่ยวกับโครงสร้างของ API, รูปแบบการใช้งานทั่วไป, และวิธีผสานความสามารถของมันเข้าสู่แอปพลิเคชันองค์กรขนาดใหญ่.

## ทำไมต้องดึงข้อยกเว้นของปฏิทิน?
การดึงข้อยกเว้นของปฏิทินทำให้คุณสร้างไทม์ไลน์ของโครงการที่แม่นยำโดยเคารพวันหยุดและตารางทำงานที่กำหนดเอง, สร้างเครื่องมือรายงานที่เน้นวันไม่ทำงาน, และซิงค์ปฏิทิน Project กับระบบภายนอกเช่น ERP หรือแพลตฟอร์ม HR. Aspose.Tasks สามารถอ่านข้อยกเว้นจาก **30+** ประเภทของปฏิทินและรองรับ **3 major** รูปแบบไฟล์ MS Project (MPP, MPT, XML) โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ทำให้การประมวลผลโครงการหลายร้อยหน้ามีประสิทธิภาพ.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:

1. **Java Development Kit (JDK)** – ตรวจสอบว่าคุณมี JDK 8 หรือรุ่นที่ใหม่กว่าได้ติดตั้งไว้แล้ว.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดและติดตั้ง Aspose.Tasks for Java จาก **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE)** – คุณสามารถใช้ IDE ใดก็ได้ที่คุณต้องการ, เช่น IntelliJ IDEA หรือ Eclipse.

คุณยังสามารถรับ Aspose.Tasks for Java จาก **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** หากคุณต้องการเตือนความจำในภายหลังในบทเรียน.

## คุณตั้งค่าไดเรกทอรีข้อมูลอย่างไร?
กำหนดโฟลเดอร์ที่บรรจุไฟล์ Project ที่คุณต้องการวิเคราะห์. การใช้เส้นทางแบบเต็มหรือเส้นทางที่สัมพันธ์กับโฟลเดอร์ resources ของโครงการของคุณจะป้องกัน `FileNotFoundException`. เก็บไฟล์ของคุณในโฟลเดอร์ `resources` แยกเฉพาะและอ้างอิงด้วย `Paths.get(...)` เพื่อทำให้โค้ดเป็นอิสระต่อแพลตฟอร์มและหลีกเลี่ยงเส้นทาง Windows ที่กำหนดค่าตายตัว.

## นำเข้าแพ็กเกจ
คำสั่ง import จะนำคลาสของ Aspose.Tasks เข้ามาในไฟล์ซอร์ส Java ของคุณ, ทำให้คุณสามารถทำงานกับโครงการ, ปฏิทิน, และข้อยกเว้นได้.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## คลาส Project คืออะไร?
`Project` แสดงไฟล์ MS Project ที่โหลดเข้าสู่หน่วยความจำ. มันเป็นอ็อบเจ็กต์หลักของ Aspose.Tasks ที่ให้คุณเข้าถึงปฏิทิน, งาน, ทรัพยากร, และข้อมูลโครงการอื่น ๆ ผ่าน API ที่เป็นวัตถุ‑ออริเอนต์ที่สะอาด. โดยการใช้คลาส `Project` คุณสามารถสอบถามและจัดการทุกองค์ประกอบของโครงการโดยไม่ต้องติดตั้ง Microsoft Project, ทำให้เหมาะสำหรับการประมวลผลฝั่งเซิร์ฟเวอร์และการรายงานอัตโนมัติ.

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูลของคุณ
กำหนดโฟลเดอร์ที่บรรจุไฟล์ Project ที่คุณต้องการวิเคราะห์. การใช้เส้นทางแบบเต็มหรือเส้นทางที่สัมพันธ์กับโฟลเดอร์ resources ของโครงการของคุณจะป้องกัน `FileNotFoundException`.

```java
String dataDir = "C:/Projects/Data/";
```

> **เคล็ดลับ:** เก็บไฟล์ Project ของคุณในโฟลเดอร์ resources แยกเฉพาะและอ้างอิงด้วย `Paths.get(...)` เพื่อเส้นทางที่เป็นอิสระต่อแพลตฟอร์ม.

## ขั้นตอนที่ 2: โหลดไฟล์ ms project
คลาส `Project` แสดงไฟล์ MS Project และให้เข้าถึงปฏิทิน, งาน, ทรัพยากร, และข้อมูลโครงการอื่น ๆ. โหลดไฟล์ Project เข้าไปในอ็อบเจ็กต์ `Project`. อ็อบเจ็กต์นี้แสดงไฟล์ MS Project ทั้งหมดในหน่วยความจำและให้เข้าถึงปฏิทิน, งาน, ทรัพยากร, และอื่น ๆ.

```java
Project project = new Project(dataDir + "project.mpp");
```

## คุณดึงข้อยกเว้นของปฏิทินจากโครงการที่โหลดแล้วอย่างไร?
วนลูปผ่านแต่ละปฏิทินในโครงการและจากนั้นผ่านแต่ละข้อยกเว้นของปฏิทินภายในปฏิทินนั้น. พิมพ์วันที่เริ่มต้นและสิ้นสุดของแต่ละข้อยกเว้น. ลูปสองระดับนี้ทำให้คุณจับข้อยกเว้นทั้งหมด, แม้ว่าโครงการจะมีหลายปฏิทิน (มาตรฐาน, ทรัพยากร, หรือกำหนดเอง). โดยการตรวจสอบแต่ละ `CalendarException` คุณสามารถสร้างรายงานกำหนดเอง, ปรับตารางเวลา, หรือส่งออกข้อมูลไปยังระบบอื่น.

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
| **ไม่มีการพิมพ์ผลลัพธ์** | ไฟล์ Project ไม่มีข้อยกเว้นของปฏิทินใด ๆ. | ตรวจสอบว่าปฏิทินใน MS Project มีการกำหนดข้อยกเว้น (เช่น วันหยุด). |
| **`NullPointerException`** | เส้นทาง `dataDir` ไม่ถูกต้องหรือไม่พบไฟล์. | ตรวจสอบเส้นทางไดเรกทอรีอีกครั้งและให้แน่ใจว่าไฟล์ `project.mpp` มีอยู่. |
| **ความไม่ตรงกันของโซนเวลา** | วันที่แสดงเป็นเวลา UTC. | ใช้ `calExc.getFromDate().toLocalDateTime()` เพื่อแปลงเป็นเวลาท้องถิ่นหากจำเป็น. |

## คำถามที่พบบ่อย
### Aspose.Tasks สามารถจัดการกับเวอร์ชันต่าง ๆ ของไฟล์ MS Project ได้หรือไม่?
ใช่, Aspose.Tasks รองรับ **all major** รูปแบบของ MS Project, รวมถึง MPP, MPT, และ XML, สำหรับเวอร์ชันตั้งแต่ปี 2000 จนถึงรุ่นล่าสุด.

### มีรุ่นทดลองฟรีสำหรับ Aspose.Tasks หรือไม่?
ใช่, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.Tasks ได้จาก **[Aspose free trial download page](https://releases.aspose.com/)**.

### ฉันสามารถหาเอกสารสำหรับ Aspose.Tasks for Java ได้ที่ไหน?
คุณสามารถอ้างอิงเอกสารได้จาก **[Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)**.

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร?
คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน **[Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)**.

### มีตัวเลือกสำหรับไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks หรือไม่?
ใช่, คุณสามารถรับไลเซนส์ชั่วคราวได้จาก **[temporary license purchase page](https://purchase.aspose.com/temporary-license/)**.

**คำถามเพิ่มเติม & คำตอบ**

**Q:** *ฉันสามารถแก้ไขข้อยกเว้นของปฏิทินหลังจากดึงข้อมูลแล้วได้หรือไม่?*  
**A:** แน่นอน. ใช้ `CalendarException.setFromDate()` และ `setToDate()` เพื่อปรับวันที่, จากนั้นบันทึกโครงการด้วย `project.save(...)`.

**Q:** *Aspose.Tasks รักษาฟิลด์กำหนดเองบนปฏิทินไว้หรือไม่?*  
**A:** ใช่, ฟิลด์กำหนดเองทั้งหมดและแอตทริบิวต์ขยายจะถูกเก็บไว้เมื่อตอนโหลดและบันทึกโครงการ.

## สรุป
ใน **asp tasks java tutorial** นี้ เราได้เรียนรู้วิธีดึงข้อยกเว้นของปฏิทินจาก MS Project ด้วย Aspose.Tasks สำหรับ Java. ด้วยการทำตามขั้นตอนง่าย ๆ นี้ คุณสามารถผสานฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น, ทำให้มีคุณลักษณะการกำหนดเวลาที่ครอบคลุมและการวิเคราะห์โครงการที่แม่นยำยิ่งขึ้น.

---

**อัปเดตล่าสุด:** 2026-11-19  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  








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

- [สร้างข้อยกเว้นของปฏิทินแบบกำหนดเองด้วย Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)
- [วิธีใช้ Aspose.Tasks เพื่อดึงข้อมูลปฏิทิน MS Project](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [วิธีอ่าน Workweeks Java จากปฏิทิน MS Project ด้วย Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}