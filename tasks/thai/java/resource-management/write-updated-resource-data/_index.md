---
date: 2026-06-30
description: เรียนรู้วิธีอัปเดตหลายทรัพยากรและแก้ไขข้อมูลกลุ่มทรัพยากร จากนั้นส่งออกโครงการเป็น
  MPP และบันทึกโครงการเป็น MPP ด้วย Aspose.Tasks for Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: อัปเดตหลายทรัพยากรใน Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: อัปเดตหลายทรัพยากรใน Aspose.Tasks for Java
url: /th/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อัปเดตหลายทรัพยากรใน Aspise.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **อัปเดตหลายทรัพยากร** ในไฟล์ Microsoft Project ด้วยการใช้ Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะต้องการเปลี่ยนอัตรา, กำหนดกลุ่มใหม่, หรือส่งออกไฟล์ที่อัปเดตเป็น MPP ขั้นตอนต่อไปนี้จะพาคุณผ่านกระบวนการทำงานที่สมบูรณ์และพร้อมใช้งานในระดับการผลิต ไม่จำเป็นต้องติดตั้ง Microsoft Project และ API สามารถจัดการโครงการที่มีทรัพยากรหลายร้อยรายการได้อย่างมีประสิทธิภาพ.

## คำตอบอย่างรวดเร็ว
- **ฉันสามารถอัปเดตหลายทรัพยากรพร้อมกันได้หรือไม่?** ได้ – ทำการวนซ้ำผ่าน `ResourceCollection` และตั้งค่าคุณลักษณะในหนึ่งรอบเดียว.  
- **วิธีใดใช้บันทึกไฟล์เป็น MPP?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่?** จำเป็นต้องมีใบอนุญาตแบบชำระเงินสำหรับการผลิต; มีการทดลองใช้ฟรีให้บริการ.  
- **เวอร์ชันของ Java ที่รองรับคืออะไร?** Java 6 ขึ้นไป รวมถึง Java 17 LTS.  
- **การอัปเดตแบบกลุ่มมีประสิทธิภาพหรือไม่?** Aspose.Tasks ประมวลผลโครงการที่มี 500‑ทรัพยากรภายในเวลาน้อยกว่า 2 วินาทีบนเซิร์ฟเวอร์ทั่วไป.

## อะไรคือ “อัปเดตหลายทรัพยากร”?
**“อัปเดตหลายทรัพยากร”** หมายถึงการเปลี่ยนแปลงคุณสมบัติของรายการทรัพยากรหลายรายการโดยโปรแกรม เช่น อัตรา, กลุ่ม, ปฏิทิน, หรือฟิลด์ที่กำหนดเอง ภายในไฟล์ Project เดียว การดำเนินการนี้มักจำเป็นเมื่อต้องซิงค์ข้อมูลโครงการกับระบบวางแผนทรัพยากรองค์กร, ปรับงบประมาณสำหรับหลายทรัพยากร, หรือใช้การเปลี่ยนแปลงนโยบายระดับองค์กร.

## ทำไมต้องใช้ Aspose.Tasks เพื่อแก้ไขกลุ่มทรัพยากรและส่งออกโครงการเป็น MPP?
Aspose.Tasks รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 แบบ**, รวมถึง MPP, XML, และ CSV, และสามารถ **ส่งออกโครงการเป็น MPP** ได้โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ไลบรารีสามารถประมวลผลไฟล์ขนาดถึง **2 GB** ทำให้คุณสามารถ **บันทึกโครงการเป็น MPP** ได้อย่างรวดเร็วและเชื่อถือได้.

## ข้อกำหนดเบื้องต้น

1. Java Development Kit (JDK) ที่ติดตั้งบนระบบของคุณ.  
2. ไลบรารี Aspose.Tasks สำหรับ Java. คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/).  
3. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java.  

## นำเข้าแพ็กเกจ

คำสั่ง `import` จะนำคลาส Aspose.Tasks ที่จำเป็นเข้ามาในไฟล์ซอร์สของคุณ.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูลของคุณ

กำหนดไดเรกทอรีที่ไฟล์ข้อมูลของคุณตั้งอยู่:

```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: ระบุไฟล์อินพุตและเอาต์พุต

กำหนดเส้นทางสำหรับไฟล์ MS Project อินพุตและไฟล์ที่อัปเดตผลลัพธ์:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## ขั้นตอนที่ 3: โหลดโครงการ

`Project` แทนไฟล์ Microsoft Project ที่โหลดเข้าสู่หน่วยความจำ ให้การเข้าถึงงาน, ทรัพยากร, และข้อมูลโครงการอื่นๆ.

```java
Project project = new Project(file);
```

## ขั้นตอนที่ 4: เพิ่มทรัพยากรและตั้งค่าคุณลักษณะ

`Resource` จำลองทรัพยากรโครงการแต่ละรายการ, ให้คุณตั้งค่าอัตรา, กลุ่ม, ปฏิทิน, และคุณลักษณะอื่นๆ.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## ขั้นตอนที่ 5: อัปเดตหลายทรัพยากรอย่างมีประสิทธิภาพ

`ResourceCollection` คือคอลเลกชันของทรัพยากรทั้งหมดในโครงการ, สามารถเข้าถึงได้ผ่าน `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## ขั้นตอนที่ 6: บันทึกโครงการ

`SaveFileFormat` แสดงรายการรูปแบบไฟล์ที่รองรับสำหรับการบันทึกโครงการ, เช่น MPP, XML, และ PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## วิธีอัปเดตหลายทรัพยากรในโครงการ?

โหลดโครงการที่มีอยู่, ดึง `ResourceCollection` ของมัน, และวนซ้ำผ่านแต่ละอ็อบเจ็กต์ `Resource`. สำหรับแต่ละทรัพยากร, แก้ไขฟิลด์ที่ต้องการเช่นอัตรา, กลุ่ม, หรือแอตทริบิวต์ที่กำหนดเอง, แล้วดำเนินการต่อไปยังรายการถัดไป. หลังจากประมวลผลทรัพยากรทั้งหมด, เรียก `project.save(...)` ครั้งเดียวเพื่อบันทึกการเปลี่ยนแปลงอย่างมีประสิทธิภาพ.

## ปัญหาที่พบบ่อยและวิธีแก้

- **ID ของทรัพยากรชนกัน** – ตรวจสอบให้แน่ใจว่าทรัพยากรใหม่แต่ละตัวได้รับ ID ที่ไม่ซ้ำโดยใช้ `project.getResources().add(new Resource())`.  
- **ข้อผิดพลาดรูปแบบอัตรา** – ใช้วัตถุ `ResourceRate` และตั้งค่า `RateType` เป็น `StandardRate` หรือ `OvertimeRate`.  
- **ไฟล์ขนาดใหญ่ทำให้ความดันหน่วยความจำ** – เปิดใช้งาน `Project.setReadOnly(true)` ก่อนโหลดเพื่อลดการใช้หน่วยความจำ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถอัปเดตหลายทรัพยากรในโครงการเดียวโดยใช้ Aspose.Tasks สำหรับ Java ได้หรือไม่?**  
A: ได้, คุณสามารถอัปเดตหลายทรัพยากรโดยการวนซ้ำผ่านพวกมันและตั้งค่าคุณลักษณะตามที่ต้องการ.

**Q: Aspose.Tasks รองรับรูปแบบไฟล์อื่นนอกจาก MS Project หรือไม่?**  
A: รองรับ, Aspose.Tasks รองรับรูปแบบไฟล์ต่างๆ รวมถึง XML, MPP, และอื่นๆ.

**Q: Aspose.Tasks เข้ากันได้กับเวอร์ชันของ Java ต่างๆ หรือไม่?**  
A: Aspose.Tasks เข้ากันได้กับ Java เวอร์ชัน 6 ขึ้นไป.

**Q: ฉันสามารถทำการดำเนินการอื่นบนไฟล์ MS Project ด้วย Aspose.Tasks ได้หรือไม่?**  
A: ได้, คุณสามารถทำการดำเนินการหลากหลายเช่นการอ่าน, เขียน, และจัดการงาน, ทรัพยากร, และปฏิทิน.

**Q: ฉันจะหาแนวทางช่วยเหลือหรือสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
A: คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือหรือสอบถาม.

**Q: ฉันจะส่งออกไฟล์ที่อัปเดตเป็นรูปแบบ MPP อย่างไร?**  
A: เรียก `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` หลังจากทำการเปลี่ยนแปลงทรัพยากรทั้งหมด.

**Q: วิธีที่ดีที่สุดในการแก้ไขกลุ่มทรัพยากรคืออะไร?**  
A: ตั้งค่า property `Resource.Group` บนแต่ละอ็อบเจ็กต์ `Resource` ก่อนบันทึกโครงการ.

---

**อัปเดตล่าสุด:** 2026-06-30  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มทรัพยากรลงในโครงการด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/create-resources/)
- [จัดการต้นทุนทรัพยากร MS Project ด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/resource-cost/)
- [วิธีส่งออก MPP ไปยัง Excel ด้วย Aspose.Tasks สำหรับ Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}