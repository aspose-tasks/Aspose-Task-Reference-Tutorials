---
date: 2026-08-08
description: เรียนรู้วิธีตั้งปฏิทิน ms project, กำหนดชั่วโมงทำงานต่อวัน, และเพิ่มวันทำงานในวันหยุดสุดสัปดาห์โดยใช้
  Aspose.Tasks สำหรับ Java. บันทึกโครงการเป็น XML ด้วยเพียงไม่กี่บรรทัดของโค้ด.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: วิธีตั้งปฏิทิน ms project และกำหนดวันทำงาน
og_description: ตั้งปฏิทิน ms project, กำหนดวันทำงาน, และเพิ่มวันทำงานในวันหยุดสุดสัปดาห์โดยใช้
  Aspose.Tasks สำหรับ Java. ทำตามบทแนะนำขั้นตอนต่อขั้นตอนนี้และบันทึกเป็น XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: ตั้งปฏิทิน ms project ด้วย Aspose.Tasks – คู่มือ Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: วิธีตั้งปฏิทิน ms project และกำหนดวันทำงาน
url: /th/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งปฏิทิน MS Project และกำหนดวันทำงาน

ในบทเรียนนี้คุณจะได้เรียนรู้ **how to set calendar ms project** แบบโปรแกรม, กำหนดวันทำงาน, และกำหนดวันทำงานแบบกำหนดเองโดยใช้ไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะสร้างเครื่องมือกำหนดเวลา, ผสานกับระบบ ERP, หรือเพียงต้องการสร้างแผนโครงการโดยไม่ต้องเปิด Microsoft Project, ขั้นตอนต่อไปนี้จะแสดงวิธีสร้างปฏิทิน, ตั้งชั่วโมงทำงานต่อวัน, และเพิ่มวันทำงานในวันหยุดสุดสัปดาห์ด้วยไม่กี่บรรทัดของโค้ด

## คำตอบสั้น
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Tasks for Java.  
- **ฉันสามารถเพิ่มวันทำงานในวันหยุดสุดสัปดาห์ได้หรือไม่?** ได้ – เพียงทำเครื่องหมายให้วันเสาร์และวันอาทิตย์เป็นวันทำงาน.  
- **ฉันจะบันทึกโปรเจกต์อย่างไร?** เรียก `prj.save(..., SaveFileFormat.Xml)`.  
- **ต้องการไลเซนส์หรือไม่?** สามารถใช้รุ่นทดลองฟรีเพื่อการประเมิน; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 หรือสูงกว่า.

## set calendar ms project คืออะไร?
การตั้งค่าปฏิทินใน MS Project กำหนดว่ามีวันใดบ้างที่ถือเป็นวันทำงาน, จำนวนชั่วโมงทำงานต่อวัน, และข้อยกเว้นพิเศษเช่นวันหยุดหรือการปิดทำการของบริษัท ข้อมูลนี้ใช้ในการกำหนดเวลา งาน, การจัดสรรทรัพยากร, และไทม์ไลน์ของโครงการทั้งหมด เพื่อให้การคำนวณสอดคล้องกับรูปแบบการทำงานจริงขององค์กร

## ทำไมต้องใช้ Aspose.Tasks สำหรับการจัดการปฏิทิน?
Aspose.Tasks ให้คุณควบคุมปฏิทินแบบโปรแกรมโดยไม่ต้องเปิด UI ของ Microsoft Project ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java, รองรับรูปแบบไฟล์เข้า‑ออกกว่า 50 รูปแบบ, และสามารถประมวลผลโครงการหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8+** – ดาวน์โหลดจาก [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – รับ JAR ล่าสุดจาก [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- IDE หรือเครื่องมือสร้าง (Maven/Gradle) เพื่อเพิ่ม Aspose.Tasks JAR ไปยัง classpath ของคุณ

## นำเข้าแพ็กเกจ
นำเข้าคลาสที่ให้การเข้าถึงโปรเจกต์, ปฏิทิน, และอ็อบเจ็กต์เวลาทำงาน

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: สร้างอินสแตนซ์ของโปรเจกต์
สร้างอ็อบเจ็กต์ `Project` ซึ่งเป็นตัวแทนไฟล์ MS Project ที่คุณจะจัดการ

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### ขั้นตอนที่ 2: กำหนดปฏิทินใหม่
`Calendar` แสดงชุดเวลาทำงาน, ข้อยกเว้น, และวันหยุดสำหรับโครงการ

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### ขั้นตอนที่ 3: เพิ่มวันทำงานมาตรฐาน (วันจันทร์‑วันพฤหัสบดี)
`WeekDay` กำหนดเวลาทำงานสำหรับวันเฉพาะของสัปดาห์

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### ขั้นตอนที่ 4: เพิ่มวันทำงานในวันหยุดสุดสัปดาห์
หากโครงการของคุณทำงานในวันหยุดสุดสัปดาห์, ให้เพิ่มวันเสาร์และวันอาทิตย์เป็นวันทำงานปกติ นี่เป็นการสาธิต **add weekend working days**

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### ขั้นตอนที่ 5: ตั้งค่าวันทำงานสั้นแบบกำหนดเอง (วันศุกร์)
กำหนดวันศุกร์ด้วยช่วงเช้า (9 am‑12 pm) และช่วงบ่าย (1 pm‑4 pm) เพื่อแสดง **set daily working hours** และวันทำงานสั้นแบบกำหนดเอง

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### ขั้นตอนที่ 6: บันทึกโปรเจกต์เป็น XML
`SaveFileFormat` ระบุรูปแบบไฟล์ที่รองรับเมื่อบันทึกโปรเจกต์, เช่น XML หรือ MPP

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## ปัญหาและวิธีแก้ไขทั่วไป
| ปัญหา | วิธีแก้ |
|-------|----------|
| **เวลาทำงานไม่ถูกนำไปใช้** | ตรวจสอบให้แน่ใจว่าได้เรียก `setDayWorking(true)` กับแต่ละ `WeekDay` ที่กำหนดเอง |
| **ไม่พบไฟล์ขณะบันทึก** | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน |
| **ปฏิทินไม่แสดงในงาน** | กำหนดปฏิทินที่สร้างใหม่ให้กับทรัพยากรหรืองานโดยใช้ `task.setCalendar(cal)` |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถกำหนดวันไม่ทำงานแบบกำหนดเองโดยใช้ Aspose.Tasks for Java ได้หรือไม่?**  
ตอบ: ได้. ตั้งค่า `DayWorking` เป็น `false` สำหรับ `WeekDay` ใด ๆ ที่ต้องการให้เป็นวันไม่ทำงาน

**ถาม: จะเพิ่มวันหยุดหรือข้อยกเว้นระดับบริษัทอย่างไร?**  
ตอบ: สร้างอ็อบเจ็กต์ `CalendarException`, ระบุวันที่ยกเว้น, แล้วเพิ่มลงใน `cal.getExceptions()`

**ถาม: ไลบรารีนี้เข้ากันได้กับเวอร์ชัน MS Project เก่า ๆ หรือไม่?**  
ตอบ: แน่นอน. Aspose.Tasks รองรับรูปแบบ MPP, MPT, และ XML ในหลายเวอร์ชันของ Project

**ถาม: ฉันสามารถแก้ไขปฏิทินที่มีอยู่ในโปรเจกต์ที่นำเข้าได้หรือไม่?**  
ตอบ: โหลดโปรเจกต์ด้วย `new Project("existing.mpp")`, ดึงปฏิทินที่ต้องการ, ทำการเปลี่ยนแปลง, แล้วบันทึก

**ถาม: Aspose.Tasks รองรับงานที่ทำซ้ำ (recurring tasks) หรือไม่?**  
ตอบ: ใช่, คุณสามารถสร้างและแก้ไขงานที่ทำซ้ำได้โดยใช้คลาส `RecurringTask`

## สรุป
คุณได้เรียนรู้ **how to set calendar ms project**, กำหนดวันทำงาน, เพิ่มวันทำงานในวันหยุดสุดสัปดาห์, และตั้งค่าวันศุกร์สั้น—all ด้วย Aspose.Tasks for Java. บันทึกผลลัพธ์เป็น XML และผสานตรรกะปฏิทินเข้ากับโซลูชันการจัดการโครงการที่พัฒนาด้วย Java ใด ๆ

---

**Last Updated:** 2026-08-08  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [เพิ่มปฏิทินลงในโปรเจกต์ด้วย Aspose.Tasks สำหรับ Java](/tasks/java/calendars/create/)
- [กำหนดวันทำงาน & ชั่วโมงทำงานด้วย Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [เพิ่มวันหยุดลงในปฏิทินและบันทึกเป็น MPP ด้วย Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}