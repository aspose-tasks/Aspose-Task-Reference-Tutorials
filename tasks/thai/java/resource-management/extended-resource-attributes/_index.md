---
title: จัดการแอตทริบิวต์โครงการ MS อย่างมีประสิทธิภาพด้วย Aspose.Tasks
linktitle: จัดการแอตทริบิวต์ทรัพยากรเพิ่มเติมใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการแอตทริบิวต์ทรัพยากร Microsoft Project แบบขยายอย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java ขั้นตอนง่ายๆ และคำแนะนำที่ครอบคลุม
type: docs
weight: 11
url: /th/java/resource-management/extended-resource-attributes/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกวิธีจัดการแอตทริบิวต์ทรัพยากร Microsoft Project แบบขยายอย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรม โดยมีฟังก์ชันการทำงานที่ครอบคลุมสำหรับการจัดการงานและทรัพยากร
## ข้อกำหนดเบื้องต้น
ก่อนดำเนินการต่อ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตั้งค่า Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับไลบรารี Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ติดตั้ง IDE เช่น Eclipse หรือ IntelliJ IDEA สำหรับการพัฒนา Java

## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ 
```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```
## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
กำหนดเส้นทางไปยังไดเร็กทอรีที่มีข้อมูลโครงการของคุณอยู่
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
 ยกตัวอย่าง`Project` วัตถุโดยการโหลดไฟล์ Microsoft Project ของคุณ
```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```
## ขั้นตอนที่ 3: กำหนดแอตทริบิวต์เพิ่มเติม
กำหนดแอตทริบิวต์เพิ่มเติมสำหรับทรัพยากร
```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```
## ขั้นตอนที่ 4: สร้างแอตทริบิวต์เพิ่มเติมและตั้งค่า
สร้างแอตทริบิวต์เพิ่มเติมและกำหนดค่าตัวเลขให้กับแอตทริบิวต์ดังกล่าว
```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```
## ขั้นตอนที่ 5: เพิ่มทรัพยากรและแอตทริบิวต์เพิ่มเติม
เพิ่มทรัพยากรใหม่ให้กับโครงการพร้อมกับแอตทริบิวต์เพิ่มเติม
```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```
## ขั้นตอนที่ 6: บันทึกโครงการ
บันทึกโครงการที่แก้ไขลงในไฟล์ใหม่
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
## ขั้นตอนที่ 7: แสดงผล
พิมพ์ข้อความยืนยันความสมบูรณ์ของกระบวนการ
```java
System.out.println("Process completed Successfully");
```
ด้วยการทำตามขั้นตอนเหล่านี้อย่างพิถีพิถัน คุณสามารถจัดการแอตทริบิวต์ทรัพยากร MS Project แบบขยายได้อย่างราบรื่นโดยใช้ Aspose.Tasks สำหรับ Java

## บทสรุป
โดยสรุป Aspose.Tasks สำหรับ Java มอบความสามารถที่แข็งแกร่งในการจัดการไฟล์ Microsoft Project รวมถึงการจัดการแอตทริบิวต์ทรัพยากรเพิ่มเติม ด้วยการใช้ประโยชน์จากฟังก์ชันการทำงานที่นำเสนอโดย Aspose.Tasks นักพัฒนาจึงสามารถจัดการข้อมูลโครงการได้อย่างมีประสิทธิภาพเพื่อตอบสนองความต้องการที่หลากหลาย
## คำถามที่พบบ่อย
### Aspose.Tasks สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ใช่ Aspose.Tasks ให้การสนับสนุนที่ครอบคลุมสำหรับโครงสร้างโปรเจ็กต์ที่ซับซ้อน ทำให้ผู้ใช้สามารถจัดการงาน ทรัพยากร และคุณลักษณะได้อย่างราบรื่น
### Aspose.Tasks เข้ากันได้กับ Microsoft Project เวอร์ชันล่าสุดหรือไม่
Aspose.Tasks ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าสามารถใช้งานร่วมกับ Microsoft Project เวอร์ชันล่าสุดได้ ทำให้ผู้ใช้ได้รับโซลูชันที่เชื่อถือได้สำหรับการจัดการโครงการ
### Aspose.Tasks รองรับการพัฒนาข้ามแพลตฟอร์มหรือไม่
ใช่ นักพัฒนาสามารถใช้ Aspose.Tasks สำหรับ Java บนแพลตฟอร์มต่างๆ ได้ ทำให้เป็นตัวเลือกที่หลากหลายสำหรับแอปพลิเคชันการจัดการโครงการ
### ฉันสามารถรวม Aspose.Tasks เข้ากับไลบรารี Java อื่นได้หรือไม่
แน่นอนว่า Aspose.Tasks สามารถรวมเข้ากับไลบรารี Java อื่นๆ ได้อย่างราบรื่น เพื่อปรับปรุงฟังก์ชันการทำงานและปรับปรุงกระบวนการพัฒนา
### มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่
ใช่ ผู้ใช้สามารถเข้าถึงการสนับสนุนด้านเทคนิคผ่านฟอรัม Aspose.Tasks ซึ่งพวกเขาสามารถขอความช่วยเหลือและมีส่วนร่วมกับชุมชนได้