---
date: 2026-08-13
description: เรียนรู้วิธีสร้างปฏิทินมาตรฐานของ MS Project ด้วย Java โดยใช้ Aspose.Tasks
  คู่มือขั้นตอนต่อขั้นตอนนี้จะแสดงวิธีสร้างปฏิทินมาตรฐานของ MS Project, เพิ่มเป็นค่าเริ่มต้น,
  และบันทึกไฟล์
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: สร้างปฏิทินมาตรฐานใน Aspose.Tasks
og_description: วิธีสร้างปฏิทินด้วย Java และ Aspose.Tasks เรียนรู้การสร้างปฏิทินมาตรฐานของ
  MS Project ตั้งเป็นค่าเริ่มต้น และบันทึกไฟล์โปรเจกต์ในไม่กี่นาที
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: วิธีสร้างปฏิทิน – สร้างปฏิทินมาตรฐานใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: วิธีสร้างปฏิทิน – สร้างปฏิทินมาตรฐานใน Aspose.Tasks
url: /th/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างปฏิทิน – สร้างปฏิทินมาตรฐานใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีสร้างปฏิทิน** สำหรับไฟล์ Microsoft Project ด้วยการใช้ไลบรารี Aspose.Tasks for Java เราจะอธิบายขั้นตอนการสร้างปฏิทินมาตรฐานของ MS Project การตั้งให้เป็นปฏิทินเริ่มต้น (มาตรฐาน) และการบันทึกไฟล์โครงการ เมื่อจบคู่มือคุณจะสามารถผสานการสร้างปฏิทินเข้าไปในโซลูชันการจัดการโครงการที่ใช้ Java ได้ทุกประเภท

## คำตอบอย่างรวดเร็ว
- **หมายถึง “ปฏิทินมาตรฐาน” คืออะไร?** เป็นการกำหนดเวลาทำงานเริ่มต้นที่ใช้กับงานที่ไม่ได้กำหนดปฏิทินแบบกำหนดเอง
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks for Java – API แบบ pure‑Java ที่ทำงานได้โดยไม่ต้องติดตั้ง Microsoft Project
- **ต้องการใบอนุญาตหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต
- **ไฟล์รูปแบบใดที่สร้างขึ้น?** ไฟล์ Microsoft Project แบบ XML (`.xml`).
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ประมาณ 5‑10 นาทีสำหรับการตั้งค่าปฏิทินพื้นฐาน

## ปฏิทินมาตรฐานใน Microsoft Project คืออะไร?
ปฏิทินมาตรฐานกำหนดวันและชั่วโมงทำงานเริ่มต้นของโครงการ โดยทั่วไปคือวันจันทร์ถึงศุกร์ เวลา 8 โมงเช้าถึง 5 โมงเย็น เมื่อคุณเพิ่มปฏิทินมาตรฐาน งานใดที่ไม่ได้กำหนดปฏิทินแบบกำหนดเองจะสืบทอดช่วงเวลาทำงานเหล่านี้ ทำให้การกำหนดเวลาเป็นไปอย่างสม่ำเสมอทั่วทั้งโครงการ

## ทำไมต้องใช้ Aspose.Tasks เพื่อสร้างปฏิทิน?
Aspose.Tasks for Java รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 รูปแบบ** และสามารถประมวลผลโครงการที่มีงานสูงสุด **10,000 งาน** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ไลบรารี pure‑Java นี้ช่วยให้คุณอัตโนมัติการสร้างไฟล์ Project บนเซิร์ฟเวอร์, สายงาน CI หรือแอปพลิเคชัน Java ใด ๆ ทำให้ไม่จำเป็นต้องติดตั้ง Microsoft Project ที่มีลิขสิทธิ์

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มต้น โปรดตรวจสอบให้แน่ใจว่ามีสิ่งต่อไปนี้พร้อมใช้งาน:

### การติดตั้ง Java Development Kit (JDK)
ติดตั้ง JDK เวอร์ชันล่าสุดจากเว็บไซต์ของ Oracle หรือจากการแจกจ่าย OpenJDK

### ไลบรารี Aspose.Tasks for Java
ดาวน์โหลดไลบรารีจาก [หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/). เพิ่มไฟล์ JAR ไปยัง classpath ของโครงการของคุณ

## นำเข้าแพ็กเกจ
เราต้องการการนำเข้าเพียงหนึ่งรายการสำหรับบทแนะนำนี้:

```java
import com.aspose.tasks.*;
```

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดตำแหน่งที่ไฟล์โครงการที่สร้างขึ้นจะถูกบันทึก

```java
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยเส้นทางเต็มบนเครื่องของคุณ (เช่น `C:/Projects/Output/`).

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ของโครงการ
`Project` คืออ็อบเจ็กต์ระดับบนสุดของ Aspose.Tasks ที่แสดงไฟล์ Microsoft Project หนึ่งไฟล์ในหน่วยความจำ การสร้างอินสแตนซ์นี้จะให้คอนเทนเนอร์สำหรับปฏิทิน งาน ทรัพยากร และข้อมูลโครงการอื่น ๆ

```java
Project project = new Project();
```

### ขั้นตอนที่ 3: กำหนดและตั้งค่าปฏิทินเป็นมาตรฐาน
`Calendar` คือคลาสที่จำลองตารางเวลาการทำงาน การเพิ่มปฏิทินใหม่ชื่อ **“My Cal”** และเรียก `makeStandardCalendar` จะทำให้มันเป็นปฏิทินเริ่มต้นสำหรับโครงการทั้งหมด

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **เคล็ดลับ:** เมธอด `makeStandardCalendar` จะทำเครื่องหมายปฏิทินที่ระบุให้เป็นค่าเริ่มต้นของโครงการโดยอัตโนมัติ ซึ่งเป็นสิ่งที่คุณต้องการเมื่อคุณต้องการ **เพิ่มฟังก์ชันการทำงานของปฏิทินมาตรฐาน**.

### ขั้นตอนที่ 4: บันทึกโครงการ
SaveFileFormat คือ enumeration ที่ระบุรูปแบบไฟล์ที่จะใช้เมื่อบันทึกโครงการ  
บันทึกโครงการ (รวมถึงปฏิทินใหม่) เป็นไฟล์ XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

คุณสามารถเปลี่ยนชื่อไฟล์หรือรูปแบบ (`SaveFileFormat.Pp`) หากต้องการเวอร์ชัน Project ที่แตกต่าง

### ขั้นตอนที่ 5: แสดงข้อความเสร็จสิ้น
แสดงสัญญาณภาพให้คุณทราบว่ากระบวนการเสร็จสิ้นโดยไม่มีข้อผิดพลาด

```java
System.out.println("Process completed Successfully");
```

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **ไม่พบไฟล์** | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | สร้างโฟลเดอร์หรือใช้เส้นทางเต็ม |
| **ข้อยกเว้นใบอนุญาต** | ทำงานโดยไม่มีใบอนุญาต Aspose.Tasks ที่ถูกต้องในสภาพแวดล้อมการผลิต | กำหนดไฟล์ใบอนุญาตโดยใช้ `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **ปฏิทินว่าง** | ลืมเพิ่มการกำหนดเวลาทำงาน | ใช้ `cal1.getWeekDays().add(WeekDay.DayType.Monday)` เป็นต้น หากต้องการชั่วโมงทำงานแบบกำหนดเอง |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks รองรับทุกเวอร์ชันของ Microsoft Project หรือ?**  
A: ใช่, Aspose.Tasks รองรับช่วงเวอร์ชันของ Microsoft Project อย่างกว้างขวาง ตั้งแต่ปี 2000 จนถึงรุ่นล่าสุด

**Q: ฉันสามารถปรับแต่งการตั้งค่าปฏิทินเพิ่มเติมได้หรือไม่?**  
A: ได้เลย! คุณสามารถแก้ไขวันทำงาน เพิ่มข้อยกเว้น และกำหนดช่วงเวลาทำงานเฉพาะโดยใช้คลาส `WeekDay` และ `WorkingTime`

**Q: Aspose.Tasks เหมาะกับแอปพลิเคชันระดับองค์กรหรือไม่?**  
A: แน่นอน ไลบรารีนี้ออกแบบมาสำหรับสภาพแวดล้อมที่มีประสิทธิภาพสูงและขยายได้ และให้การสนับสนุนอย่างครบถ้วนสำหรับไฟล์ Project ขนาดใหญ่

**Q: Aspose.Tasks มีการสนับสนุนทางเทคนิคสำหรับนักพัฒนาหรือไม่?**  
A: ใช่, Aspose มีฟอรั่มเฉพาะ, การสนับสนุนแบบตั๋ว, และเอกสารที่ครอบคลุมเพื่อช่วยคุณแก้ไขปัญหาได้อย่างรวดเร็ว

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: ได้, คุณสามารถสำรวจรุ่นทดลองฟรีที่มีบน [เว็บไซต์](https://purchase.aspose.com/buy) ซึ่งช่วยให้คุณประเมินคุณสมบัติทั้งหมดก่อนตัดสินใจ

---

**อัปเดตล่าสุด:** 2026-08-13  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มปฏิทินลงในโครงการด้วย Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [วิธีตั้งค่าปฏิทินโครงการใน Java ด้วย Aspose.Tasks](/tasks/java/calendars/properties/)
- [สร้างข้อยกเว้นปฏิทินแบบกำหนดเองด้วย Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}