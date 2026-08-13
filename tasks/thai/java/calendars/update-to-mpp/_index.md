---
date: 2026-08-13
description: เรียนรู้วิธีเพิ่มวันหยุดในปฏิทิน, กำหนดปฏิทินให้กับโครงการ, และบันทึกไฟล์
  MS Project เป็น MPP ด้วย Aspose.Tasks for Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: อัปเดตปฏิทินเป็นรูปแบบ MPP ใน Aspose.Tasks
og_description: เพิ่มวันหยุดในปฏิทิน, กำหนดให้กับโครงการ, และแปลงกำหนดการเป็น MPP
  ด้วย Aspose.Tasks for Java. เรียนรู้การทำงานอัตโนมัติแบบขั้นตอนต่อขั้นตอน.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: เพิ่มวันหยุดในปฏิทินและบันทึกเป็น MPP ด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: เพิ่มวันหยุดในปฏิทินและบันทึกเป็น MPP ด้วย Aspose.Tasks
url: /th/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มวันหยุดลงในปฏิทินและบันทึกเป็น MPP ด้วย Aspose.Tasks

## บทนำ

ในการจัดการโครงการสมัยใหม่ คุณมักต้อง **เพิ่มวันหยุดลงในปฏิทิน** ไฟล์, สร้าง **ปฏิทิน MS Project**, และจากนั้นแชร์กำหนดการในรูปแบบ MPP ดั้งเดิม ไม่ว่าคุณจะรวมไทม์ไลน์จากหลายแหล่งหรือย้ายข้อมูลเก่า การสร้างปฏิทินโดยอัตโนมัติช่วยขจัดข้อผิดพลาดจากการทำมือและเร่งความเร็วในการส่งมอบ บทเรียนนี้จะพาคุณผ่านกระบวนการทั้งหมดของการสร้างปฏิทินใน MS Project, ปรับแต่งด้วยวันหยุด, **กำหนดปฏิทินให้กับโครงการ**, และสุดท้าย **แปลงโครงการเป็น MPP** โดยใช้ Aspose.Tasks Java API.

## คำตอบสั้น
- **บทเรียนนี้ครอบคลุมอะไร?** การเพิ่มวันหยุดลงในปฏิทิน, การกำหนดให้กับโครงการ, และการบันทึกผลลัพธ์เป็นไฟล์ MPP ด้วย Aspose.Tasks สำหรับ Java.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้งานฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า (JDK 8+).  
- **ฉันสามารถปรับแต่งปฏิทินได้หรือไม่?** ได้ – คุณสามารถเพิ่มเวลาทำงาน, ข้อยกเว้น, และวันหยุด.  
- **การดำเนินการใช้เวลานานเท่าใด?** ประมาณ 10‑15 นาทีสำหรับปฏิทินพื้นฐาน.  

## อะไรคือ “create calendar MS Project”?
การสร้างปฏิทิน MS Project หมายถึงการกำหนดวันทำงาน, ชั่วโมงทำงาน, และข้อยกเว้นที่ใช้ในการกำหนดตารางงานของงานภายในไฟล์ Microsoft Project. ด้วย Aspose.Tasks คุณสามารถสร้างปฏิทินนี้โดยอัตโนมัติ, ตั้งค่าวันหยุด, และฝังลงในโครงการโดยไม่ต้องเปิด UI ของ MS Project.

## ทำไมต้องใช้ Aspose.Tasks สำหรับงานนี้?
คุณควรใช้ Aspose.Tasks เพราะให้ความเข้ากันได้เต็มรูปแบบกับ Java, ไม่ต้องใช้ Microsoft Office, และทำให้คุณสามารถสร้างและบันทึกไฟล์ MPP ดั้งเดิมโดยตรงจากโค้ด. ไลบรารีนี้รองรับคุณสมบัติของปฏิทินทั้งหมด, ทำงานบนสภาพแวดล้อมเซิร์ฟเวอร์ใดก็ได้, และประมวลผลโครงการที่มีงานสูงสุด 10,000 งานในเวลาไม่ถึงหนึ่งวินาที.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK) 8+** – ตรวจสอบให้แน่ใจว่า `java -version` แสดงผลเป็น 1.8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขใด ๆ ที่คุณต้องการ.  
4. **Basic Java knowledge** – ความคุ้นเคยกับคลาส, เมธอด, และการทำ I/O ของไฟล์.  

## วิธีเพิ่มวันหยุดลงในปฏิทิน
เพื่อเพิ่มวันหยุด คุณสร้างอ็อบเจ็กต์ `Calendar` ใหม่, ดึงคอลเลกชัน `Exceptions` ของมัน, และเพิ่มรายการ `DateException` สำหรับแต่ละวันที่เป็นวันหยุด. `DateException` แสดงถึงวันที่หรือช่วงวันที่ไม่ทำงานในปฏิทิน. Aspose.Tasks จะถือว่าวันเหล่านั้นเป็นวันไม่ทำงาน, ทำให้แน่ใจว่างานจะถูกกำหนดตามวันหยุดที่กำหนด.

### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
First, bring the Aspose.Tasks classes and Java utilities into scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### ขั้นตอนที่ 2: ตั้งค่าไดเรกทอรีข้อมูล
Define where your input template and output files will live. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 3: กำหนดชื่อไฟล์อินพุตและเอาต์พุต
We’ll load an existing MPP file (or a blank project) and write the result to a new file.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### ขั้นตอนที่ 4: โหลดโครงการและเพิ่มปฏิทินใหม่
`Project` class represents an MS Project file in memory and provides access to its calendars, tasks, and resources.

Create a `Project` instance from the source file and add a calendar named **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### ขั้นตอนที่ 5: ปรับแต่งปฏิทิน (ไม่บังคับ)
`Calendar` object defines working days, hours, and exceptions for a project schedule.

If you need specific working times, holidays, or exceptions, call your own helper method. The sample uses `GetTestCalendar` as a placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **เคล็ดลับ:** คุณสามารถจัดการ `cal1.getWeekDays()` โดยตรงเพื่อกำหนดชั่วโมงทำงานสำหรับแต่ละวันของสัปดาห์, หรือใช้ `cal1.getExceptions()` เพื่อ **เพิ่มวันหยุดลงในปฏิทิน**.

### ขั้นตอนที่ 6: กำหนดปฏิทินให้กับโครงการ
Tell the project to use the newly created calendar for all its scheduling calculations.

```java
project.set(Prj.CALENDAR, cal1);
```

### ขั้นตอนที่ 7: บันทึกโครงการเป็น MPP
`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating native Microsoft Project format.

Now **แปลงโครงการเป็น MPP** by saving it with the `SaveFileFormat.Mpp` option.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### ขั้นตอนที่ 8: ยืนยันการทำงานสำเร็จ
A simple console message lets you know the process finished without errors.

```java
System.out.println("Process completed Successfully");
```

## กรณีการใช้งานทั่วไป
- **การสร้างกำหนดการอัตโนมัติ** สำหรับโครงการที่ทำซ้ำ (เช่น สปรินท์รายสัปดาห์).  
- **การย้ายปฏิทิน CSV หรือ Excel เก่า** ไปยังไฟล์ MS Project ที่มีคุณสมบัติครบถ้วน.  
- **การรายงานฝั่งเซิร์ฟเวอร์** ที่บริการเว็บส่งคืนไฟล์ MPP ตามความต้องการ.  

## การแก้ไขปัญหาและข้อผิดพลาดทั่วไป
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่หรือสร้างขึ้นโดยโปรแกรม |
| ปฏิทินไม่ได้ถูกใช้กับงาน | งานยังอ้างอิงปฏิทินเริ่มต้น | หลังจากตั้งค่า `Prj.CALENDAR`, ให้ปรับปรุง `Task.CALENDAR` ของแต่ละงานด้วยหากเคยถูกแทนที่ก่อนหน้า |
| ไฟล์เอาต์พุตมีขนาด 0 KB | ไม่มีสิทธิ์เขียน | รัน JVM ด้วยสิทธิ์ระบบไฟล์ที่เหมาะสมหรือเลือกเส้นทางที่สามารถเขียนได้ |

## คำถามที่พบบ่อย
**Q: Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?**  
A: ใช่, Aspose.Tasks รองรับรูปแบบไฟล์ Microsoft Project ทั้งหมดตั้งแต่ Project 2007 ถึง Project 2024, ครอบคลุมมากกว่า 10 เวอร์ชัน.

**Q: ฉันสามารถปรับแต่งปฏิทินตามความต้องการเฉพาะของโครงการได้หรือไม่?**  
A: แน่นอน. คุณสามารถกำหนดวันทำงาน, ตั้งสัปดาห์ทำงานแบบกำหนดเอง, เพิ่มวันหยุด, และแม้กระทั่งสร้างหลายปฏิทินภายในไฟล์โครงการเดียว.

**Q: Aspose.Tasks for Java มีการสนับสนุนการแก้ไขปัญหาและความช่วยเหลือหรือไม่?**  
A: มี, คุณสามารถรับความช่วยเหลือจากฟอรั่มชุมชน Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: มี, การทดลองใช้ฟรีที่ทำงานเต็มรูปแบบพร้อมให้ใช้งาน [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks for Java ได้อย่างไร?**  
A: สามารถขอไลเซนส์ชั่วคราวผ่านเว็บไซต์ Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

**อัปเดตล่าสุด:** 2026-08-13  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง
- [เพิ่มปฏิทินลงในโครงการด้วย Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [วิธีกำหนดวันทำงานในปฏิทิน MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [สร้างข้อยกเว้นปฏิทินแบบกำหนดเองด้วย Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}