---
title: เขียนข้อมูลทรัพยากรที่อัปเดตใน Aspose.Tasks
linktitle: เขียนข้อมูลทรัพยากรที่อัปเดตใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอัปเดตข้อมูลทรัพยากรในไฟล์ MS Project ได้อย่างง่ายดายโดยใช้ Aspose.Tasks for Java
weight: 21
url: /th/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เขียนข้อมูลทรัพยากรที่อัปเดตใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดการอัปเดตข้อมูลทรัพยากร Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็น Java API ที่ทรงพลังที่ช่วยให้คุณจัดการไฟล์ Microsoft Project โดยไม่ต้องติดตั้ง Microsoft Project บนระบบของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า

ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks ในโค้ด Java ของคุณ เพิ่มคำสั่งการนำเข้าต่อไปนี้ลงในไฟล์ Java ของคุณ:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูลของคุณ

กำหนดไดเร็กทอรีที่มีไฟล์ข้อมูลของคุณ:

```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: ระบุไฟล์อินพุตและเอาต์พุต

กำหนดเส้นทางสำหรับไฟล์ MS Project อินพุตและไฟล์ที่อัพเดตผลลัพธ์:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // ทดสอบไฟล์ด้วยหนึ่ง rsc ที่จะอัปเดต
String resultFile = dataDir + "OutputMPP.mpp"; // ไฟล์สำหรับเขียนโปรเจ็กต์ทดสอบ
```

## ขั้นตอนที่ 3: โหลดโครงการ

 โหลดไฟล์ MS Project ลงในไฟล์`Project` วัตถุ:

```java
Project project = new Project(file);
```

## ขั้นตอนที่ 4: เพิ่มทรัพยากรและตั้งค่าคุณสมบัติ

เพิ่มทรัพยากรใหม่ให้กับโครงการและตั้งค่าคุณลักษณะ เช่น อัตรามาตรฐาน อัตราล่วงเวลา และกลุ่ม:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## ขั้นตอนที่ 5: บันทึกโครงการ

บันทึกโครงการที่อัปเดตด้วยข้อมูลทรัพยากรที่แก้ไข:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สาธิตวิธีอัปเดตข้อมูลทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการข้อมูลทรัพยากรในไฟล์ MS Project ของคุณโดยทางโปรแกรมได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถอัปเดตทรัพยากรหลายรายการในโปรเจ็กต์เดียวกันโดยใช้ Aspose.Tasks for Java ได้หรือไม่

A1: ได้ คุณสามารถอัปเดตทรัพยากรหลายรายการได้โดยการวนซ้ำและตั้งค่าแอตทริบิวต์ให้สอดคล้องกัน

### คำถามที่ 2: Aspose.Tasks รองรับไฟล์รูปแบบอื่นนอกเหนือจาก MS Project หรือไม่

ตอบ 2: ใช่ Aspose.Tasks รองรับไฟล์หลากหลายรูปแบบ รวมถึง XML, MPP และอื่นๆ

### คำถามที่ 3: Aspose.Tasks เข้ากันได้กับ Java เวอร์ชันต่างๆ หรือไม่

A3: Aspose.Tasks เข้ากันได้กับ Java เวอร์ชัน 6 ขึ้นไป

### คำถามที่ 4: ฉันสามารถดำเนินการอื่นๆ กับไฟล์ MS Project ด้วย Aspose.Tasks ได้หรือไม่

A4: ได้ คุณสามารถดำเนินการได้หลากหลาย เช่น การอ่าน การเขียน และการจัดการงาน ทรัพยากร และปฏิทิน

### คำถามที่ 5: ฉันจะขอความช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้ที่ไหน

 A5: คุณสามารถเยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
