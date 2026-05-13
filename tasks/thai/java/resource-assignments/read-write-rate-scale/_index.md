---
date: 2026-01-10
description: เรียนรู้วิธีอ่านอัตราสเกลและจัดการการมอบหมายทรัพยากรใน Aspose.Tasks สำหรับ
  Java กำหนดทรัพยากรวัสดุ วิธีตั้งสเกล และมอบทรัพยากรให้กับงาน
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีอ่านสเกลอัตราและเขียนสเกลอัตราสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
url: /th/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านและเขียน Rate Scale สำหรับการมอบหมายทรัพยากรใน Aspose.Tasks

ในบทแนะนำนี้คุณจะได้ค้นพบ **how to read rate** การตั้งค่า scale และปรับเปลี่ยนสำหรับการมอบหมายทรัพยากรโดยใช้ Aspose.Tasks for Java ไม่ว่าคุณจะกำลังสร้างตัวจัดตารางเวลา เครื่องมือรายงาน หรือเพียงต้องการทำให้การอัปเดตโครงการเป็นอัตโนมัติ การเชี่ยวชาญการจัดการ rate scale จะให้การควบคุมที่ละเอียดสำหรับทรัพยากรวัสดุและงาน

## คำตอบอย่างรวดเร็ว
- **คลาสหลักสำหรับการจัดการอัตราคืออะไร?** `ResourceAssignment` with the `Asn.RATE_SCALE` property.  
- **enum ใดกำหนดตัวเลือกของ scale?** `RateScaleType` (Day, Week, Month, etc.).  
- **ฉันต้องมีไลเซนส์เพื่อรันตัวอย่างหรือไม่?** ไลเซนส์ทดลองฟรีทำงานสำหรับการทดสอบ; ไลเซนส์เชิงพาณิชย์จำเป็นสำหรับการใช้งานจริง.  
- **ฉันสามารถเปลี่ยน scale หลังจากบันทึกได้หรือไม่?** ได้ – โหลดโครงการใหม่และแก้ไข `Asn.RATE_SCALE` ตามที่แสดง.  
- **IDE ที่รองรับ?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) can compile the code.

## Rate Scale คืออะไร?
Rate scale กำหนดหน่วยเวลา (วัน, สัปดาห์, เดือน ฯลฯ) ที่อัตราค่าต้นทุนของทรัพยากรถูกนำไปใช้ การปรับ scale ช่วยให้คุณจำลองการใช้วัสดุหรือความพยายามของแรงงานได้อย่างแม่นยำ

## ทำไมต้องอ่านและเขียน rate scale?
การอ่าน scale ปัจจุบันช่วยให้คุณตรวจสอบตารางเวลาที่มีอยู่ได้ ในขณะที่การเขียน scale ใหม่ทำให้คุณสามารถปรับทรัพยากรให้สอดคล้องกับนโยบายการเรียกเก็บเงินหรือการใช้ของโครงการ ซึ่งมีประโยชน์อย่างยิ่งเมื่อ **defining material resource** ค่าใช้จ่ายหรือเมื่อคุณต้อง **set scale** สำหรับปฏิทินการทำงานที่ไม่เป็นมาตรฐาน

## Prerequisites
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
1. **Java Development Environment** – JDK 8 หรือสูงกว่า  
2. **Aspose.Tasks for Java Library** – ดาวน์โหลดและติดตั้งไลบรารีจาก [here](https://releases.aspose.com/tasks/java/)

## นำเข้าแพ็กเกจ
ก่อนอื่นให้ import คลาสที่จำเป็นของ Aspose.Tasks

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Step 1: ตั้งค่าโครงการ Java ของคุณ
สร้างโครงการ Maven หรือ Gradle และเพิ่มไฟล์ JAR ของ Aspose.Tasks ไปยัง classpath ขั้นตอนนี้ทำให้คอมไพเลอร์สามารถค้นพบคลาสที่ import ได้

## Step 2: โหลดไฟล์โครงการ
โหลดไฟล์ Microsoft Project ที่คุณต้องการทำงานด้วย

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Step 3: เพิ่ม Task
สร้างงานใหม่ที่จะรับการมอบหมายทรัพยากรในภายหลัง

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Step 4: กำหนดทรัพยากร
ที่นี่เราจะ **define material resource** และทรัพยากรงานทั่วไป โปรดสังเกตการใช้ `ResourceType.Material` สำหรับทรัพยากรประเภทวัสดุ

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Step 5: มอบหมายทรัพยากรให้กับ Task
ตอนนี้เราจะ **assign resources to task** และระบุ **how to set scale** ด้วยการใช้ `RateScaleType.Week` ตัวอย่างนี้แสดงการอ่านและเขียน rate scale ทั้งสองอย่าง

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Step 6: บันทึกโครงการ
บันทึกการเปลี่ยนแปลงลงในไฟล์ใหม่เพื่อให้เราสามารถตรวจสอบ rate scale ที่เก็บไว้ได้ในภายหลัง

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Step 7: ดึงข้อมูลการมอบหมายทรัพยากร
โหลดโครงการที่บันทึกไว้ใหม่และ **read the rate** scale เพื่อยืนยันว่ามีการเขียนอย่างถูกต้อง

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## ข้อผิดพลาดและเคล็ดลับทั่วไป
- **UID Mismatch** – ในกรณีที่ดึงการค้นคว้าวิจัย UID สามารถตรวจสอบได้ว่า UID โดยปกติค่าที่กำหนดสำหรับการสร้าง
- **Incorrect Resource Type** – `ResourceType.Material` สำหรับทรัพยากรงานของเธอที่รวบรวมข้อมูลอัตราการเต้นของหัวใจ
- **รูปแบบการบันทึก** – คุณสมบัติบันทึกของข้อมูลต่างๆ `SaveFileFormat.Mpp` (หรือรูปแบบที่รองรับสิ่งอื่น) ในส่วนของข้อมูลเช่น สเกลอัตรา

## บทสรุป
บางครั้งอัตราสเกลที่จำเป็นต้องใช้ทรัพยากรใน Aspose.Tasks for Java ไม่จำเป็นต้องรู้จักคลาสและคุณสมบัติที่ทำตามคู่มือนี้เพื่อดู **อัตราการอ่าน** ข้อมูล, **กำหนดทรัพยากรวัสดุ** อ็อบเจ็กต์, **กำหนดสเกล**, และ **มอบหมายทรัพยากรให้กับงาน**

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Tasks for Java กับ IDE Java อัพโหลดหรือไม่?**
ตอบ: ตรวจสอบได้, Aspose.Tasks for Java เข้ากันได้กับ IDE Java หลักทั้งหมดและ IntelliJ IDEA, Eclipse, และ NetBeans

**ถาม: Aspose.Tasks รูปแบบไฟล์ที่รองรับไฟล์อื่นนอกจาก MPP เป็นอย่างไร?**
ตอบ: ถูกต้อง, Aspose.Tasks ที่รองรับรูปแบบไฟล์หลายรูปแบบรวมถึง MPP, XML, และ HTML

**ถาม: Aspose.Tasks สำหรับการจัดการโครงการระดับองค์กรหรือไม่**
ตอบ: แน่นอน Aspose.Tasks มีครบถ้วนสำหรับการจัดการโครงการทุกขนาดที่ไม่เหมาะกับการจัดการโครงการระดับองค์กร

**ถาม: ฉันสามารถตรวจสอบการทำอะไรเพิ่มเติมได้ที่เรตสเกล?**
ตอบ: ถูกต้อง, Aspose.Tasks จำเป็นต้องมีการพิจารณาการที่ต้องใช้ทรัพยากรและค่าใช้จ่าย, งาน, และต้องใช้เวลานาน

**ถาม: มีฟอรั่มชุมชนสำหรับ Aspose.Tasks หรือเปล่า?**
ตอบ: มีแหล่งที่มาหลายแห่งสนับสนุนและพบกับผู้ใช้คนอื่นได้ในฟอรั่ม Aspose.Tasks [ที่นี่](https://forum.aspose.com/c/tasks/15)

---

**อัปเดตล่าสุด:** 2026-01-10
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (เวอร์ชันล่าสุด ณ เวลาที่เขียน)
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}