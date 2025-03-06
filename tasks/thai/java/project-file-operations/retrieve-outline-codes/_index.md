---
title: รับรหัสโครงร่างโครงการ MS ใน Aspose.Tasks
linktitle: รับรหัสเค้าร่างใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีรับโค้ดเค้าร่างของ Microsoft Project โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ Java ปรับปรุงความสามารถในการจัดการโครงการของคุณ
type: docs
weight: 15
url: /th/java/project-file-operations/retrieve-outline-codes/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีรับโค้ดเค้าร่างของ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java รหัสเค้าร่างใน MS Project มีวิธีที่มีโครงสร้างในการจัดหมวดหมู่และจัดระเบียบงานของโครงการ ทรัพยากร และการมอบหมายงาน Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถจัดการและจัดการไฟล์ Microsoft Project โดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. สภาพแวดล้อมการพัฒนาจาวา
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จากเว็บไซต์ Oracle
### 2. ห้องสมุด Aspose.Tasks
 ดาวน์โหลดและรวมไลบรารี Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[Aspose.Tasks สำหรับหน้าดาวน์โหลด Java](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Tasks ในโค้ด Java ของคุณ:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
ตอนนี้เรามาแบ่งโค้ดตัวอย่างที่ให้มาออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: โหลดโครงการ
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 ในขั้นตอนนี้ เราจะโหลดไฟล์ Microsoft Project ลงในไฟล์`Project` วัตถุโดยใช้ชื่อไฟล์ที่ให้มา
## ขั้นตอนที่ 2: รับรหัสโครงร่าง
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
เราวนซ้ำแต่ละคำจำกัดความของโค้ดเค้าร่างในโครงการ
## ขั้นตอนที่ 3: เข้าถึงคุณสมบัติของโค้ดโครงร่าง
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
เราดึงข้อมูลและพิมพ์คุณสมบัติต่างๆ ของคำจำกัดความโค้ดเค้าร่าง เช่น นามแฝง รหัสฟิลด์ และชื่อฟิลด์
## ขั้นตอนที่ 4: ตรวจสอบรหัสที่กำหนดเองขององค์กร
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
เราตรวจสอบว่าโค้ดโครงร่างเป็นโค้ดแบบกำหนดเองขององค์กรหรือไม่ และพิมพ์ผลลัพธ์ตามนั้น
## ขั้นตอนที่ 5: แสดงมาสก์โค้ดโครงร่าง
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
เราวนซ้ำแต่ละมาสก์ที่เกี่ยวข้องกับโค้ดโครงร่าง และพิมพ์ระดับและค่าของมาสก์
## ขั้นตอนที่ 6: แสดงค่าโค้ดโครงร่าง
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
เราวนซ้ำค่าโค้ดเค้าร่างแต่ละค่า และพิมพ์คำอธิบาย รหัสค่า ค่า และประเภท
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีดึงโค้ดโครงร่างของ MS Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณจะสามารถเข้าถึงและจัดการโค้ดเค้าร่างในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ ซึ่งช่วยให้สามารถจัดการโครงการขั้นสูงได้
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java เพื่อแก้ไขโค้ดโครงร่างในไฟล์โปรเจ็กต์ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks for Java มี API เพื่อแก้ไขโค้ดโครงร่างในไฟล์ MS Project โดยทางโปรแกรม
### คำถามที่ 2: Aspose.Tasks สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks for Java เวอร์ชันทดลองใช้ฟรีได้จาก[เว็บไซต์ Aspose.Tasks](https://releases.aspose.com/).
### คำถามที่ 3: ฉันจะได้รับการสนับสนุนด้านเทคนิคสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถรับการสนับสนุนด้านเทคนิคได้โดยไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) และโพสต์คำถามของคุณที่นั่น
### คำถามที่ 4: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่
 ตอบ: ได้ คุณสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้จาก[หน้าซื้อ](https://purchase.aspose.com/temporary-license/).
### คำถามที่ 5: ฉันจะหาเอกสารฉบับสมบูรณ์สำหรับ Aspose.Tasks for Java ได้ที่ไหน
 ตอบ: คุณสามารถดูได้ที่[เอกสารประกอบ](https://reference.aspose.com/tasks/java/) สำหรับข้อมูลโดยละเอียดเกี่ยวกับการใช้ Aspose.Tasks สำหรับ Java