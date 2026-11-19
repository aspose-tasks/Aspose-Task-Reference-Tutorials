---
date: 2026-11-19
description: เรียนรู้วิธีสร้างปฏิทินแบบกำหนดเองใน Java ด้วย Aspose.Tasks คู่มือนี้จะแสดงวิธีกำหนดวันทำงาน
  ตั้งชั่วโมงทำงาน และแก้ไขปฏิทินของ MS Project โดยใช้โปรแกรม
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: ปฏิทิน
og_description: เรียนรู้วิธีสร้างปฏิทินแบบกำหนดเองใน Java ด้วย Aspose.Tasks เชี่ยวชาญการกำหนดวันทำงาน
  การตั้งชั่วโมงทำงาน และการแก้ไขปฏิทินของ MS Project อย่างมีประสิทธิภาพ
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: วิธีสร้างปฏิทินแบบกำหนดเองใน Java ด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: วิธีสร้างปฏิทินแบบกำหนดเองใน Java ด้วย Aspose.Tasks
url: /th/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปฏิทิน

## บทนำ

หากคุณเป็นนักพัฒนา Java ที่ต้องการ **สร้างโซลูชันปฏิทินแบบกำหนดเองใน Java** คุณมาถูกที่แล้ว ศูนย์นี้รวบรวมบทแนะนำ Aspose.Tasks for Java ทั้งหมดที่แสดงวิธี **กำหนดวันทำงานใน MS Project**, **ตั้งค่าชั่วโมงทำงานใน MS Project**, และปรับการตั้งค่าปฏิทินโดยโปรแกรม ไม่ว่าคุณจะสร้างเครื่องมือกำหนดเวลาใหม่หรือขยายแผนที่มีอยู่ การเชี่ยวชาญ API เหล่านี้จะให้การควบคุมที่แม่นยำต่อรูปแบบวันทำงาน, วันหยุด, และกะงานแบบกำหนดเอง—โดยไม่ต้องเปิด UI ของ MS Project

## คำตอบด่วน
- **อะไรคือวัตถุประสงค์หลักของการกำหนดวันทำงาน?**  
  เพื่อบอก MS Project ว่าวันใดเป็นวันทำงานและชั่วโมงทำงานของแต่ละวันคืออะไร.  
- **ไลบรารีใดจัดการการกำหนดวันทำงานใน Java?**  
  Aspose.Tasks for Java มี API แบบ fluent สำหรับการจัดการปฏิทิน.  
- **ฉันต้องการไลเซนส์หรือไม่?**  
  ไลเซนส์ทดลองฟรีใช้ได้สำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถกำหนดหลายปฏิทินสำหรับทีมต่าง ๆ ได้หรือไม่?**  
  ได้ – แต่ละโครงการสามารถมีหลายปฏิทิน, แต่ละปฏิทินมีการตั้งค่าวันทำงานของตนเอง.  
- **มีโครงการตัวอย่างให้เริ่มต้นหรือไม่?**  
  บทแนะนำ “Define Weekdays in Calendar” ที่ลิงก์ด้านล่างมีตัวอย่างพร้อมรัน.

## วิธีสร้างปฏิทินแบบกำหนดเองใน Java?

โหลดโครงการ, สร้างหรือดึงปฏิทิน, เพิ่มการกำหนดวันทำงาน, และบันทึกไฟล์—ทั้งหมดในไม่กี่คำสั่ง API วิธีนี้ลบขั้นตอน UI ที่ทำด้วยมือ, ทำให้คุณอัตโนมัติการสร้างปฏิทินข้ามหลายสิบโครงการ, และทำให้รูปแบบวันทำงานสอดคล้องทั่วทั้งองค์กรของคุณ.

## คลาส Project คืออะไร?

คลาส `Project` เป็นอ็อบเจ็กต์ศูนย์กลางสำหรับการโหลด, แก้ไข, และบันทึกไฟล์ MS Project. มันเก็บคอลเลกชันของงาน, ทรัพยากร, และปฏิทิน, เปิดเผยเมธอดที่ให้คุณอ่านและแก้ไขทุกแง่มุมของโครงการโดยโปรแกรม. ด้วยคลาสนี้คุณสามารถเข้าถึงคอลเลกชันปฏิทินของโครงการ, ปรับเวลาทำงาน, และบันทึกการเปลี่ยนแปลงกลับเป็นไฟล์ MPP หรือ XML.

## ฉันจะกำหนดวันทำงานในปฏิทิน MS Project อย่างไร?

คลาส `Project` แทนไฟล์ MS Project และให้การเข้าถึงโครงสร้างข้อมูลของมัน. อ็อบเจ็กต์ `Calendar` เก็บการกำหนดเวลาทำงานและข้อยกเว้นสำหรับโครงการ. โหลดโครงการของคุณด้วย `new Project("myproject.mpp")`, ดึง (หรือสร้าง) อ็อบเจ็กต์ `Calendar`, แล้วเรียก `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. บรรทัดเดียวนี้สร้างรายการวันทำงานวันจันทร์ที่มีกะ 8 ชั่วโมง. ทำซ้ำสำหรับวันอื่น ๆ, แล้วบันทึกโครงการด้วย `project.save("updated.mpp")`. รูปแบบสั้นนี้ทำให้คุณกำหนด, แก้ไข, หรือ ลบวันทำงานได้ด้วยไม่กี่คำสั่ง API, ไม่ต้องใช้ UI ด้วยตนเอง.

## วัตถุ WeekDay คืออะไร?

วัตถุ `WeekDay` แทนรายการวันหนึ่งในสัปดาห์ภายในปฏิทิน. มันเก็บข้อมูลว่ามันเป็นวันทำงานหรือไม่, ช่วงเวลาทำงานของวันนั้น, และแฟล็กสำหรับพฤติกรรมค่าเริ่มต้น. คุณสามารถแนบช่วง `WorkingTime` หนึ่งหรือหลายช่วงเพื่อจำลองกะงานแยก, ตั้งค่าวันเป็นวันไม่ทำงาน, หรือสืบทอดค่าเริ่มต้นจากปฏิทินแม่.

## วิธีกำหนดวันทำงานใน MS Project?

คุณกำหนดวันทำงานโดยการเพิ่มวัตถุ `WeekDay` ลงในคอลเลกชัน `WeekDays` ของปฏิทิน. แต่ละ `WeekDay` ระบุว่ามันเป็นวันทำงานหรือไม่และช่วงเวลาที่ถือเป็นเวลาทำงาน. ตัวอย่างเช่น, เพื่อทำให้วันเสาร์เป็นครึ่งวัน, เพิ่ม `WeekDay` ที่มี `WorkingTime` เดียวจาก 10:00 ถึง 14:00. API จะอัปเดตการคำนวณตารางเวลาโครงการโดยอัตโนมัติ.

## วิธีตั้งค่าชั่วโมงทำงานใน MS Project?

ตั้งค่าชั่วโมงทำงานโดยการสร้างช่วง `WorkingTime` หนึ่งหรือหลายช่วงสำหรับแต่ละ `WeekDay`. `WorkingTime` รับค่าชั่วโมงเริ่ม, นาทีเริ่ม, ชั่วโมงสิ้นสุด, และนาทีสิ้นสุด. คุณสามารถกำหนดหลายช่วงให้กับวันเดียวเพื่อจำลองกะงานแยก (เช่น 08:00‑12:00 และ 13:00‑17:00). หลังจากกำหนดวันทำงานทั้งหมด, เรียก `project.save(...)` เพื่อบันทึกการเปลี่ยนแปลง.

## ทำไมต้องใช้ Aspose.Tasks for Java เพื่อกำหนดวันทำงาน?

- **การควบคุม API อย่างเต็มรูปแบบ** – ไม่มีข้อจำกัดของ UI; คุณสามารถสร้าง, แก้ไข หรือ ลบรายการวันทำงานโดยโปรแกรมได้.  
- **ข้ามแพลตฟอร์ม** – ทำงานบนสภาพแวดล้อมที่รองรับ JVM ใด ๆ ตั้งแต่แอปเดสก์ท็อปจนถึงบริการคลาวด์.  
- **ความแม่นยำ** – ตั้งเวลาทำงานที่แตกต่างสำหรับแต่ละวันทำงาน, เพิ่มข้อยกเว้นสำหรับวันหยุด, และซิงโครไนซ์ปฏิทินข้ามหลายโครงการ.  
- **ประสิทธิภาพ** – ประมวลผลโครงการที่มีงานมากกว่า 500 งานและปฏิทินที่มีมากกว่า 100 สัปดาห์โดยไม่ต้องโหลด UI ทั้งหมด, ทำให้เวลาการแปลงต่ำกว่า 2 วินาทีบนเซิร์ฟเวอร์มาตรฐาน 2.5 GHz (อ้างอิงจากการทดสอบของ Aspose).  
- **การสนับสนุนรูปแบบที่หลากหลาย** – Aspose.Tasks รองรับ API ที่เกี่ยวกับปฏิทินกว่า 30 รายการและสามารถนำเข้า/ส่งออกไปยังไฟล์รูปแบบมากกว่า 20 แบบ, ทำให้การบูรณาการกับสายงานข้อมูลโครงการที่มีอยู่เป็นไปอย่างราบรื่น.

## ข้อกำหนดเบื้องต้น
- ติดตั้ง Java 8 หรือสูงกว่า.  
- ไลบรารี Aspose.Tasks for Java (ดาวน์โหลดจากเว็บไซต์ Aspose หรือเพิ่มผ่าน Maven/Gradle).  
- ไลเซนส์ Aspose.Tasks ที่ถูกต้อง (ไลเซนส์ทดลองใช้ได้สำหรับการเรียนรู้).  

## จัดการคุณสมบัติปฏิทิน MS Project ใน Aspose.Tasks

ปลดล็อกศักยภาพเต็มของการจัดการคุณสมบัติปฏิทิน MS Project ใน Java ด้วย Aspose.Tasks. บทแนะนำของเรานำคุณผ่านความซับซ้อนของการจัดการปฏิทิน, ให้ข้อมูลเชิงลึกที่มีค่าเกี่ยวกับการปรับแต่งและการเพิ่มประสิทธิภาพ. ตั้งแต่การปรับชั่วโมงทำงานจนถึงการกำหนดวันที่พิเศษ, คุณจะเชี่ยวชาญทุกอย่าง.

พร้อมที่จะควบคุมไทม์ไลน์ของโครงการของคุณ? [Explore the tutorial here](./properties/)

## สร้างปฏิทิน MS Project ด้วย Aspose.Tasks

ทำให้การจัดการโครงการของคุณง่ายขึ้นด้วยการสร้างปฏิทิน MS Project ด้วย Aspose.Tasks for Java. บทแนะนำของเราทำให้กระบวนการง่ายดาย, ทำให้คุณสามารถตั้งค่าปฏิทินที่เหมาะกับความต้องการเฉพาะของโครงการของคุณ. ก้าวแรกสู่การวางแผนและการจัดองค์กรที่มีประสิทธิภาพ.

พร้อมที่จะสร้างปฏิทินอย่างง่ายดาย? [Check out the tutorial](./create/)

## กำหนดวันทำงานในปฏิทินด้วย Aspose.Tasks

ปรับแต่งปฏิทิน MS Project ของคุณโดยการกำหนดวันทำงานด้วย Aspose.Tasks for Java. บทแนะนำนี้จะพาคุณผ่านขั้นตอนการปรับวันทำงานและช่วงเวลา, ให้ความยืดหยุ่นที่คุณต้องการสำหรับการจัดการโครงการที่ประสบความสำเร็จ. ทำให้ปฏิทินของคุณทำงานตามที่คุณต้องการ.

พร้อมที่จะกำหนดวันทำงานอย่างง่ายดาย? [Get started here](./define-weekdays/)

ขณะที่คุณสำรวจบทแนะนำเหล่านี้, คุณจะพบหัวข้อเพิ่มเติมที่ครอบคลุมการสกัดชั่วโมงทำงาน, การสร้างปฏิทินมาตรฐาน, การอ่านสัปดาห์ทำงาน, และการอัปเดตปฏิทินเป็นรูปแบบ MPP. แต่ละบทแนะนำถูกออกแบบเพื่อให้คุณได้รับความรู้เชิงปฏิบัติ, ทำให้คุณสามารถนำไปใช้กับโครงการ Java ของคุณได้โดยตรง.

## ดึงชั่วโมงทำงานจากปฏิทินด้วย Aspose.Tasks

ทำให้การจัดการโครงการของคุณง่ายขึ้นโดยการสกัดชั่วโมงทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks for Java. บทแนะนำนี้จะสอนคุณให้มีทักษะที่จำเป็นเพื่อเพิ่มประสิทธิภาพไทม์ไลน์ของโครงการของคุณอย่างมีประสิทธิภาพ.

พร้อมที่จะสกัดชั่วโมงทำงานอย่างง่ายดาย? [Explore the tutorial](./working-hours/)

## สร้างปฏิทินมาตรฐานใน Aspose.Tasks

เพิ่มศักยภาพการจัดการโครงการของคุณโดยเรียนรู้วิธีสร้างปฏิทิน MS Project มาตรฐานใน Java ด้วย Aspose.Tasks. บทแนะนำแบบขั้นตอนนี้ทำให้คุณสามารถนำแนวทางมาตรฐานไปใช้กับไทม์ไลน์ของโครงการของคุณได้.

พร้อมที่จะสร้างปฏิทินมาตรฐาน? [Check out the tutorial](./make-standard/)

## อ่านสัปดาห์ทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks

รับข้อมูลเชิงลึกอย่างครบถ้วนเกี่ยวกับการอ่านสัปดาห์ทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks for Java. บทแนะนำนี้ให้คำแนะนำโดยละเอียด, ช่วยให้คุณจัดการตารางเวลาโครงการของคุณได้อย่างมีประสิทธิภาพ.

พร้อมที่จะอ่านสัปดาห์ทำงานอย่างง่ายดาย? [Get started here](./read-work-weeks/)

## อัปเดตปฏิทิน MS Project เป็นรูปแบบ MPP ด้วย Aspose.Tasks

อัปเดตปฏิทิน MS Project เป็นรูปแบบ MPP อย่างไม่มีรอยต่อด้วย Aspose.Tasks for Java. บทแนะนำนี้ให้วิธีการที่ราบรื่นเพื่อให้ข้อมูลโครงการของคุณอยู่ในรูปแบบที่เหมาะสมสำหรับความเข้ากันได้สูงสุด.

พร้อมที่จะอัปเดตปฏิทินเป็นรูปแบบ MPP? [Explore the tutorial](./update-to-mpp/)

ปลดล็อกศักยภาพเต็มของ Aspose.Tasks for Java และยกระดับทักษะการจัดการโครงการของคุณ. แต่ละบทแนะนำออกแบบมาสำหรับนักพัฒนาทุกระดับ, เพื่อให้ประสบการณ์การเรียนรู้ราบรื่น. ลงมือทำและปฏิวัติการจัดการโครงการ Java ของคุณวันนี้!

## บทแนะนำเกี่ยวกับปฏิทิน
### [จัดการคุณสมบัติปฏิทิน MS Project ใน Aspose.Tasks](./properties/)
เรียนรู้วิธีจัดการคุณสมบัติปฏิทิน MS Project ใน Java ด้วย Aspose.Tasks. ให้คำแนะนำทีละขั้นตอนสำหรับการใช้ปฏิทินในแอปพลิเคชัน Java ของคุณ.
### [สร้างปฏิทิน MS Project ด้วย Aspose.Tasks](./create/)
เรียนรู้วิธีสร้างปฏิทิน MS Project ด้วย Aspose.Tasks for Java. ทำให้การจัดการโครงการเป็นเรื่องง่าย.
### [กำหนดวันทำงานในปฏิทินด้วย Aspose.Tasks](./define-weekdays/)
เรียนรู้วิธีกำหนดวันทำงานในปฏิทิน MS Project ด้วย Aspose.Tasks for Java. ปรับแต่งวันทำงานและช่วงเวลาได้อย่างง่ายดาย.
### [ดึงชั่วโมงทำงานจากปฏิทินด้วย Aspose.Tasks](./working-hours/)
สกัดชั่วโมงทำงานจากปฏิทิน MS Project อย่างง่ายด้วย Aspose.Tasks for Java. ทำให้ภาระงานการจัดการโครงการง่ายขึ้น.
### [สร้างปฏิทินมาตรฐานใน Aspose.Tasks](./make-standard/)
เรียนรู้วิธีสร้างปฏิทิน MS Project มาตรฐานใน Java ด้วย Aspose.Tasks. เพิ่มศักยภาพการจัดการโครงการของคุณด้วยบทแนะนำขั้นตอนนี้.
### [อ่านสัปดาห์ทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks](./read-work-weeks/)
เรียนรู้วิธีอ่านสัปดาห์ทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks for Java. รับคำแนะนำทีละขั้นตอนในบทแนะนำที่ครอบคลุมนี้.
### [อัปเดตปฏิทิน MS Project เป็นรูปแบบ MPP อย่างง่ายดายโดยใช้ Aspose.Tasks for Java](./update-to-mpp/)
เรียนรู้วิธีอัปเดตปฏิทิน MS Project เป็นรูปแบบ MPP อย่างง่ายดายโดยใช้ Aspose.Tasks for Java.

## คำถามที่พบบ่อย

**Q: ฉันสามารถกำหนดชั่วโมงทำงานที่แตกต่างสำหรับแต่ละวันทำงานได้หรือไม่?**  
A: ได้. Aspose.Tasks ให้คุณตั้งเวลาเริ่มและสิ้นสุดแยกตามวันจันทร์ถึงอาทิตย์.

**Q: ฉันจะจัดการวันหยุดหรือวันไม่ทำงานอย่างไร?**  
A: หลังจากกำหนดวันทำงาน, คุณสามารถเพิ่มข้อยกเว้น (วันที่) เพื่อระบุวันหยุดหรือช่วงเวลาที่ไม่ทำงานตามต้องการ.

**Q: สามารถคัดลอกการกำหนดวันทำงานจากปฏิทินหนึ่งไปยังอีกปฏิทินได้หรือไม่?**  
A: แน่นอน. คุณสามารถดึงวัตถุ `WeekDay` จากปฏิทินที่มีอยู่และเพิ่มลงในอินสแตนซ์ปฏิทินอื่นได้.

**Q: จำเป็นต้องรีโหลดโครงการหลังจากอัปเดตวันทำงานหรือไม่?**  
A: ไม่จำเป็น. การเปลี่ยนแปลงจะถูกนำไปใช้โดยตรงกับอ็อบเจ็กต์ `Project` ในหน่วยความจำ; เพียงบันทึกโครงการเมื่อเสร็จสิ้น.

**Q: ต้องใช้เวอร์ชัน Aspose.Tasks ใดสำหรับการจัดการวันทำงาน?**  
A: ทุกเวอร์ชันล่าสุด (20.10 ขึ้นไป) รองรับ API การจัดการวันทำงานเต็มรูปแบบ. เราแนะนำให้ใช้รุ่นเสถียรล่าสุดเพื่อประสิทธิภาพที่ดีที่สุด.

**อัปเดตล่าสุด:** 2026-11-19  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determine Working Days & Working Hours with Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}