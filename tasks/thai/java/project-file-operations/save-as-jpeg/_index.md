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

## Introduction
ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **ปรับคุณภาพ JPEG** เมื่อบันทึกไฟล์ Microsoft Project เป็นภาพ JPEG โดยใช้ Aspose.Tasks for Java ความสามารถนี้มีประโยชน์สำหรับการสร้างรายงานภาพที่ชัดเจน การฝังภาพโครงการลงในงานนำเสนอ หรือเพียงแค่ส่งออกไฟล์ JPEG ด้วยระดับรายละเอียดที่คุณต้องการ

## Quick Answers
- **“ปรับคุณภาพ JPEG” ทำอะไร?** มันให้คุณควบคุมระดับการบีบอัดของ JPEG ที่ส่งออก เพื่อสมดุลระหว่างขนาดไฟล์และความคมชัดของภาพ  
- **ไลบรารีที่ทำการแปลงคืออะไร?** Aspose.Tasks for Java มี API ที่ใช้งานง่ายสำหรับการส่งออกไฟล์ Project เป็น JPEG  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีสามารถใช้เพื่อประเมินผลได้; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ฉันสามารถตั้งค่าคุณภาพในโค้ดได้หรือไม่?** ได้, ใช้เมธอด `ImageSaveOptions.setJpegQuality(int)` (ช่วง 0‑100)  
- **กระบวนการเร็วหรือไม่?** การแปลงไฟล์โครงการทั่วไปเป็น JPEG ใช้เวลาเพียงไม่กี่วินาทีบนฮาร์ดแวร์สมัยใหม่  

## What is “adjust JPEG quality”?
การปรับคุณภาพ JPEG หมายถึงการตั้งค่าปัจจัยการบีบอัดที่ใช้เมื่อบันทึกรูปภาพในรูปแบบ JPEG คุณภาพที่สูงกว่า (ค่าที่ใกล้ 100) จะรักษารายละเอียดมากขึ้นแต่ไฟล์จะใหญ่ขึ้น, ในขณะที่คุณภาพที่ต่ำกว่าจะลดขนาดไฟล์แต่เสียความคมชัดของภาพ

## Why use Aspose.Tasks for JPEG export?
Aspose.Tasks ให้วิธีที่เชื่อถือได้และไม่ขึ้นกับแพลตฟอร์มในการเรนเดอร์แผนภูมิ Gantt, มุมมองทรัพยากร, และภาพโครงการอื่น ๆ โดยตรงเป็นไฟล์ภาพ มันช่วยขจัดความจำเป็นในการถ่ายภาพหน้าจอด้วยตนเองและรับประกันผลลัพธ์ที่สม่ำเสมอในทุกสภาพแวดล้อม

## Prerequisites
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้งเวอร์ชันล่าสุดจาก [Java website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks for Java: ดาวน์โหลดและตั้งค่า Aspose.Tasks for Java ตามคำแนะนำใน [documentation](https://reference.aspose.com/tasks/java/).

## Import Packages
แรกสุด, นำเข้าแพ็กเกจที่จำเป็นไปยังไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## Step 1: Define Data Directory
กำหนดเส้นทางไปยังไดเรกทอรีข้อมูลของคุณที่ไฟล์ MS Project อยู่
```java
String dataDir = "Your Data Directory";
```

## Step 2: Load MS Project File
โหลดไฟล์ MS Project ด้วย Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## Step 3: Adjust JPEG Quality (Optional)
หากคุณต้องการปรับแต่งผลลัพธ์, คุณสามารถ **ตั้งค่าคุณภาพ JPEG** โดยใช้คลาส `ImageSaveOptions` ค่า quality อยู่ในช่วง 0 ถึง 100, และนี่เป็นวิธีทั่วไปในการ **set jpeg quality java**‑style.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## Step 4: Save Project as JPEG
บันทึกไฟล์ MS Project เป็นภาพ JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## How to Export JPEG from MS Project
ขั้นตอนข้างต้นแสดง **วิธีการส่งออก JPEG** จากไฟล์ Microsoft Project โดยการปรับคุณภาพ JPEG, คุณควบคุมการแลกเปลี่ยนระหว่างความคมชัดของภาพและขนาดไฟล์, ทำให้ภาพที่ส่งออกเหมาะสำหรับการเผยแพร่บนเว็บ, รายงานที่พิมพ์, หรือสไลด์ที่ฝัง

## Conclusion
ในบทแนะนำนี้, เราได้อธิบายวิธี **ปรับคุณภาพ JPEG** ขณะแปลงไฟล์ Microsoft Project เป็นภาพ JPEG ด้วย Aspose.Tasks for Java วิธีนี้ช่วยให้การแชร์ภาพการมองเห็นโครงการเป็นเรื่องง่าย, รับประกันคุณภาพภาพที่สม่ำเสมอ, และให้คุณควบคุมขนาดผลลัพธ์ได้เต็มที่

## FAQ's
### Q: Can I adjust the quality of the JPEG image?
A: ใช่, คุณสามารถปรับคุณภาพได้โดยใช้เมธอด `setJpegQuality()`, ช่วงค่าตั้งแต่ 0 ถึง 100.  

### Q: What if I don't specify the JPEG quality?
A: หากคุณไม่ได้ระบุคุณภาพ, ระบบจะใช้คุณภาพเริ่มต้น.  

### Q: Is Aspose.Tasks for Java free to use?
A: Aspose.Tasks for Java เป็นไลบรารีเชิงพาณิชย์, แต่คุณสามารถสำรวจคุณสมบัติโดยใช้การทดลองใช้ฟรี. เยี่ยมชม [free trial page](https://releases.aspose.com/) สำหรับข้อมูลเพิ่มเติม.  

### Q: Where can I get support for Aspose.Tasks for Java?
A: คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).  

### Q: Can I purchase a temporary license for Aspose.Tasks?
A: ใช่, คุณสามารถซื้อไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/).  

## Additional Frequently Asked Questions

**Q: Does adjusting JPEG quality affect Gantt chart readability?**  
A: คุณภาพที่สูงจะรักษาข้อความและรายละเอียดเส้นไว้ได้ดี, ในขณะที่คุณภาพที่ต่ำมากอาจทำให้ป้ายกำกับขนาดเล็กอ่านยาก.  

**Q: Can I export other image formats besides JPEG?**  
A: ใช่, Aspose.Tasks รองรับ PNG, BMP, และ TIFF ผ่าน enum `SaveFileFormat` ที่เหมาะสม.  

**Q: Is it possible to export multiple pages (e.g., different views) at once?**  
A: คุณสามารถวนลูปผ่านมุมมองที่ต้องการและบันทึกแต่ละอันเป็น JPEG แยกไฟล์โดยใช้การตั้งค่า `ImageSaveOptions` เดียวกัน.  

**Q: What Java version is required?**  
A: Aspose.Tasks for Java ทำงานกับ JDK 8 ขึ้นไป.  

**Q: How do I handle large projects that produce big images?**  
A: พิจารณาลดคุณภาพ JPEG หรือปรับขนาดมิติภาพผ่านการตั้งค่าเพิ่มเติมของ `ImageSaveOptions`.  

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}