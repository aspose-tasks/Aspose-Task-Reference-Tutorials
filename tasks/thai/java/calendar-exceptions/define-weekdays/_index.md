---
date: 2026-07-29
description: เรียนรู้วิธี schedule non working days โดยการสร้าง project calendar ด้วย
  Aspose.Tasks for Java, กำหนด weekday exceptions และจัดการ holiday schedules
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Schedule Non Working Days – สร้าง Project Calendar ด้วย Aspose
og_description: Schedule non working days ด้วย Aspose.Tasks for Java. เรียนรู้การกำหนด
  weekdays, เพิ่ม calendar exceptions, และจัดการ holiday schedules อย่างมีประสิทธิภาพ
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Schedule Non Working Days – สร้าง Project Calendar ด้วย Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Schedule Non Working Days – สร้าง Project Calendar ด้วย Aspose
url: /th/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดวันไม่ทำงาน – สร้างปฏิทินโครงการ Aspose

### บทนำ
เมื่อคุณต้อง **schedule non working days** สำหรับโครงการ คุณต้องสามารถจำลองวันหยุด, กะพิเศษ, หรือการปิดชั่วคราวโดยตรงในแผนโครงการ Aspose.Tasks for Java ให้คุณควบคุมการกำหนดปฏิทินได้อย่างเต็มที่, สามารถเพิ่มข้อยกเว้นที่สะท้อนตารางเวลาจริงได้ ในบทเรียนนี้เราจะอธิบายขั้นตอนที่แน่นอนในการกำหนดวันทำงานสำหรับข้อยกเว้นของปฏิทิน, เพื่อให้ไทม์ไลน์ของโครงการของคุณแม่นยำและเชื่อถือได้ ในตอนท้ายคุณจะเห็นว่ามันสอดคล้องกับกลยุทธ์ **non‑working days schedule** ที่กว้างขวางสำหรับโครงการระดับองค์กรใด ๆ

## คำตอบด่วน
- **What does “schedule non working days” mean?**  
  หมายถึงการใช้ Aspose.Tasks เพื่อสร้างปฏิทินที่ทำเครื่องหมายวันที่เฉพาะว่าเป็นวันไม่ทำงาน, ซึ่งมีผลต่อวันที่ของงานโดยอัตโนมัติ.  
- **Do I need a license to run the sample?**  
  การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Which IDEs are supported?**  
  IntelliJ IDEA, Eclipse, NetBeans หรือ IDE ใด ๆ ที่รองรับ Java 8+.  
- **Can I add multiple exceptions to the same calendar?**  
  ใช่ – คุณสามารถเพิ่มอ็อบเจ็กต์ `CalendarException` ได้ตามต้องการ.  
- **What file formats can I save the project to?**  
  XML, MPP และรูปแบบอื่น ๆ ที่รองรับโดย Aspose.Tasks.  

## ปฏิทินโครงการใน Aspose.Tasks คืออะไร?
**project calendar** คืออ็อบเจ็กต์ระดับบนสุดของ Aspose.Tasks ที่กำหนดวันและชั่วโมงทำงานสำหรับโครงการ มันมีผลโดยตรงต่อวันที่เริ่ม/สิ้นสุดของงาน, การจัดสรรทรัพยากร, และการคำนวณตารางเวลาโดยรวม โดยการปรับแต่งปฏิทิน คุณจะทำให้ตารางเวลาตรงตามข้อจำกัดในโลกจริง เช่น วันหยุดของบริษัทหรือแนวทางการทำงานในวันหยุดสุดสัปดาห์

## ทำไมต้องกำหนดวันทำงานสำหรับข้อยกเว้นของปฏิทิน?
การกำหนดข้อยกเว้นของวันทำงานทำให้เครื่องยนต์โครงการถือว่าวันเหล่านั้นเป็นวันไม่ทำงาน, ป้องกันไม่ให้งานถูกกำหนดเวลาโดยอัตโนมัติในวันเหล่านั้นและทำให้ไทม์ไลน์สอดคล้องกับข้อจำกัดในโลกจริง เช่น วันหยุด, ช่วงเวลาบำรุงรักษา, หรือรูปแบบกะพิเศษในองค์กร
- **Accurate timelines:** งานจะไม่ถูกวางในวันหยุดหรือช่วงเวลาปิดระบบ.  
- **Resource planning:** ทรัพยากรจะถูกจัดสรรเฉพาะในวันทำงานที่ถูกต้อง, ป้องกันการจัดสรรเกิน.  
- **Compliance:** ตารางเวลาจะปฏิบัติตามนโยบายขององค์กรหรือปฏิทินวันหยุดตามกฎหมายโดยอัตโนมัติ.  

## กำหนดวันไม่ทำงานด้วยข้อยกเว้นของปฏิทิน
เมื่อคุณดูแล **non‑working days schedule**, คุณมักจะมีรายการหลักของวันหยุด, ช่วงเวลาบำรุงรักษา, หรือช่วงเวลาปิดระบบอื่น ๆ การเพิ่มวันที่เหล่านั้นเป็นอ็อบเจ็กต์ `CalendarException` จะรับประกันว่าการคำนวณทุกอย่าง—ไม่ว่าจะเป็นการวิเคราะห์เส้นทางวิกฤติหรือการปรับระดับทรัพยากร—จะเคารพข้อจำกัดเหล่านั้นโดยอัตโนมัติ วิธีการนี้ช่วยขจัดการปรับวันที่ด้วยมือและลดความเสี่ยงของการเบี่ยงเบนของตารางเวลา

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดจาก [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans หรือเครื่องมือแก้ไขที่รองรับ Java.  

## วิธีกำหนดวันไม่ทำงานโดยใช้ข้อยกเว้นของปฏิทิน
โหลดโครงการของคุณ, สร้างปฏิทินแบบกำหนดเอง, และเพิ่มอ็อบเจ็กต์ `CalendarException` ที่ทำเครื่องหมายวันทำงานที่ต้องการเป็นวันไม่ทำงาน กระบวนการทั้งหมดนี้สามารถทำได้ในไม่กี่ขั้นตอนที่ง่ายดาย, และปฏิทินที่ได้จะมีผลต่อตรรกะการกำหนดเวลาของงานทั้งหมดโดยอัตโนมัติ.

### คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
เราต้องการคลาสหลักของ Aspose.Tasks และ `GregorianCalendar` ของ Java สำหรับการจัดการวันที่.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### ขั้นตอนที่ 2: กำหนดไดเรกทอรีข้อมูล
ระบุที่ตั้งที่ไฟล์โครงการที่สร้างขึ้นจะถูกบันทึก.

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 3: สร้างอินสแตนซ์ Project
`Project` คืออ็อบเจ็กต์หลักที่เก็บข้อมูลโครงการทั้งหมด, รวมถึงงาน, ทรัพยากร, และปฏิทิน.

```java
Project project = new Project();
```

### ขั้นตอนที่ 4: กำหนดปฏิทิน
`Calendar` แสดงตารางเวลาของช่วงเวลาทำงานและไม่ทำงานภายในโครงการ.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### ขั้นตอนที่ 5: กำหนดข้อยกเว้นวันทำงาน
`CalendarException` แสดงช่วงเวลาที่ทำเครื่องหมายว่าเป็นวันไม่ทำงานในปฏิทิน.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### ขั้นตอนที่ 6: บันทึกโครงการ
บันทึกโครงการรวมถึงปฏิทินแบบกำหนดเองและข้อยกเว้นของมันเป็นไฟล์ XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **Exception dates not applied** | ตรวจสอบ `setEnteredByOccurrences(false)` และค่าของ `FromDate/ToDate` ที่ถูกต้อง. |
| **Saved file is empty** | ยืนยันว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่สามารถเขียนได้และชื่อไฟล์ลงท้ายด้วย `.xml`. |
| **Calendar not reflected in task scheduling** | กำหนดปฏิทินให้กับงานหรือทรัพยากรโดยใช้ `task.setCalendar(cal)` หรือ `resource.setCalendar(cal)`. |

## คำถามที่พบบ่อย
**Q: Can I define multiple exceptions for different weekdays within the same calendar?**  
A: ใช่. เพิ่มอ็อบเจ็กต์ `CalendarException` ลงใน `cal.getExceptions()` สำหรับแต่ละช่วงหรือกฎที่แตกต่างกัน.

**Q: Is Aspose.Tasks for Java compatible with different Java IDEs?**  
A: แน่นอน. ไลบรารีนี้ทำงานร่วมกับ IntelliJ IDEA, Eclipse, NetBeans, และ IDE ใด ๆ ที่รองรับโครงการ Java มาตรฐาน.

**Q: Can I customize exception types other than daily exceptions?**  
A: ใช่. ใช้ `CalendarExceptionType.Weekly`, `Monthly`, หรือ `Yearly` เพื่อให้ตรงกับความต้องการการกำหนดเวลาของคุณ.

**Q: How can I handle exceptions dynamically based on project requirements?**  
A: สร้างอ็อบเจ็กต์ข้อยกเว้นโดยโปรแกรม—เช่น อ่านวันที่วันหยุดจากฐานข้อมูลหรือไฟล์กำหนดค่าและสร้างอินสแตนซ์ `CalendarException` ในลูป.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: ใช่, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีจาก [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้วิธี **schedule non working days** ด้วยการสร้างปฏิทินโครงการและกำหนดข้อยกเว้นของวันทำงานที่สะท้อนวันหยุดหรือช่วงเวลาที่ไม่ทำงานพิเศษอย่างแม่นยำ การกำหนดค่าปฏิทินอย่างเหมาะสมเป็นสิ่งสำคัญสำหรับตารางเวลาที่เป็นจริง, การจัดสรรทรัพยากร, และความสำเร็จของโครงการโดยรวม สำรวจต่อไปโดยการแนบปฏิทินแบบกำหนดเองให้กับงานหรือทรัพยากรและทดลองใช้ประเภทข้อยกเว้นอื่น ๆ เพื่อสร้าง **non‑working days schedule** ที่ครอบคลุมสำหรับโครงการใด ๆ

---

**อัปเดตล่าสุด:** 2026-07-29  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง
- [เพิ่มปฏิทินในโครงการด้วย Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [สร้างข้อยกเว้นของปฏิทิน Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)
- [วิธีตั้งค่าปฏิทินและกำหนดวันทำงานใน MS Project ด้วย Aspose.Tasks](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}