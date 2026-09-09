---
date: 2026-09-09
description: เรียนรู้วิธีระบุงานข้ามโครงการโดยใช้ Aspose.Tasks for Java. สำรวจการบูรณาการที่ราบรื่น
  การจัดการที่มีประสิทธิภาพ และตัวอย่างจากโลกจริง.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: ระบุงานข้ามโครงการใน Aspose.Tasks
og_description: ระบุงานข้ามโครงการใน Aspose.Tasks for Java. เรียนรู้วิธีตั้งค่า document
  directory, ดึง task IDs, และจัดการ linked projects อย่างมีประสิทธิภาพ.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: ระบุงานข้ามโครงการใน Aspose.Tasks – คู่มือ Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: ระบุงานข้ามโครงการใน Aspose.Tasks
url: /th/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ระบุงานข้ามโครงการใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีการระบุงานข้ามโครงการ** ด้วย Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะดูแลพอร์ตโฟลิโอของกำหนดการที่พึ่งพากันหรือจำเป็นต้องตรวจสอบการพึ่งพาภายนอก ขั้นตอนต่อไปนี้จะแสดงวิธีการค้นหางานที่อ้างอิงไฟล์โครงการอื่น ดึงตัวระบุของพวกมัน และทำงานกับมันโดยโปรแกรม

## คำตอบอย่างรวดเร็ว
- **“identify cross project tasks” หมายถึงอะไร?** หมายถึงการค้นหางานที่อ้างอิงหรือพึ่งพางานในไฟล์โครงการอื่น.  
- **เมธอดใดที่พิมพ์ ID ของงาน?** ใช้ `externalTask.get(Tsk.ID)` เพื่อพิมพ์ ID ของงาน.  
- **ฉันจะตั้งค่าไดเรกทอรีเอกสารอย่างไร?** กำหนดเส้นทางโฟลเดอร์ให้กับตัวแปร `String` (เช่น `dataDir`).  
- **คุณสมบัติใดที่ดึงงานโดย UID?** เรียก `getChildren().getByUid(yourUid)`.  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์.

## “identify cross project tasks” คืออะไร?
การระบุงานข้ามโครงการช่วยให้คุณติดตามความสัมพันธ์ระหว่างงานที่กระจายอยู่ในหลายไฟล์ Microsoft Project โดยการค้นหางานที่อ้างอิงหรือพึ่งพากำหนดการภายนอก คุณสามารถเข้าใจว่ารายการงานทำงานร่วมกันอย่างไรข้ามขอบเขตโครงการ ป้องกันการทำงานซ้ำซ้อน และรักษาไทม์ไลน์ที่แม่นยำ ความสามารถนี้เป็นสิ่งจำเป็นสำหรับพอร์ตโฟลิโอขนาดใหญ่ที่งานถูกแชร์หรือพึ่งพากำหนดการภายนอก

## ทำไมต้องใช้ Aspose.Tasks สำหรับ Java?
Aspose.Tasks สำหรับ Java รองรับ **รูปแบบเข้าและออกกว่า 50 แบบ** (รวมถึง MPP, MPX, XML, และ CSV) และสามารถประมวลผลโครงการที่มี **งานสูงสุด 10,000 งาน** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ไลบรารีทำงานบนแพลตฟอร์มที่เข้ากันได้กับ JVM ใด ๆ ไม่ต้องติดตั้ง Microsoft Project และให้การเข้าถึง API อย่างเต็มรูปแบบต่อ ID, UID, External ID, และเมตาดาต้าเชื่อมโยง

## ข้อกำหนดเบื้องต้น
- สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (JDK 8 หรือสูงกว่า).  
- ติดตั้ง Aspose.Tasks สำหรับ Java คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/tasks/java/)**.  
- ไฟล์ใบอนุญาต Aspose.Tasks ที่ถูกต้อง หากคุณวางแผนจะรันโค้ดในสภาพการผลิต.

## นำเข้าแพ็กเกจ
คลาส `Project` แทนไฟล์ Microsoft Project, `Task` แทนงานแต่ละรายการ, และ `Tsk` ให้ค่าคงที่ของฟิลด์งาน.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
สตริง `dataDir` เก็บเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ `.mpp` ของคุณ.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: โหลดโครงการภายนอก
`Project externalProject` โหลดไฟล์โครงการภายนอกที่ระบุเพื่อทำการตรวจสอบ.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## ขั้นตอนที่ 3: ดึงงานภายนอกโดย uid
`externalProject.getChildren().getByUid(uid)` ดึงงานจากคอลเลกชันงานของโครงการภายนอกโดยใช้ตัวระบุที่ไม่ซ้ำกัน.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## ขั้นตอนที่ 4: พิมพ์ ID ของงาน (กรณีใช้งานหลัก)
`externalTask.get(Tsk.ID)` คืนค่า ID ภายในที่ Aspose.Tasks กำหนดให้กับงานที่ระบุ.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## ขั้นตอนที่ 5: พิมพ์ ID งานต้นฉบับ (ภายนอก)
`externalTask.get(Tsk.ExternalID)` ดึง ID ดั้งเดิมของงานตามที่กำหนดในไฟล์โครงการต้นทาง.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

ทำซ้ำขั้นตอนข้างต้นสำหรับงานเพิ่มเติมใด ๆ ที่คุณต้องการติดตามข้ามโครงการ.

## ปัญหาทั่วไปและเคล็ดลับ
- **ข้อผิดพลาดของเส้นทาง** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ที่เหมาะสม (`/` หรือ `\\`).  
- **ไม่พบ UID** – ยืนยันว่า UID มีอยู่ในโครงการภายนอก; ใช้ `externalProject.getRootTask().getChildren().size()` เพื่อแสดง UID ที่มี.  
- **ข้อยกเว้นใบอนุญาต** – การไม่มีหรือใบอนุญาตไม่ถูกต้องจะทำให้เกิดข้อยกเว้นใบอนุญาตในขณะรัน.  
- **โครงการขนาดใหญ่** – สำหรับโครงการที่มีงานมากกว่า 5,000 งาน, พิจารณาใช้ `ProjectReader` พร้อมกับแฟล็ก `LoadOptions` เพื่อสตรีมข้อมูลและลดการใช้หน่วยความจำ.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: ใช่, Aspose.Tasks รองรับหลายภาษา รวมถึง Java, .NET, และอื่น ๆ.

**ถาม: ฉันจะหาเอกสารรายละเอียดสำหรับ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
A: ดูเอกสาร **[ที่นี่](https://reference.aspose.com/tasks/java/)**.

**ถาม: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks สำหรับ Java หรือไม่?**  
A: ใช่, คุณสามารถรับการทดลองใช้ฟรี **[ที่นี่](https://releases.aspose.com/)**.

**ถาม: ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร?**  
A: รับใบอนุญาตชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)**.

**ถาม: ต้องการความช่วยเหลือหรือมีคำถามเฉพาะ?**  
A: เยี่ยมชมฟอรั่มสนับสนุน Aspose.Tasks **[ที่นี่](https://forum.aspose.com/c/tasks/15)**.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างการเชื่อมโยงงานการจัดการโครงการใน Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [ตั้งค่าวันเริ่มต้นโครงการและจัดการงานพาเรนท์และชิลด์ใน Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [สร้างโครงการ MPP ด้วย Java – เปลี่ยนความคืบหน้าของงานด้วย Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}