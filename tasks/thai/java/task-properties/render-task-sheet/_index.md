---
date: 2026-02-26
description: เรียนรู้วิธีบันทึกโครงการเป็น PDF และสร้างแผ่นงานงานโดยใช้ Aspose.Tasks
  สำหรับ Java ส่งออก MPP เป็น PDF อย่างรวดเร็วด้วยคู่มือขั้นตอนต่อขั้นตอนนี้
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: บันทึกโครงการเป็น PDF – แสดงแผ่นงานงานด้วย Aspose.Tasks สำหรับ Java
url: /th/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกโครงการเป็น PDF – แสดงแผ่นงานงานใน Aspose.Tasks

## บทนำ
ในคู่มือฉบับครอบคลุมนี้ คุณจะได้เรียนรู้วิธี **save project as PDF** และสร้างแผ่นงานงานด้วย Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะต้องการส่งออกไฟล์ MPP เป็น PDF เพื่อการตรวจสอบของผู้มีส่วนได้ส่วนเสีย หรือเพียงแค่แสดงแผ่นงานงานที่สะอาดสำหรับการรายงาน คู่มือนี้จะพาคุณผ่านทุกขั้นตอน อธิบายว่าทำไมการตั้งค่าแต่ละอย่างจึงสำคัญ และแสดงโค้ดที่ต้องใช้อย่างแม่นยำ

## คำตอบอย่างรวดเร็ว
- **What does “save project as pdf” do?** มันแปลงไฟล์ Microsoft Project (MPP) ให้เป็นเอกสาร PDF โดยอาจจัดรูปแบบเป็นแผ่นงานงานได้  
- **Which format is used for a task‑sheet PDF?** ตัวเลือก `PresentationFormat.TaskSheet` ใน `PdfSaveOptions`  
- **Do I need a license to run the code?** จำเป็นต้องมีใบอนุญาตแบบชั่วคราวหรือเต็มสำหรับการใช้งานจริง; รุ่นทดลองฟรีสามารถใช้เพื่อประเมินได้  
- **What are the main prerequisites?** Java JDK, ไลบรารี Aspose.Tasks for Java, และไฟล์โครงการที่ถูกต้อง (เช่น *.mpp)  
- **Can I customize the PDF layout?** ได้, Aspose.Tasks มีคุณสมบัติ `PdfSaveOptions` มากมายสำหรับการจัดสไตล์และการตั้งค่าหน้ากระดาษ  

## อะไรคือ “save project as pdf”?
การบันทึกโครงการเป็น PDF จะเปลี่ยนข้อมูลภายในของโครงการให้เป็นเอกสารพกพาแบบอ่าน‑อย่างเดียว ซึ่งเหมาะสำหรับการแชร์กำหนดการ, แผ่นงานงาน, หรือรายงานสถานะให้กับผู้มีส่วนได้ส่วนเสียที่ไม่มี Microsoft Project ติดตั้ง

## ทำไมต้องแสดงแผ่นงานงาน?
แผ่นงานงานจะแสดงแต่ละงานในรูปแบบตาราง พร้อมแสดงรหัส, ชื่อ, วันที่เริ่ม/สิ้นสุด, และฟิลด์อื่น ๆ การแปลงเป็น PDF ทำให้รูปแบบคงที่บนทุกแพลตฟอร์มและง่ายต่อการพิมพ์หรือฝังในเอกสารอื่น

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชันล่าสุดที่ติดตั้งและ `java`/`javac` พร้อมใช้งานใน PATH ของคุณ  
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีจากเว็บไซต์อย่างเป็นทางการ [here](https://releases.aspose.com/tasks/java/)  
3. ไฟล์ **project** ที่ถูกต้อง (`*.mpp`) ที่คุณต้องการแปลง, เช่น `NewProductDev.mpp`  

## นำเข้าแพ็กเกจ
แรกเริ่ม, นำเข้าคลาสของ Aspose.Tasks ที่จำเป็น การนำเข้าต่าง ๆ นี้ทำให้คุณเข้าถึงตัวเลือกการบันทึก PDF, รูปแบบการแสดงผล, และอ็อบเจ็กต์หลัก `Project`  

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ
กำหนดโฟลเดอร์ที่ไฟล์ MPP ต้นทางอยู่และที่ PDF ที่สร้างขึ้นจะถูกเขียนออกไป การใช้พาธแบบเต็มหรือแบบสัมพันธ์ก็ได้; เพียงตรวจสอบให้แน่ใจว่าโฟลเดอร์มีอยู่  

```java
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ MPP ที่มีอยู่ อ็อบเจ็กต์นี้แสดงโครงสร้างโครงการทั้งหมดในหน่วยความจำ  

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการบันทึก – ส่งออก MPP เป็น PDF
สร้างอินสแตนซ์ `PdfSaveOptions` และบอก Aspose.Tasks ว่าคุณต้องการให้ PDF แสดงเป็น **task sheet** นี่คือขั้นตอนสำคัญสำหรับกรณีการใช้ *export project pdf*  

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### ขั้นตอนที่ 4: บันทึกโครงการเป็นแผ่นงานงาน – Save Project as PDF
เรียกเมธอด `save` บนวัตถุ `Project` โดยส่งชื่อไฟล์เป้าหมายและตัวเลือกที่กำหนดไว้ การกระทำนี้ **แปลงไฟล์ MPP เป็น PDF** ที่จัดรูปแบบเป็นแผ่นงานงาน  

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### ขั้นตอนที่ 5: ตรวจสอบผลลัพธ์
ไปยังไดเรกทอรีที่คุณระบุ (`dataDir`). คุณควรเห็นไฟล์ `taskSheet.pdf` ที่มีรายการงานทั้งหมดที่จัดรูปแบบอย่างเรียบร้อย เปิดไฟล์ด้วยโปรแกรมดู PDF ใดก็ได้เพื่อยืนยันว่าการแปลงสำเร็จ  

## ปัญหาที่พบบ่อยและวิธีแก้
- **FileNotFoundException** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นพาธ (`/` หรือ `\\`) และชื่อไฟล์ MPP ถูกต้อง  
- **LicenseException** – หากพบข้อผิดพลาดเกี่ยวกับใบอนุญาต, ให้ใช้ใบอนุญาตชั่วคราวหรือใบอนุญาตที่ซื้อก่อนเรียกใช้ API ของ Aspose.Tasks  
- **Blank PDF** – ตรวจสอบว่าโครงการมีงานจริง; โครงการว่างจะสร้าง PDF ว่าง  

## คำถามที่พบบ่อย

**Q: Aspose.Tasks รองรับเวอร์ชัน Java ทั้งหมดหรือไม่?**  
A: ใช่, Aspose.Tasks ทำงานได้กับหลายเวอร์ชันของ Java ดูที่ [documentation](https://reference.aspose.com/tasks/java/) สำหรับรายละเอียด  

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: แน่นอน! สำรวจเวอร์ชันทดลองฟรี [here](https://releases.aspose.com/)  

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
A: เข้าร่วมชุมชน Aspose.Tasks ใน [forum](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุนและการสนทนา  

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร?**  
A: รับใบอนุญาตชั่วคราวของคุณ [here](https://purchase.aspose.com/temporary-license/)  

**Q: ฉันสามารถซื้อ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: ซื้อ Aspose.Tasks for Java [here](https://purchase.aspose.com/buy)  

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้วิธี **save project as PDF**, โดยเฉพาะการแสดงแผ่นงานงาน, ด้วย Aspose.Tasks for Java ความสามารถนี้ทำให้คุณสามารถ *export MPP to PDF* ได้อย่างรวดเร็ว, แชร์ภาพรวมโครงการที่อ่านได้, และรวมข้อมูลโครงการเข้าสู่กระบวนการรายงานที่กว้างขึ้น  

---

**อัปเดตล่าสุด:** 2026-02-26  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}