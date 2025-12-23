---
date: 2025-12-23
description: เรียนรู้วิธีสร้างสรุป MPP และอัปเดตผู้เขียนโครงการด้วย Aspose.Tasks สำหรับ
  Java ตั้งค่าและดึงข้อมูลโครงการได้อย่างง่ายดาย
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีสร้างสรุป MPP และอัปเดตผู้เขียนโครงการด้วย Aspose.Tasks
url: /th/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เขียนสรุปโครงการ MPP ใน Aspose.Tasks

## บทนำ
ในบทเรียนนี้ คุณจะ **สร้างสรุป MPP** สำหรับไฟล์ Microsoft Project และเรียนรู้วิธี **อัปเดตผู้เขียนโครงการ** โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะกำลังสร้างเครื่องมือการจัดการโครงการหรือทำการอัตโนมัติรายงาน การควบคุมคุณสมบัติสรุปโดยโปรแกรมจะช่วยประหยัดเวลาและทำให้ข้อมูลสอดคล้องกันในทุกโครงการของคุณ

## คำตอบสั้น
- **สร้างสรุป MPP หมายถึงอะไร?** หมายถึงการตั้งค่าคุณสมบัติระดับสูงของโครงการ (ผู้เขียน, รุ่น, คำสำคัญ ฯลฯ) ที่ปรากฏในกล่องโต้ตอบ Project Summary Information ของ Microsoft Project.  
- **ไลบรารีใดจัดการเรื่องนี้?** Aspose.Tasks for Java มี API ที่ไหลลื่นสำหรับอ่านและเขียนคุณสมบัติเหล่านั้น.  
- **ฉันต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองใช้งานฟรี แต่ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมจริง.  
- **ฉันสามารถเปลี่ยนผู้เขียนหลังจากไฟล์ถูกบันทึกได้หรือไม่?** ใช่ – คุณสามารถ **อัปเดตผู้เขียนโครงการ** โดยเรียก `project.set(Prj.AUTHOR, "New Author")` แล้วบันทึกไฟล์ใหม่อีกครั้ง.  
- **รูปแบบไฟล์ที่รองรับคืออะไร?** ทั้ง MPP และ XML (SaveFileFormat.Xml) ได้รับการสนับสนุนเต็มรูปแบบ.

## สร้างสรุป MPP คืออะไร?
การสร้างสรุป MPP เกี่ยวข้องกับการเติมข้อมูลเมตาดาต้าของโครงการ—ผู้เขียน, หมายเลขรุ่น, คำสำคัญ, ความคิดเห็น, วันที่สร้าง, และวันที่พิมพ์ เมตาดาต้านี้ถูกเก็บไว้ในบันทึก Project Summary Information และแสดงในส่วน **File → Info** ของ Microsoft Project.

## ทำไมต้องอัปเดตผู้เขียนโครงการ?
การรักษาข้อมูล **ผู้เขียนโครงการ** ให้แม่นยำเป็นสิ่งสำคัญสำหรับการตรวจสอบ, การทำงานร่วมกัน, และการรายงาน เมื่อสมาชิกทีมหลายคนมีส่วนร่วม คุณอาจต้อง **อัปเดตผู้เขียนโครงการ** เพื่อสะท้อนการเปลี่ยนแปลงล่าสุดหรือเพื่อระบุผู้ทำงานอย่างถูกต้อง.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:
1. Java Development Kit (JDK) ที่ติดตั้งบนเครื่องของคุณ.  
2. Aspose.Tasks for Java – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/).  
3. IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans.

## นำเข้าแพ็กเกจ
ขั้นแรก ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่คลาส Java ของคุณ:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: ตั้งค่าโครงการและกำหนดข้อมูลสรุป
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
ในโค้ดด้านบน เรา **สร้างสรุป MPP** ฟิลด์ต่าง ๆ เช่น ผู้เขียน, รุ่น, และคำสำคัญ คุณยังสามารถ **อัปเดตผู้เขียนโครงการ** ภายหลังโดยเรียก `project.set(Prj.AUTHOR, "New Name")`.

## ขั้นตอนที่ 2: บันทึกข้อมูลสรุปโครงการ
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
การบันทึกโครงการจะทำให้ข้อมูลสรุปทั้งหมดที่คุณกำหนดไว้คงอยู่.

## ขั้นตอนที่ 3: อ่านข้อมูลสรุปโครงการ
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
ส่วนนี้แสดงวิธี **อ่านกลับ** ข้อมูลสรุป เพื่อยืนยันว่าการ **สร้างสรุป MPP** สำเร็จ.

## ปัญหาทั่วไปและวิธีแก้
- **ค่า Null หลังการอ่าน:** ตรวจสอบว่าโครงการถูกบันทึกสำเร็จก่อนโหลดใหม่ ตรวจสอบเส้นทางไฟล์และสิทธิ์การเข้าถึง.  
- **ความแตกต่างของรูปแบบวันที่:** `project.get(Prj.CREATION_DATE)` คืนค่าเป็น `java.util.Date` ใช้ `SimpleDateFormat` หากต้องการรูปแบบการแสดงผลที่กำหนดเอง.  
- **ไม่ได้ตั้งค่าไลเซนส์:** หากไม่มีไลเซนส์ที่ถูกต้อง Aspose.Tasks จะทำงานในโหมดประเมินผลและอาจใส่ลายน้ำ ลงทะเบียนไลเซนส์ของคุณตั้งแต่ต้นในโค้ด.

## คำถามที่พบบ่อย
**Q: ฉันสามารถใช้ Aspose.Tasks for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?**  
A: ใช่, Aspose.Tasks for Java สามารถผสานรวมกับไลบรารี Java อื่นได้อย่างราบรื่นเพื่อเพิ่มความสามารถในการจัดการโครงการของคุณ.

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีได้จาก [here](https://releases.aspose.com/).

**Q: Aspose.Tasks for Java มีการอัปเดตบ่อยแค่ไหน?**  
A: Aspose.Tasks for Java มีการอัปเดตเป็นประจำเพื่อให้เข้ากันได้กับเวอร์ชันล่าสุดของ Java และไฟล์ Microsoft Project.

**Q: ฉันสามารถปรับแต่งข้อมูลสรุปโครงการเพิ่มเติมได้หรือไม่?**  
A: แน่นอน, Aspose.Tasks for Java มีตัวเลือกมากมายสำหรับการปรับแต่งข้อมูลสรุปโครงการตามความต้องการของคุณ.

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## สรุป
ในบทเรียนนี้ เราได้แสดงวิธี **สร้างสรุป MPP** ข้อมูล, **อัปเดตผู้เขียนโครงการ**, และตรวจสอบการเปลี่ยนแปลงเหล่านั้นโดยใช้ Aspose.Tasks for Java ด้วยการอัตโนมัติกระบวนการเหล่านี้ คุณจะได้การควบคุมเมตาดาต้าโครงการอย่างเต็มที่ ทำให้แอปพลิเคชันของคุณแข็งแรงขึ้นและรายงานโครงการของคุณแม่นยำยิ่งขึ้น.

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบกับ:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}