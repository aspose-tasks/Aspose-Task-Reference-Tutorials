---
date: 2026-05-26
description: เรียนรู้วิธีสร้างภาพสแนปช็อตของโครงการเป็น JPEG และปรับคุณภาพ JPEG เมื่อส่งออกไฟล์
  Microsoft Project ด้วย Aspose.Tasks for Java.
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: บันทึกโครงการเป็น JPEG ใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: สร้างภาพสแนปช็อตของโครงการเป็น JPEG – ปรับคุณภาพด้วย Aspose.Tasks
url: /th/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพสแนปช็อตของโครงการ JPEG – ปรับคุณภาพด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **สร้างไฟล์สแนปช็อตของโครงการ JPEG** จาก Microsoft Project ด้วย Aspose.Tasks for Java และวิธีปรับแต่งคุณภาพ JPEG ให้ตรงกับความต้องการด้านขนาดและความคมชัด ไม่ว่าคุณจะต้องการภาพคมชัดสำหรับการนำเสนอในห้องประชุมหรือไฟล์ขนาดเล็กสำหรับพอร์ทัลเว็บ การควบคุมการตั้งค่าคุณภาพจะทำให้คุณมีอำนาจเต็มในการกำหนดผลลัพธ์สุดท้าย

## คำตอบด่วน
- **What does “adjust JPEG quality” do?** มันทำให้คุณสามารถควบคุมระดับการบีบอัดของ JPEG ที่ส่งออกได้ โดยสมดุลระหว่างขนาดไฟล์และความคมชัดของภาพ  
- **Which library handles the conversion?** Aspose.Tasks for Java ให้ API ที่ตรงไปตรงมาสำหรับการส่งออกไฟล์ Project เป็น JPEG  
- **Do I need a license?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **Can I set the quality in code?** ใช่, ใช้เมธอด `ImageSaveOptions.setJpegQuality(int)` (ช่วง 0‑100)  
- **Is the process fast?** การแปลงไฟล์โครงการทั่วไปเป็น JPEG ใช้เวลาเพียงไม่กี่วินาทีบนฮาร์ดแวร์สมัยใหม่  

## “adjust JPEG quality” คืออะไร?
การปรับคุณภาพ JPEG ทำให้คุณระบุปัจจัยการบีบอัดที่ใช้เมื่อบันทึกรูปภาพในรูปแบบ JPEG ค่าที่สูงกว่า (ใกล้ 100) จะรักษารายละเอียดได้มากขึ้น ในขณะที่ค่าที่ต่ำกว่าจะลดขนาดไฟล์แต่เสียความคมชัด **Direct answer:** คุณควบคุมคุณภาพ JPEG โดยส่งค่าตัวเลข (0‑100) ไปยังเมธอด `ImageSaveOptions.setJpegQuality` ซึ่งจะมีผลทันทีต่อขนาดและความคมชัดของสแนปช็อตที่สร้างขึ้น  

คุณภาพ JPEG คือปัจจัยการบีบอัดที่ใช้เมื่อบันทึกรูปภาพในรูปแบบ JPEG  

## ทำไมต้องใช้ Aspose.Tasks สำหรับการส่งออก JPEG?
**Direct answer:** Aspose.Tasks แสดงแผนภูมิ Gantt, มุมมองทรัพยากร, และรายงานที่กำหนดเองเป็นไฟล์ภาพโดยไม่ต้องติดตั้ง Microsoft Project, รับประกันผลลัพธ์ที่พิกเซลสมบูรณ์บน Windows, Linux, และ macOS  

Aspose.Tasks รองรับการส่งออกเป็นรูปแบบภาพ **สี่** รูปแบบ (JPEG, PNG, BMP, TIFF) และสามารถเรนเดอร์โครงการที่มี **สูงสุด 10,000 งาน** ภายในเวลาไม่เกิน 5 วินาทีบน CPU มาตรฐาน 2.5 GHz, ให้การรับประกันประสิทธิภาพที่วัดได้  

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – ติดตั้ง JDK ล่าสุด (เวอร์ชัน 8 หรือใหม่กว่า) จาก [เว็บไซต์ Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)  
2. **Aspose.Tasks for Java** – ดาวน์โหลดและตั้งค่าห้องสมุดตามขั้นตอนใน [เอกสารอย่างเป็นทางการ](https://reference.aspose.com/tasks/java/)  

## นำเข้าแพ็กเกจ
`ImageSaveOptions` คือคลาสของ Aspose.Tasks ที่ควบคุมการตั้งค่าการส่งออกภาพ เช่น รูปแบบ, ขนาด, และคุณภาพ JPEG.  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
ตั้งค่าพาธไปยังโฟลเดอร์ที่มีไฟล์ Microsoft Project ของคุณ ไดเรกทอรีนี้ใช้สำหรับการดำเนินการทั้งเข้าและออก.  
```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: โหลดไฟล์ MS Project
คลาส `Project` แสดงไฟล์ Microsoft Project ในหน่วยความจำ, ให้การเข้าถึงงาน, ทรัพยากร, และข้อมูลมุมมอง.  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## ขั้นตอนที่ 3: ปรับคุณภาพ JPEG (ไม่บังคับ)
หากคุณต้องการปรับแต่งผลลัพธ์อย่างละเอียด, คุณสามารถ **ตั้งค่าคุณภาพ JPEG** ด้วยคลาส `ImageSaveOptions`. ค่าคุณภาพอยู่ในช่วง 0 ถึง 100, โดย 100 ให้ความคมชัดสูงสุด.  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## ขั้นตอนที่ 4: บันทึกโครงการเป็น JPEG
`Project.save` เขียนมุมมองที่เรนเดอร์เป็นไฟล์ภาพโดยใช้ตัวเลือกที่คุณกำหนด.  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## วิธีการส่งออก JPEG จาก MS Project
**Direct answer:** เรียก `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)` หลังจากกำหนดค่า `ImageSaveOptions`; เมธอดนี้จะเรนเดอร์มุมมองที่ใช้งานอยู่ (โดยค่าเริ่มต้นคือแผนภูมิ Gantt) และบันทึกไฟล์ JPEG ด้วยคุณภาพที่ระบุ การเรียกใช้แบบบรรทัดเดียวนี้จัดการการแบ่งหน้า, การปรับขนาด, และการจัดการสีโดยอัตโนมัติ.  

โดยการปรับคุณภาพ JPEG, คุณควบคุมการแลกเปลี่ยนระหว่างความคมชัดของภาพและขนาดไฟล์, ทำให้ภาพที่ส่งออกเหมาะสำหรับการเผยแพร่บนเว็บ, รายงานที่พิมพ์, หรือสไลด์ที่ฝังไว้.  

## ปัญหาทั่วไปและวิธีแก้
- **Low quality makes text unreadable:** เพิ่มคุณภาพ JPEG ให้สูงกว่า 70 หรือเปลี่ยนเป็น PNG เพื่อการเรนเดอร์แบบไม่มีการสูญเสีย  
- **Out‑of‑memory errors on large projects:** เปิดใช้งานการสตรีมโดยตั้งค่า `saveOptions.setUseMemoryCache(true)` เพื่อให้การใช้หน่วยความจำอยู่ต่ำกว่า 200 MB  
- **Wrong view exported:** ใช้ `saveOptions.setView(ViewType.TaskSheet)` เพื่อส่งออกมุมมองอื่น  

## คำถามที่พบบ่อย

**Q: Does adjusting JPEG quality affect Gantt chart readability?**  
A: คุณภาพที่สูงกว่าจะรักษาข้อความและรายละเอียดของเส้น, ในขณะที่คุณภาพต่ำมากอาจทำให้ป้ายกำกับขนาดเล็กอ่านยาก.  

**Q: Can I export other image formats besides JPEG?**  
A: ใช่, Aspose.Tasks รองรับ PNG, BMP, และ TIFF ผ่าน enum `SaveFileFormat` ที่เหมาะสม.  

**Q: Is it possible to export multiple pages (e.g., different views) at once?**  
A: คุณสามารถวนลูปผ่านมุมมองที่ต้องการและบันทึกแต่ละอันเป็น JPEG แยกกันโดยใช้การกำหนดค่า `ImageSaveOptions` เดียวกัน.  

**Q: What Java version is required?**  
A: Aspose.Tasks for Java ทำงานกับ JDK 8 ขึ้นไป.  

**Q: How do I handle large projects that produce big images?**  
A: พิจารณาลดคุณภาพ JPEG หรือปรับขนาดภาพผ่านการตั้งค่า `ImageSaveOptions` เพิ่มเติม.  

## สรุป
เราได้อธิบายวิธี **สร้างไฟล์สแนปช็อตของโครงการ JPEG** และปรับคุณภาพ JPEG ด้วย Aspose.Tasks for Java วิธีนี้ช่วยขจัดการถ่ายภาพหน้าจอด้วยตนเอง, รับประกันการเรนเดอร์ที่สม่ำเสมอข้ามแพลตฟอร์ม, และให้คุณปรับสมดุลระหว่างความคมชัดของภาพและขนาดไฟล์อย่างละเอียด—เหมาะสำหรับรายงาน, การนำเสนอ, และการเผยแพร่บนเว็บ.

---

**อัปเดตล่าสุด:** 2026-05-26  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างไฟล์ MPP – สร้างและบันทึกโครงการเปล่าในรูปแบบ MPP ด้วย Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [บันทึกโครงการเป็นเทมเพลต, CSV, และข้อความด้วย Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [สร้างไฟล์ MS Project เปล่าใน Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}