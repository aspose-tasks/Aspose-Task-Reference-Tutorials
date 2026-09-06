---
date: 2026-08-18
description: สร้างข้อยกเว้นปฏิทินแบบกำหนดเองได้อย่างง่ายดาย, ผสานรวมปฏิทิน MS Project,
  และจัดการ, กำหนด, จัดการและดึงข้อมูลข้อยกเว้นปฏิทินในโครงการ Java ด้วย Aspose.Tasks.
  ปรับกระบวนการทำงานของโครงการให้คล่องตัวเพื่อการจัดการโครงการที่มีประสิทธิภาพ.
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: ข้อยกเว้นปฏิทิน
og_description: เรียนรู้วิธีสร้างข้อยกเว้นปฏิทิน, จัดการปฏิทินโครงการ, และตั้งค่าวันหยุดใน
  Java ด้วย Aspose.Tasks. คู่มือสั้นสำหรับนักพัฒนา.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: วิธีสร้างข้อยกเว้นปฏิทินด้วย Aspose.Tasks สำหรับ Java
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: วิธีสร้างข้อยกเว้นปฏิทินด้วย Aspose.Tasks สำหรับ Java
url: /th/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างข้อยกเว้นปฏิทินด้วย Aspose.Tasks สำหรับ Java

## บทนำ

`Aspose.Tasks` เป็นไลบรารี Java ที่ช่วยให้สามารถสร้าง, แก้ไข, และแปลงไฟล์ Microsoft Project ได้โดยอัตโนมัติ ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **สร้างข้อยกเว้นปฏิทิน** — ช่วงเวลาที่ไม่ทำงานแบบกำหนดเองซึ่งจะแทนที่ปฏิทินเริ่มต้นของโครงการ การควบคุมวันทำงานและวันหยุดอย่างแม่นยำเป็นสิ่งสำคัญสำหรับการคาดการณ์กำหนดการที่ถูกต้อง, การจัดสรรทรัพยากร, และการปฏิบัติตามวันหยุดประจำภูมิภาค เมื่อจบคู่มือคุณจะทราบวิธี **รวมปฏิทิน MS Project** เข้าในแอปพลิเคชัน Java ของคุณและดึงหรือแก้ไขข้อยกเว้นเหล่านั้น

## คำตอบสั้น
- **อะไรที่ฉันทำได้?** สร้าง, แก้ไข, และดึงข้อยกเว้นปฏิทินแบบกำหนดเองในโครงการ Java.  
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Tasks for Java (รุ่นเสถียรล่าสุด).  
- **ฉันต้องมีลิขสิทธิ์หรือไม่?** ใช่, จำเป็นต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ฉันสามารถทำงานกับไฟล์ MS Project ได้หรือไม่?** แน่นอน – คุณสามารถนำเข้า, แก้ไข, และส่งออกข้อมูลปฏิทินของ MS Project.  
- **ต้องตั้งค่าอะไรเป็นพิเศษหรือไม่?** เพียงเพิ่มไฟล์ JAR ของ Aspose.Tasks ไปยัง classpath ของคุณและนำเข้าคลาสที่เกี่ยวข้อง.

## วิธีสร้างข้อยกเว้นปฏิทินแบบกำหนดเองใน Aspose.Tasks สำหรับ Java?

`Project` class แทนไฟล์ Microsoft Project และให้การเข้าถึงเนื้อหาต่าง ๆ ของไฟล์นั้น `Calendar` object กำหนดช่วงเวลาทำงานและไม่ทำงานของโครงการ `addException()` method เพิ่มข้อยกเว้นปฏิทินใหม่ลงในปฏิทิน

โหลดโครงการเป้าหมายด้วย `Project project = new Project("example.mpp")`, ดึงอ็อบเจกต์ `Calendar` ของมัน, แล้วเรียก `addException()` พร้อมช่วงวันที่และการตั้งค่าเวลาทำงานที่ต้องการ รูปแบบสองขั้นตอนนี้จะสร้างข้อยกเว้นใหม่ทันทีและบันทึกไว้เมื่อคุณบันทึกโครงการ สำหรับวันหยุดที่เกิดซ้ำ ให้กำหนด `RecurrencePattern` บนข้อยกเว้นก่อนบันทึก

การสร้างข้อยกเว้นปฏิทินแบบนี้ทำให้คุณ **ตั้งค่าวันหยุดไม่ทำงาน** อย่างแม่นยำ ไม่ว่าจะเป็นการปิดทำการครั้งเดียวหรือวันหยุดประจำปี หลังจากเพิ่มข้อยกเว้นแล้วคุณสามารถเรียก `project.save("updated.mpp")` เพื่อเขียนการเปลี่ยนแปลงกลับไปยังดิสก์

### ภาพรวมขั้นตอน
1. โหลดไฟล์โครงการ.  
2. ดึงหรือสร้างอินสแตนซ์ `Calendar`.  
3. กำหนดช่วงวันที่และเวลาทำงานของข้อยกเว้น.  
4. (ทางเลือก) ตั้งค่าการเกิดซ้ำสำหรับวันหยุดประจำปี.  
5. บันทึกโครงการ.

## จัดการข้อยกเว้นปฏิทินใน Aspose.Tasks
[เรียนรู้วิธีเพิ่มและลบข้อยกเว้นปฏิทินใน Aspose.Tasks สำหรับ Java อย่างมีประสิทธิภาพ](./add-remove/). เมื่อพูดถึงการจัดการโครงการ ความยืดหยุ่นเป็นกุญแจสำคัญ Aspose.Tasks ช่วยให้คุณจัดการข้อยกเว้นปฏิทินได้อย่างง่ายดาย ทำให้สามารถปรับเปลี่ยนไทม์ไลน์ของโครงการได้อย่างไดนามิก บทเรียนนี้ให้คำแนะนำทีละขั้นตอน เพื่อให้คุณเข้าใจกระบวนการอย่างเต็มที่ ค้นพบวิธีเพิ่มประสิทธิภาพการทำงานของคุณด้วยการจัดการข้อยกเว้นปฏิทินอย่างง่ายดาย

## กำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินด้วย Aspose.Tasks
[เชี่ยวชาญการกำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินในโครงการ Java](./define-weekdays/) ด้วย Aspose.Tasks. การวางแผนโครงการที่แม่นยำต้องอาศัยความละเอียดรอบคอบ ด้วย Aspose.Tasks คุณสามารถกำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินได้อย่างแม่นยำ ทำให้โครงการของคุณสอดคล้องกับไทม์ไลน์ที่กำหนดไว้ได้อย่างไร้รอยต่อ บทเรียนนี้ให้ความรู้ที่จำเป็นเพื่อเพิ่มประสิทธิภาพการกำหนดเวลา ให้คุณควบคุมไทม์ไลน์ของโครงการได้อย่างเต็มที่

## จัดการเหตุการณ์ในข้อยกเว้นปฏิทินโดยใช้ Aspose.Tasks
[จัดการข้อยกเว้นปฏิทินในโครงการ Java อย่างมีประสิทธิภาพ](./handle-occurrences/) ด้วย Aspose.Tasks for Java. การจัดการโครงการเป็นกระบวนการไดนามิกที่มักต้องปรับเปลี่ยนเพื่อรับมือกับเหตุการณ์ที่ไม่คาดคิด Aspose.Tasks ช่วยให้คุณจัดการข้อยกเว้นปฏิทินได้อย่างมีประสิทธิภาพ ให้แนวทางที่เป็นระบบสำหรับการจัดการโครงการ ค้นหาวิธีจัดการความไม่แน่นอนของโครงการได้อย่างง่ายดายผ่านบทเรียนละเอียดนี้

## ดึงข้อยกเว้นปฏิทินด้วย Aspose.Tasks
[เรียนรู้วิธีดึงข้อยกเว้นปฏิทินจาก MS Project ด้วย Aspose.Tasks for Java](./retrieve/). ผสานข้อยกเว้นปฏิทินเข้ากับกระบวนการจัดการโครงการของคุณได้อย่างราบรื่นด้วย Aspose.Tasks บทเรียนนี้นำคุณผ่านขั้นตอนการดึงข้อยกเว้นปฏิทินอย่างละเอียด เพื่อให้การผสานเข้ากับโครงการของคุณเป็นไปอย่างราบรื่นและมีประสิทธิภาพ ใช้พลังของ Aspose.Tasks เพื่อยกระดับความสามารถในการจัดการโครงการของคุณ

## วิธีรวมปฏิทิน MS Project กับ Aspose.Tasks?

`Project` class โหลดไฟล์ Microsoft Project และเปิดเผยปฏิทินและข้อมูลโครงการอื่น ๆ การนำเข้าไฟล์ MS Project ที่มีอยู่โดยใช้ `new Project("source.mpp")`; ไลบรารีจะโหลดปฏิทินเริ่มต้นและข้อยกเว้นที่กำหนดเองโดยอัตโนมัติ จากนั้นคุณสามารถอ่าน, แก้ไข, หรือรวมข้อยกเว้นเหล่านั้นก่อนบันทึกโครงการกลับไปยังดิสก์ วิธีนี้ทำให้คุณ **แก้ไขข้อมูลปฏิทิน MS Project** ได้โดยโปรแกรมโดยไม่ต้องแก้ไขด้วยตนเองใน UI ของ MS Project

## กรณีการใช้งานทั่วไป
- **การกำหนดวันหยุด** – กำหนดวันหยุดประจำชาติเป็นวันไม่ทำงานในหลายโครงการ.  
- **งานกะ** – ตั้งสัปดาห์ทำงานแบบกำหนดเองสำหรับทีมที่ทำงานตามตารางที่ไม่เป็นมาตรฐาน.  
- **การควบคุมขั้นตอนโครงการ** – ปิดช่วงเวลาที่ไม่ควรมีการกำหนดงาน เช่น ช่วงเวลาบำรุงรักษา.  
- **การย้ายข้อมูลจากระบบเดิม** – นำเข้าปฏิทินจากไฟล์ MS Project เก่าและปรับเปลี่ยนโดยอัตโนมัติ.

## เคล็ดลับและแนวทางปฏิบัติที่ดีที่สุด
- **เคล็ดลับมืออาชีพ:** ควรดึงปฏิทินที่มีอยู่ก่อนเพิ่มข้อยกเว้นใหม่เพื่อหลีกเลี่ยงการซ้ำซ้อน.  
- **คำเตือน:** การเปลี่ยนปฏิทินที่ได้กำหนดให้กับงานแล้วอาจทำให้วันที่ของงานเปลี่ยนแปลง; ควรคำนวณกำหนดการใหม่หลังการแก้ไข.  
- **ประสิทธิภาพ:** ทำการอัปเดตข้อยกเว้นหลายรายการในชุดเดียวเพื่อ ลดภาระ I/O ของไฟล์. Aspose.Tasks สามารถประมวลผลไฟล์ขนาดถึง 500 MB โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, รองรับการเรียก API ที่เกี่ยวกับปฏิทินกว่า 50 ครั้งต่อวินาทีบนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไป.

## บทเรียนข้อยกเว้นปฏิทิน
### [จัดการข้อยกเว้นปฏิทินใน Aspose.Tasks](./add-remove/)
เรียนรู้วิธีเพิ่มและลบข้อยกเว้นปฏิทินใน Aspose.Tasks for Java อย่างมีประสิทธิภาพ เพิ่มประสิทธิภาพการทำงานของโครงการได้อย่างง่ายดาย.
### [กำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินด้วย Aspose.Tasks](./define-weekdays/)
เรียนรู้วิธีกำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินในโครงการ Java ด้วย Aspose.Tasks เพื่อการวางแผนโครงการที่แม่นยำ.
### [จัดการเหตุการณ์ในข้อยกเว้นปฏิทินโดยใช้ Aspose.Tasks](./handle-occurrences/)
เรียนรู้วิธีจัดการข้อยกเว้นปฏิทินอย่างมีประสิทธิภาพในโครงการ Java ด้วย Aspose.Tasks for Java. ปรับกระบวนการจัดการโครงการของคุณให้เป็นระบบทันที.
### [ดึงข้อยกเว้นปฏิทินด้วย Aspose.Tasks](./retrieve/)
เรียนรู้วิธีดึงข้อยกเว้นปฏิทินจาก MS Project ด้วย Aspose.Tasks for Java. บทเรียนขั้นตอนต่อขั้นตอนสำหรับการผสานอย่างราบรื่น.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถแก้ไขข้อยกเว้นปฏิทินหลังจากโครงการถูกเผยแพร่แล้วหรือไม่?**  
**ตอบ:** ใช่. ใช้ API เพิ่ม‑ลบและกำหนดวันทำงานเพื่ออัปเดตปฏิทิน, แล้วบันทึกไฟล์โครงการใหม่อีกครั้ง.

**ถาม: Aspose.Tasks รองรับข้อยกเว้นที่เกิดซ้ำ (เช่น ทุกวันจันทร์แรกของเดือน) หรือไม่?**  
**ตอบ:** แน่นอน. บทเรียน “จัดการเหตุการณ์” ครอบคลุมวิธีตั้งค่ารูปแบบการเกิดซ้ำ.

**ถาม: ฉันจะทำให้ปฏิทินที่กำหนดเองถูกใช้โดยงานทั้งหมดในโครงการได้อย่างไร?**  
**ตอบ:** กำหนดปฏิทินให้เป็นปฏิทินเริ่มต้นของโครงการหรือกำหนดให้กับแต่ละงานผ่านคุณสมบัติ `Calendar` ของงาน.

**ถาม: สามารถรวมปฏิทินจากหลายไฟล์ MS Project ได้หรือไม่?**  
**ตอบ:** ได้. ดึงปฏิทินแต่ละอัน, รวมข้อยกเว้นโดยโปรแกรม, แล้วกำหนดปฏิทินที่รวมแล้วให้กับโครงการเป้าหมาย.

**ถาม: ต้องใช้เวอร์ชันใดของ Aspose.Tasks เพื่อใช้ฟีเจอร์เหล่านี้?**  
**ตอบ:** ฟีเจอร์ทั้งหมดพร้อมใช้งานในรุ่นเสถียรล่าสุดของ Aspose.Tasks for Java (2025.x).

---

**อัปเดตล่าสุด:** 2026-08-18  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้างปฏิทินโครงการ Aspose – กำหนดวันทำงานสำหรับข้อยกเว้นปฏิทิน](/tasks/java/calendar-exceptions/define-weekdays/)
- [ดึงข้อยกเว้นปฏิทินด้วย Aspose.Tasks – บทเรียน Java](/tasks/java/calendar-exceptions/retrieve/)
- [สร้างข้อยกเว้นปฏิทิน Aspose สำหรับ Java](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}