---
date: 2025-12-21
description: เรียนรู้วิธีบันทึกโครงการเป็นเทมเพลต, ส่งออกไฟล์ MPP เป็น CSV, และแปลงไฟล์
  MPP เป็นข้อความโดยใช้ Aspose.Tasks สำหรับ Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: บันทึกโครงการเป็นเทมเพลต, CSV และข้อความด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกโครงการเป็นเทมเพลต, CSV, และข้อความด้วย Aspise.Tasks

## บทนำ
ในบทแนะนำนี้ คุณจะได้ค้นพบ **วิธีบันทึกโครงการเป็นเทมเพลต** และวิธีส่งออกไฟล์ Microsoft Project (MPP) ของคุณเป็นรูปแบบ CSV และข้อความธรรมดาโดยใช้ไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะต้องการสร้างเทมเพลตโครงการที่ใช้ซ้ำได้, สร้างรายงาน CSV สำหรับการวิเคราะห์, หรือผลิตข้อความสรุปง่าย ๆ เพื่อการรวมระบบ ขั้นตอนเหล่านี้จะช่วยคุณดำเนินการอย่างรวดเร็วและมีประสิทธิภาพ

## คำตอบสั้น
- **ฉันสามารถส่งออก MPP เป็น CSV ได้หรือไม่?** ใช่ – ใช้ `project.save(..., SaveFileFormat.CSV)`.  
- **วิธีส่งออกเป็นข้อความ?** บันทึกด้วย `SaveFileFormat.TEXT`.  
- **“บันทึกโครงการเป็นเทมเพลต” ทำอะไร?** มันสร้างไฟล์ `.mpt` ที่ลบค่าจริงและค่าฐานต้นแบบออก, พร้อมใช้ซ้ำ.  
- **ฉันต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองให้ใช้; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ต้องการเวอร์ชัน Java ใด?** รองรับ Java 8+

## อะไรคือ “บันทึกโครงการเป็นเทมเพลต”?
การบันทึกโครงการเป็นเทมเพลต (`.mpt`) จะบันทึกโครงสร้าง, ลำดับงาน, และการมอบหมายทรัพยากรในขณะที่ลบวันที่เริ่ม/สิ้นสุดจริงและข้อมูลฐานต้นแบบออก ทำให้เทมเพลตนี้เหมาะสำหรับการใช้ซ้ำโครงร่างโครงการมาตรฐานในหลายโครงการใหม่.

## ทำไมต้องใช้ Aspose.Tasks สำหรับ Java?
Aspose.Tasks ช่วยให้คุณจัดการไฟล์ Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project เอง มันรองรับ **วิธีส่งออก MPP**, **วิธีส่งออกเป็นข้อความ**, และ **แปลง MPP เป็น CSV**, ทั้งหมดจากโค้ด Java แท้ ซึ่งเหมาะอย่างยิ่งสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์, สายงาน CI, หรือยูทิลิตี้บนเดสก์ท็อป.

## ข้อกำหนดเบื้องต้น
1. Java Development Kit (JDK) 8 หรือสูงกว่า ติดตั้งแล้ว.  
2. ไลบรารี Aspose.Tasks สำหรับ Java ถูกเพิ่มในโปรเจกต์ของคุณ ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/).  
3. ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และการตั้งค่าโปรเจกต์ Maven/Gradle.

## นำเข้าแพ็กเกจ
แรกเริ่ม ให้นำเข้าคลาสที่จำเป็นในไฟล์ซอร์ส Java ของคุณ:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## บันทึกโครงการเป็น CSV (ส่งออก MPP เป็น CSV)
การส่งออกไฟล์ MPP เป็น CSV มีประโยชน์สำหรับการวิเคราะห์ข้อมูลใน Excel หรือเครื่องมือ BI.

### ขั้นตอนที่ 1: โหลดโครงการ
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### ขั้นตอนที่ 2: บันทึกเป็น CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## บันทึกโครงการเป็นข้อความ (วิธีส่งออกเป็นข้อความ)
หากคุณต้องการการแสดงผลเป็นข้อความธรรมดาของงาน, ทรัพยากร, หรือการมอบหมาย, ให้บันทึกโครงการเป็นไฟล์ข้อความ.

### ขั้นตอนที่ 1: โหลดโครงการ
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### ขั้นตอนที่ 2: บันทึกเป็นข้อความ
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## บันทึกโครงการเป็นเทมเพลต (สร้างเทมเพลตโครงการ Java)
การสร้างเทมเพลตที่ใช้ซ้ำได้จะลบวันที่จริงและฐานต้นแบบ, ทำให้เหลือโครงกระดูกที่สะอาดสำหรับโครงการใหม่.

### ขั้นตอนที่ 1: โหลดโครงการ
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### ขั้นตอนที่ 2: ตั้งค่าตัวเลือกเทมเพลต
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### ขั้นตอนที่ 3: บันทึกเป็นเทมเพลต
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## ปัญหาทั่วไป & เคล็ดลับ
- **ไฟล์ไม่พบ:** ตรวจสอบให้แน่ใจว่าเส้นทางไปยัง `YourProject.mpp` ถูกต้องหรือใช้เส้นทางแบบเต็ม.  
- **ข้อยกเว้นไลเซนส์:** หากไม่มีไลเซนส์ที่ถูกต้อง ไลบรารีจะทำงานในโหมดประเมินและอาจเพิ่มลายน้ำ ใส่ไลเซนส์ของคุณตั้งแต่ต้นในโค้ด (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **โครงการขนาดใหญ่:** สำหรับไฟล์ MPP ขนาดใหญ่มาก ให้พิจารณาเพิ่มขนาด heap ของ JVM (`-Xmx2g`) เพื่อหลีกเลี่ยง `OutOfMemoryError`.

## สรุป
เราได้อธิบาย **วิธีบันทึกโครงการเป็นเทมเพลต**, รวมถึง **วิธีส่งออก MPP เป็น CSV** และ **วิธีแปลง MPP เป็นข้อความ** ด้วย Aspose.Tasks สำหรับ Java ความสามารถเหล่านี้ช่วยให้คุณอัตโนมัติการจัดการข้อมูลโครงการ, สร้างเทมเพลตที่ใช้ซ้ำได้, และรวมข้อมูลโครงการเข้ากับระบบอื่น ๆ — ทั้งหมดโดยไม่ต้องติดตั้ง Microsoft Project

## คำถามที่พบบ่อย
### Q: Aspose.Tasks สำหรับ Java สามารถจัดการไฟล์โครงการที่ซับซ้อนได้หรือไม่?
A: แน่นอน! Aspose.Tasks สำหรับ Java สามารถจัดการโครงการที่มีความซับซ้อนหลากหลายได้อย่างง่ายดาย พร้อมให้การสนับสนุนที่ครอบคลุมสำหรับรูปแบบไฟล์ Microsoft Project.

### Q: มีรุ่นทดลองสำหรับ Aspose.Tasks สำหรับ Java หรือไม่?
A: มี, คุณสามารถรับรุ่นทดลองฟรีของ Aspose.Tasks สำหรับ Java ได้จาก [here](https://releases.aspose.com/).

### Q: ฉันสามารถหาการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน?
A: คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือหรือสอบถามเกี่ยวกับ Aspose.Tasks สำหรับ Java.

### Q: ฉันสามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่?
A: ได้, คุณสามารถซื้อไลเซนส์ชั่วคราวจาก [here](https://purchase.aspose.com/temporary-license/), ซึ่งทำให้คุณประเมินศักยภาพเต็มของไลบรารีได้.

### Q: Aspose.Tasks สำหรับ Java เข้ากันได้กับระบบปฏิบัติการต่าง ๆ หรือไม่?
A: ใช่, Aspose.Tasks สำหรับ Java เข้ากันได้กับระบบปฏิบัติการหลายประเภท รวมถึง Windows, macOS, และ Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-21  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (latest)  
**ผู้เขียน:** Aspose