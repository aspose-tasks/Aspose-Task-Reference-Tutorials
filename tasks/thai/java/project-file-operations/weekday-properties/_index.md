---
date: 2025-12-23
description: เรียนรู้วิธีใช้ Aspose.Tasks Java เพื่ออัปเดตกำหนดการโครงการ ตั้งวันเริ่มต้นของสัปดาห์
  เปลี่ยนจำนวนวันต่อเดือน และปรับแต่งปฏิทินโครงการอย่างมีประสิทธิภาพ
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – การจัดการคุณสมบัติของวันทำงาน
url: /th/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – การจัดการคุณสมบัติของวันทำงาน

## บทนำ
Aspose.Tasks for Java (aspose tasks java) เป็น API ที่แข็งแกร่งซึ่งช่วยให้นักพัฒนา Java ทำงานกับไฟล์ Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **โหลดไฟล์ MPP**, **ตั้งค่าวันเริ่มสัปดาห์**, **เปลี่ยนจำนวนวันต่อเดือน**, และ **ปรับแต่งปฏิทินโครงการ** — ขั้นตอนสำคัญสำหรับการอัปเดตกำหนดการโครงการ เมื่อจบบทเรียนคุณจะสามารถปรับคุณสมบัติของวันทำงานโดยใช้โปรแกรมและบันทึกการเปลี่ยนแปลงในรูปแบบที่ต้องการได้

## คำตอบสั้น
- **คลาสหลักสำหรับจัดการโครงการคืออะไร?** `Project` จากไลบรารี Aspose.Tasks.  
- **ฉันจะเปลี่ยนวันเริ่มสัปดาห์ได้อย่างไร?** ใช้ `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **ฉันสามารถโหลดไฟล์ .mpp ที่มีอยู่ได้หรือไม่?** ได้ — สร้างอินสแตนซ์ `Project` พร้อมเส้นทางไฟล์.  
- **เมธอดใดที่บันทึกโครงการเป็น XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน; ต้องมีไลเซนส์สำหรับการใช้งานจริง.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มต้น, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Java Development Kit (JDK)** – ติดตั้งเวอร์ชันล่าสุด  
- **Aspose.Tasks for Java library** – ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/tasks/java/).  
- **IDE** เช่น IntelliJ IDEA, Eclipse หรือ NetBeans.  

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น, ให้นำเข้าคลาส Aspose.Tasks ที่จำเป็น:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

ตอนนี้เราจะเดินผ่านแต่ละขั้นตอนของการจัดการคุณสมบัติของวันทำงาน.

## ขั้นตอนที่ 1: โหลดไฟล์ MPP
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*ที่นี่เราจะ **โหลดไฟล์ .mpp ที่มีอยู่** (`load mpp file`) เพื่อให้เราสามารถตรวจสอบและแก้ไขการตั้งค่าปฏิทินของมันได้.*

## ขั้นตอนที่ 2: แสดงคุณสมบัติของวันทำงานปัจจุบัน
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
โค้ดนี้จะแสดง **วันเริ่มสัปดาห์**, **จำนวนวันต่อเดือน**, **นาทีต่อวัน**, และ **นาทีต่อสัปดาห์** — ส่วนสำคัญที่คุณมักต้อง **ปรับแต่งปฏิทินโครงการ**.

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติของวันทำงานใหม่
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
ในขั้นตอนนี้เราจะ **ตั้งค่าวันเริ่มสัปดาห์** เป็น Monday, **เปลี่ยนจำนวนวันต่อเดือน** เป็น 24, และปรับจำนวนนาทีต่อวันและต่อสัปดาห์ การตั้งค่านี้เป็นปกติเมื่อคุณต้อง **อัปเดตกำหนดการโครงการ** ให้สอดคล้องกับปฏิทินการทำงานที่ไม่เป็นมาตรฐาน.

## ขั้นตอนที่ 4: บันทึกโครงการที่อัปเดต
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
โครงการที่แก้ไขแล้วจะถูกบันทึกเป็นไฟล์ XML ทำให้ง่ายต่อการแชร์หรือนำเข้าไปยังเครื่องมืออื่น ๆ.

## ขั้นตอนที่ 5: ยืนยันการดำเนินการ
```java
System.out.println("Process completed Successfully");
```
ข้อความคอนโซลง่าย ๆ จะบอกคุณว่ากระบวนการทำงานเสร็จสมบูรณ์โดยไม่มีข้อผิดพลาด.

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **เส้นทางไฟล์ไม่ถูกต้อง** – ตรวจสอบว่า `dataDir` ลงท้ายด้วยเครื่องหมายทับหรือใช้ `Paths.get(...)` สำหรับเส้นทางที่เป็นอิสระต่อแพลตฟอร์ม.  
- **ไม่ได้ตั้งค่าไลเซนส์** – ในสภาพแวดล้อมการผลิต, เรียก `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` ก่อนสร้าง `Project`.  
- **วันเริ่มสัปดาห์ที่ไม่คาดคิด** – ตรวจสอบว่าคุณใช้ค่า enum `DayType` ที่ถูกต้อง (เช่น `DayType.Sunday`).  

## คำถามที่พบบ่อย

**Q: Aspose.Tasks for Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?**  
A: ใช่, Aspose.Tasks for Java ให้การสนับสนุนที่ครอบคลุมสำหรับการจัดการโครงสร้างโครงการที่ซับซ้อนได้อย่างง่ายดาย.

**Q: Aspose.Tasks for Java เข้ากันได้กับเวอร์ชันต่าง ๆ ของไฟล์ Microsoft Project หรือไม่?**  
A: แน่นอน, Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของไฟล์ Microsoft Project, ทำให้มั่นใจได้ว่ามีความเข้ากันได้ข้ามแพลตฟอร์ม.

**Q: ฉันสามารถรวม Aspose.Tasks for Java เข้าไปในแอปพลิเคชัน Java ที่มีอยู่ของฉันได้หรือไม่?**  
A: ได้, Aspose.Tasks for Java มีความสามารถในการบูรณาการอย่างราบรื่น, ช่วยให้คุณเสริมแอปพลิเคชัน Java ของคุณด้วยฟีเจอร์การจัดการโครงการที่ทรงพลัง.

**Q: Aspose.Tasks for Java มีเอกสารและการสนับสนุนหรือไม่?**  
A: ใช่, คุณสามารถเข้าถึงเอกสารที่ครอบคลุมและการสนับสนุนจากชุมชนสำหรับ Aspose.Tasks for Java ได้ที่ [เว็บไซต์](https://releases.aspose.com/).

**Q: มีเวอร์ชันทดลองฟรีสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีของ Aspose.Tasks for Java จาก [เว็บไซต์](https://reference.aspose.com/tasks/java/) เพื่อสำรวจคุณสมบัติก่อนตัดสินใจซื้อ.

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}