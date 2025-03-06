---
title: อ่านข้อมูลคำจำกัดความกลุ่มใน Aspose.Tasks
linktitle: อ่านข้อมูลคำจำกัดความกลุ่มใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอ่านข้อมูลคำจำกัดความกลุ่มจากไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเรา
weight: 10
url: /th/java/project-data-reading/read-group-definition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านข้อมูลคำจำกัดความกลุ่มใน Aspose.Tasks

## การแนะนำ
Aspose.Tasks for Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะอธิบายกระบวนการอ่านข้อมูลคำจำกัดความกลุ่มจากไฟล์โปรเจ็กต์ทีละขั้นตอนโดยใช้ Aspose.Tasks สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการ เช่น IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มทำงานกับ Aspose.Tasks สำหรับ Java
```java
import com.aspose.tasks.*;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูลของคุณ
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่มีไฟล์โครงการของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```java
Project project = new Project(dataDir + "project.mpp");
```
 โหลดไฟล์โครงการของคุณโดยใช้ไฟล์`Project` ตัวสร้างคลาส ส่งเส้นทางไปยังไฟล์โครงการของคุณ
## ขั้นตอนที่ 3: ดึงข้อมูลจำนวนกลุ่มงาน
```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```
 ดึงข้อมูลจำนวนกลุ่มงานในโครงการโดยใช้`getTaskGroups()` วิธี.
## ขั้นตอนที่ 4: ดึงข้อมูลกลุ่มงาน
```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```
รับข้อมูลเกี่ยวกับกลุ่มงานเฉพาะ เช่น ชื่อและจำนวนเกณฑ์ของกลุ่ม
## ขั้นตอนที่ 5: ดึงข้อมูลเกณฑ์กลุ่ม
```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```
รับข้อมูลเกี่ยวกับเกณฑ์ของกลุ่ม เช่น เขตข้อมูล กลุ่มบน สีของเซลล์ และรูปแบบ
## ขั้นตอนที่ 6: ตรวจสอบกลุ่มผู้ปกครอง
```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```
ตรวจสอบว่ากลุ่มหลักเท่ากับกลุ่มงานหรือไม่
## ขั้นตอนที่ 7: ดึงข้อมูลแบบอักษรของเกณฑ์
```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```
ดึงข้อมูลแบบอักษรสำหรับเกณฑ์ เช่น ตระกูลแบบอักษร ขนาด สไตล์ และลำดับการเรียงลำดับ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีอ่านข้อมูลคำจำกัดความกลุ่มจากไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแยกและใช้ข้อมูลกลุ่มงานในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java เพื่อแก้ไขไฟล์โปรเจ็กต์ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks for Java มีคุณสมบัติมากมายสำหรับทั้งการอ่านและการแก้ไขไฟล์ Microsoft Project โดยทางโปรแกรม
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP และ XML
### ถาม: ฉันจะจัดการกับข้อผิดพลาดขณะทำงานกับ Aspose.Tasks สำหรับ Java ได้อย่างไร
ตอบ: คุณสามารถใช้กลไกการจัดการข้อผิดพลาดได้โดยใช้บล็อก try-catch เพื่อจัดการข้อยกเว้นที่อาจเกิดขึ้นระหว่างการจัดการไฟล์ได้อย่างสวยงาม
### ถาม: Aspose.Tasks for Java รองรับการส่งออกข้อมูลโปรเจ็กต์เป็นรูปแบบอื่นหรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ Java ช่วยให้คุณสามารถส่งออกข้อมูลโปรเจ็กต์เป็นรูปแบบต่างๆ เช่น PDF, XLSX และ CSV
### ถาม: ฉันจะค้นหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[Aspose.Tasks สำหรับเอกสาร Java](https://reference.aspose.com/tasks/java/) สำหรับคำแนะนำที่ครอบคลุมและดูที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อสนับสนุนชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
