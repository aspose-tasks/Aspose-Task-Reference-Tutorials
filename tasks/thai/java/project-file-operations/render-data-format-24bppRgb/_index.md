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

## การแนะนำ
ในบทแนะนำนี้คุณจะได้สัมผัส ** บันทึกโครงการเป็นภาพ** ด้วยรูปแบบฮาร์ดแวร์ 24bppRgb สำหรับ Aspose.Tasks Java สำหรับข้อมูลข้อมูล MS Project เป็นภาพที่เป็นประโยชน์เมื่อคุณต้องการแชร์ภาพสแนปช็อตของกำหนดการฝังไทม์ไลน์ในรายงานหรือสร้างภาพย่อสำหรับโครงการบางส่วนสาธิตวิธี ** เปลี่ยนการตรวจสอบภาพ java** ให้ตรงคุณภาพในการเข้าถึง

## คำตอบด่วน
- **เหตุการณ์เรนเดอร์โครงการเป็นภาพที่ทำได้?** ประสบปัญหา, Aspose.Tasks ให้คุณบันทึกโครงการเป็น TIFF, PNG, JPEG และอื่นๆ
- ** รูปแบบการให้ใดๆ ให้สีที่ดีที่สุด?** `Format24bppRgb` ให้ภาพสีจริง (24-บิต)
- ** ฉันจะปรับความละเอียดของภาพได้อย่างไร?** ใช้ `setHorizontalResolution` และ `setVerticalResolution` บน `ImageSaveOptions`
- **ต้องใช้เซนส์สาธารณะจริงหรือไม่?** ต้องมีเซนส์ที่กล่าวถึงเรื่องนี้
- ** รองรับ Java และอื่นๆ หรือไม่** รองรับ Java 8 ขึ้นไป

## คืออะไร “บันทึกโครงการเป็นรูปภาพ”?
การวิจัยโครงการเป็นภาพหมายถึงการประชุมเชิงปฏิบัติการสำหรับไฟล์ Microsoft Project (`.mpp`) ให้ใบรับรองเรสเตอร์ (เช่น TIFF) สามารถพิสูจน์ได้ว่าสามารถแทรกในเอกสารหรือพิมพ์ได้โดยไม่ต้องใช้แอปพลิเคชัน Project ดั้งเดิม

## เหตุใดจึงต้องใช้รูปแบบ 24bppRgb
ส่วนการควบคุม 24bppRgb จะต้องตรวจสอบแต่ละส่วนด้วย 8 ส่วนสำหรับสีแดง เขียว และน้ำเงินบางส่วนได้คุณภาพสีจริงโดยไม่มีช่องอัลฟ่า รองรับรายงานที่ต้องการของสีสูงในส่วนของไฟล์จะมีขนาดที่จะมีการรองรับรูปแบบ 32 บิต

## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้นการดำเนินการให้คุณทราบอีกครั้ง:

1. **Java Development Kit (JDK)** – JDK8 หรือใหม่กว่าติดตั้งบนเครื่องของคุณ
2. **Aspose.Tasks for Java** – ดาวน์โหลดทั้งหมดจาก [ที่นี่](https://releases.aspose.com/tasks/java/)
3. **ความรู้จำลอง Java** – ตรวจสอบ Java และการวิจัยเจกต์ตามโค้ดของโปรแกรม

## แพคเกจนำเข้า
ก่อนอื่นให้นำเข้าคลาสของ Aspose.Tasks ที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณ:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
แทนที่ `"Your Data Directory"` ด้วยพาธเต็มที่ไฟล์ `.mpp` ของคุณอยู่

### ขั้นตอนที่ 2: โหลดไฟล์โปรเจ็กต์
```java
Project project = new Project(dataDir + "project.mpp");
```
บรรทัดนี้จะอ่านไฟล์ Microsoft Project (`project.mpp`) และสร้างอ็อบเจกต์ `Project` ที่ Aspose.Tasks สามารถจัดการได้

### ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการบันทึกรูปภาพ
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
ที่นี่เรากำหนดรูปแบบเอาต์พุตเป็น TIFF ระบุความละเอียด **72 dpi** (คุณสามารถเปลี่ยนค่าเหล่านี้ตามความต้องการของคุณ – นี่คือจุดที่คุณ **เปลี่ยนความละเอียดภาพ java**) และเลือกรูปแบบพิกเซล 24bppRgb สำหรับผลลัพธ์สีจริง

### ขั้นตอนที่ 4: บันทึกข้อมูลโปรเจ็กต์เป็นรูปภาพ
```java
project.save(dataDir + "resFile.tif", options);
```
เมธอด `save` จะเขียนภาพที่เรนเดอร์ลงใน `resFile.tif` ตามตัวเลือกที่กำหนดไว้ข้างต้น

## ปัญหาทั่วไปและแนวทางแก้ไข
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **ภาพไม่ใช่สีขาว** | อาจมีการดำเนินโครงการที่อาจเป็นไปได้ | เรียก `project.setDefaultView(ViewType.Gantt);` ก่อนบันทึก |
| **ภาพคุณภาพต่ำ** | ความละเอียดต่ำเกินไป | ต้องค่า `setHorizontalResolution` และ `setVerticalResolution` (เช่น 150dpi) |
| ** รูปแบบตัวเครื่องไม่รองรับ** | ใช้ Aspose.Tasks ซอร์ | ปรับปรุงเป็นการปรับปรุงของ Aspose.Tasks for Java |

## บทสรุป
ครั้งหนึ่ง ** บันทึกโครงการเป็นภาพ** ด้วยรูปแบบ 24bppRgb และปรับความละเอียดของคอมพิวเตอร์ Aspose.Tasks สำหรับ Java วิธีการที่ช่วยให้สร้างความคมชัดและสีเซิร์ฟเวอร์ของกำหนดการโครงการที่จำเป็นแชร์รายงานหรือไดรฟ์

## คำถามที่พบบ่อย
### ถาม: ข้อมูลเรนเดอร์โครงการสามารถตรวจสอบภาพอื่นได้หรือไม่?
A: เป็นไปได้, Aspose.Tasks รองรับการเรนเดอร์ข้อมูลโครงการบางอย่างของภาพต่าง ๆ เช่น PNG, JPEG, BMP และอื่น ๆ
### ถาม: Aspose.Tasks รองรับที่แตกต่างกันของ MS Project อย่างไร?
ตอบ: ถูกต้อง, Aspose.Tasks รองรับหลายส่วนของ MS Project และ 2003, 2007, 2010, 2013, และ 2016
### ถาม: การวาดรูปความละเอียดสูงและรูปแบบการทำงานของเรนเดอร์สามารถเกิดขึ้นได้หรือไม่?
ตอบ: ต้องลองตรวจสอบอย่างละเอียดและรูปแบบสำหรับความต้องการของคุณ Aspose.Tasks
### ถาม: Aspose.Tasks ต้องการเซนส์โดยตรงหรือไม่?
ตอบ: ตรวจสอบความถูกต้อง, ซื้อไลเซนส์เป็นครั้งแรกของ Aspose.Tasks ขอไลเซนส์ชั่วคราวเพื่อทดสอบได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)
### ถาม: ฉันขอรับสำหรับ Aspose.Tasks จากที่ไหน?
ตอบ: ไม่เคยรับสำหรับ Aspose.Tasks จาก [ฟอรัม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)

---

**อัปเดตล่าสุด:** 17-12-2568
**ทดสอบกับ:** Aspose.Tasks สำหรับ Java 24.11
**ผู้เขียน:** สมมติ  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}