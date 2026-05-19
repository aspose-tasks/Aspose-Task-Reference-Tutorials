---
date: 2026-01-15
description: เรียนรู้วิธีเพิ่มทรัพยากรลงในโครงการ ปรับปรุงข้อมูลทรัพยากร และบันทึกโครงการเป็นไฟล์
  MPP ด้วย Aspose.Tasks for Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: เพิ่มทรัพยากรลงในโครงการโดยใช้ Aspose.Tasks สำหรับ Java
url: /th/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มทรัพยากรลงในโครงการโดยใช้ Aspose.Tasks สำหรับ Java

## Introduction
ในบทเรียนเชิงปฏิบัตินี้คุณจะค้นพบ **วิธีเพิ่มทรัพยากรลงในโครงการ** อย่างโปรแกรมเมติกด้วย Aspose.Tasks Java API เราจะเดินผ่านการโหลดไฟล์ MS Project XML ที่มีอยู่, การแทรกทรัพยากรใหม่, การอัปเดตคุณสมบัติของมัน, และสุดท้าย **บันทึกโครงการเป็น MPP** เมื่อเสร็จคุณจะมีรูปแบบที่ชัดเจนและทำซ้ำได้ซึ่งสามารถนำไปใช้ในเครื่องมือรายงานหรืออัตโนมัติที่ใช้ Java ใด ๆ

## Quick Answers
- **“add resource to project” หมายความว่าอย่างไร?** มันสร้างรายการทรัพยากรใหม่ (คน, อุปกรณ์, วัสดุ) ภายในไฟล์ Microsoft Project.  
- **ไลบรารีที่จัดการเรื่องนี้คืออะไร?** Aspose.Tasks for Java – ไม่จำเป็นต้องติดตั้ง Microsoft Project.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถแปลง XML เป็น MPP ได้หรือไม่?** ใช่ – โหลดไฟล์ XML และ **บันทึกโครงการเป็น MPP** ด้วย `project.save(...)`.  
- **ต้องการเวอร์ชัน Java ใด?** Java 6 หรือใหม่กว่า (แนะนำ Java 8+).

## “add resource to project” คืออะไร?
การเพิ่มทรัพยากรลงในโครงการหมายถึงแทรกแถวใหม่ในตาราง Resources ของไฟล์ MS Project แถวนี้เก็บรายละเอียดเช่น ชื่อ, อัตราค่าใช้จ่าย, กลุ่ม, และฟิลด์กำหนดเองที่งานสามารถอ้างอิงได้ในภายหลัง.

## Why use Aspose.Tasks for Java?
- **ไม่มีการพึ่งพา Microsoft Project** – ทำงานบนระบบปฏิบัติการหรือเซิร์ฟเวอร์ CI ใดก็ได้.  
- **ความแม่นยำเต็มรูปแบบ** – รักษาฟีเจอร์ดั้งเดิมของ Project ทั้งหมดเมื่อแปลงระหว่างรูปแบบ.  
- **Rich API** – ให้คุณอ่าน, เขียน, และจัดการงาน, ทรัพยากร, ปฏิทิน, และอื่น ๆ.

## Prerequisites
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

1. Java Development Kit (JDK) 8 หรือใหม่กว่า ติดตั้งแล้ว.  
2. ไลบรารี Aspose.Tasks for Java – ดาวน์โหลดจาก [here](https://releases.aspose.com/tasks/java/).  
3. ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และการตั้งค่าโครงการ Maven/Gradle.

## Import Packages
เพิ่มคลาส Aspose.Tasks ที่จำเป็นลงในไฟล์ซอร์ส Java ของคุณ:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Set Up Your Data Directory
กำหนดตำแหน่งที่ไฟล์ XML ต้นฉบับและไฟล์ MPP ที่ได้จะถูกจัดเก็บ:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Specify Input and Output Files
ระบุไฟล์ XML ที่คุณต้องการแปลง (**convert XML to MPP**) และไฟล์ MPP ปลายทางที่จะบรรจุทรัพยากรใหม่:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Step 3: Load the Project
สร้างอ็อบเจ็กต์ `Project` จากแหล่ง XML:

```java
Project project = new Project(file);
```

## Step 4: Add a Resource and Set Attributes
นี่คือจุดที่เราจะ **add resource to project** และกำหนดอัตราและกลุ่มของมัน:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*เคล็ดลับ:* คุณสามารถเรียก `add` ซ้ำภายในลูปเพื่อ **update multiple resources** ในการทำงานครั้งเดียว.

## Step 5: Save the Project
สุดท้าย, **save project as MPP** เพื่อบันทึกการเปลี่ยนแปลง:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusion
คุณเพิ่งเรียนรู้ **how to add resource to project**, ปรับปรุงคุณสมบัติของมัน, และ **save the project as MPP** ด้วย Aspose.Tasks for Java วิธีนี้เหมาะสำหรับสายงานการรายงานอัตโนมัติ, การนำเข้าทรัพยากรจำนวนมาก, หรือสถานการณ์ใด ๆ ที่คุณต้องการจัดการไฟล์ MS Project โดยไม่ต้องใช้แอปพลิเคชันบนเดสก์ท็อป.

## Frequently Asked Questions

**Q1: ฉันสามารถอัปเดตหลายทรัพยากรในโครงการเดียวกันโดยใช้ Aspose.Tasks for Java ได้หรือไม่?**  
A: ใช่, ทำการวนซ้ำผ่าน `project.getResources()` หรือเรียก `add` ซ้ำหลายครั้ง, ตั้งค่าฟิลด์ของแต่ละทรัพยากรตามต้องการ.

**Q2: Aspose.Tasks รองรับรูปแบบไฟล์อื่น ๆ นอกจาก MS Project หรือไม่?**  
A: แน่นอน – XML, MPP, MPX, Primavera และอื่น ๆ ทั้งหมดได้รับการสนับสนุน.

**Q3: Aspose.Tasks เข้ากันได้กับเวอร์ชัน Java ต่าง ๆ หรือไม่?**  
A: ไลบรารีทำงานกับ Java 6 และใหม่กว่า; แนะนำให้ใช้ Java 8+ เพื่อประสิทธิภาพที่ดีที่สุด.

**Q4: ฉันสามารถทำการดำเนินการอื่น ๆ กับไฟล์ MS Project ด้วย Aspose.Tasks ได้หรือไม่?**  
A: ใช่, คุณสามารถอ่าน/เขียนงาน, ปฏิทิน, การมอบหมาย, ฟิลด์กำหนดเอง, และแม้กระทั่งสร้างรายงานได้.

**Q5: ฉันจะหาแนวทางช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ.

---

**อัปเดตล่าสุด:** 2026-01-15  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}