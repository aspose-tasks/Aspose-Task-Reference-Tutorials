---
date: 2025-12-17
description: เรียนรู้วิธีบันทึกโครงการเป็นภาพและเปลี่ยนความละเอียดของภาพใน Java ด้วย
  Aspose.Tasks for Java คู่มือขั้นตอนต่อขั้นตอนนี้แสดงการเรนเดอร์ข้อมูล MS Project
  ด้วยรูปแบบ 24bppRgb.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: บันทึกโครงการเป็นภาพ – รูปแบบ 24bppRgb ด้วย Aspose.Tasks
url: /th/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกโครงการเป็นภาพ – รูปแบบ 24bppRgb กับ Aspose.Tasks

## Introduction
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **บันทึกโครงการเป็นภาพ** ด้วยรูปแบบพิกเซล 24bppRgb โดยใช้ Aspose.Tasks สำหรับ Java การแสดงผลข้อมูล MS Project เป็นภาพเป็นประโยชน์เมื่อคุณต้องการแชร์ภาพสแนปช็อตของกำหนดการ ฝังไทม์ไลน์ในรายงาน หรือสร้างภาพย่อสำหรับพอร์ทัลโครงการ เราจะสาธิตวิธี **เปลี่ยนความละเอียดภาพ java** ให้ตรงตามความต้องการคุณภาพของคุณด้วย

## Quick Answers
- **ฉันสามารถเรนเดอร์โครงการเป็นภาพได้หรือไม่?** ใช่, Aspose.Tasks ให้คุณบันทึกโครงการเป็น TIFF, PNG, JPEG ฯลฯ  
- **รูปแบบพิกเซลใดให้ความลึกสีที่ดีที่สุด?** `Format24bppRgb` ให้ภาพสีจริง (24‑bit)  
- **ฉันจะปรับความละเอียดภาพได้อย่างไร?** ใช้ `setHorizontalResolution` และ `setVerticalResolution` บน `ImageSaveOptions`  
- **ต้องใช้ไลเซนส์สำหรับการใช้งานจริงหรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่การประเมินผล  
- **รองรับเวอร์ชัน Java ทั้งหมดหรือไม่?** ทำงานได้กับ Java 8 ขึ้นไป

## What is “save project as image”?
การบันทึกโครงการเป็นภาพหมายถึงการแปลงการแสดงผลเชิงภาพของไฟล์ Microsoft Project (`.mpp`) ให้เป็นรูปแบบเรสเตอร์ (เช่น TIFF) ไฟล์ที่ได้สามารถแสดงในเบราว์เซอร์ แทรกในเอกสาร หรือพิมพ์ได้โดยไม่ต้องใช้แอปพลิเคชัน Project ดั้งเดิม

## Why use the 24bppRgb format?
รูปแบบพิกเซล 24bppRgb จะเก็บข้อมูลแต่ละพิกเซลด้วย 8 บิตสำหรับสีแดง เขียว และน้ำเงิน ทำให้ได้คุณภาพสีจริงโดยไม่มีช่องอัลฟ่า เหมาะสำหรับรายงานที่ต้องการความคมชัดของสีสูง ในขณะเดียวกันไฟล์จะมีขนาดที่สมเหตุสมผลเมื่อเทียบกับรูปแบบ 32‑bit

## Prerequisites
ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Java Development Kit (JDK)** – JDK 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ  
2. **Aspose.Tasks for Java** – ดาวน์โหลดและติดตั้งจาก [here](https://releases.aspose.com/tasks/java/)  
3. **ความรู้พื้นฐานของ Java** – ความคุ้นเคยกับไวยากรณ์ Java และการตั้งค่าโปรเจกต์จะช่วยให้คุณตามโค้ดได้ง่ายขึ้น

## Import Packages
ก่อนอื่นให้นำเข้าคลาสของ Aspose.Tasks ที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณ:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
แทนที่ `"Your Data Directory"` ด้วยพาธเต็มที่ไฟล์ `.mpp` ของคุณอยู่

### Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
บรรทัดนี้จะอ่านไฟล์ Microsoft Project (`project.mpp`) และสร้างอ็อบเจกต์ `Project` ที่ Aspose.Tasks สามารถจัดการได้

### Step 3: Configure Image Save Options
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
ที่นี่เรากำหนดรูปแบบเอาต์พุตเป็น TIFF ระบุความละเอียด **72 dpi** (คุณสามารถเปลี่ยนค่าเหล่านี้ตามความต้องการของคุณ – นี่คือจุดที่คุณ **เปลี่ยนความละเอียดภาพ java**) และเลือกรูปแบบพิกเซล 24bppRgb สำหรับผลลัพธ์สีจริง

### Step 4: Save Project Data as Image
```java
project.save(dataDir + "resFile.tif", options);
```
เมธอด `save` จะเขียนภาพที่เรนเดอร์ลงใน `resFile.tif` ตามตัวเลือกที่กำหนดไว้ข้างต้น

## Common Issues and Solutions
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **ภาพออกเป็นสีขาวเปล่า** | มุมมองของโครงการอาจว่างเปล่า | เรียก `project.setDefaultView(ViewType.Gantt);` ก่อนบันทึก |
| **ภาพคุณภาพต่ำ** | ตั้งค่าความละเอียดต่ำเกินไป | เพิ่มค่า `setHorizontalResolution` และ `setVerticalResolution` (เช่น 150 dpi) |
| **รูปแบบพิกเซลไม่รองรับ** | ใช้ Aspose.Tasks รุ่นเก่า | อัปเกรดเป็นรุ่นล่าสุดของ Aspose.Tasks for Java |

## Conclusion
คุณได้เรียนรู้วิธี **บันทึกโครงการเป็นภาพ** ด้วยรูปแบบ 24bppRgb และปรับความละเอียดโดยใช้ Aspose.Tasks สำหรับ Java วิธีนี้ช่วยให้คุณสร้างภาพที่คมชัดและสีแม่นยำของกำหนดการโครงการเพื่อการแชร์ รายงาน หรือการเก็บรักษา

## FAQ's
### Q: ฉันสามารถเรนเดอร์ข้อมูลโครงการในรูปแบบภาพอื่นได้หรือไม่?
A: ใช่, Aspose.Tasks รองรับการเรนเดอร์ข้อมูลโครงการเป็นรูปแบบภาพต่าง ๆ เช่น PNG, JPEG, BMP ฯลฯ  
### Q: Aspose.Tasks รองรับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?
A: ใช่, Aspose.Tasks รองรับหลายเวอร์ชันของ MS Project รวมถึง 2003, 2007, 2010, 2013, และ 2016  
### Q: ฉันสามารถปรับความละเอียดและรูปแบบพิกเซลของภาพที่เรนเดอร์ได้หรือไม่?
A: ใช่, คุณสามารถปรับความละเอียดและรูปแบบพิกเซลตามความต้องการของคุณโดยใช้ Aspose.Tasks  
### Q: Aspose.Tasks ต้องการไลเซนส์สำหรับการใช้งานเชิงพาณิชย์หรือไม่?
A: ใช่, คุณต้องซื้อไลเซนส์สำหรับการใช้งานเชิงพาณิชย์ของ Aspose.Tasks คุณสามารถขอไลเซนส์ชั่วคราวเพื่อทดสอบได้จาก [here](https://purchase.aspose.com/temporary-license/)  
### Q: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?
A: คุณสามารถรับการสนับสนุนสำหรับ Aspose.Tasks ได้จาก [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}