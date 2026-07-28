---
date: 2026-01-28
description: เรียนรู้วิธีสร้างปฏิทินโครงการด้วย Aspose, กำหนดวันทำงานสำหรับข้อยกเว้นของปฏิทิน,
  และจัดการตารางวันหยุดโดยใช้ Aspose.Tasks สำหรับ Java.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: สร้างปฏิทินโครงการ Aspose – กำหนดวันทำงานสำหรับข้อยกเว้นของปฏิทิน
url: /th/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Project Calendar Aspose – กำหนดวันทำงานสำหรับข้อยกเว้นของปฏิทิน

### บทนำ
เมื่อคุณต้องการ **create project calendar aspose** คุณต้องสามารถจำลองวันทำงานที่ไม่เป็นมาตรฐาน เช่น วันหยุด, การทำงานพิเศษ, หรือการปิดชั่วคราว Aspose.Tasks for Java ให้การควบคุมเต็มรูปแบบในการกำหนดปฏิทิน ช่วยให้คุณเพิ่มข้อยกเว้นที่สะท้อนตารางเวลาจริง ในบทแนะนำนี้เราจะเดินผ่านขั้นตอนที่แน่นอนเพื่อกำหนดวันทำงานสำหรับข้อยกเว้นของปฏิทิน เพื่อให้ไทม์ไลน์ของโครงการของคุณแม่นยำและเชื่อถือได้ ในตอนท้ายคุณจะเห็นว่ามันสอดคล้องกับกลยุทธ์ **non‑working days schedule** สำหรับโครงการระดับองค์กรอย่างไร

## คำตอบด่วน
- **What does “create project calendar aspose” mean?**  
  หมายถึงการใช้ Aspose.Tasks เพื่อสร้างอ็อบเจกต์ปฏิทินแบบกำหนดเองที่ใช้ในการกำหนดการทำงานของงาน
- **Do I need a license to run the sample?**  
  การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง
- **Which IDEs are supported?**  
  IntelliJ IDEA, Eclipse, NetBeans หรือ IDE ใด ๆ ที่รองรับ Java 8+
- **Can I add multiple exceptions to the same calendar?**  
  ได้ – คุณสามารถเพิ่มอ็อบเจกต์ `CalendarException` ได้ตามต้องการ
- **What file formats can I save the project to?**  
  XML, MPP และรูปแบบอื่น ๆ ที่รองรับโดย Aspose.Tasks

## Project Calendar คืออะไรใน Aspose.Tasks?
A **project calendar** กำหนดวันและชั่วโมงทำงานสำหรับโครงการ มันมีผลต่อวันที่เริ่ม/สิ้นสุดของงาน, การจัดสรรทรัพยากร, และการคำนวณกำหนดการโดยรวม โดยการปรับแต่งปฏิทิน คุณจะทำให้กำหนดการเคารพข้อจำกัดในโลกจริง เช่น วันหยุดของบริษัทหรือนโยบายการทำงานในวันหยุดสุดสัปดาห์

## ทำไมต้องกำหนดวันทำงานสำหรับข้อยกเว้นของปฏิทิน?
- **Accurate timelines:** งานจะไม่ถูกกำหนดเวลาในวันที่ถูกทำเครื่องหมายว่าไม่ทำงาน
- **Resource planning:** ทรัพยากรจะถูกจัดสรรเฉพาะในวันทำงานที่เป็นไปได้
- **Compliance:** ทำให้กำหนดการโครงการสอดคล้องกับนโยบายขององค์กรหรือวันหยุดตามกฎหมาย

## ตารางวันหยุดไม่ทำงานกับข้อยกเว้นของปฏิทิน
เมื่อคุณดูแล **non‑working days schedule** คุณมักจะมีรายการหลักของวันหยุด, หน้าต่างการบำรุงรักษา, หรือช่วงเวลาที่ไม่ทำงานอื่น ๆ การเพิ่มวันที่เหล่านี้เป็นอ็อบเจกต์ `CalendarException` ทำให้การคำนวณทุกอย่าง—ไม่ว่าจะเป็นการวิเคราะห์เส้นทางวิกฤติหรือการปรับระดับทรัพยากร—อัตโนมัติเคารพข้อจำกัดเหล่านั้น วิธีนี้ช่วยขจัดการปรับวันที่ด้วยมือและลดความเสี่ยงของการเบี่ยงเบนกำหนดการ

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดจากหน้า [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) อย่างเป็นทางการ.  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans หรือเครื่องมือแก้ไขที่รองรับ Java

## วิธีสร้าง project calendar aspose – กำหนดวันทำงานสำหรับข้อยกเว้นของปฏิทิน

### คู่มือขั้นตอน

### ขั้นตอนที่ 1: นำเข้าชุดแพ็คเกจที่จำเป็น
เราต้องการคลาสหลักของ Aspose.Tasks และ `GregorianCalendar` ของ Java สำหรับการจัดการวันที่

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### ขั้นตอนที่ 2: กำหนดไดเรกทอรีข้อมูล
ระบุที่ตั้งที่ไฟล์โครงการที่สร้างขึ้นจะถูกบันทึก

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 3: สร้างอินสแตนซ์ Project
สร้างอ็อบเจกต์ `Project` ใหม่ – ซึ่งเป็นคอนเทนเนอร์สำหรับข้อมูลโครงการทั้งหมด รวมถึงปฏิทิน

```java
Project project = new Project();
```

### ขั้นตอนที่ 4: กำหนดปฏิทิน
เพิ่มปฏิทินแบบกำหนดเองไปยังโครงการ ปฏิทินนี้จะเก็บข้อยกเว้นของเรา

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### ขั้นตอนที่ 5: กำหนดข้อยกเว้นวันทำงาน
สร้าง `CalendarException` ที่ทำเครื่องหมายช่วงวัน (เช่น สัปดาห์สุดท้ายของเดือนธันวาคม) ว่าไม่ทำงาน  
ตัวอย่างตั้งค่าข้อยกเว้นตั้งแต่ **24 Dec 2009** ถึง **31 Dec 2009**, ปิดการทำงานในวันเหล่านั้น, และถือว่าข้อยกเว้นเป็นประเภทรายวัน

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
บันทึกโครงการรวมถึงปฏิทินแบบกำหนดเองและข้อยกเว้นของมันเป็นไฟล์ XML

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Solution |
|-------|----------|
| **Exception dates not applied** | ตรวจสอบว่าได้ตั้งค่า `setEnteredByOccurrences(false)` และค่าของ `FromDate/ToDate` ถูกต้อง |
| **Saved file is empty** | ยืนยันว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่สามารถเขียนได้และชื่อไฟล์ลงท้ายด้วย `.xml` |
| **Calendar not reflected in task scheduling** | กำหนดปฏิทินให้กับงานหรือทรัพยากรโดยใช้ `task.setCalendar(cal)` หรือ `resource.setCalendar(cal)` |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถกำหนดข้อยกเว้นหลายรายการสำหรับวันธรรมดาที่แตกต่างกันภายในปฏิทินเดียวกันได้หรือไม่**
ตอบ: ได้. ไม่สามารถอ็อบเจกต์ `CalendarException` สิ่งที่สำคัญใน `cal.getExceptions()` ขึ้นอยู่กับช่วงหรือกฎของร่างกาย

**ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java IDE ที่แตกต่างกันหรือไม่**
A: แน่นอน. ไลบรารี่กับ IntelliJ IDEA, Eclipse, NetBeans และ IDE ใด ๆ ที่เข้ากันได้กับโครงการ Java มาตรฐาน

**ถาม: ฉันสามารถปรับแต่งประเภทข้อยกเว้นนอกเหนือจากข้อยกเว้นรายวันได้หรือไม่**
ตอบ: ได้. ใช้ `CalendarExceptionType.Weekly`, `Monthly`, หรือ `Yearly` เพื่อความต้องการของระบบของคุณ

**ถาม: ฉันจะจัดการข้อยกเว้นแบบไดนามิกตามความต้องการของโปรเจ็กต์ได้อย่างไร**
ตอบ: สร้างอ็อบเจกต์โดยโปรแกรม—เช่นอ่านวันที่หยุดจากเทคโนโลยีหรือไฟล์ที่สามารถพบได้ `CalendarException` ในเทพเจ้ากรีก

**ถาม: มี Aspose.Tasks สำหรับ Java รุ่นทดลองใช้งานหรือไม่** 
A: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีจาก [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/)

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้วิธี **create project calendar aspose** และกำหนดข้อยกเว้นวันทำงานที่สะท้อนวันหยุดหรือช่วงเวลาที่ไม่ทำงานพิเศษอย่างแม่นยำ การกำหนดค่าปฏิทินที่เหมาะสมเป็นสิ่งสำคัญสำหรับกำหนดการที่เป็นจริง การจัดสรรทรัพยากร และความสำเร็จของโครงการโดยรวม สำรวจต่อไปโดยเชื่อมปฏิทินแบบกำหนดเองกับงานหรือทรัพยากรและทดลองใช้ประเภทข้อยกเว้นอื่น ๆ เพื่อสร้าง **non‑working days schedule** ที่ครอบคลุมสำหรับโครงการใด ๆ

---

**อัปเดตล่าสุด:** 2026-01-28  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}