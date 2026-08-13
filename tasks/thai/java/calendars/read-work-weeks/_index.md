---
date: 2026-08-13
description: เรียนรู้วิธีอ่าน workweeks จากปฏิทิน MS Project ด้วย Aspose.Tasks สำหรับ
  Java ทำตามคำแนะนำขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ดและเคล็ดลับการแก้ไขปัญหา
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: อ่าน Work Weeks จากปฏิทินด้วย Aspose.Tasks
og_description: วิธีอ่าน workweeks จากปฏิทิน MS Project ด้วย Aspose.Tasks สำหรับ Java
  ทำตามบทแนะนำสั้น ๆ พร้อมขั้นตอนการตั้งค่า ตัวอย่างโค้ด และเคล็ดลับการแก้ไขปัญหา
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: วิธีอ่าน workweeks จากปฏิทิน MS ด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: วิธีอ่าน workweeks จากปฏิทิน MS ด้วย Aspose.Tasks
url: /th/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านสัปดาห์ทำงานจากปฏิทิน MS ด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะ **เรียนรู้วิธีอ่านสัปดาห์ทำงาน** จากปฏิทิน Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะสร้างแดชบอร์ดรายงาน, ซิงโครไนซ์ตารางเวลากับระบบ ERP, หรืออัตโนมัติการดึงข้อมูลเพื่อการวิเคราะห์ การเข้าถึงคำนิยามสัปดาห์ทำงานแบบโปรแกรมช่วยประหยัดชั่วโมงทำงานด้วยมือเป็นจำนวนมาก Aspose.Tasks รองรับ **50+ รูปแบบการนำเข้าและส่งออก** และสามารถประมวลผลไฟล์โครงการหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้คุณได้ทั้งความยืดหยุ่นและประสิทธิภาพ

## คำตอบอย่างรวดเร็ว
- **What does “read workweeks” mean?** หมายถึงการสกัดคำนิยามสัปดาห์ทำงาน (วันที่และกฎเวลาทำงานประจำวัน) จากไฟล์ Project ผ่านโค้ด Java.  
- **Which library is required?** Aspose.Tasks for Java (free trial available) (**มีให้ทดลองใช้งานฟรี**).  
- **Do I need a license for development?** การทดลองใช้งานทำงานสำหรับการทดสอบ; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมจริง.  
- **What file formats are supported?** รองรับไฟล์ *.mpp* และไฟล์ Project XML รวมถึงรูปแบบอื่น ๆ มากกว่า 50 รูปแบบสำหรับการนำเข้า/ส่งออก.  
- **How long does the implementation take?** โดยทั่วไปใช้เวลาน้อยกว่า 10 นาทีเมื่อไลบรารีถูกตั้งค่าเรียบร้อยแล้ว.

## สัปดาห์ทำงานคืออะไรใน MS Project?
สัปดาห์ทำงานกำหนดกฎปฏิทินที่บ่งบอกว่าแหล่งทรัพยากรพร้อมทำงานในช่วงเวลาใดบ้างในช่วงระยะเวลาที่กำหนด ประกอบด้วยวันที่เริ่มต้น, วันที่สิ้นสุด, และช่วงเวลาทำงานประจำวัน (เช่น 9 am–5 pm). ใน MS Project แต่ละปฏิทินสามารถมีสัปดาห์ทำงานหลายสัปดาห์ได้, ทำให้คุณสามารถจำลองวันหยุด, รูปแบบกะงาน, หรือกำหนดการตามฤดูกาลได้.

## Aspose.Tasks อ่านสัปดาห์ทำงานจากปฏิทินอย่างไร?
Aspose.Tasks เปิดเผย `WorkWeekCollection` ของอ็อบเจ็กต์ `Calendar`. โดยการสร้างอินสแตนซ์ `Project`, เลือกปฏิทินที่ต้องการ (โดย UID หรือชื่อ), และวนลูปผ่าน `WorkWeekCollection` ของมัน, คุณสามารถดึงข้อมูลป้ายชื่อสัปดาห์ทำงาน, ช่วงวันที่มีผลบังคับใช้, และช่วงเวลาทำงานประจำวันโดยละเอียดได้. API จะจัดการการแปลงวันที่‑เวลาและเคารพการตั้งค่าโซนเวลาของโครงการโดยอัตโนมัติ.

## ทำไมต้องอ่านสัปดาห์ทำงานด้วย Java จากปฏิทิน Microsoft Project?
การอ่านสัปดาห์ทำงานแบบโปรแกรมช่วยขจัดการคัดลอก‑วางด้วยมือ, ทำให้ระบบ downstream (ERP, HR, รายงาน) ใช้กฎการจัดตารางเวลาเดียวกันอย่างแม่นยำ, และรับประกันความสอดคล้องระหว่างหลายโครงการ. การอัตโนมัติยังลดข้อผิดพลาดของมนุษย์และเร่งกระบวนการรวมระบบ, โดยเฉพาะเมื่อคุณต้องประมวลผลโครงการหลายสิบไฟล์ทุกคืน.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่าได้ถูกติดตั้ง.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจากเว็บไซต์อย่างเป็นทางการ: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **sample Project file** (`ReadWorkWeeksInformation.mpp`) ที่วางไว้ในโฟลเดอร์ที่รู้จักบนเครื่องของคุณ.

## นำเข้าแพ็กเกจ
ก่อนอื่น, ให้นำเข้าคลาสที่เราต้องใช้เพื่อโต้ตอบกับปฏิทินและสัปดาห์ทำงาน:

`Project` แทนไฟล์ Microsoft Project, `Calendar` ให้ข้อมูลปฏิทิน, `WorkWeek` นิยามสัปดาห์ทำงาน, และ `WeekDay` แทนวันหนึ่งวัน.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์ข้อมูลของคุณ
กำหนดโฟลเดอร์ที่บรรจุไฟล์ `.mpp`. แทนที่ตัวแปรตำแหน่งที่เก็บด้วยพาธจริงบนเครื่องของคุณ:

```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ Project และเข้าถึงปฏิทิน
คลาส `Project` แทนไฟล์ Microsoft Project และให้การเข้าถึงโครงสร้างข้อมูลต่าง ๆ รวมถึงปฏิทิน, งาน, และทรัพยากร.  
สร้างอ็อบเจ็กต์ `Project`, เลือกปฏิทินที่ต้องการ (โดย UID), และรับ `WorkWeekCollection` ของมัน:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** หากคุณไม่แน่ใจเกี่ยวกับ UID ของปฏิทิน, ให้วนลูปผ่าน `project.getCalendars()` และพิมพ์ชื่อและ UID ของแต่ละปฏิทินก่อน.

## ขั้นตอนที่ 3: วนลูปผ่านสัปดาห์ทำงาน
คลาส `WorkWeek` รวมคำนิยามสัปดาห์ทำงาน, มีวันที่เริ่ม/สิ้นสุดและการตั้งค่าชั่วโมงทำงานประจำวัน.  
วนลูปผ่านแต่ละ `WorkWeek` เพื่อแสดงชื่อ, วันที่เริ่ม/สิ้นสุด, และชั่วโมงทำงานประจำวัน:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**สิ่งที่คุณจะเห็น:** คอนโซลจะแสดงป้ายชื่อของแต่ละสัปดาห์ทำงาน (เช่น “Standard”), ช่วงวันที่มีผลบังคับใช้, และคุณสามารถเจาะลึกไปยังชั่วโมงทำงานที่แน่นอนสำหรับแต่ละวันได้.

## ปัญหาทั่วไปและวิธีแก้
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | Wrong UID or calendar does not exist | Verify the UID with `project.getCalendars().size()` and list available calendars first. |
| No output for work weeks | The selected calendar has no custom work weeks (uses default) | Use the default calendar (`project.getDefaultCalendar()`) or create a work week programmatically. |
| Date format looks odd | `System.out.println` uses default `java.util.Date` format | Apply a `SimpleDateFormat` to format dates as needed. |

## คำถามที่พบบ่อย
**Q: Can I modify the work weeks information using Aspose.Tasks for Java?**  
A: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property setters to change names, dates, and working times.

**Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?**  
A: Absolutely. It supports MPP files from Project 98 up to the latest releases, as well as Project XML files.

**Q: Can I integrate Aspose.Tasks with other Java frameworks?**  
A: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta EE, or any other framework.

**Q: Is there a trial version available for Aspose.Tasks?**  
A: Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**อัปเดตล่าสุด:** 2026-08-13  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มปฏิทินลงในโครงการด้วย Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [ดึงข้อยกเว้นของปฏิทินด้วย Aspose.Tasks – บทแนะนำ asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [วิธีตั้งค่าปฏิทินและกำหนดวันทำงานใน MS Projectด้วย Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}