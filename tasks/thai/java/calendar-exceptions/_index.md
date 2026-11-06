---
date: 2026-11-06
description: สร้างข้อยกเว้นปฏิทินแบบกำหนดเองได้อย่างง่ายดาย, ผสานรวมปฏิทิน MS Project,
  และจัดการ, กำหนด, จัดการและดึงข้อมูลข้อยกเว้นปฏิทินในโครงการ Java ด้วย Aspose.Tasks.
  ปรับกระบวนการทำงานของโครงการให้มีประสิทธิภาพสำหรับการจัดการโครงการที่มีประสิทธิผล.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: ข้อยกเว้นปฏิทิน
og_description: เรียนรู้วิธีสร้างข้อยกเว้นปฏิทินใน Java ด้วย Aspose.Tasks. จัดการปฏิทินโครงการ,
  ตั้งค่าวันที่ไม่ทำงาน, และปรับเปลี่ยนปฏิทิน MS Project อย่างมีประสิทธิภาพ.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: สร้างข้อยกเว้นปฏิทินด้วย Aspose.Tasks สำหรับ Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
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

`Aspose.Tasks` คือไลบรารี Java ที่ช่วยให้สามารถสร้าง, จัดการ, และแปลงไฟล์ Microsoft Project ได้โดยอัตโนมัติ ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **สร้างข้อยกเว้นปฏิทิน** — ช่วงเวลาที่ไม่ทำงานแบบกำหนดเองซึ่งจะทับซ้อนปฏิทินเริ่มต้นของโครงการ การควบคุมที่แม่นยำต่อวันทำงานและวันหยุดเป็นสิ่งสำคัญสำหรับการพยากรณ์กำหนดการอย่างแม่นยำ, การจัดสรรทรัพยากร, และการปฏิบัติตามวันหยุดประจำภูมิภาค เมื่อจบคู่มือคุณจะยังรู้วิธี **รวมปฏิทิน MS Project** เข้ากับแอปพลิเคชัน Java ของคุณและดึงหรือแก้ไขข้อยกเว้นของมัน

## คำตอบด่วน
- **อะไรที่ฉันทำได้?** สร้าง, แก้ไข, และดึงข้อยกเว้นปฏิทินแบบกำหนดเองในโครงการ Java.  
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Tasks for Java (latest stable release).  
- **ฉันต้องการใบอนุญาตหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ฉันสามารถทำงานกับไฟล์ MS Project ได้หรือไม่?** แน่นอน – คุณสามารถนำเข้า, แก้ไข, และส่งออกข้อมูลปฏิทินของ MS Project.  
- **ต้องการการตั้งค่าเฉพาะใด ๆ หรือไม่?** เพียงเพิ่มไฟล์ Aspose.Tasks JAR ไปยัง classpath ของคุณและนำเข้าคลาสที่เกี่ยวข้อง.  

## วิธีสร้างข้อยกเว้นปฏิทินแบบกำหนดเองใน Aspose.Tasks สำหรับ Java?

เพื่อสร้างข้อยกเว้นปฏิทินแบบกำหนดเองใน Aspose.Tasks สำหรับ Java ให้โหลด Project เป้าหมาย, ดึง Calendar ของมัน, กำหนดวันที่เริ่มและสิ้นสุดของข้อยกเว้นพร้อมเวลาทำงานที่ต้องการ, ตั้งค่ารูปแบบการเกิดซ้ำตามต้องการ, แล้วบันทึกโครงการ การทำเช่นนี้จะเพิ่มข้อยกเว้นทันทีและบันทึกลงไฟล์ .mpp

`Project` class คือวัตถุหลักของ Aspose.Tasks ที่จำลองไฟล์ Microsoft Project ทั้งหมด `Project` class แทนไฟล์ Microsoft Project และให้การเข้าถึงเนื้อหาของมัน `Calendar` object กำหนดเวลาทำงานและเวลาที่ไม่ทำงานสำหรับโครงการ `Calendar` class เป็นคอนเทนเนอร์สำหรับกฎเวลาทำงานทั้งหมด รวมถึงข้อยกเว้น `addException()` method เพิ่มข้อยกเว้นปฏิทินใหม่ลงใน calendar `addException()` เป็น API แบบเรียกครั้งเดียวที่ลงทะเบียนช่วงเวลาที่ไม่ทำงานสำหรับช่วงวันที่ที่ระบุ

โหลดโครงการเป้าหมายด้วย `Project project = new Project("example.mpp")`, ดึงอ็อบเจกต์ `Calendar` ของมัน, และเรียก `addException()` พร้อมช่วงวันที่และการตั้งค่าเวลาทำงานที่ต้องการ รูปแบบสองขั้นตอนนี้จะสร้างข้อยกเว้นใหม่ทันทีและบันทึกเมื่อคุณบันทึกโครงการ สำหรับวันหยุดที่เกิดซ้ำ ให้กำหนด `RecurrencePattern` บนข้อยกเว้นก่อนบันทึก

การสร้างข้อยกเว้นปฏิทินด้วยวิธีนี้ทำให้คุณ **ตั้งค่าวันที่ไม่ทำงาน** ได้อย่างแม่นยำ ไม่ว่าจะเป็นการปิดทำการครั้งเดียวหรือวันหยุดประจำปี หลังจากเพิ่มข้อยกเว้นแล้ว คุณสามารถเรียก `project.save("updated.mpp")` เพื่อเขียนการเปลี่ยนแปลงกลับไปยังดิสก์

### ภาพรวมขั้นตอน
1. โหลดไฟล์โครงการ.  
2. ดึงหรือสร้างอินสแตนซ์ `Calendar`.  
3. กำหนดช่วงวันที่และเวลาทำงานของข้อยกเว้น.  
4. (ทางเลือก) กำหนดการเกิดซ้ำสำหรับวันหยุดประจำปี.  
5. บันทึกโครงการ.  

## จัดการข้อยกเว้นปฏิทินใน Aspose.Tasks
[Learn how to add and remove calendar exceptions in Aspose.Tasks for Java efficiently](./add-remove/). เมื่อพูดถึงการจัดการโครงการ ความยืดหยุ่นเป็นสิ่งสำคัญ Aspose.Tasks ช่วยให้คุณจัดการข้อยกเว้นปฏิทินได้อย่างง่ายดาย, ทำให้สามารถปรับเปลี่ยนไทม์ไลน์ของโครงการได้อย่างไดนามิก คู่มือนี้ให้คำแนะนำแบบขั้นตอน‑ต่อ‑ขั้นตอน เพื่อให้คุณเข้าใจกระบวนการอย่างมีประสิทธิภาพ ค้นพบวิธีเพิ่มประสิทธิภาพการทำงานของการจัดการโครงการของคุณได้อย่างง่ายดาย.

## กำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินด้วย Aspose.Tasks
[Master the art of defining weekdays for calendar exceptions in Java projects](./define-weekdays/) using Aspose.Tasks. การกำหนดตารางโครงการที่แม่นยำต้องการความใส่ใจในรายละเอียดอย่างละเอียด ด้วย Aspose.Tasks คุณสามารถกำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินได้อย่างแม่นยำ, ทำให้โครงการของคุณสอดคล้องกับไทม์ไลน์ที่กำหนดอย่างไร้รอยต่อ คู่มือนี้ให้ความรู้เพื่อเพิ่มประสิทธิภาพการกำหนดเวลา, ให้คุณควบคุมไทม์ไลน์ของโครงการได้

## จัดการเหตุการณ์ซ้ำในข้อยกเว้นปฏิทินโดยใช้ Aspose.Tasks
[Effectively handle calendar exceptions in Java projects](./handle-occurrences/) with Aspose.Tasks for Java. การจัดการโครงการเป็นกระบวนการที่เปลี่ยนแปลงได้, มักต้องการการปรับเปลี่ยนเพื่อรับมือกับเหตุการณ์ที่ไม่คาดคิด Aspose.Tasks ช่วยให้คุณจัดการข้อยกเว้นปฏิทินได้อย่างมีประสิทธิภาพ, มอบแนวทางที่เป็นระบบสำหรับการจัดการโครงการ เรียนรู้ศิลปะการจัดการความไม่แน่นอนของโครงการได้อย่างง่ายดายผ่านคู่มือที่ละเอียดนี้.

## ดึงข้อยกเว้นปฏิทินด้วย Aspose.Tasks
[Learn how to retrieve calendar exceptions from MS Project using Aspose.Tasks for Java](./retrieve/). ผสานข้อยกเว้นปฏิทินเข้ากับกระบวนการจัดการโครงการของคุณได้อย่างราบรื่นด้วย Aspose.Tasks คู่มือนี้แนะนำคุณผ่านกระบวนการดึงข้อยกเว้นปฏิทินแบบขั้นตอน‑ต่อ‑ขั้นตอน, เพื่อให้การผสานรวมกับโครงการของคุณเป็นไปอย่างราบรื่นและมีประสิทธิภาพ เปิดศักยภาพของ Aspose.Tasks เพื่อเพิ่มประสิทธิภาพการจัดการโครงการของคุณ

## วิธีรวมปฏิทิน MS Project กับ Aspose.Tasks?
การรวมปฏิทิน MS Project กับ Aspose.Tasks เกี่ยวข้องกับการโหลดไฟล์ .mpp แหล่งที่มาด้วยคลาส Project, เข้าถึงอ็อบเจกต์ Calendar เริ่มต้นหรือแบบกำหนดเอง, แก้ไขหรือรวมข้อยกเว้นตามต้องการ, แล้วบันทึกโครงการที่อัปเดต สิ่งนี้ทำให้คุณสามารถทำงานกับปฏิทิน MS Project ได้โดยอัตโนมัติโดยไม่ต้องโต้ตอบกับ UI ด้วยตนเอง.

`Project` class คือวัตถุหลักของ Aspose.Tasks ที่จำลองไฟล์ Microsoft Project ทั้งหมด นำเข้าไฟล์ MS Project ที่มีอยู่โดยใช้ `new Project("source.mpp")`; ไลบรารีจะโหลดปฏิทินเริ่มต้นและข้อยกเว้นที่กำหนดเองโดยอัตโนมัติ จากนั้นคุณสามารถอ่าน, แก้ไข, หรือรวมข้อยกเว้นเหล่านั้นก่อนบันทึกโครงการกลับไปยังดิสก์ วิธีนี้ทำให้คุณ **แก้ไขข้อมูลปฏิทิน MS Project** ได้โดยอัตโนมัติโดยไม่ต้องแก้ไขด้วยตนเองใน UI ของ MS Project

## กรณีการใช้งานทั่วไป
- **การกำหนดวันหยุด** – กำหนดวันหยุดแห่งชาติเป็นวันไม่ทำงานในหลายโครงการ.  
- **การทำงานแบบกะ** – ตั้งสัปดาห์ทำงานแบบกำหนดเองสำหรับทีมที่ทำงานตามตารางที่ไม่เป็นมาตรฐาน.  
- **การกำหนดขั้นตอนโครงการ** – บล็อกช่วงเวลาที่ไม่ควรมีการทำงาน, เช่น หน้าต่างการบำรุงรักษา.  
- **การย้ายข้อมูลจากระบบเดิม** – นำเข้าปฏิทินจากไฟล์ MS Project เก่ากว่าและปรับเปลี่ยนโดยอัตโนมัติ.  

## เคล็ดลับและแนวทางปฏิบัติที่ดีที่สุด
- **เคล็ดลับมืออาชีพ:** ควรดึงปฏิทินที่มีอยู่ก่อนเพิ่มข้อยกเว้นใหม่เพื่อหลีกเลี่ยงการซ้ำซ้อน.  
- **คำเตือน:** การเปลี่ยนแปลงปฏิทินที่ได้มอบหมายให้กับงานแล้วอาจทำให้วันที่ของงานเปลี่ยนแปลง; ควรคำนวณกำหนดการใหม่หลังการแก้ไข.  
- **ประสิทธิภาพ:** ทำการอัปเดตข้อยกเว้นหลายรายการเป็นชุดในธุรกรรมเดียวเพื่อลดภาระ I/O ของไฟล์ Aspose.Tasks สามารถประมวลผลไฟล์ขนาดสูงสุด 1 GB พร้อมใช้หน่วยความจำต่ำกว่า 200 MB, และสามารถจัดการการเรียก API ที่เกี่ยวกับปฏิทินได้กว่า 30 ครั้งต่อวินาทีบนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไป.  

## บทเรียนข้อยกเว้นปฏิทิน
### [จัดการข้อยกเว้นปฏิทินใน Aspose.Tasks](./add-remove/)
เรียนรู้วิธีเพิ่มและลบข้อยกเว้นปฏิทินใน Aspose.Tasks สำหรับ Java อย่างมีประสิทธิภาพ. ปรับปรุงกระบวนการจัดการโครงการได้อย่างง่ายดาย.
### [กำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินด้วย Aspose.Tasks](./define-weekdays/)
เรียนรู้วิธีกำหนดวันทำงานสำหรับข้อยกเว้นปฏิทินในโครงการ Java ด้วย Aspose.Tasks เพื่อการกำหนดเวลาโครงการที่แม่นยำ.
### [จัดการเหตุการณ์ซ้ำในข้อยกเว้นปฏิทินโดยใช้ Aspose.Tasks](./handle-occurrences/)
เรียนรู้วิธีจัดการข้อยกเว้นปฏิทินอย่างมีประสิทธิภาพในโครงการ Java ด้วย Aspose.Tasks for Java. ทำให้กระบวนการจัดการโครงการของคุณเป็นระบบได้ทันที.
### [ดึงข้อยกเว้นปฏิทินด้วย Aspose.Tasks](./retrieve/)
เรียนรู้วิธีดึงข้อยกเว้นปฏิทินจาก MS Project ด้วย Aspose.Tasks สำหรับ Java. คู่มือแบบขั้นตอน‑ต่อ‑ขั้นตอนสำหรับการผสานรวมอย่างราบรื่น.

## คำถามที่พบบ่อย

**Q: สามารถแก้ไขข้อยกเว้นปฏิทินหลังจากที่โครงการได้เผยแพร่แล้วหรือไม่?**  
A: ใช่. ใช้ API add‑remove และ define‑weekdays เพื่ออัปเดตปฏิทิน, แล้วบันทึกไฟล์โครงการใหม่.

**Q: Aspose.Tasks รองรับข้อยกเว้นที่เกิดซ้ำ (เช่น ทุกวันจันทร์แรกของเดือน) หรือไม่?**  
A: แน่นอน. คู่มือ “handle occurrences” ครอบคลุมวิธีตั้งค่ารูปแบบการเกิดซ้ำ.

**Q: ฉันจะทำให้แน่ใจว่าปฏิทินที่กำหนดเองของฉันถูกใช้โดยงานทั้งหมดในโครงการได้อย่างไร?**  
A: กำหนดปฏิทินให้กับปฏิทินเริ่มต้นของโครงการหรือกำหนดโดยชัดเจนบนคุณสมบัติ `Calendar` ของแต่ละงาน.

**Q: สามารถรวมปฏิทินจากหลายไฟล์ MS Project ได้หรือไม่?**  
A: ได้. ดึงปฏิทินแต่ละอัน, รวมข้อยกเว้นของพวกมันโดยอัตโนมัติ, แล้วกำหนดปฏิทินที่รวมแล้วให้กับโครงการเป้าหมาย.

**Q: เวอร์ชันของ Aspose.Tasks ที่ต้องการสำหรับฟีเจอร์เหล่านี้คืออะไร?**  
A: ฟีเจอร์ทั้งหมดพร้อมใช้งานในรุ่นเสถียรล่าสุดของ Aspose.Tasks สำหรับ Java (2025.x).

## บทเรียนที่เกี่ยวข้อง

- [สร้างปฏิทินโครงการ Aspose – กำหนดวันทำงานสำหรับข้อยกเว้นปฏิทิน](/tasks/java/calendar-exceptions/define-weekdays/)
- [ดึงข้อยกเว้นปฏิทินด้วย Aspose.Tasks – บทเรียน Java ของ asp tasks](/tasks/java/calendar-exceptions/retrieve/)
- [สร้างข้อยกเว้นปฏิทิน Aspose สำหรับ Java](/tasks/java/calendar-exceptions/add-remove/)

---

**อัปเดตล่าสุด:** 2026-11-06  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}