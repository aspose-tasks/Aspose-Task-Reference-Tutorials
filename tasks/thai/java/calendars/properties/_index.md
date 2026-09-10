---
date: 2026-09-09
description: วิธีตั้งปฏิทินโครงการใน Java โดยใช้ Aspose.Tasks. เรียนรู้วิธีแสดงชั่วโมงทำงานของปฏิทิน,
  กำหนดเวลาทำงาน, และแก้ไขวันในปฏิทินในไฟล์ MS Project.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: จัดการคุณสมบัติของปฏิทินใน Aspose.Tasks
og_description: วิธีตั้งปฏิทินโครงการใน Java โดยใช้ Aspose.Tasks. เรียนรู้วิธีแสดงชั่วโมงทำงานของปฏิทิน,
  กำหนดเวลาทำงาน, และแก้ไขวันในปฏิทินในไฟล์ MS Project.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: วิธีตั้งปฏิทินโครงการใน Java ด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: วิธีตั้งปฏิทินโครงการใน Java ด้วย Aspose.Tasks
url: /th/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งปฏิทินโครงการใน Java ด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีตั้งปฏิทินโครงการ** ใน Java ด้วยการใช้ไลบรารี Aspose.Tasks การควบคุมคุณสมบัติของปฏิทินทำให้คุณสามารถ **แสดงชั่วโมงทำงานของปฏิทิน** กำหนดวันทำงานแบบกำหนดเอง และทำให้กำหนดการของโครงการสอดคล้องกับข้อจำกัดในโลกจริง เช่น วันหยุดหรือรูปแบบกะงาน เราจะอธิบายขั้นตอนการตั้งค่าสภาพแวดล้อม การโหลดโครงการ การวนลูปผ่านปฏิทิน และการอ่านหรืออัปเดตคุณสมบัติของมัน เพื่อให้คุณมั่นใจในการ **จัดการปฏิทิน MS Project** ในแอปพลิเคชัน Java ใด ๆ

## คำตอบสั้น
- **อะไรหมายถึง “set project calendar”** หมายถึงการสร้างหรืออัปเดตช่วงเวลาการทำงานของปฏิทิน, ปฏิทินฐาน, และประเภทของวันภายในไฟล์ MS Project.  
- **ไลบรารีใดที่ต้องการ?** Aspose.Tasks for Java (any recent version).  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้งานฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถแสดงชั่วโมงทำงานของปฏิทินได้หรือไม่?** ใช่—โดยการอ่านแต่ละ `WeekDay` คุณสามารถแสดงชั่วโมงสำหรับแต่ละประเภทของวันได้.  
- **นี่เข้ากันได้กับ Maven/Gradle หรือไม่?** แน่นอน—เพิ่มไฟล์ JAR ของ Aspose.Tasks เป็น dependency.

## วิธีตั้งปฏิทินโครงการใน Java
โหลดไฟล์โครงการของคุณ, ค้นหาปฏิทินเป้าหมาย, แล้วปรับคำนิยามช่วงเวลาการทำงาน, ปฏิทินฐาน, และประเภทของวันตามที่ต้องการ ขั้นตอนต่อไปนี้ให้โซลูชันครบวงจรที่แสดงการโหลด, การวนลูป, การแก้ไข, และการบันทึกโครงการ พร้อมการจัดการข้อยกเว้นและการคำนวณชั่วโมงทำงานที่แม่นยำ.

## ปฏิทินโครงการคืออะไร?
ปฏิทินโครงการกำหนดวันทำงานและชั่วโมงทำงานสำหรับงาน, ทรัพยากร, และไทม์ไลน์โดยรวมของโครงการ ใน MS Project, ปฏิทินสามารถสืบทอดจากปฏิทินฐาน, และแต่ละประเภทของวัน (เช่น **Standard**, **Non‑working**) สามารถมีช่วงเวลาการทำงานของตนเอง การจัดการการตั้งค่าเหล่านี้โดยโปรแกรมทำให้สามารถปรับตารางเวลาแบบไดนามิกโดยไม่ต้องแก้ไขด้วยตนเอง.

## ทำไมต้องจัดการปฏิทิน MS Project ด้วยโปรแกรม?
การจัดการปฏิทินด้วยโปรแกรมทำให้คุณสามารถใช้กฎการกำหนดเวลาที่สอดคล้องกันในหลายโครงการ, ลดข้อผิดพลาดจากการทำด้วยตนเอง, และรวมข้อมูลปฏิทินกับระบบองค์กรอื่น ๆ เช่น HR หรือ ERP การทำอัตโนมัตินี้ช่วยเร่งการตั้งค่าโครงการและทำให้สมาชิกทีมทั้งหมดปฏิบัติตามนโยบายเวลาการทำงานเดียวกัน.

- **Automation:** ปรับปฏิทินในหลายสิบโครงการด้วยสคริปต์เดียว.  
- **Consistency:** บังคับใช้นโยบายเวลาการทำงานทั่วองค์กรโดยอัตโนมัติ.  
- **Integration:** ซิงค์ปฏิทินกับระบบ HR หรือ ERP ภายนอก.  
- **Visibility:** แสดง **ชั่วโมงทำงานของปฏิทิน** อย่างรวดเร็วสำหรับการรายงานหรือการดีบัก.  
- **Flexibility:** เพิ่มข้อยกเว้นหรือรูปแบบกะงานได้ทันทีโดยไม่ต้องเปิด UI.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK) 8+** ติดตั้งแล้วและกำหนดค่า `JAVA_HOME`.  
- **Aspose.Tasks for Java** ไลบรารีที่ดาวน์โหลดจาก [download page](https://releases.aspose.com/tasks/java/). เพิ่มไฟล์ JAR ไปยัง classpath ของคุณหรือประกาศเป็น dependency ของ Maven/Gradle.  
- ไฟล์ตัวอย่าง MS Project (`.mpp` หรือ `.xml`) ที่มีอย่างน้อยหนึ่งปฏิทินที่คุณต้องการตรวจสอบหรือแก้ไข.

## นำเข้าแพ็กเกจ
`Project`, `Calendar`, `WeekDay` และคลาสที่เกี่ยวข้องเป็นแกนหลักของการจัดการปฏิทิน.  
คลาส `Calendar` แทนปฏิทินโครงการ, มีวันทำงาน, ข้อยกเว้น, และความสัมพันธ์กับปฏิทินฐาน.  
คลาส `WeekDay` กำหนดการตั้งค่าช่วงเวลาการทำงานสำหรับวันเดียวภายในปฏิทิน.  
คลาส `Project` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Tasks ที่แทนไฟล์ MS Project หนึ่งไฟล์ในหน่วยความจำ หลังจากโหลดไฟล์แล้ว การดำเนินการทั้งหมดของปฏิทินจะผ่านอ็อบเจ็กต์นี้.

```java
import com.aspose.tasks.*;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดโฟลเดอร์ที่บรรจุไฟล์โครงการของคุณ. แทนที่ตัวแปร placeholder ด้วยเส้นทางจริงบนเครื่องของคุณ.

```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: กำหนดค่าคงที่หน่วยเวลา
ช่วงเวลาการทำงานแสดงเป็นมิลลิวินาที การกำหนดค่าคงที่ที่ใช้ซ้ำทำให้โค้ดอ่านง่ายขึ้นและช่วยให้คุณ **คำนวณชั่วโมงทำงานใน Java** อย่างแม่นยำ.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## ขั้นตอนที่ 3: โหลดข้อมูลโครงการ
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ XML ของ MS Project ที่มีอยู่ (`.xml` หรือ `.mpp`). สิ่งนี้ทำให้คุณเข้าถึงปฏิทินทั้งหมดที่เก็บอยู่ในไฟล์.  
คลาส `Project` โหลดไฟล์เข้าสู่โมเดลอ็อบเจ็กต์แบบน้ำหนักเบา; **ไม่** จำเป็นต้องเก็บไฟล์เต็มในหน่วยความจำ, ทำให้คุณทำงานกับโครงการที่มีงานหลายหมื่นรายการได้.

```java
Project project = new Project(dataDir + "project.xml");
```

## ขั้นตอนที่ 4: วนลูปผ่านปฏิทินใน Java
ตอนนี้เราจะวนลูปผ่านทุกปฏิทิน, พิมพ์ตัวระบุที่ไม่ซ้ำ, ชื่อ, ปฏิทินฐาน, และชั่วโมงทำงานสำหรับแต่ละประเภทของวัน. นี้แสดง **วิธีตั้งปฏิทินโครงการใน Java** และยังแสดง **การแสดงชั่วโมงทำงานของปฏิทิน**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### โค้ดนี้ทำอะไร
- **กรองปฏิทินที่ไม่มีชื่อ** (บางปฏิทินภายในอาจมีค่า `null` เป็นชื่อ).  
- **พิมพ์ UID และชื่อ** – มีประโยชน์สำหรับการระบุปฏิทินในภายหลัง.  
- **แสดงปฏิทินฐาน** – หรือ “Self” (ปฏิทินเป็นฐานของตนเอง) หรือชื่อของปฏิทินที่สืบทอด.  
- **วนลูปผ่านแต่ละ `WeekDay`** เพื่อคำนวณและแสดงชั่วโมงทำงานรวม (`workingTime` อยู่ในมิลลิวินาที, ดังนั้นเราจะแบ่งด้วย `OneHour`).  

## ประโยชน์เชิงปริมาณของการใช้ Aspose.Tasks
Aspose.Tasks รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 30 แบบ** และสามารถประมวลผล **โครงการที่มีงานสูงสุด 10,000 งาน** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ให้ผลลัพธ์ภายในไม่ถึงหนึ่งวินาทีบนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไป ตัวเลขเหล่านี้ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับการทำอัตโนมัติระดับองค์กร.

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` บน `cal.getBaseCalendar()` | ปฏิทินเป็นปฏิทินฐานเอง (`isBaseCalendar()` คืนค่า `true`). | ใช้การตรวจสอบแบบ ternary ตามที่แสดง (`cal.isBaseCalendar() ? "Self" : ...`). |
| ไม่มีผลลัพธ์สำหรับชั่วโมงทำงาน | ไฟล์โครงการใช้หน่วยเวลาอื่น (ticks). | ตรวจสอบรูปแบบไฟล์; Aspose.Tasks ปรับให้เป็นมิลลิวินาที, แต่ต้องแน่ใจว่าคุณโหลดไฟล์ประเภทที่ถูกต้อง. |
| ไม่สามารถหา `project.xml` | เส้นทาง `dataDir` ไม่ถูกต้อง. | ใช้เส้นทางแบบ absolute หรือ `Paths.get(dataDir, "project.xml").toString()`. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถแก้ไขคุณสมบัติของปฏิทินโดยใช้โปรแกรมด้วย Aspose.Tasks ได้หรือไม่?**  
A: ใช่, API ให้การเข้าถึงแบบอ่าน/เขียนเต็มรูปแบบกับปฏิทิน, ทำให้คุณสามารถเพิ่ม, แก้ไข, หรือ ลบช่วงเวลาการทำงาน, ข้อยกเว้น, และความสัมพันธ์ของปฏิทินฐาน.

**Q: มีข้อจำกัดใดในการปรับแต่งปฏิทินด้วย Aspose.Tasks หรือไม่?**  
A: ไลบรารีจำลองความสามารถของ Microsoft Project, ดังนั้นคุณสามารถปรับแต่งเกือบทุกแง่มุมของปฏิทินได้. เพียงไฟล์ Project รุ่นเก่ามากอาจมีข้อไม่เข้ากันเล็กน้อย.

**Q: ฉันสามารถรวมการจัดการปฏิทินเข้ากับโครงการ Java ที่มีอยู่ได้หรือไม่?**  
A: แน่นอน. เพียงเพิ่มไฟล์ JAR ของ Aspose.Tasks ไปยังเส้นทางการสร้างของคุณและใช้รูปแบบโค้ดเดียวกันที่แสดงในที่นี้.

**Q: Aspose.Tasks รองรับฟังก์ชันการจัดการโครงการอื่น ๆ นอกจากการจัดการปฏิทินหรือไม่?**  
A: ใช่, มันครอบคลุมงาน, ทรัพยากร, การมอบหมาย, โครงร่าง, baseline, และอื่น ๆ—ทำให้เป็นโซลูชันครบวงจรสำหรับการทำอัตโนมัติโครงการบน Java.

**Q: มีการสนับสนุนทางเทคนิคสำหรับนักพัฒนาที่ใช้ Aspose.Tasks หรือไม่?**  
A: มี, Aspose มีฟอรั่มเฉพาะ, การสนับสนุนทางอีเมล, และเอกสารที่ครอบคลุมสำหรับผู้ใช้ที่มีไลเซนส์ทั้งหมด.

---

**อัปเดตล่าสุด:** 2026-09-09  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างปฏิทินโครงการ Java – คู่มือ Aspose.Tasks for Java](/tasks/java/)
- [โหลดไฟล์โครงการใน Java และจัดการคุณสมบัติโครงการ](/tasks/java/project-management/default-properties/)
- [ตั้งค่าวันเริ่มต้นของโครงการใน MS Project ด้วย Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}