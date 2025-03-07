---
title: กำหนดวันธรรมดาในปฏิทินด้วย Aspose.Tasks
linktitle: กำหนดวันธรรมดาในปฏิทินด้วย Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีกำหนดวันธรรมดาใน MS Project Calendar โดยใช้ Aspose.Tasks สำหรับ Java ปรับแต่งวันและเวลาทำงานได้อย่างง่ายดาย
weight: 12
url: /th/java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดวันธรรมดาในปฏิทินด้วย Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการกำหนดวันธรรมดาใน MS Project Calendar โดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project โดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ถ้าคุณยังไม่ได้
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/). ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์โปรเจ็กต์
สร้างอินสแตนซ์ของวัตถุ Project ซึ่งแสดงถึงไฟล์ MS Project ที่คุณจะใช้งาน:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## ขั้นตอนที่ 2: กำหนดปฏิทิน
สร้างอินสแตนซ์ปฏิทินใหม่และเพิ่มลงในโปรเจ็กต์:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## ขั้นตอนที่ 3: เพิ่มวันทำการ
กำหนดวันทำงานโดยเพิ่มวันจันทร์ถึงพฤหัสบดีด้วยการกำหนดเวลาเริ่มต้น:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## ขั้นตอนที่ 4: กำหนดวันทำงานที่กำหนดเอง
กำหนดวันเสาร์และวันอาทิตย์เป็นวันทำการ:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## ขั้นตอนที่ 5: กำหนดวันทำงานที่สั้น
กำหนดให้วันศุกร์เป็นวันทำงานสั้นโดยมีเวลาทำงานที่กำหนดเอง:
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
## ขั้นตอนที่ 6: บันทึกโครงการ
บันทึกโครงการที่แก้ไขลงในไฟล์ XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## บทสรุป
ยินดีด้วย! คุณได้กำหนดวันธรรมดาในปฏิทินโครงการ MS โดยใช้ Aspose.Tasks สำหรับ Java สำเร็จแล้ว ตอนนี้คุณสามารถรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ของคุณเพื่อจัดการไฟล์ MS Project โดยทางโปรแกรมได้
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถกำหนดวันที่ไม่ทำงานแบบกำหนดเองโดยใช้ Aspose.Tasks for Java ได้หรือไม่
 ตอบ: ได้ คุณสามารถกำหนดวันที่ไม่ทำงานแบบกำหนดเองได้โดยตั้งค่า`DayWorking` ทรัพย์สินเพื่อ`false` สำหรับวันธรรมดาตามลำดับ
### คำถามที่ 2: ฉันจะเพิ่มวันหยุดลงในปฏิทินได้อย่างไร
 ตอบ: คุณสามารถเพิ่มวันหยุดได้โดยการสร้างอินสแตนซ์ของ`CalendarExceptions`และระบุวันที่ไม่ทำงาน
### คำถามที่ 3: Aspose.Tasks เข้ากันได้กับไฟล์ MS Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์ MS Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP, MPT และ XML
### คำถามที่ 4: ฉันสามารถแก้ไขปฏิทินที่มีอยู่ในไฟล์ MS Project ได้หรือไม่
ตอบ: ได้ คุณสามารถโหลดโปรเจ็กต์ที่มีอยู่ด้วยปฏิทิน ทำการแก้ไข จากนั้นบันทึกการเปลี่ยนแปลงกลับไปยังไฟล์ต้นฉบับได้
### คำถามที่ 5: Aspose.Tasks ให้การสนับสนุนงานที่เกิดซ้ำหรือไม่
ตอบ: ได้ Aspose.Tasks ช่วยให้คุณสามารถทำงานกับงานที่เกิดซ้ำได้ รวมถึงการกำหนดรูปแบบและระยะเวลาของการเกิดซ้ำ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
