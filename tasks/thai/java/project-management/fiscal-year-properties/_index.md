---
date: 2026-04-01
description: เรียนรู้วิธีบันทึก XML, ตั้งปีงบประมาณ, และแปลง MPP เป็น XML ด้วย Aspose.Tasks
  สำหรับ Java. คู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ด.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: วิธีบันทึก XML และจัดการปีงบประมาณใน Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีบันทึก XML และจัดการปีงบประมาณใน Aspose.Tasks
url: /th/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบันทึก XML และจัดการปีงบประมาณใน Aspose.Tasks

## บทนำ
หากคุณต้องการ **how to save xml** ไฟล์ที่สร้างจากข้อมูลของ Microsoft Project, Aspose.Tasks for Java จะมอบวิธีที่สะอาดและไม่มีค่าไลเซนส์ให้คุณทำได้ ในบทแนะนำนี้เราจะอธิบายขั้นตอนการโหลดไฟล์ MPP, แสดงข้อมูลปีงบประมาณ, ตั้งค่าคุณสมบัติของปีงบประมาณ, และสุดท้าย **how to save xml** ผลลัพธ์ คุณจะได้เห็นวิธี **how to set fiscal** รายละเอียดและ **how to convert mpp** ไฟล์โดยไม่ต้องเปิด Microsoft Project.

## คำตอบอย่างรวดเร็ว
- **“manage fiscal year” หมายถึงอะไรใน Aspose.Tasks?** It lets you define the fiscal year start month and enable fiscal year numbering for a project.  
- **วิธีตั้งค่าเดือนเริ่มต้นของปีงบประมาณ?** Use the `Prj.FY_START_DATE` property with a `Month` enum value (e.g., `Month.JULY`).  
- **ฉันสามารถโหลดไฟล์ MPP ได้หรือไม่?** Yes, simply create a `Project` instance with the path to the *.mpp* file.  
- **วิธีแปลง MPP เป็น XML?** Call `project.save(..., SaveFileFormat.Xml)` after setting any desired properties.  
- **ฉันต้องการไลเซนส์หรือไม่?** A free trial is available; a commercial license is required for production use.  

## “manage fiscal year” คืออะไรในไฟล์โครงการ?
การจัดการปีงบประมาณหมายถึงการกำหนดปฏิทินที่โครงการของคุณใช้สำหรับการรายงานทางการเงิน ซึ่งรวมถึงการตั้งค่าเดือนเริ่มต้นของปีงบประมาณและอาจเปิดใช้งานการนับเลขปีงบประมาณ ซึ่งส่งผลต่อวิธีการคำนวณและแสดงวันที่ในรายงาน

## ทำไมต้องใช้ Aspose.Tasks สำหรับการจัดการปีงบประมาณ?
- **ไม่จำเป็นต้องใช้ Microsoft Project** – ทำงานกับไฟล์โครงการโดยตรงใน Java.  
- **ควบคุมเต็มรูปแบบ** – ตั้งค่าเดือนเริ่มต้นของปีงบประมาณ, เปิดใช้งานการนับเลข, และแปลงรูปแบบโดยโปรแกรม.  
- **Robust API** – การจัดการไฟล์ MPP ขนาดใหญ่อย่างเชื่อถือได้และการส่งออก XML อย่างราบรื่น.  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK) ติดตั้งบนระบบของคุณ.  
2. Aspose.Tasks for Java JAR – ดาวน์โหลดจาก [here](https://releases.aspose.com/tasks/java/) และเพิ่มลงใน classpath ของโปรเจกต์ของคุณ.

## นำเข้าแพ็กเกจ
To get started, import the necessary classes in your Java source file:
```java
import com.aspose.tasks.*;
```

## วิธีโหลดไฟล์ MPP และแสดงข้อมูลปีงบประมาณ
ด้านล่างเราจะแบ่งกระบวนการเป็นขั้นตอนที่ชัดเจนและเป็นลำดับเลข.

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
ที่นี่เราจะ **load an MPP file** (`project.mpp`) จากไดเรกทอรีที่ระบุ นี่เป็นขั้นตอนแรกในกระบวนการใด ๆ ที่เกี่ยวข้องกับปีงบประมาณ.

### ขั้นตอนที่ 2: แสดงคุณสมบัติของปีงบประมาณ
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
คุณสมบัติ `Prj.FY_START_DATE` และ `Prj.FISCAL_YEAR_START` ทำให้คุณ **display fiscal year** รายละเอียด, ตอบคำถาม “การกำหนดค่าปีงบประมาณปัจจุบันคืออะไร?”

### ขั้นตอนที่ 3: ตั้งค่าเริ่มต้นปีงบประมาณและเปิดใช้งานการนับเลข
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
ในขั้นตอนนี้เราจะ **how to set fiscal** การตั้งค่า:
- `Month.JULY` กำหนดเดือนเริ่มต้นของปีงบประมาณ.  
- `NullableBool(true)` เปิดการนับเลขปีงบประมาณ.  
- สุดท้าย, โครงการจะ **converted MPP to XML** ด้วย `SaveFileFormat.Xml`.

### ขั้นตอนที่ 4: ยืนยันการทำงาน
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
ข้อความคอนโซลง่าย ๆ ยืนยันว่าปีงบประมาณได้ถูกกำหนดค่าและไฟล์ได้ถูกบันทึกแล้ว.

## ทำไมเรื่องนี้ถึงสำคัญ
การบันทึกโครงการเป็น XML จะให้รูปแบบที่พกพาได้และเป็นข้อความที่สามารถแยกวิเคราะห์, ควบคุมเวอร์ชัน, หรือรวมเข้ากับระบบอื่น ๆ ได้อย่างง่ายดาย เมื่อการตั้งค่าปีงบประมาณถูกต้อง รายงานการเงินและแดชบอร์ดที่ต่อมาจะสอดคล้องกับช่วงเวลาการบัญชีขององค์กรของคุณ.

## กรณีการใช้งานทั่วไป
- **Financial reporting** – ปรับตารางโครงการให้สอดคล้องกับปฏิทินปีงบประมาณก่อนส่งออกไปยังเครื่องมือ BI.  
- **Data migration** – แปลงไฟล์ *.mpp* เก่าเป็น XML เพื่อทำการนำเข้าไปยังแพลตฟอร์มการจัดการโครงการบนคลาวด์.  
- **Automated audits** – ตรวจสอบโดยอัตโนมัติว่าโครงการทุกโครงการใช้เดือนเริ่มต้นปีงบประมาณที่ถูกต้อง.

## เคล็ดลับการแก้ไขปัญหาและข้อผิดพลาดทั่วไป
| ปัญหา | วิธีแก้ |
|-------|----------|
| **ค่าของเดือนไม่ถูกต้อง** | ตรวจสอบว่าคุณใช้ `Month` enum (เช่น `Month.JANUARY`). |
| **ไม่พบไฟล์** | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและชื่อไฟล์ตรงกัน. |
| **การบันทึกล้มเหลว** | ตรวจสอบสิทธิ์การเขียนในไดเรกทอรีเป้าหมายและว่า `SaveFileFormat` รองรับ. |
| **ปีงบประมาณไม่แสดงใน XML** | หลังจากบันทึก, เปิดไฟล์ XML และยืนยันว่าโหนด `<FiscalYearStart>` และ `<FiscalYearNumbering>` มีค่าที่คาดหวัง. |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Tasks for Java เพื่อจัดการคุณสมบัติอื่นของโครงการได้หรือไม่?**  
A: ใช่, Aspose.Tasks มีฟังก์ชันที่ครอบคลุมเพื่อจัดการคุณสมบัติโครงการต่าง ๆ นอกเหนือจากการตั้งค่าปีงบประมาณ.

**ถาม: Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการต่าง ๆ หรือไม่?**  
A: ใช่, รองรับรูปแบบหลากหลายรวมถึง MPP, XML และอื่น ๆ.

**ถาม: ฉันจะขอรับการสนับสนุนได้อย่างไรหากพบปัญหาในการใช้ Aspose.Tasks for Java?**  
A: คุณสามารถขอความช่วยเหลือจากชุมชน Aspose.Tasks ได้ที่ [forum](https://forum.aspose.com/c/tasks/15) หรือ ติดต่อทีมสนับสนุนโดยตรง.

**ถาม: Aspose.Tasks มีเวอร์ชันทดลองใช้ฟรีหรือไม่?**  
A: ใช่, คุณสามารถเข้าถึงเวอร์ชันทดลองใช้ฟรีของ Aspose.Tasks ได้จาก [here](https://releases.aspose.com/).

**ถาม: ฉันสามารถซื้อไลเซนส์สำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: คุณสามารถซื้อไลเซนส์สำหรับ Aspose.Tasks for Java ได้จาก [here](https://purchase.aspose.com/buy).

## สรุป
การจัดการคุณสมบัติของปีงบประมาณใน Aspose.Tasks for Java ทำได้อย่างง่ายดาย โดยทำตามขั้นตอนข้างต้นคุณสามารถ **how to save xml**, **load mpp file**, **display fiscal year**, **set fiscal year**, และ **convert mpp to xml** อย่างมั่นใจ ใช้เทคนิคเหล่านี้เพื่อให้ตารางโครงการของคุณสอดคล้องกับปฏิทินการเงินขององค์กรและสร้างการแสดงผล XML ที่พกพาได้สำหรับการประมวลผลต่อไป.

---

**อัปเดตล่าสุด:** 2026-04-01  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}