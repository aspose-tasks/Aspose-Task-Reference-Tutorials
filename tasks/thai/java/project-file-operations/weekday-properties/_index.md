---
date: 2026-03-29
description: เรียนรู้วิธีเปลี่ยนจำนวนวันต่อเดือนและจัดการคุณสมบัติของวันในสัปดาห์อื่น
  ๆ ใน Aspose.Tasks สำหรับ Java ปรับแต่งวันเริ่มต้นของสัปดาห์ แก้ไขปฏิทินโครงการ และบันทึกโครงการเป็น
  XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: เปลี่ยนจำนวนวันต่อเดือนโดยใช้คุณสมบัติ Weekday ของ Aspose.Tasks
url: /th/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เปลี่ยนจำนวนวันต่อเดือนด้วยคุณสมบัติวันทำงานของ Aspose.Tasks

## บทนำ
Aspose.Tasks for Java ให้คุณ **change days per month** และปรับแต่งการตั้งค่าวันทำงานอื่น ๆ ได้โดยไม่ต้องติดตั้ง Microsoft Project ไม่ว่าคุณจะกำหนดปฏิทินโครงการให้สอดคล้องกับเดือนงบประมาณที่ไม่เป็นมาตรฐานหรือเพียงต้องการปรับวันเริ่มต้นของสัปดาห์ การสอนนี้จะพาคุณผ่านสถานการณ์ที่พบบ่อยที่สุด — การดึงวันเริ่มต้นสัปดาห์ปัจจุบัน, การกำหนดวันเริ่มต้นสัปดาห์, การแก้ไขปฏิทินโครงการ, และการบันทึกโครงการเป็น XML.

## คำตอบอย่างรวดเร็ว
- **ฉันสามารถเปลี่ยนจำนวนวันต่อเดือนได้หรือไม่?** ใช่, ใช้ `Prj.DAYS_PER_MONTH` กับอ็อบเจ็กต์ `Project`.  
- **ฉันจะกำหนดวันเริ่มต้นของสัปดาห์อย่างไร?** ตั้งค่า `Prj.WEEK_START_DAY` เป็นค่า `DayType` (เช่น `DayType.Monday`).  
- **ฉันสามารถใช้รูปแบบใดเพื่อส่งออกโครงการ?** ตัวอย่างบันทึกไฟล์เป็น XML ด้วย `SaveFileFormat.Xml`.  
- **ต้องการใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานที่ไม่ใช่การประเมินผล.  
- **IDE ใดบ้างที่รองรับ?** IDE ของ Java ใดก็ได้ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans จะทำงานได้.

## อะไรคือ “change days per month” ใน Aspose.Tasks?
การเปลี่ยนจำนวนวันต่อเดือนหมายถึงการอัปเดตคุณสมบัติ `Prj.DAYS_PER_MONTH` ของอินสแตนซ์ `Project` คุณสมบัตินี้บอกให้เอนจินทราบว่าต้องพิจารณาจำนวนวันทำงานในแต่ละเดือนเท่าใด ซึ่งมีผลโดยตรงต่อการจัดตารางงานและการคำนวณค่าใช้จ่าย.

## ทำไมต้องแก้ไขคุณสมบัติของปฏิทินโครงการ?
การปรับแต่งปฏิทินโครงการ — เช่น การตั้งค่าวันเริ่มต้นของสัปดาห์ที่แตกต่างหรือการเปลี่ยนจำนวนนาทีต่อวัน — ช่วยให้คุณ:
- ปรับตารางให้สอดคล้องกับสัปดาห์ทำงานของภูมิภาค.  
- จำลองรูปแบบการทำงานที่ไม่เป็นมาตรฐาน (เช่น สัปดาห์ 4 วัน).  
- รับประกันการรายงานที่แม่นยำสำหรับสัญญาที่ใช้ปฏิทินแบบกำหนดเอง.

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** – ติดตั้ง JDK รุ่นล่าสุดจาก Oracle.  
- **Aspose.Tasks for Java library** – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ [here](https://releases.aspose.com/tasks/java/).  
- **IDE ที่คุณเลือก** – IntelliJ IDEA, Eclipse, หรือ NetBeans ทำงานได้.

## นำเข้าแพ็กเกจ
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
นี่จะโหลดไฟล์ Microsoft Project ที่มีอยู่ (`project.mpp`) จากโฟลเดอร์ที่คุณระบุ.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## ขั้นตอนที่ 2: แสดงคุณสมบัติวันทำงาน
ที่นี่เราดึงและพิมพ์การตั้งค่าวันทำงานปัจจุบัน รวมถึง **week start day** และ **days per month**.

```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติวันทำงาน
ในขั้นตอนนี้เราจะ **change days per month** เป็น 24, ตั้งให้สัปดาห์เริ่มต้นในวันจันทร์, และปรับจำนวนนาทีต่อวัน/สัปดาห์. สิ่งนี้แสดงให้เห็นวิธี **modify project calendar** ค่าโดยโปรแกรม.

```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```

## ขั้นตอนที่ 4: บันทึกโครงการ
โครงการที่แก้ไขแล้วจะถูกบันทึกโดยใช้รูปแบบ **save project as XML** ซึ่งสะดวกสำหรับการรวมกับเครื่องมืออื่นหรือการจัดเก็บที่ควบคุมเวอร์ชัน.

```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```

## ขั้นตอนที่ 5: แสดงผล
การยืนยันอย่างง่ายว่าการดำเนินการเสร็จสิ้นโดยไม่มีข้อผิดพลาด.

```java
System.out.println("Process completed Successfully");
```

## วิธีกำหนดวันเริ่มต้นของสัปดาห์
หากองค์กรของคุณใช้ปฏิทินที่เริ่มต้นด้วยวันอาทิตย์, ให้แทนที่ `DayType.Monday` ด้วย `DayType.Sunday`. คุณสมบัติเดียวกัน (`Prj.WEEK_START_DAY`) ถูกใช้ ทำให้การเปลี่ยนแปลงง่ายดาย.

## วิธีดึงวันเริ่มต้นของสัปดาห์
คุณสามารถเรียก `project.get(Prj.WEEK_START_DAY)` ได้ตลอดเวลาเพื่อ **retrieve week start day** ข้อมูล ตามที่แสดงในขั้นตอน 2.

## วิธีแก้ไขปฏิทินโครงการ
นอกจากวันเริ่มต้นของสัปดาห์แล้ว คุณยังสามารถปรับ `Prj.MINUTES_PER_DAY` และ `Prj.MINUTES_PER_WEEK` เพื่อสะท้อนชั่วโมงทำงานหรือรูปแบบกะที่กำหนดเอง.

## ปัญหาทั่วไปและวิธีแก้
- **Incorrect day type value** – ตรวจสอบว่าคุณใช้ enum `DayType` (เช่น `DayType.Monday`).  
- **File path errors** – ตรวจสอบว่า `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ที่เหมาะสม (`/` หรือ `\`).  
- **License not set** – หากคุณเห็นคำเตือนเรื่องใบอนุญาต, ลงทะเบียนใบอนุญาต Aspose.Tasks ของคุณก่อนสร้างอ็อบเจ็กต์ `Project`.

## คำถามที่พบบ่อย

**Q: Aspose.Tasks for Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?**  
A: ใช่, Aspose.Tasks for Java ให้การสนับสนุนอย่างครอบคลุมสำหรับการจัดการโครงสร้างโครงการที่ซับซ้อนได้อย่างง่ายดาย.

**Q: Aspose.Tasks for Java เข้ากันได้กับเวอร์ชันต่าง ๆ ของไฟล์ Microsoft Project หรือไม่?**  
A: แน่นอน, Aspose.Tasks for Java รองรับไฟล์ Microsoft Project หลายเวอร์ชัน, ทำให้มั่นใจว่ามีความเข้ากันได้ข้ามแพลตฟอร์ม.

**Q: ฉันสามารถผสานรวม Aspose.Tasks for Java เข้ากับแอปพลิเคชัน Java ที่มีอยู่ของฉันได้หรือไม่?**  
A: ใช่, Aspose.Tasks for Java มีความสามารถในการผสานรวมอย่างราบรื่น, ช่วยให้คุณเพิ่มคุณลักษณะการจัดการโครงการที่ทรงพลังให้กับแอปพลิเคชัน Java ของคุณ.

**Q: Aspose.Tasks for Java มีเอกสารและการสนับสนุนหรือไม่?**  
A: ใช่, คุณสามารถเข้าถึงเอกสารที่ครอบคลุมและการสนับสนุนจากชุมชนสำหรับ Aspose.Tasks for Java ได้ที่ [website](https://releases.aspose.com/).

**Q: มีการทดลองใช้งานฟรีสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: ใช่, คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีของ Aspose.Tasks for Java จาก [website](https://reference.aspose.com/tasks/java/) เพื่อสำรวจคุณสมบัติก่อนทำการซื้อ.

---

**อัปเดตล่าสุด:** 2026-03-29  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}