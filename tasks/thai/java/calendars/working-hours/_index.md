---
date: 2026-08-24
description: เรียนรู้วิธีเพิ่ม holidays calendar, กำหนด working days และคำนวณ task
  duration โดยการสกัด working hours จาก MS Project calendars ด้วย Aspose.Tasks for
  Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: วิธีเพิ่ม holidays calendar และกำหนด working days
og_description: เรียนรู้วิธีเพิ่ม holidays calendar, กำหนด working days และคำนวณ task
  duration โดยการสกัด working hours จาก MS Project calendars ด้วย Aspose.Tasks for
  Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: วิธีเพิ่ม holidays calendar และกำหนด working days
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: วิธีเพิ่ม holidays calendar และกำหนด working days
url: /th/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มปฏิทินวันหยุดและกำหนดวันทำงาน

การจัดการปฏิทินโครงการเป็นส่วนสำคัญของการวางแผนโครงการที่ประสบความสำเร็จ ในบทเรียนนี้คุณจะ **เพิ่มปฏิทินวันหยุด**, **กำหนดวันทำงาน** สำหรับงานใด ๆ, และ **ดึงชั่วโมงทำงาน** จากปฏิทิน MS Project โดยใช้ Aspose.Tasks for Java เมื่อจบคู่มือคุณจะสามารถ **คำนวณระยะเวลางาน**, ปรับแต่งชั่วโมงทำงาน, และโหลด **ไฟล์ MPP** เพื่อดึงข้อมูลที่ต้องการ—ทั้งหมดโดยไม่ต้องติดตั้ง Microsoft Project.

## คำตอบอย่างรวดเร็ว
- **“determine working days” หมายความว่าอะไร?** หมายถึงการระบุว่าข้อวันที่ในปฏิทินใดถือเป็นวันทำงานสำหรับงานที่กำหนด  
- **ควรใช้ไลบรารีใด?** Aspose.Tasks for Java มี API ที่ครบถ้วนสำหรับการทำงานกับไฟล์ MS Project.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** โดยทั่วไปใช้เวลาประมาณ 10–15 นาทีสำหรับการสกัดข้อมูลพื้นฐาน.  
- **ฉันต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองใช้ฟรี; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ฉันสามารถปรับแต่งชั่วโมงทำงานได้หรือไม่?** ได้ – คุณสามารถแก้ไขปฏิทิน, เพิ่มวันหยุด, และกำหนดช่วงเวลาทำงานที่กำหนดเอง.  

## “determine working days” คืออะไร?
**Determine working days** หมายถึงการสอบถามปฏิทินโครงการเพื่อค้นหาว่าวันที่ใดถูกทำเครื่องหมายว่าเป็นวันทำงานหรือไม่ทำงาน (วันหยุดสุดสัปดาห์, วันหยุด, หรือข้อยกเว้นที่กำหนดเอง) ข้อมูลนี้สำคัญสำหรับการ **calculate task duration** ที่แม่นยำ เนื่องจากเฉพาะวันทำงานเท่านั้นที่มีส่วนในการคำนวณระยะเวลาที่ผ่านไปของงาน

## ทำไมต้องใช้ Aspose.Tasks เพื่อดึงชั่วโมงทำงาน?
Aspose.Tasks ช่วยให้คุณอ่านไฟล์ MS Project ได้โดยไม่ต้องติดตั้ง Microsoft Project ทำให้สามารถทำอัตโนมัติบนแพลตฟอร์มใดก็ได้ นอกจากนี้ยังให้การประมวลผลที่มีประสิทธิภาพสูง, รองรับรูปแบบไฟล์หลายประเภท, และมีเอกสารประกอบที่ละเอียด  

- **Full calendar support** – ปฏิทินเริ่มต้น, ปฏิทินทรัพยากร, และปฏิทินงานทั้งหมดสามารถเข้าถึงได้.  
- **High performance** – สามารถประมวลผลโครงการที่มี **10,000+ งาน** ภายในเวลาไม่ถึง 2 วินาทีบน CPU มาตรฐาน 2.5 GHz.  
- **Extensive format coverage** – รองรับ **กว่า 50 รูปแบบการนำเข้าและส่งออก**, รวมถึง MPP, MPX, XML, และ Primavera.  
- **Comprehensive documentation** – ตัวอย่างโค้ด, เอกสารอ้างอิง API, และฟอรั่มชุมชน มีให้ใช้งานทั้งหมด.  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน, โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือสูงกว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. ความรู้พื้นฐานการเขียนโปรแกรม Java.  

## นำเข้าแพ็กเกจ
คลาส `Project` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Tasks ที่แทนไฟล์ MS Project หนึ่งไฟล์ในหน่วยความจำ นำเข้า namespace ที่จำเป็นก่อนเริ่มทำงาน:

นำเข้าแพ็กเกจ

```java
import com.aspose.tasks.*;
```

## วิธีโหลดไฟล์ MPP ด้วย Aspose.Tasks?
`Project` class โหลดไฟล์ MS Project และให้เข้าถึงข้อมูลของมัน โหลดไฟล์โครงการด้วยบรรทัดโค้ดเดียว; ไม่จำเป็นต้องใช้ UI หรือ COM interop ขั้นตอนที่ง่ายนี้ทำให้คุณเข้าถึงปฏิทิน, งาน, และทรัพยากรทั้งหมดได้อย่างเต็มที่

การโหลดไฟล์ MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## ดึงข้อมูลงานและปฏิทิน
`Task` แทนงานในโครงการ, และ `Calendar` กำหนดกฎเวลาทำงานของมัน เลือกงานที่ต้องการวิเคราะห์และดึงปฏิทินที่เชื่อมโยง `Task` อ็อบเจ็กต์มีเมธอด `getStart()` และ `getFinish()`, ส่วน `Calendar` เปิดเผยการกำหนดเวลาทำงาน

การดึงข้อมูลงานและปฏิทิน

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## กำหนดวันที่เริ่มต้นและสิ้นสุด
อ็อบเจ็กต์ `Date` ระบุช่วงเวลาสำหรับการวิเคราะห์ปฏิทิน ตั้งค่าช่วงเวลาที่คุณต้องการ **determine working days** การใช้วันที่เริ่มและสิ้นสุดของงานทำให้คุณประเมินเฉพาะช่วงที่เกี่ยวข้อง

การกำหนดวันที่

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## วนลูปผ่านวันที่
ลูป `for` สามารถวนผ่านแต่ละวันในช่วงวันที่ได้ วนลูปผ่านแต่ละวันที่อยู่ในระยะเวลาของงาน ลูปนี้จะทำให้คุณสามารถ **customize working hours** ในภายหลังหากต้องการและเป็นพื้นฐานสำหรับการคำนวณเวลาทำงานรวม

การวนลูปวันที่

```java
java.util.Calendar tempDate = calStartDate;
```

## คำนวณระยะเวลา
`Duration` รวมเวลาทำงานทั้งหมดที่คำนวณจากการวนลูป ในระหว่างการวนลูปคุณตรวจสอบว่าทุกวันเป็นวันทำงานหรือไม่, รวมชั่วโมงทำงาน, และสุดท้ายคำนวณระยะเวลาของงานเป็นนาที, ชั่วโมง, และวัน ซึ่งแสดงวิธี **calculate working days** และ **calculate task duration** อย่างโปรแกรม

การคำนวณระยะเวลา

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## วิธีปรับแต่งชั่วโมงทำงานและวันหยุด
คุณสามารถแก้ไขช่วงเวลาทำงานของปฏิทินและเพิ่มข้อยกเว้นเช่นวันหยุด ใช้ `taskCalendar.addWorkingTime()` เพื่อตั้งช่วงเวลาทำงานใหม่และ `taskCalendar.addException()` เพื่อใส่วันหยุด นี่เป็นประโยชน์เมื่อตารางเวลา 9‑5 เริ่มต้นไม่สอดคล้องกับนโยบายขององค์กรของคุณ

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **Task คืนค่า `null` สำหรับ calendar** | ตรวจสอบให้แน่ใจว่างานมีการกำหนด calendar จริง ๆ; หากไม่มีก็จะสืบทอด calendar เริ่มต้นของโครงการ. |
| **ระยะเวลาไม่ถูกต้องเนื่องจากวันหยุด** | ตรวจสอบว่ามีการกำหนดวันหยุดใน calendar ของงานหรือใน calendar พื้นฐานของโครงการ. |
| **ความไม่ตรงกันของโซนเวลา** | ใช้ `java.util.TimeZone` เพื่อปรับโซนเวลาของ calendar ให้ตรงกับระบบของคุณหากจำเป็น. |

## คำถามที่พบบ่อย
### Q: Aspose.Tasks for Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?
A: ใช่, Aspose.Tasks for Java มีการสนับสนุนอย่างครบถ้วนสำหรับการจัดการโครงสร้างโครงการที่ซับซ้อน รวมถึงงาน, ทรัพยากร, และปฏิทิน

### Q: Aspose.Tasks for Java เข้ากันได้กับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?
A: แน่นอน, Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของ MS Project, ทำให้เข้ากันได้ในสภาพแวดล้อมที่หลากหลาย

### Q: ฉันสามารถปรับแต่งชั่วโมงทำงานและวันหยุดในปฏิทินโครงการได้หรือไม่?
A: ได้, คุณสามารถปรับแต่งชั่วโมงทำงานและวันหยุดตามความต้องการของโครงการของคุณได้อย่างง่ายดายโดยใช้ Aspose.Tasks for Java APIs.

### Q: Aspose.Tasks for Java มีการสนับสนุนและเอกสารประกอบหรือไม่?
A: มี, Aspose.Tasks for Java มีเอกสารประกอบอย่างละเอียดและฟอรั่มสนับสนุนเฉพาะเพื่อช่วยนักพัฒนาใช้คุณลักษณะต่าง ๆ อย่างมีประสิทธิภาพ

### Q: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for Java หรือไม่?
A: มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีของ Aspose.Tasks for Java ได้จาก [Aspose releases page](https://releases.aspose.com/).

## สรุป
ในคู่มือนี้เราได้สาธิตวิธี **add holidays calendar**, **determine working days**, **retrieve working hours**, และ **calculate task duration** จากปฏิทิน MS Project ด้วย Aspose.Tasks for Java โดยทำตามขั้นตอนข้างต้นคุณสามารถทำอัตโนมัติการวิเคราะห์กำหนดเวลา, ปรับแต่งปฏิทิน, และทำให้แผนโครงการของคุณแม่นยำและเป็นปัจจุบัน คุณมีเครื่องมือเพื่อ **read MS Project** ข้อมูล, **load an MPP file**, และทำการคำนวณระยะเวลาอย่างแม่นยำโดยไม่ต้องใช้ Microsoft Project

---

**อัปเดตล่าสุด:** 2026-08-24  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มปฏิทินในโครงการด้วย Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [เพิ่มวันหยุดในปฏิทินและบันทึกเป็น MPP ด้วย Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [สร้างข้อยกเว้นปฏิทินแบบกำหนดเองด้วย Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}