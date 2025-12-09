---
date: 2025-12-02
description: เรียนรู้วิธีตั้งปฏิทิน, กำหนดวันทำงานใน MS Project และตั้งค่าวันทำงานแบบกำหนดเองโดยใช้
  Aspose.Tasks สำหรับ Java. บันทึกโครงการเป็น XML ด้วยเพียงไม่กี่บรรทัดของโค้ด.
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีตั้งปฏิทินและกำหนดวันทำงานใน MS Project ด้วย Aspose.Tasks
url: /th/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งปฏิทินและกำหนดวันทำงานใน MS Project ด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีตั้งปฏิทิน** อย่างโปรแกรมและกำหนดวันทำงานในไฟล์ Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะต้องการสร้างสัปดาห์ทำงานมาตรฐาน, เพิ่มวันทำงานในวันหยุดสุดสัปดาห์, หรือกำหนดตารางทำงานสั้นสำหรับวันศุกร์ คู่มือนี้จะพาคุณผ่านทุกขั้นตอน ตั้งแต่การสร้างโครงการจนถึงการบันทึกไฟล์เป็น XML.

## คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks for Java  
- **ฉันสามารถเพิ่มวันทำงานในวันหยุดสุดสัปดาห์ได้หรือไม่?** ได้ – เพียงเพิ่มวันเสาร์และวันอาทิตย์เป็นวันทำงาน.  
- **ฉันบันทึกโครงการอย่างไร?** ใช้ `prj.save(..., SaveFileFormat.Xml)`.  
- **ฉันต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า.

## อะไรคือ “วิธีตั้งปฏิทิน” ในบริบทของ MS Project?
การตั้งปฏิทินใน MS Project หมายถึงการกำหนดว่าวันใดเป็นวันทำงาน, ชั่วโมงทำงานต่อวัน, และข้อยกเว้นใด ๆ เช่น วันหยุด ปฏิทินนี้เป็นตัวกำหนดการจัดตารางงาน, การจัดสรรทรัพยากร, และไทม์ไลน์ของโครงการโดยรวม.

## ทำไมต้องใช้ Aspose.Tasks สำหรับการจัดการปฏิทิน?
- **การควบคุมเต็มรูปแบบ** – สร้าง, แก้ไข หรือ ลบปฏิทินโดยใช้โปรแกรมโดยไม่ต้องเปิด UI.  
- **ข้ามแพลตฟอร์ม** – ทำงานบนระบบปฏิบัติการใด ๆ ที่รองรับ Java.  
- **รองรับทุกรูปแบบไฟล์** – MPP, MPT, และ XML, ดังนั้นคุณสามารถ *save project as XML* เพื่อการรวมระบบกับระบบอื่นได้ง่าย.  
- **ไม่มีการพึ่งพา COM** – แตกต่างจากไลบรารี Microsoft Project Interop.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK) 8+** – ดาวน์โหลดจาก [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – รับไฟล์ JAR ล่าสุดจาก [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. IDE หรือเครื่องมือ build (Maven/Gradle) เพื่อเพิ่ม Aspose.Tasks JAR เข้าไปใน classpath ของโปรเจคของคุณ.

## นำเข้าแพคเกจ
แรกสุด, นำเข้าคลาสที่คุณต้องการใช้ การนำเข้าเหล่านี้ทำให้คุณเข้าถึงวัตถุ project, calendar, และ working‑time ได้.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: สร้างอินสแตนซ์ Project
สร้างอ็อบเจ็กต์ `Project` ใหม่ อ็อบเจ็กต์นี้แทนไฟล์ MS Project ที่คุณจะทำการแก้ไข.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### ขั้นตอนที่ 2: กำหนดปฏิทินใหม่
เพิ่มปฏิทินใหม่เข้าไปในโปรเจค การตั้งชื่อที่ชัดเจนช่วยเมื่อคุณมีหลายปฏิทิน.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### ขั้นตอนที่ 3: เพิ่มวันทำงานมาตรฐาน (จันทร์‑พฤหัสบดี)
ใช้ตัวช่วยในตัว `WeekDay.createDefaultWorkingDay` เพื่อกำหนดตารางเวลาเริ่มต้น 9 am‑5 pm สำหรับสัปดาห์ทำงานหลัก.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### ขั้นตอนที่ 4: เพิ่มวันทำงานในวันหยุดสุดสัปดาห์
หากโครงการของคุณทำงานในวันหยุดสุดสัปดาห์ เพียงเพิ่มวันเสาร์และวันอาทิตย์เป็นวันทำงานปกติ นี้เป็นการสาธิต **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### ขั้นตอนที่ 5: ตั้งวันทำงานสั้นแบบกำหนดเอง (วันศุกร์)
ที่นี่เราจะ **set custom working days** สำหรับวันศุกร์: ช่วงเช้า (9 am‑12 pm) และช่วงบ่าย (1 pm‑4 pm).

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

### ขั้นตอนที่ 6: บันทึกโครงการเป็น XML
สุดท้าย, บันทึกการเปลี่ยนแปลง ตัวเลือก `SaveFileFormat.Xml` ทำให้คุณ **save project as XML**, ซึ่งเป็นประโยชน์สำหรับการรวมกับเครื่องมืออื่น.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## ปัญหาทั่วไป & วิธีแก้

| ปัญหา | วิธีแก้ |
|-------|----------|
| **เวลาทำงานไม่ถูกนำไปใช้** | ตรวจสอบว่าได้เรียก `setDayWorking(true)` บน `WeekDay` ที่กำหนดเอง. |
| **ไม่พบไฟล์ขณะบันทึก** | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และแอปพลิเคชันของคุณมีสิทธิ์เขียน. |
| **ปฏิทินไม่แสดงในงาน** | กำหนดปฏิทินที่สร้างใหม่ให้กับทรัพยากรหรืองานโดยใช้ `task.setCalendar(cal)`. |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถกำหนดวันไม่ทำงานแบบกำหนดเองโดยใช้ Aspose.Tasks for Java ได้หรือไม่?**  
**ตอบ:** ใช่. ตั้งค่า `DayWorking` เป็น `false` สำหรับ `WeekDay` ใด ๆ ที่คุณต้องการให้เป็นวันไม่ทำงาน.

**ถาม: ฉันจะเพิ่มวันหยุดหรือข้อยกเว้นระดับบริษัทได้อย่างไร?**  
**ตอบ:** สร้างอ็อบเจ็กต์ `CalendarException`, ระบุวันที่ยกเว้น, แล้วเพิ่มเข้าไปใน `cal.getExceptions()`.

**ถาม: ไลบรารีนี้เข้ากันได้กับเวอร์ชัน MS Project เก่าไหม?**  
**ตอบ:** แน่นอน. Aspose.Tasks รองรับรูปแบบ MPP, MPT, และ XML ในหลายเวอร์ชันของ Project.

**ถาม: ฉันสามารถแก้ไขปฏิทินที่มีอยู่ในโครงการที่นำเข้าได้หรือไม่?**  
**ตอบ:** โหลดโครงการด้วย `new Project("existing.mpp")`, ดึงปฏิทินที่ต้องการ, ทำการเปลี่ยนแปลง, แล้วบันทึก.

**ถาม: Aspose.Tasks รองรับงานที่ทำซ้ำ (recurring tasks) หรือไม่?**  
**ตอบ:** ใช่, คุณสามารถสร้างและแก้ไขงานที่ทำซ้ำโดยใช้คลาส `RecurringTask`.

## สรุป
คุณได้เรียนรู้ **วิธีตั้งปฏิทิน** การตั้งค่า, **กำหนดวันทำงานใน MS Project**, เพิ่มวันทำงานในวันหยุดสุดสัปดาห์, และสร้างตารางวันศุกร์สั้น—all ด้วย Aspose.Tasks for Java. บันทึกผลลัพธ์เป็น XML และรวมตรรกะปฏิทินเข้าไปในโซลูชันการจัดการโครงการที่ใช้ Java ใด ๆ.

---

**อัปเดตล่าสุด:** 2025-12-02  
**ทดสอบกับ:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}