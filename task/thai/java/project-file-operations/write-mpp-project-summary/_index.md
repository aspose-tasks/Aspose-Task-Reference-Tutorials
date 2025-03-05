---
title: เขียนสรุปโครงการ MPP ใน Aspose.Tasks
linktitle: เขียนสรุปโครงการ MPP ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีเขียนสรุปโครงการ MPP ใน Java โดยใช้ Aspose.Tasks ตั้งค่าและดึงข้อมูลโครงการได้อย่างง่ายดาย
type: docs
weight: 27
url: /th/java/project-file-operations/write-mpp-project-summary/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่อเขียนสรุปโปรเจ็กต์ MPP Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังสำหรับการทำงานกับไฟล์ Microsoft Project ด้วยการทำตามขั้นตอนที่อธิบายไว้ด้านล่าง คุณจะสามารถตั้งค่าและดึงข้อมูลสรุปต่างๆ เกี่ยวกับโครงการโดยใช้ไลบรารีนี้ได้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการสำหรับการพัฒนา Java เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

## แพ็คเกจนำเข้า
ประการแรก นำเข้าแพ็คเกจที่จำเป็นไปยังคลาส Java ของคุณ:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการและกำหนดข้อมูลสรุป
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
//เริ่มต้นวัตถุโครงการใหม่ด้วยเส้นทางไปยังไฟล์โครงการของคุณ
Project project = new Project(dataDir + "project.mpp");
// กำหนดข้อมูลสรุปเกี่ยวกับโครงการ
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// กำหนดวันที่สร้างโครงการ
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// กำหนดคำสำคัญสำหรับโครงการ
project.set(Prj.KEYWORDS, "MPP Aspose");
// กำหนดวันที่พิมพ์ล่าสุดของโครงการ
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## ขั้นตอนที่ 2: บันทึกข้อมูลสรุปโครงการ
```java
// บันทึกโครงการกลับในรูปแบบ MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// แสดงข้อความแสดงความสำเร็จ
System.out.println("Process completed Successfully");
```
## ขั้นตอนที่ 3: อ่านข้อมูลสรุปโครงการ
```java
// อ่านข้อมูลสรุปโครงการ
project = new Project(dataDir + "MppAspose.xml");
// ผู้เขียนโครงการพิมพ์
System.out.println("Author: " + project.get(Prj.AUTHOR));
// พิมพ์ผู้เขียนคนสุดท้ายของโครงการ
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// พิมพ์หมายเลขการแก้ไขของโครงการ
System.out.println("Revision: " + project.get(Prj.REVISION));
// พิมพ์คำสำคัญของโครงการ
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// พิมพ์ความเห็นของโครงการ
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// พิมพ์วันที่สร้างโครงการ
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// พิมพ์คำสำคัญของโครงการ (อีกครั้ง)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// พิมพ์วันที่พิมพ์ล่าสุดของโครงการ
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีเขียนสรุปโปรเจ็กต์ MPP โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถตั้งค่าและเรียกข้อมูลสรุปต่างๆ เกี่ยวกับไฟล์โครงการของคุณได้อย่างมีประสิทธิภาพ Aspose.Tasks ลดความซับซ้อนของกระบวนการทำงานกับไฟล์ Microsoft Project ในแอปพลิเคชัน Java นำเสนอฟังก์ชันการทำงานที่แข็งแกร่งและใช้งานง่าย
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับไลบรารี Java อื่นๆ ได้หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ Java สามารถผสานรวมกับไลบรารี Java อื่นๆ ได้อย่างราบรื่น เพื่อเพิ่มขีดความสามารถในการจัดการโปรเจ็กต์ของคุณ
### ถาม: Aspose.Tasks สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: Aspose.Tasks สำหรับ Java อัปเดตบ่อยแค่ไหน
ตอบ: Aspose.Tasks สำหรับ Java ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าสามารถเข้ากันได้กับไฟล์ Java และ Microsoft Project เวอร์ชันล่าสุด
### ถาม: ฉันสามารถปรับแต่งข้อมูลสรุปโครงการเพิ่มเติมได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks for Java มีตัวเลือกมากมายในการปรับแต่งข้อมูลสรุปโปรเจ็กต์ตามความต้องการเฉพาะของคุณ
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
ตอบ: คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).