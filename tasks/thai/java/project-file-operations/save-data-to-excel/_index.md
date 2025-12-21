---
date: 2025-12-21
description: เรียนรู้วิธีการส่งออก MPP ไปยัง Excel และแปลงไฟล์โครงการเป็น Excel ด้วย
  Aspose.Tasks สำหรับ Java ขั้นตอนง่ายสำหรับนักพัฒนา Java.
linktitle: Save Data to Excel in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีการส่งออก MPP ไปยัง Excel ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการส่งออก MPP ไปยัง Excel ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
Aspose.Tasks for Java เป็นไลบรารีที่ทรงพลังที่ช่วยให้คุณ **ส่งออก MPP ไปยัง Excel** อย่างรวดเร็วและเชื่อถือได้ ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนที่จำเป็นในการแปลงไฟล์ Microsoft Project (.mpp) ไปเป็นเวิร์กบุ๊ก Excel (.xlsx) เมื่อเสร็จคุณจะเข้าใจวิธี **แปลงไฟล์โครงการเป็น Excel**, ทำไมการแปลงนี้จึงมีประโยชน์, และวิธีผสานกระบวนการนี้เข้ากับแอปพลิเคชัน Java ใด ๆ

## คำตอบสั้น
- **API ทำอะไร?** มันอ่านไฟล์ Project และบันทึกโดยตรงเป็นเวิร์กบุ๊ก XLSX.  
- **รูปแบบที่สร้างคืออะไร?** ไฟล์ Excel ที่ใช้ตัวเลือก `SaveFileFormat.Xlsx`.  
- **ต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองใช้ได้สำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ข้อกำหนดเบื้องต้นคืออะไร?** ติดตั้ง JDK และเพิ่มไลบรารี Aspose.Tasks for Java ลงในโปรเจกต์ของคุณ.  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับการส่งออกพื้นฐาน.

## การส่งออก MPP ไปยัง Excel คืออะไร?
การส่งออก MPP ไปยัง Excel หมายถึงการนำกำหนดการ, ทรัพยากร, และข้อมูลงานที่เก็บไว้ในไฟล์ Microsoft Project แล้วเขียนลงในสเปรดชีต Excel ที่มีโครงสร้าง ทำให้สามารถแชร์ข้อมูลโครงการกับผู้มีส่วนได้ส่วนเสียที่อาจไม่มีโปรแกรม Project ติดตั้งได้ง่าย

## ทำไมต้องแปลงไฟล์ MPP เป็น XLSX?
- **การเข้าถึงที่กว้างขวาง:** Excel มีอยู่ทั่วไปในสภาพแวดล้อมธุรกิจ.  
- **การรายงานที่ง่ายขึ้น:** ใช้ Pivot Table, แผนภูมิ, และสูตรของ Excel เพื่อวิเคราะห์เมตริกของโครงการ.  
- **เป็นมิตรกับการอัตโนมัติ:** ไฟล์ Excel สามารถประมวลผลโดยระบบหรือสคริปต์อื่น ๆ โดยไม่ต้องใช้ Project.  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Java Development Kit (JDK)** – ติดตั้งและเพิ่มลงใน PATH ของระบบของคุณ.  
2. **ไลบรารี Aspose.Tasks for Java** – ดาวน์โหลดจาก [download link](https://releases.aspose.com/tasks/java/) และเพิ่มไฟล์ JAR ไปยัง classpath ของโปรเจกต์ของคุณ.

## นำเข้าแพ็กเกจ
แรกเริ่ม, ให้นำเข้าคลาสที่คุณต้องการ ใช้บล็อกนี้ตามที่แสดงไว้โดยไม่แก้ไข – จำเป็นสำหรับการทำงานของ API.

```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรีข้อมูล
กำหนดโฟลเดอร์ที่ไฟล์ `.mpp` ของคุณอยู่. แทนที่ตัวแปรตำแหน่งที่เก็บด้วยเส้นทางจริงของคุณ.

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์ Project
สร้างอินสแตนซ์ `Project` โดยการโหลดไฟล์ `.mpp` ที่คุณต้องการแปลง. การทำเช่นนี้จะอ่านงานทั้งหมด, ทรัพยากร, และข้อมูลการกำหนดเวลา.

```java
Project project = new Project(dataDir + "project5.mpp");
```

### ขั้นตอนที่ 3: บันทึก Project เป็น XLSX
สุดท้าย, ส่งออกโปรเจกต์ที่โหลดแล้วเป็นเวิร์กบุ๊ก Excel. ธง `SaveFileFormat.Xlsx` บอก Aspose.Tasks ให้สร้างไฟล์ `.xlsx` สมัยใหม่, ซึ่งเป็นการ **แปลงไฟล์ MPP เป็น XLSX** อย่างมีประสิทธิภาพ.

```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```

## กรณีการใช้งานทั่วไป
- **การรายงานระดับผู้บริหาร:** ให้ภาพรวมโครงการระดับสูงใน Excel สำหรับผู้บริหารระดับสูง.  
- **การวิเคราะห์ข้อมูล:** ป้อนข้อมูลงานและทรัพยากรเข้าสู่ Power Query ของ Excel เพื่อรับข้อมูลเชิงลึกที่ลึกซึ้ง.  
- **การบูรณาการ:** ส่งไฟล์ Excel ที่ส่งออกให้กับระบบ downstream ที่รับเฉพาะอินพุต CSV/Excel.  

## สรุป
ในคู่มือนี้เราได้สาธิต **วิธีการส่งออก MPP ไปยัง Excel** ด้วย Aspose.Tasks for Java โดยทำตามสามขั้นตอนง่าย ๆ — กำหนดไดเรกทอรีข้อมูล, โหลดไฟล์ Project, และบันทึกเป็น XLSX — คุณสามารถ **ส่งออกข้อมูลโครงการไปยัง Excel** ได้อย่างง่ายดายและเสริมพลังให้ทีมของคุณด้วยรายงานที่ยืดหยุ่นและสามารถแชร์ได้.

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks for Java เพื่อจัดการข้อมูลโครงการแบบโปรแกรมได้หรือไม่?
ใช่, Aspose.Tasks for Java มีฟีเจอร์ที่ครอบคลุมในการจัดการข้อมูลโครงการ, รวมถึงการอ่าน, เขียน, และแก้ไขไฟล์โครงการ.

### มีเวอร์ชันทดลองฟรีสำหรับ Aspose.Tasks for Java หรือไม่?
ใช่, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีของ Aspose.Tasks for Java ได้จาก [here](https://releases.aspose.com/).

### ฉันจะหาเอกสารสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
คุณสามารถค้นหาเอกสารสำหรับ Aspose.Tasks for Java ได้ที่ [here](https://reference.aspose.com/tasks/java/).

### ฉันจะรับการสนับสนุนสำหรับปัญหาหรือคำถามที่เกี่ยวกับ Aspose.Tasks for Java อย่างไร?
คุณสามารถรับการสนับสนุนโดยไปที่ฟอรั่ม Aspose.Tasks ที่ [here](https://forum.aspose.com/c/tasks/15).

### ฉันสามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks for Java ได้หรือไม่?
ใช่, คุณสามารถซื้อไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-21  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose