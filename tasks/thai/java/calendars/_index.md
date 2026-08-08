---
date: 2026-08-08
description: เรียนรู้วิธีกำหนดวันทำงานในปฏิทิน MS Project ด้วย Aspose.Tasks สำหรับ
  Java คู่มือนี้จะแสดงวิธีแก้ไขปฏิทิน MS Project, สร้าง custom calendar Java, และ
  schedule working days อย่างมีประสิทธิภาพ
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: ปฏิทิน
og_description: เรียนรู้วิธีกำหนดวันทำงานในปฏิทิน MS Project ด้วย Aspose.Tasks สำหรับ
  Java. ควบคุม custom calendar Java, แก้ไขปฏิทิน MS Project, และ schedule working
  days อย่างมีประสิทธิภาพ
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: วิธีกำหนดวันทำงานในปฏิทิน MS Project – Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: วิธีกำหนดวันทำงานในปฏิทิน MS Project – Aspose.Tasks Java
url: /th/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปฏิทิน

## บทนำ

หากคุณเป็นนักพัฒนา Java ที่ต้องการ **define weekdays** ในตารางโครงการของคุณ คุณมาถูกที่แล้ว ในศูนย์รวมนี้เรารวบรวมบทเรียน Aspose.Tasks for Java ทั้งหมดที่แสดง **how to define weekdays** ภายในปฏิทิน MS Project ปรับชั่วโมงทำงาน และทำให้ไทม์ไลน์ของคุณชัดเจน ไม่ว่าคุณจะกำลังสร้างเอนจินการจัดตารางใหม่หรือปรับแผนที่มีอยู่แล้ว การเข้าใจการกำหนดวันทำงานจะให้การควบคุมที่แม่นยำต่อรูปแบบวันทำงาน, วันหยุด, และกะงานที่กำหนดเอง คู่มือนี้ยังอธิบาย **how to modify MS Project calendar** ผ่านโปรแกรม เพื่อให้คุณสามารถสร้างปฏิทินอัตโนมัติในหลายโครงการได้

## คำตอบอย่างรวดเร็ว
- **วัตถุประสงค์หลักของการกำหนดวันทำงานคืออะไร?**  
  เพื่อบอก MS Project ว่าวันใดเป็นวันทำงานและชั่วโมงทำงานของวันนั้นเป็นเท่าใด
- **ไลบรารีใดจัดการการกำหนดวันทำงานใน Java?**  
  Aspose.Tasks for Java ให้ API ที่เป็น fluent สำหรับการจัดการปฏิทิน
- **ฉันต้องมีไลเซนส์หรือไม่?**  
  ไลเซนส์ประเมินผลฟรีใช้ได้สำหรับการทดสอบ; ไลเซนส์เชิงพาณิชย์จำเป็นสำหรับการใช้งานในผลิตภัณฑ์
- **ฉันสามารถกำหนดหลายปฏิทินสำหรับทีมต่าง ๆ ได้หรือไม่?**  
  ได้ – แต่ละโครงการสามารถมีหลายปฏิทิน, แต่ละปฏิทินมีการตั้งค่าวันทำงานของตนเอง
- **มีโครงการตัวอย่างให้เริ่มต้นหรือไม่?**  
  บทเรียน “Define Weekdays in Calendar” ที่ลิงก์ด้านล่างมีตัวอย่างพร้อมรัน

## ฉันจะกำหนดวันทำงานในปฏิทิน MS Project อย่างไร

คลาส `Project` แทนไฟล์ MS Project และให้การเข้าถึงโครงสร้างข้อมูลของมัน `Calendar` เก็บการกำหนดเวลาทำงานและข้อยกเว้นสำหรับโครงการ โหลดโครงการของคุณด้วย `new Project("myproject.mpp")`, ดึง (หรือสร้าง) อ็อบเจ็กต์ `Calendar`, แล้วเรียก `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. บรรทัดเดียวนี้สร้างรายการวันทำงานวันจันทร์ที่มีกะ 8 ชั่วโมง ทำซ้ำสำหรับวันอื่น ๆ และสุดท้ายบันทึกโครงการด้วย `project.save("updated.mpp")`. รูปแบบสั้นนี้ทำให้คุณสามารถกำหนด, แก้ไข, หรือ ลบวันทำงานได้ด้วยไม่กี่คำสั่ง API, ลดความจำเป็นในการโต้ตอบ UI ด้วยตนเอง

## WeekDay object คืออะไร

อ็อบเจ็กต์ `WeekDay` แทนรายการวันในสัปดาห์หนึ่งรายการภายในปฏิทิน Aspose.Tasks, เก็บสถานะการทำงานและช่วงเวลาทำงาน คุณสามารถกำหนดเวลาเริ่ม/สิ้นสุด, ตั้งให้เป็นวันไม่ทำงาน, หรือแนบช่วงเวลาโอเวอร์ไทม์ได้ สามารถมีหลายช่วง `WorkingTime` เพื่อจำลองกะงานแยกส่วน, และรองรับแฟล็กสำหรับวันทำงานเริ่มต้น ใช้ API `WeekDay` เพื่อเปิดหรือปิดวัน, กำหนดชั่วโมงปกติ, หรือระบุกฎโอเวอร์ไทม์สำหรับสถานการณ์การจัดตารางขั้นสูง

## ทำไมต้องใช้ Aspose.Tasks for Java เพื่อกำหนดวันทำงาน

- **Full API control** – ไม่มีข้อจำกัดของ UI; คุณสามารถสร้าง, แก้ไข, หรือ ลบรายการวันทำงานได้โดยโปรแกรม  
- **Cross‑platform** – ทำงานบนสภาพแวดล้อมที่รองรับ JVM ใด ๆ, ตั้งแต่แอปเดสก์ท็อปจนถึงบริการคลาวด์  
- **Precision** – ตั้งเวลาทำงานที่แตกต่างกันสำหรับแต่ละวันทำงาน, เพิ่มข้อยกเว้นสำหรับวันหยุด, และซิงค์ปฏิทินข้ามหลายโครงการ  
- **Performance** – ประมวลผลโครงการที่มีงาน 500 + งานและปฏิทินที่มี 100 + สัปดาห์โดยไม่ต้องโหลด UI ทั้งหมด, ทำให้เวลาแปลงต่ำกว่า 2 วินาทีบนเซิร์ฟเวอร์ 2.5 GHz มาตรฐาน (อ้างอิงจากการทดสอบของ Aspose)

## ข้อกำหนดเบื้องต้น
- ติดตั้ง Java 8 หรือสูงกว่า  
- ไลบรารี Aspose.Tasks for Java (ดาวน์โหลดจากเว็บไซต์ Aspose หรือเพิ่มผ่าน Maven/Gradle)  
- ไลเซนส์ Aspose.Tasks ที่ถูกต้อง (ไลเซนส์ประเมินผลใช้ได้สำหรับการเรียนรู้)

## จัดการคุณสมบัติของปฏิทิน MS Project ใน Aspose.Tasks

ปลดล็อกศักยภาพเต็มรูปแบบของการจัดการคุณสมบัติปฏิทิน MS Project ใน Java ด้วย Aspose.Tasks บทเรียนของเราจะพาคุณผ่านรายละเอียดการจัดการปฏิทิน, ให้ข้อมูลเชิงลึกเกี่ยวกับการปรับแต่งและการเพิ่มประสิทธิภาพ ตั้งแต่การปรับชั่วโมงทำงานจนถึงการกำหนดวันที่พิเศษ, คุณจะเชี่ยวชาญทุกอย่าง

พร้อมที่จะควบคุมไทม์ไลน์โครงการของคุณหรือยัง? [Explore the tutorial here](./properties/)

## สร้างปฏิทิน MS Project ด้วย Aspose.Tasks

ทำให้การจัดการโครงการของคุณเป็นเรื่องง่ายด้วยการสร้างปฏิทิน MS Project ด้วย Aspose.Tasks for Java บทเรียนของเราจะทำให้กระบวนการง่ายขึ้น, เพื่อให้คุณตั้งค่าปฏิทินที่เหมาะกับความต้องการเฉพาะของโครงการของคุณ ก้าวแรกสู่การวางแผนและการจัดองค์กรที่มีประสิทธิภาพ

พร้อมสร้างปฏิทินอย่างง่ายดายหรือยัง? [Check out the tutorial](./create/)

## กำหนดวันทำงานในปฏิทินด้วย Aspose.Tasks

ปรับแต่งปฏิทิน MS Project ของคุณโดยการกำหนดวันทำงานด้วย Aspose.Tasks for Java บทเรียนนี้จะนำคุณผ่านขั้นตอนการกำหนดวันทำงานและเวลา, ให้ความยืดหยุ่นที่จำเป็นสำหรับการจัดการโครงการที่ประสบความสำเร็จ ทำให้ปฏิทินทำงานตามที่คุณต้องการ

พร้อมกำหนดวันทำงานอย่างง่ายดายหรือยัง? [Get started here](./define-weekdays/)

ขณะที่คุณสำรวจบทเรียนเหล่านี้, คุณจะพบหัวข้อเพิ่มเติมเกี่ยวกับการสกัดชั่วโมงทำงาน, การสร้างปฏิทินมาตรฐาน, การอ่านสัปดาห์ทำงาน, และการอัปเดตปฏิทินเป็นรูปแบบ MPP. แต่ละบทเรียนถูกออกแบบเพื่อให้คุณได้รับความรู้เชิงปฏิบัติ, เพื่อให้คุณสามารถนำไปใช้กับโครงการ Java ของคุณได้โดยตรง

## ดึงชั่วโมงทำงานจากปฏิทินด้วย Aspose.Tasks

ทำให้การจัดการโครงการของคุณง่ายขึ้นด้วยการสกัดชั่วโมงทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks for Java. บทเรียนนี้จะสอนคุณวิธีเพิ่มประสิทธิภาพไทม์ไลน์โครงการอย่างมีประสิทธิผล

พร้อมสกัดชั่วโมงทำงานอย่างง่ายดายหรือยัง? [Explore the tutorial](./working-hours/)

## สร้างปฏิทินมาตรฐานใน Aspose.Tasks

เพิ่มศักยภาพการจัดการโครงการของคุณโดยเรียนรู้วิธีสร้างปฏิทิน MS Project มาตรฐานใน Java ด้วย Aspose.Tasks. บทเรียนขั้นตอนต่อขั้นตอนนี้ทำให้คุณสามารถนำแนวทางมาตรฐานไปใช้กับไทม์ไลน์โครงการของคุณได้

พร้อมสร้างปฏิทินมาตรฐานหรือยัง? [Check out the tutorial](./make-standard/)

## อ่านสัปดาห์ทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks

รับข้อมูลเชิงลึกอย่างครบถ้วนในการอ่านสัปดาห์ทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks for Java. บทเรียนนี้ให้คำแนะนำโดยละเอียด, ช่วยให้คุณจัดการตารางโครงการได้อย่างมีประสิทธิภาพ

พร้อมอ่านสัปดาห์ทำงานอย่างง่ายดายหรือยัง? [Get started here](./read-work-weeks/)

## อัปเดตปฏิทิน MS Project เป็นรูปแบบ MPP ด้วย Aspose.Tasks

อัปเดตปฏิทิน MS Project เป็นรูปแบบ MPP อย่างไม่มีความยุ่งยากด้วย Aspose.Tasks for Java. บทเรียนนี้ให้วิธีการที่ราบรื่นเพื่อให้ข้อมูลโครงการของคุณอยู่ในรูปแบบที่เหมาะสมสำหรับความเข้ากันได้สูงสุด

พร้อมอัปเดตปฏิทินเป็นรูปแบบ MPP หรือยัง? [Explore the tutorial](./update-to-mpp/)

ปลดล็อกศักยภาพเต็มที่ของ Aspose.Tasks for Java และยกระดับทักษะการจัดการโครงการของคุณ. แต่ละบทเรียนออกแบบมาสำหรับนักพัฒนาทุกระดับ, เพื่อให้ประสบการณ์การเรียนรู้ราบรื่น. เริ่มต้นและปฏิวัติการจัดการโครงการ Java ของคุณวันนี้!

## บทเรียนปฏิทิน
### [จัดการคุณสมบัติของปฏิทิน MS Project ใน Aspose.Tasks](./properties/)
เรียนรู้วิธีจัดการคุณสมบัติของปฏิทิน MS Project ใน Java ด้วย Aspose.Tasks. ให้คำแนะนำขั้นตอนต่อขั้นตอนสำหรับปฏิทินในแอปพลิเคชัน Java ของคุณ
### [สร้างปฏิทิน MS Project ด้วย Aspose.Tasks](./create/)
เรียนรู้วิธีสร้างปฏิทิน MS Project ด้วย Aspose.Tasks for Java. ทำให้การจัดการโครงการเป็นเรื่องง่าย
### [กำหนดวันทำงานในปฏิทินด้วย Aspose.Tasks](./define-weekdays/)
เรียนรู้วิธีกำหนดวันทำงานในปฏิทิน MS Project ด้วย Aspose.Tasks for Java. ปรับแต่งวันทำงานและเวลาอย่างไม่มีความยุ่งยาก
### [ดึงชั่วโมงทำงานจากปฏิทินด้วย Aspose.Tasks](./working-hours/)
สกัดชั่วโมงทำงานจากปฏิทิน MS Project อย่างง่ายดายด้วย Aspose.Tasks for Java. ทำให้ภาระงานการจัดการโครงการง่ายขึ้น
### [สร้างปฏิทินมาตรฐานใน Aspose.Tasks](./make-standard/)
เรียนรู้วิธีสร้างปฏิทิน MS Project มาตรฐานใน Java ด้วย Aspose.Tasks. เพิ่มศักยภาพการจัดการโครงการของคุณด้วยบทเรียนขั้นตอนต่อขั้นตอนนี้
### [อ่านสัปดาห์ทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks](./read-work-weeks/)
เรียนรู้วิธีอ่านสัปดาห์ทำงานจากปฏิทิน MS Project ด้วย Aspose.Tasks for Java. รับคำแนะนำขั้นตอนต่อขั้นตอนในบทเรียนที่ครอบคลุมนี้
### [อัปเดตปฏิทิน MS Project เป็นรูปแบบ MPP ด้วย Aspose.Tasks](./update-to-mpp/)
เรียนรู้วิธีอัปเดตปฏิทิน MS Project เป็นรูปแบบ MPP อย่างไม่มีความยุ่งยากด้วย Aspose.Tasks for Java

## คำถามที่พบบ่อย

**Q: ฉันสามารถกำหนดชั่วโมงทำงานที่แตกต่างกันสำหรับแต่ละวันทำงานได้หรือไม่?**  
A: ได้. Aspose.Tasks ให้คุณตั้งเวลาเริ่มและสิ้นสุดแยกตามวันจันทร์ถึงอาทิตย์

**Q: ฉันจะจัดการกับวันหยุดหรือวันไม่ทำงานอย่างไร?**  
A: หลังจากกำหนดวันทำงานแล้ว, คุณสามารถเพิ่มข้อยกเว้น (วันที่) เพื่อระบุวันหยุดหรือช่วงเวลาที่ไม่ทำงานตามต้องการ

**Q: สามารถคัดลอกการกำหนดวันทำงานจากปฏิทินหนึ่งไปยังอีกปฏิทินได้หรือไม่?**  
A: แน่นอน. คุณสามารถดึงอ็อบเจ็กต์ `WeekDay` จากปฏิทินที่มีอยู่แล้วและเพิ่มเข้าไปในอินสแตนซ์ปฏิทินอื่น

**Q: จำเป็นต้องโหลดโครงการใหม่หลังจากอัปเดตวันทำงานหรือไม่?**  
A: ไม่จำเป็น. การเปลี่ยนแปลงจะถูกนำไปใช้โดยตรงกับอ็อบเจ็กต์ `Project` ในหน่วยความจำ; เพียงบันทึกโครงการเมื่อเสร็จสิ้น

**Q: ต้องใช้เวอร์ชัน Aspose.Tasks ใดสำหรับการจัดการวันทำงาน?**  
A: ทุกเวอร์ชันล่าสุด (20.10 ขึ้นไป) รองรับ API การจัดการวันทำงานเต็มรูปแบบ. เราแนะนำให้ใช้รุ่นเสถียรล่าสุดเพื่อประสิทธิภาพที่ดีที่สุด

---

**Last updated:** 2026-08-08  
**Tested with:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determine Working Days & Working Hours with Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}