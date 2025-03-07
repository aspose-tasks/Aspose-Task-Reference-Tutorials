---
title: กำหนดค่ามุมมองแผนภูมิแกนต์ในโครงการ Aspose.Tasks
linktitle: กำหนดค่ามุมมองแผนภูมิแกนต์ในโครงการ Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีกำหนดค่า Gantt MS Project Chart View ใน Aspose.Tasks โดยใช้ Java ปรับแต่งโปรเจ็กต์และแสดงภาพในแผนภูมิแกนต์ทีละขั้นตอน
weight: 10
url: /th/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดค่ามุมมองแผนภูมิแกนต์ในโครงการ Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีกำหนดค่ามุมมองแผนภูมิโครงการ Gantt MS ในโปรเจ็กต์ Aspose.Tasks โดยใช้ Java Aspose.Tasks เป็น Java API ที่ทรงพลังซึ่งช่วยให้คุณทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรมได้ เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับแต่งมุมมองแผนภูมิ Gantt ตามความต้องการของโครงการของคุณได้
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
2.  ไลบรารี Aspose.Tasks: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการ บทช่วยสอนนี้ใช้ IntelliJ IDEA แต่คุณสามารถใช้ IDE ใดก็ได้ที่คุณพอใจ
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ เพิ่มคำสั่งการนำเข้าต่อไปนี้ลงในไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.*;
```
ตอนนี้ เรามาแจกแจงขั้นตอนการกำหนดค่า Gantt MS Project Chart View ให้เป็นคำแนะนำทีละขั้นตอน:
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีข้อมูลโครงการของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```java
Project project = new Project(dataDir + "project.mpp");
```
โหลดไฟล์โครงการของคุณ (`project.mpp` ในตัวอย่างนี้) โดยใช้`Project` คลาสจาก Aspose.Tasks
## ขั้นตอนที่ 3: เพิ่มกิจกรรมใหม่
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 สร้างงานใหม่ในโครงการของคุณโดยใช้`Task` และเพิ่มลงในลูก ๆ ของงานรูท
## ขั้นตอนที่ 4: กำหนดแอตทริบิวต์ที่กำหนดเอง
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 กำหนดแอตทริบิวต์ที่กำหนดเองใหม่โดยใช้`ExtendedAttributeDefinition`และเพิ่มลงในแอตทริบิวต์เพิ่มเติมของโครงการ
## ขั้นตอนที่ 5: เพิ่มแอตทริบิวต์ที่กำหนดเองให้กับงาน
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 เพิ่มแอตทริบิวต์ที่กำหนดเองให้กับงานที่สร้างขึ้นโดยใช้`createExtendedAttribute` วิธี.
## ขั้นตอนที่ 6: ปรับแต่งตาราง
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
ปรับแต่งตารางโดยการเพิ่มฟิลด์แอตทริบิวต์ข้อความที่มีความกว้าง ชื่อ และการจัดแนวที่ระบุ
## ขั้นตอนที่ 7: บันทึกโครงการ
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
บันทึกโปรเจ็กต์ด้วยมุมมองแผนภูมิโครงการ Gantt MS ที่กำหนดค่าไว้ ไฟล์ผลลัพธ์สามารถเปิดได้ใน Microsoft Project 2010
## บทสรุป
ยินดีด้วย! คุณได้กำหนดค่ามุมมองแผนภูมิโครงการ Gantt MS ในโครงการ Aspose.Tasks โดยใช้ Java สำเร็จแล้ว ตอนนี้คุณสามารถปรับแต่งคุณลักษณะของโครงการและแสดงภาพในแผนภูมิแกนต์ได้ตามความต้องการของโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ตอบ: ใช่ Aspose.Tasks ใช้งานได้กับภาษาการเขียนโปรแกรมหลายภาษา รวมถึง .NET, Java และ C++.
### ถาม: Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
ตอบ: คุณสามารถค้นหาการสนับสนุนและถามคำถามได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: คุณสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวเพื่อการทดสอบหรือไม่
 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
