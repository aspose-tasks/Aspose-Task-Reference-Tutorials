---
date: 2026-03-27
description: เรียนรู้วิธีดึงรหัสโครงร่างของ MS Project อย่างโปรแกรมโดยใช้ Aspose.Tasks
  สำหรับ Java. เพิ่มศักยภาพการจัดการโครงการของคุณ.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ดึงรหัสโครงร่างของ MS Project ใน Aspose.Tasks
url: /th/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงรหัสโครงร่างของ MS Project ด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีดึงรหัสโครงร่างของ ms project** ด้วย Aspose.Tasks สำหรับ Java รหัสโครงร่างใน MS Project ให้วิธีการจัดกลุ่มงาน, ทรัพยากร, และการมอบหมายที่มีประสิทธิภาพ และการเข้าถึงโดยโปรแกรมทำให้คุณสร้างรายงานแบบกำหนดเอง, ระบบอัตโนมัติ, หรือโซลูชันการบูรณาการได้ เราจะเดินผ่านตัวอย่างครบถ้วนแบบขั้นตอน‑ต่อ‑ขั้นตอนที่คุณสามารถคัดลอกไปใช้ในโปรเจกต์ของคุณได้เลย

## คำตอบสั้น
- **โค้ดนี้ทำอะไร?** โหลดไฟล์ Project แล้วพิมพ์คำนิยามของรหัสโครงร่างทุกตัว, มาสก์ของมัน, และค่าต่าง ๆ  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks สำหรับ Java (เวอร์ชันล่าสุดใดก็ได้)  
- **ต้องใช้ไลเซนส์หรือไม่?** เวอร์ชันทดลองใช้ได้สำหรับการพัฒนา; ต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า  
- **สามารถแก้ไขรหัสหลังจากดึงมาได้หรือไม่?** ได้ – API เดียวกันช่วยให้คุณเพิ่ม, แก้ไข, หรือ ลบ รหัสโครงร่างได้

## รหัสโครงร่างของ ms project คืออะไร?
รหัสโครงร่างเป็นฟิลด์ที่กำหนดเองซึ่งช่วยให้ผู้จัดการโครงการจัดกลุ่มและกรองงานได้เหนือระดับลำดับขั้นพื้นฐาน สามารถเป็นค่าตัวเลข, สตริง, หรือแม้แต่รหัสที่กำหนดระดับองค์กรโดยทั่วทั้งองค์กร การอ่านรหัสเหล่านี้ทำให้คุณสามารถขับเคลื่อนแดชบอร์ด, ส่งออกข้อมูล, หรือบังคับใช้กฎการตั้งชื่อโดยอัตโนมัติได้

## ทำไมต้องดึงรหัสโครงร่างของ ms project ด้วย Aspose.Tasks?
- **อัตโนมัติ:** สร้างรายงานหรือเรียกใช้ workflow โดยไม่ต้องส่งออกด้วยมือ  
- **บูรณาการ:** ซิงค์รหัสโครงร่างกับ ERP, PPM, หรือเครื่องมือ BI  
- **ปรับแต่ง:** ใช้กฎธุรกิจตามค่ารหัส (เช่น การจัดสรรต้นทุน)  
- **ข้ามแพลตฟอร์ม:** ทำงานบน Windows, Linux, และ macOS โดยไม่ขึ้นกับ UI ของ Microsoft Project

## วิธีอ่านไฟล์ MPP เพื่อดึงรหัสโครงร่าง?
การอ่านไฟล์ MPP (Microsoft Project) เป็นขั้นตอนแรกในการสกัดรหัสโครงร่าง Aspose.Tasks ทำหน้าที่เป็นชั้นนามธรรมของรูปแบบไฟล์ ดังนั้นคุณไม่ต้องพาร์สโครงสร้างไบนารีด้วยตนเอง คลาส `Project` จะจัดการส่วนที่ซับซ้อนให้คุณ ทำให้คุณโฟกัสที่ข้อมูลที่ต้องการได้เลย

## ฟิลด์ที่กำหนดเองใน MS Project
รหัสโครงร่างเป็นประเภทหนึ่งของ **ฟิลด์ที่กำหนดเอง** ใน MS Project ขณะที่ฟิลด์มาตรฐานครอบคลุมวันที่, ระยะเวลา, และทรัพยากร, ฟิลด์ที่กำหนดเองช่วยให้คุณเก็บข้อมูลเฉพาะองค์กร การเข้าถึงผ่าน Aspose.Tasks ให้ความยืดหยุ่นเดียวกันในระดับโค้ด

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณได้ตั้งค่าข้อกำหนดต่อไปนี้เรียบร้อยแล้ว:

### 1. สภาพแวดล้อมการพัฒนา Java
ตรวจสอบว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว สามารถดาวน์โหลดและติดตั้ง JDK ได้จากเว็บไซต์ของ Oracle

### 2. ไลบรารี Aspose.Tasks
ดาวน์โหลดและเพิ่มไลบรารี Aspose.Tasks ลงในโปรเจกต์ Java ของคุณ คุณสามารถดาวน์โหลดไลบรารีได้จาก [หน้าดาวน์โหลด Aspose.Tasks สำหรับ Java](https://releases.aspose.com/tasks/java/)

## นำเข้าแพ็กเกจ
แรกเริ่มให้นำเข้าแพ็กเกจที่จำเป็นจาก Aspose.Tasks ในโค้ด Java ของคุณ:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

ต่อไปเราจะอธิบายตัวอย่างโค้ดที่ให้ไว้เป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: โหลด Project
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
ในขั้นตอนนี้ เราโหลดไฟล์ Microsoft Project เข้าไปในอ็อบเจ็กต์ `Project` โดยใช้ชื่อไฟล์ที่ระบุ

## ขั้นตอนที่ 2: ดึงรหัสโครงร่าง
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
เราวนลูปผ่านคำนิยามของรหัสโครงร่างแต่ละตัวในโปรเจกต์

## ขั้นตอนที่ 3: เข้าถึงคุณสมบัติของรหัสโครงร่าง
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
เราดึงและพิมพ์คุณสมบัติต่าง ๆ ของคำนิยามรหัสโครงร่าง เช่น Alias, Field ID, และ Field Name

## ขั้นตอนที่ 4: ตรวจสอบรหัสที่กำหนดเองระดับองค์กร
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
เราตรวจสอบว่ารหัสโครงร่างเป็นรหัสที่กำหนดเองระดับองค์กรหรือไม่และพิมพ์ผลลัพธ์ตามนั้น

## ขั้นตอนที่ 5: แสดงมาสก์ของรหัสโครงร่าง
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
เราวนลูปผ่านมาสก์แต่ละระดับที่เชื่อมกับรหัสโครงร่างและพิมพ์ระดับและค่ามาสก์

## ขั้นตอนที่ 6: แสดงค่าของรหัสโครงร่าง
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
เราวนลูปผ่านค่ารหัสโครงร่างแต่ละค่าและพิมพ์คำอธิบาย, value ID, value, และ type

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไม่มีผลลัพธ์** | เส้นทางไฟล์ Project ไม่ถูกต้อง | ตรวจสอบว่า `projectName` ชี้ไปยังไฟล์ `.mpp` ที่มีอยู่จริง |
| **ค่าเป็น Null** | รหัสโครงร่างไม่ได้กำหนดในไฟล์ | ตรวจสอบว่าไฟล์ Project มีรหัสโครงร่างจริง ๆ (ดูใน UI ของ MS Project) |
| **LicenseException** | ใช้รุ่นทดลองโดยไม่มีการเปิดใช้งานที่เหมาะสม | ใช้ไลเซนส์ชั่วคราวหรือเต็มโดยเพิ่ม `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## คำถามที่พบบ่อย

**ถาม: สามารถใช้ Aspose.Tasks สำหรับ Java เพื่อแก้ไขรหัสโครงร่างในไฟล์ Project ได้หรือไม่?**  
ตอบ: ได้, Aspose.Tasks สำหรับ Java มี API ให้แก้ไขรหัสโครงร่างได้โปรแกรมเมติก คุณสามารถเพิ่ม, แก้ไข, หรือ ลบคำนิยามโดยใช้อ็อบเจ็กต์ `Project` เดียวกัน

**ถาม: มีเวอร์ชันทดลองของ Aspose.Tasks สำหรับ Java หรือไม่?**  
ตอบ: มี, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีของ Aspose.Tasks สำหรับ Java ได้จาก [เว็บไซต์ Aspose.Tasks](https://releases.aspose.com/)

**ถาม: จะขอรับการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks สำหรับ Java อย่างไร?**  
ตอบ: คุณสามารถขอรับการสนับสนุนทางเทคนิคได้โดยไปที่ [ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) แล้วโพสต์คำถามของคุณที่นั่น

**ถาม: สามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่?**  
ตอบ: ได้, คุณสามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้จาก [หน้าซื้อไลเซนส์](https://purchase.aspose.com/temporary-license/)

**ถาม: จะหาเอกสารฉบับเต็มของ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
ตอบ: คุณสามารถอ้างอิงเอกสารได้ที่ [documentation](https://reference.aspose.com/tasks/java/) เพื่อดูข้อมูลโดยละเอียดเกี่ยวกับการใช้ Aspose.Tasks สำหรับ Java

## สรุป
ในบทแนะนำนี้ เราได้เรียนรู้วิธีดึง **รหัสโครงร่างของ ms project** ด้วย Aspose.Tasks สำหรับ Java โดยทำตามขั้นตอนที่ให้ไว้ คุณจะสามารถเข้าถึงและจัดการรหัสโครงร่างในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ เปิดทางสู่ความสามารถขั้นสูงของการจัดการโครงการ เช่น รายงานแบบกำหนดเอง, ระบบอัตโนมัติ, และการบูรณาการกับระบบองค์กรอื่น ๆ

---

**อัปเดตล่าสุด:** 2026-03-27  
**ทดสอบกับ:** Aspose.Tasks สำหรับ Java (ล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}