---
date: 2025-12-20
description: เรียนรู้วิธีดึงรหัสโครงร่างของ MS Project อย่างโปรแกรมโดยใช้ Aspose.Tasks
  สำหรับ Java. เพิ่มศักยภาพการจัดการโครงการของคุณ.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ดึงรหัสโครงร่าง MS Project ใน Aspose.Tasks
url: /th/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงรหัสโครงร่างของ MS Project ใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้ คุณจะได้ค้นพบ **วิธีดึงรหัสโครงร่างของ ms project** ด้วยการใช้ Aspose.Tasks สำหรับ Java รหัสโครงร่างใน MS Project ให้วิธีที่ทรงพลังในการจัดกลุ่มงาน, ทรัพยากร, และการมอบหมายงาน และการเข้าถึงโดยโปรแกรมช่วยให้คุณสร้างรายงานแบบกำหนดเอง, ระบบอัตโนมัติ, หรือโซลูชันการบูรณาการ เราจะเดินผ่านตัวอย่างเต็มรูปแบบแบบขั้นตอน‑โดย‑ขั้นตอนที่คุณสามารถคัดลอกไปใช้ในโปรเจกต์ของคุณได้

## คำตอบอย่างรวดเร็ว
- **โค้ดนี้ทำอะไร?** มันโหลดไฟล์ Project แล้วพิมพ์คำนิยามของรหัสโครงร่างทุกตัว, มาสก์ของมัน, และค่าต่าง ๆ  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks สำหรับ Java (เวอร์ชันล่าสุดใดก็ได้)  
- **ต้องมีลิขสิทธิ์หรือไม่?** รุ่นทดลองใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า  
- **สามารถแก้ไขรหัสหลังจากดึงได้หรือไม่?** ได้ – API เดียวกันช่วยให้คุณเพิ่ม, แก้ไข, หรือ ลบ รหัสโครงร่างได้

## รหัสโครงร่างของ ms project คืออะไร?
รหัสโครงร่างเป็นฟิลด์ที่กำหนดเองซึ่งช่วยให้ผู้จัดการโครงการสามารถจัดกลุ่มและกรองงานได้เหนือระดับโครงสร้างต้นแบบที่มีอยู่ พวกมันอาจเป็นค่าตัวเลข, สตริง, หรือแม้แต่รหัสกำหนดเองระดับองค์กรที่กำหนดไว้ที่ระดับบริษัท การอ่านรหัสเหล่านี้ทำให้คุณสามารถขับเคลื่อนแดชบอร์ด, ส่งออกข้อมูล, หรือบังคับใช้กฎการตั้งชื่อโดยอัตโนมัติ

## ทำไมต้องดึงรหัสโครงร่างของ ms project ด้วย Aspose.Tasks?
- **อัตโนมัติ:** สร้างรายงานหรือเรียกใช้ workflow โดยไม่ต้องส่งออกด้วยมือ  
- **บูรณาการ:** ซิงค์รหัสโครงร่างกับ ERP, PPM, หรือเครื่องมือ BI  
- **กำหนดเอง:** ใช้กฎธุรกิจตามค่ารหัส (เช่น การจัดสรรต้นทุน)  
- **ข้ามแพลตฟอร์ม:** ทำงานบน Windows, Linux, และ macOS โดยไม่ขึ้นกับ UI ของ Microsoft Project

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณได้ตั้งค่าข้อกำหนดต่อไปนี้แล้ว:

### 1. สภาพแวดล้อมการพัฒนา Java
ตรวจสอบว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จากเว็บไซต์ของ Oracle

### 2. ไลบรารี Aspose.Tasks
ดาวน์โหลดและเพิ่มไลบรารี Aspose.Tasks ลงในโปรเจกต์ Java ของคุณ คุณสามารถดาวน์โหลดไลบรารีได้จาก [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/)

## นำเข้าแพ็กเกจ
แรกเริ่ม, นำเข้าแพ็กเกจที่จำเป็นจาก Aspose.Tasks ในโค้ด Java ของคุณ:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

ตอนนี้เรามาแยกโค้ดตัวอย่างที่ให้มาเป็นหลายขั้นตอนกัน:

## ขั้นตอนที่ 1: โหลดโปรเจกต์
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

## ขั้นตอนที่ 4: ตรวจสอบรหัสกำหนดเองระดับองค์กร
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
เราตรวจสอบว่ารหัสโครงร่างเป็นรหัสกำหนดเองระดับองค์กรหรือไม่และพิมพ์ผลลัพธ์ตามนั้น

## ขั้นตอนที่ 5: แสดงมาสก์ของรหัสโครงร่าง
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
เราวนลูปผ่านมาสก์แต่ละตัวที่เชื่อมโยงกับรหัสโครงร่างและพิมพ์ระดับและค่ามาสก์ของมัน

## ขั้นตอนที่ 6: แสดงค่าของรหัสโครงร่าง
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
เราวนลูปผ่านค่ารหัสโครงร่างแต่ละค่าและพิมพ์คำอธิบาย, value ID, value, และ type ของมัน

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไม่มีผลลัพธ์** | เส้นทางไฟล์โปรเจกต์ไม่ถูกต้อง | ตรวจสอบว่า `projectName` ชี้ไปยังไฟล์ `.mpp` ที่ถูกต้อง |
| **ค่าเป็น Null** | รหัสโครงร่างไม่ได้กำหนดในไฟล์ | ตรวจสอบว่าไฟล์ Project มีรหัสโครงร่างอยู่จริง (ตรวจสอบใน UI ของ MS Project) |
| **LicenseException** | ใช้รุ่นทดลองโดยไม่มีการเปิดใช้งานที่ถูกต้อง | Apply a temporary or full license via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## คำถามที่พบบ่อย

**Q: สามารถใช้ Aspose.Tasks สำหรับ Java เพื่อแก้ไขรหัสโครงร่างในไฟล์ Project ได้หรือไม่?**  
A: ได้, Aspose.Tasks สำหรับ Java มี API ให้แก้ไขรหัสโครงร่างโดยโปรแกรม คุณสามารถเพิ่ม, แก้ไข, หรือ ลบคำนิยามได้โดยใช้ `Project` อ็อบเจ็กต์เดียวกัน

**Q: มีรุ่นทดลองของ Aspose.Tasks สำหรับ Java หรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.Tasks สำหรับ Java จาก [Aspose.Tasks website](https://releases.aspose.com/)  

**Q: จะขอรับการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร?**  
A: คุณสามารถขอรับการสนับสนุนทางเทคนิคได้โดยไปที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) แล้วโพสต์คำถามของคุณที่นั่น  

**Q: สามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่?**  
A: ได้, คุณสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้จาก [purchase page](https://purchase.aspose.com/temporary-license/)  

**Q: จะหาเอกสารฉบับเต็มของ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
A: คุณสามารถอ้างอิงเอกสารได้ที่ [documentation](https://reference.aspose.com/tasks/java/) เพื่อรับข้อมูลรายละเอียดเกี่ยวกับการใช้ Aspose.Tasks สำหรับ Java  

## สรุป
ในบทแนะนำนี้ เราได้เรียนรู้วิธีดึง **รหัสโครงร่างของ ms project** ด้วย Aspose.Tasks สำหรับ Java โดยทำตามขั้นตอนที่ให้ไว้ คุณจะสามารถเข้าถึงและจัดการรหัสโครงร่างในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ ส่งเสริมความสามารถขั้นสูงของการจัดการโครงการ เช่น รายงานแบบกำหนดเอง, ระบบอัตโนมัติ, และการบูรณาการกับระบบองค์กรอื่น ๆ

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}