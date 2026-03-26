---
date: 2025-12-20
description: เรียนรู้วิธีการปรับคุณภาพ JPEG และส่งออกภาพ JPEG จากไฟล์ Microsoft Project
  ด้วย Aspose.Tasks สำหรับ Java.
linktitle: Save Project As JPEG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ปรับคุณภาพ JPEG เมื่อบันทึก MS Project เป็น JPEG
url: /th/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปรับคุณภาพ JPEG เมื่อบันทึก MS Project เป็น JPEG ด้วย Aspose.Tasks

## การแนะนำ
ในบทแนะนำนี้คุณจะได้ ** ปรับคุณภาพ JPEG** หลังจากที่บันทึกไฟล์ Microsoft Project เป็นภาพ JPEG เท่านั้น Aspose.Tasks สำหรับ Java ความสามารถนี้มีประโยชน์สำหรับการบันทึกภาพที่ชัดเจนการฝังภาพโครงการลงในการนำเสนอหรือเพียงแค่ส่งออกไฟล์ JPEG ด้วยระดับรายละเอียดอีกครั้ง

## คำตอบด่วน
- **“ปรับคุณภาพ JPEG” ทำอะไร?** มันให้คุณควบคุมระดับของ JPEG ที่ส่งออกเพื่อให้สมดุลระหว่างขนาดไฟล์และประวัติศาสตร์ของภาพ
- **ไลบรารีที่ทำมันคืออะไร?** Aspose.Tasks for Java มี API ที่ไม่จำเป็นต้องใช้ไฟล์ Project เป็น JPEG
- ** ปรับแต่งไลเซนส์หรือไม่?** การจัดทำหลังคาประเมินผลได้; ควบคุมไลส์เซนส์โดยตรงจริง
- **สามารถติดตั้งคุณภาพในโค้ดได้หรือไม่** ได้, ใช้เมธอด `ImageSaveOptions.setJpegQuality(int)` (ช่วง 0-100)
- ** ต้องการเร็วหรือไม่?** สำหรับไฟล์โครงการทั่วไปเป็น JPEG เพียงเท่านั้นบนฮาร์ดแวร์สมัยใหม่

## “ปรับคุณภาพ JPEG” คืออะไร?
คุณภาพ JPEG รูปแบบปัจจัยพื้นฐานบางครั้งที่ใช้เมื่อบันทึกรูปภาพในรูปแบบ JPEG ส่วนใหญ่ที่เพิ่ม (ค่าที่ใกล้ 100) จะรักษารายละเอียดเพิ่มเติมแต่ไฟล์จะใหญ่ขึ้น, คุณภาพที่ต่ำกว่าจะลดขนาดไฟล์แต่เสียของภาพ

## เหตุใดจึงต้องใช้ Aspose.Tasks เพื่อส่งออก JPEG
Aspose.Tasks ช่วยให้ไม่สามารถขึ้นกับแพลตฟอร์มในการเรนเดอร์ในระดับ Gantt, องค์ประกอบทรัพยากร, และภาพโครงการอื่นๆ ที่จะไปถึงเป็นไฟล์ภาพมันช่วยขจัดเนื้อหาในอินเทอร์เฟซของหน้าจออย่างละเอียดและรับประกันผลลัพธ์ที่เป็นส่วนสำคัญของระบบ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, กรุณาตรวจสอบคุณอีกครั้ง:
1. Java Development Kit (JDK): ไมโครโฟนของคุณติดตั้ง Java บนระบบของคุณแล้วดาวน์โหลดบันทึกการดาวน์โหลดล่าสุดจาก [เว็บไซต์ Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
2. Aspose.Tasks for Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks for Java ตามคำแนะนำใน [documentation](https://reference.aspose.com/tasks/java/)

## แพคเกจนำเข้า
แรกสุด, นำเข้าแพ็กเกจที่จำเป็นไปยังไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
กำหนดเส้นทางไปยังไดเรกทอรีข้อมูลของคุณที่ไฟล์ MS Project อยู่
```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: โหลดไฟล์ MS Project
โหลดไฟล์ MS Project ด้วย Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## ขั้นตอนที่ 3: ปรับคุณภาพ JPEG (ไม่จำเป็น)
หากคุณต้องการปรับแต่งผลลัพธ์, คุณสามารถ **ตั้งค่าคุณภาพ JPEG** โดยใช้คลาส `ImageSaveOptions` ค่า quality อยู่ในช่วง 0 ถึง 100, และนี่เป็นวิธีทั่วไปในการ **set jpeg quality java**‑style.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## ขั้นตอนที่ 4: บันทึกโปรเจ็กต์เป็น JPEG
บันทึกไฟล์ MS Project เป็นภาพ JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## วิธีการส่งออก JPEG จาก MS Project
ขั้นตอนข้างต้นแสดง **วิธีการส่งออก JPEG** จากไฟล์ Microsoft Project โดยการปรับคุณภาพ JPEG, คุณควบคุมการแลกเปลี่ยนระหว่างความคมชัดของภาพและขนาดไฟล์, ทำให้ภาพที่ส่งออกเหมาะสำหรับการเผยแพร่บนเว็บ, รายงานที่พิมพ์, หรือสไลด์ที่ฝัง

## บทสรุป
ในบทแนะนำนี้มักจะอธิบายวิธี ** ปรับคุณภาพ JPEG** ในขณะที่แปลงไฟล์ Microsoft Project เป็นภาพ JPEG ด้วย Aspose.Tasks สำหรับ Java วิธีนี้ช่วยให้การแชร์ภาพในส่วนโครงการเป็นเรื่องง่าย, ยอมรับคุณภาพโดยรวม, และให้คุณควบคุมขนาดผลลัพธ์ได้เต็มที่

## คำถามที่พบบ่อยเพิ่มเติม

**ถาม: การปรับคุณภาพ JPEG ส่งผลต่อความสามารถในการอ่านแผนภูมิแกนต์หรือไม่**
ตอบ: ส่วนคุณภาพจะรักษาข้อความและเส้นรายละเอียดได้ดี, คุณภาพที่ต่ำมากอาจทำให้อ่านยากได้มาก.

**ถาม: ฉันสามารถส่งออกรูปแบบรูปภาพอื่นนอกเหนือจาก JPEG ได้หรือไม่**
ตอบ: ถูกต้อง, Aspose.Tasks รองรับ PNG, BMP, และ TIFF ผ่าน enum `SaveFileFormat` ดูดี

**ถาม: เป็นไปได้ไหมที่จะส่งออกหลายหน้า (เช่น มุมมองที่แตกต่างกัน) ในคราวเดียว**
ตอบ: ไม่เคยยิ่งใหญ่ผ่านมุมมองที่ต้องการและบันทึกแต่ละอันเป็น JPEG แยกไฟล์ต่างๆ มากมาย `ImageSaveOptions` เดียวกัน

**ถาม: ต้องใช้ Java เวอร์ชันใด**
A: Aspose.Tasks for Java รองรับ JDK 8 ขึ้นไป

**ถาม: ฉันจะจัดการกับโปรเจ็กต์ขนาดใหญ่ที่สร้างภาพขนาดใหญ่ได้อย่างไร**
ตอบ: พิจารณาลดคุณภาพ JPEG หรือพิจารณามิติภาพผ่านเพิ่มเติมของ `ImageSaveOptions`

---

**อัปเดตล่าสุด:** 20-12-2025
**ทดสอบกับ:** Aspose.Tasks สำหรับ Java 24.11
**ผู้เขียน:** สมมติ  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}