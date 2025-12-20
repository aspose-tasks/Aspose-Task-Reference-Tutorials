---
date: 2025-12-20
description: เรียนรู้วิธีการส่งออก PDF ใน Aspose.Tasks สำหรับ Java คู่มือง่าย ๆ เพื่อแปลง
  MPP เป็น PDF และบันทึกไฟล์โครงการของคุณอย่างมีประสิทธิภาพ
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีส่งออก PDF ใน Aspose.Tasks – บันทึกเป็น PDF
url: /th/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการส่งออก PDF ใน Aspose.Tasks – บันทึกเป็น PDF

## คำนำ
ในบทแนะนำนี้ เราจะสาธิต **วิธีการส่งออก PDF** ด้วย Aspose.Tasks สำหรับ Java โดยแนะนำขั้นตอนการบันทึกโครงการเป็นไฟล์ PDF ด้วย Aspose.Tasks คุณสามารถ **แปลง MPP เป็น PDF** ได้อย่างมีประสิทธิภาพ เพื่อให้เข้ากันได้และง่ายต่อการแชร์ระหว่างทีมและผู้มีส่วนได้ส่วนเสีย มาดูขั้นตอนเพื่อให้คุณได้ PDF ที่พิมพ์ได้จากไฟล์โครงการใด ๆ อย่างรวดเร็ว

## คำตอบสั้น
- **“ส่งออก PDF” หมายความว่าอย่างไรใน Aspose.Tasks?** หมายถึงการแปลงไฟล์โครงการ (เช่น MPP) เป็นเอกสาร PDF ที่คงรูปแบบการแสดงผลไว้  
- **ต้องใช้เวอร์ชันไลบรารีใด?** เวอร์ชัน Aspose.Tasks for Java ใดก็ได้ที่รองรับ `PdfSaveOptions` (แนะนำให้ใช้รุ่นล่าสุด)  
- **ต้องมีลิขสิทธิ์สำหรับการแปลงนี้หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถปรับแต่งลักษณะของ PDF ได้หรือไม่?** ได้ – สามารถตั้งค่า timescale, legends และ `PdfSaveOptions` อื่น ๆ  
- **การแปลงเร็วสำหรับโครงการขนาดใหญ่หรือไม่?** ปกติใช้เวลาเป็นวินาที; ประสิทธิภาพขึ้นอยู่กับขนาดโครงการและตัวเลือกที่เลือก

## “วิธีการส่งออก pdf” ในบริบทของ Aspose.Tasks คืออะไร?
การส่งออก PDF ด้วย Aspose.Tasks หมายถึงการนำไฟล์โครงการ (เช่น `.mpp`, `.xml`, หรือ `.xlsx`) มาสร้างเป็น PDF ที่สะท้อน Gantt chart, task usage view หรือรูปแบบการนำเสนออื่น ๆ ที่คุณกำหนดไว้ ซึ่งเป็นประโยชน์สำหรับการรายงาน, เอกสาร, หรือการแชร์มุมมองอ่าน‑อย่างเท่านั้นให้กับผู้ที่ไม่มีความเชี่ยวชาญด้านเทคนิค

## ทำไมต้องส่งออกไฟล์โครงการเป็น PDF?
- **ความอ่านได้ทั่วโลก:** PDF ทำงานบนอุปกรณ์ใด ๆ โดยไม่ต้องใช้ซอฟต์แวร์โครงการเดิม  
- **การนำเสนอระดับมืออาชีพ:** คงรูปแบบ, สี, และการจัดวางสำหรับรายงานที่ส่งให้ลูกค้า  
- **การกระจายที่ง่าย:** แชร์ผ่านอีเมล, อินทราเน็ต, หรือคลาวด์โดยไม่ต้องกังวลเรื่องการควบคุมเวอร์ชัน  
- **การปฏิบัติตามและการเก็บรักษา:** PDF เหมาะสำหรับการจัดเก็บระยะยาวและการปฏิบัติตามข้อกำหนดกฎระเบียบ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Java Development Kit (JDK):** JDK 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ  
2. **Aspose.Tasks for Java Library:** ดาวน์โหลดไลบรารีจากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/tasks/java/)  
3. **ไฟล์โครงการ:** มีไฟล์โครงการที่มีอยู่ (เช่น `HomeMovePlan.mpp`) พร้อมสำหรับการแปลง

## นำเข้าแพ็กเกจ
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: อ่านไฟล์โครงการต้นฉบับ
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
แทนที่ `"Your Data Directory"` ด้วยพาธเต็มที่ไฟล์ `.mpp` ของคุณอยู่ การทำเช่นนี้จะโหลดโครงการเข้าสู่หน่วยความจำเพื่อให้คุณสามารถจัดการหรือส่งออกได้

### ขั้นตอนที่ 2: บันทึกโครงการเป็น PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
บรรทัดด้านบนทำการ **บันทึกโครงการเป็น PDF** อย่างตรงไปตรงมา โดยสร้างไฟล์ `Project5.pdf` ในโฟลเดอร์เดียวกัน

### ขั้นตอนที่ 3: ปรับขนาดเนื้อหาให้พอดีกับเซลล์ (ตัวเลือกการบันทึก PDF ขั้นสูง)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
ที่นี่เราจะแสดงการใช้ **pdf save options** เพื่อควบคุมการจัดวาง:
- `setFitContent(true)` ทำให้เนื้อหาเต็มความกว้างของเซลล์  
- `setTimescale(Timescale.Months)` เปลี่ยน timescale เป็นเดือน  
- `setPresentationFormat(PresentationFormat.TaskUsage)` เลือกมุมมอง Task Usage

### ขั้นตอนที่ 4: ซ่อน Legends (ผลลัพธ์ที่สะอาดขึ้น)
```java
o.setLegendOnEachPage(false);
```
การปิดการแสดง legends สามารถทำให้ PDF มีขนาดกะทัดรัดมากขึ้น โดยเฉพาะสำหรับโครงการขนาดใหญ่

### ขั้นตอนที่ 5: บันทึกโครงการพร้อมตัวเลือกที่กำหนด
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
ขั้นตอนสุดท้ายนี้จะเขียนไฟล์ PDF โดยใช้ตัวเลือกที่กำหนดไว้ข้างต้น ผลลัพธ์คือเอกสารที่มีการสเกลเป็นเดือนและไม่มี legends ในแต่ละหน้า

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **ไฟล์ไม่พบ:** ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`) และชี้ไปยังไดเรกทอรีที่ถูกต้อง  
- **หน้าเปล่า:** ตรวจสอบว่า `PresentationFormat` ที่เลือกตรงกับมุมมองที่คุณต้องการ (เช่น Gantt, Task Usage)  
- **ไฟล์ขนาดใหญ่ใช้เวลานาน:** พิจารณาตั้งค่า `o.setFitContent(false)` สำหรับโครงการขนาดใหญ่มากเพื่อลดเวลาในการประมวลผล  

## คำถามที่พบบ่อย

**ถาม: Aspose.Tasks รองรับทุกเวอร์ชันของ Java หรือไม่?**  
ตอบ: รองรับ Java ตั้งแต่ JDK 6 ขึ้นไป

**ถาม: สามารถปรับแต่งลักษณะของ PDF ที่ได้ได้หรือไม่?**  
ตอบ: แน่นอน! Aspose.Tasks มี **pdf save options** มากมาย เช่น timescale, การแสดง/ซ่อน legend, และรูปแบบการนำเสนอ เพื่อให้คุณปรับ PDF ตามความต้องการ

**ถาม: Aspose.Tasks รองรับรูปแบบไฟล์อื่นสำหรับการแปลงหรือไม่?**  
ตอบ: รองรับการแปลงระหว่าง MPP, XML, XLSX และรูปแบบอื่น ๆ มากมาย ทำให้เป็นเครื่องมือที่หลากหลายสำหรับ **convert mpp to pdf** และการแปลงอื่น ๆ

**ถาม: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks หรือไม่?**  
ตอบ: มี คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีได้จาก [ที่นี่](https://releases.aspose.com/)

**ถาม: จะหาการสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
ตอบ: สำหรับการสนับสนุนและความช่วยเหลือ ให้เยี่ยมชมฟอรั่มอย่างเป็นทางการของ [Aspose.Tasks](https://forum.aspose.com/c/tasks/15)

## สรุป
โดยทำตามคู่มือนี้ คุณจะรู้ **วิธีการส่งออก PDF** จากโครงการ Java ใด ๆ ด้วย Aspose.Tasks ตั้งแต่การบันทึกแบบบรรทัดเดียวจนถึงการปรับแต่งขั้นสูงด้วย `PdfSaveOptions` ใช้เทคนิคเหล่านี้เพื่อสร้าง PDF ที่ดูเป็นมืออาชีพและพร้อมแชร์สำหรับการรายงาน, การนำเสนอให้ลูกค้า, หรือการเก็บรักษาเอกสาร

---

**อัปเดตล่าสุด:** 2025-12-20  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}