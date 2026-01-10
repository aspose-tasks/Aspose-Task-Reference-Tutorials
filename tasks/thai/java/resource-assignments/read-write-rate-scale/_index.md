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

## Common Pitfalls & Tips
- **UID Mismatch** – เมื่อดึงการมอบหมายโดยใช้ UID ให้ตรวจสอบให้แน่ใจว่า UID ตรงกับค่าที่กำหนดในระหว่างการสร้าง  
- **Incorrect Resource Type** – การใช้ `ResourceType.Material` สำหรับทรัพยากรงานจะทำให้การคำนวณอัตราแสดงผลไม่ถูกต้อง  
- **Saving Format** – ควรบันทึกโดยใช้ `SaveFileFormat.Mpp` (หรือรูปแบบที่รองรับอื่น) เพื่อรักษาฟิลด์ที่กำหนดเองเช่น rate scale

## Conclusion
การจัดการและตรวจสอบ rate scale สำหรับการมอบหมายทรัพยากรใน Aspose.Tasks for Java เป็นเรื่องง่ายเมื่อคุณรู้จักคลาสและคุณสมบัติที่เกี่ยวข้อง ด้วยการทำตามคู่มือนี้คุณสามารถ **read rate** ข้อมูล, **define material resource** objects, **set scale**, และ **assign resources to task** ได้อย่างมั่นใจ

## Frequently Asked Questions

**Q: ฉันสามารถใช้ Aspose.Tasks for Java กับ IDE Java ใดก็ได้หรือไม่?**  
A: ใช่, Aspose.Tasks for Java รองรับ IDE Java หลักทั้งหมด รวมถึง IntelliJ IDEA, Eclipse, และ NetBeans

**Q: Aspose.Tasks รองรับรูปแบบไฟล์อื่นนอกจาก MPP หรือไม่?**  
A: ใช่, Aspose.Tasks รองรับรูปแบบไฟล์หลายรูปแบบ รวมถึง MPP, XML, และ HTML

**Q: Aspose.Tasks เหมาะสำหรับการจัดการโครงการระดับองค์กรหรือไม่?**  
A: แน่นอน, Aspose.Tasks มีฟีเจอร์ครบถ้วนสำหรับการจัดการโครงการทุกขนาด ทำให้เหมาะกับการจัดการโครงการระดับองค์กร

**Q: ฉันสามารถปรับแต่งการมอบหมายทรัพยากรได้มากกว่าการตั้งค่า rate scale หรือไม่?**  
A: ใช่, Aspose.Tasks มีความสามารถกว้างขวางสำหรับการปรับแต่งการมอบหมายทรัพยากร รวมถึงค่าใช้จ่าย, งาน, และการปรับระยะเวลา

**Q: มีฟอรั่มชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่?**  
A: มี, คุณสามารถหาแหล่งสนับสนุนและโต้ตอบกับผู้ใช้คนอื่นได้ในฟอรั่ม Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}