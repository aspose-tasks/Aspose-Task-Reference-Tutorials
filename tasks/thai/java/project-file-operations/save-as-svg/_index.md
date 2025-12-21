---
date: 2025-12-21
description: เรียนรู้วิธีสร้าง SVG จากไฟล์ MPP ด้วย Java และบันทึกโครงการเป็น SVG
  โดยใช้ไลบรารี Aspose.Tasks คู่มือขั้นตอนต่อขั้นตอนพร้อมตัวอย่างโค้ด
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีสร้าง SVG จากไฟล์ MPP ใน Java ด้วย Aspose.Tasks
url: /th/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง SVG จาก MPP ด้วย Java

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **สร้าง SVG จาก MPP** ด้วย Aspose.Tasks for Java การแปลงไฟล์ Microsoft Project (MPP) ไปเป็นกราฟิกแบบเวกเตอร์ที่ปรับขนาดได้ (SVG) ช่วยให้คุณฝังแผนภาพคุณภาพสูงที่ไม่ขึ้นกับความละเอียดโดยตรงลงในหน้าเว็บ รายงาน หรือแดชบอร์ด เราจะอธิบายขั้นตอนการตั้งค่าที่จำเป็น แสดงโค้ดที่ต้องใช้อย่างละเอียด และอธิบายแต่ละขั้นตอนเพื่อให้คุณมั่นใจในการ **บันทึกโครงการเป็น SVG** ในแอปพลิเคชันของคุณเอง

## คำตอบสั้น
- **สร้าง SVG จาก MPP** หมายถึงอะไร?  
  มันแปลงไฟล์ Microsoft Project (.mpp) เป็นภาพ SVG ที่สามารถแสดงบนเบราว์เซอร์ใดก็ได้โดยไม่สูญเสียคุณภาพ  
- **ไลบรารีใดที่ทำการแปลง?**  
  Aspose.Tasks for Java มีเมธอด `save` แบบบรรทัดเดียวเพื่อทำการแปลง  
- **ฉันต้องการไลเซนส์หรือไม่?**  
  ต้องใช้ไลเซนส์ชั่วคราวสำหรับการใช้งานเชิงพาณิชย์; มีการทดลองใช้ฟรี  
- **ข้อกำหนดเบื้องต้นคืออะไร?**  
  Java JDK 8 ขึ้นไปและไฟล์ JAR ของ Aspose.Tasks for Java  
- **การแปลงใช้เวลานานเท่าไหร่?**  
  โดยทั่วไปใช้เวลาน้อยกว่าวินาทีสำหรับไฟล์โครงการมาตรฐาน  

## “สร้าง SVG จาก MPP” คืออะไร?
การสร้าง SVG จากไฟล์ MPP หมายถึงการส่งออกการแสดงผลภาพของกำหนดการโครงการ—งาน ไทม์ไลน์ และทรัพยากร—ไปเป็นรูปแบบ Scalable Vector Graphics (SVG) ซึ่งเป็น XML‑based, มีน้ำหนักเบา และปรับขนาดได้อย่างสมบูรณ์บนหน้าจอความละเอียดสูง

## ทำไมต้องใช้ Aspose.Tasks เพื่อบันทึกโครงการเป็น SVG?
- **ไม่ต้องติดตั้ง Microsoft Project** – ไลบรารีทำงานได้โดยอิสระ  
- **ความแม่นยำเต็มรูปแบบ** – แผนภูมิ, แถบ Gantt, และไมล์สโตนยังคงสไตล์เดิม  
- **ข้ามแพลตฟอร์ม** – รันโค้ดบน Windows, Linux หรือ macOS  
- **การผสานรวมง่าย** – การเรียก API หนึ่งบรรทัดเข้ากับ pipeline ของ Java ได้อย่างเป็นธรรมชาติ  

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า ดาวน์โหลดจากเว็บไซต์ของ Oracle  
- **Aspose.Tasks for Java** – รับไลบรารีจากหน้าดาวน์โหลดอย่างเป็นทางการ **[here](https://releases.aspose.com/tasks/java/)**  

## นำเข้าชุดแพ็กเกจ
First, import the classes you’ll need. The import block remains unchanged.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
Specify where your source MPP file lives and where the SVG will be written.

```java
String dataDir = "Your Data Directory";
```

> **เคล็ดลับ:** ใช้เส้นทางแบบเต็มหรือเส้นทางสัมพันธ์กับโฟลเดอร์ resources ของโปรเจกต์เพื่อหลีกเลี่ยง `FileNotFoundException`  

## ขั้นตอนที่ 2: โหลดไฟล์ MPP
Create a `Project` instance by loading the existing Microsoft Project file.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

บรรทัดนี้อ่านไฟล์ *HomeMovePlan.mpp* จากโฟลเดอร์ที่คุณกำหนดไว้ก่อนหน้า  

## ขั้นตอนที่ 3: บันทึกโครงการเป็น SVG
Now you can **save project as SVG** with a single command.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

เมธอดนี้จะเขียนไฟล์ `project5.svg` ไปยังไดเรกทอรีเดียวกัน SVG ที่ได้สามารถเปิดในเบราว์เซอร์สมัยใหม่ใดก็ได้หรือฝังโดยตรงใน HTML  

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไม่พบไฟล์** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่า string ของไดเรกทอรีลงท้ายด้วยตัวคั่น (`/` หรือ `\\`). |
| **ผลลัพธ์ SVG ว่าง** | โครงการถูกโหลดโดยไม่มีมุมมอง | ตรวจสอบว่าไฟล์ MPP มีมุมมอง Gantt chart ก่อนบันทึก. |
| **ข้อยกเว้นไลเซนส์** | ไม่มีการใช้ไลเซนส์ที่ถูกต้อง | ใช้ไลเซนส์ชั่วคราวโดยเรียก `License.setLicense("path/to/license.xml")` ก่อนเรียก `save`. |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks for Java รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่?**  
A: รองรับไฟล์ MPP, MPT, และ XML ตั้งแต่รุ่นเก่าไปจนถึงรุ่นล่าสุดของ Project  

**Q: ฉันสามารถปรับแต่งลักษณะของผลลัพธ์ SVG ได้หรือไม่?**  
A: ได้แน่นอน ใช้ `SvgOptions` เพื่อกำหนดฟอนต์, สี, และตัวเลือกการจัดวางก่อนเรียก `save`  

**Q: Aspose.Tasks for Java ต้องการไลเซนส์สำหรับการใช้งานเชิงพาณิชย์หรือไม่?**  
A: ต้องการไลเซนส์ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์ คุณสามารถรับไลเซนส์ชั่วคราว **[here](https://purchase.aspose.com/temporary-license/)**  

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks for Java ก่อนซื้อได้หรือไม่?**  
A: ได้ มีการทดลองใช้ฟรี **[here](https://purchase.aspose.com/buy)**  

**Q: จะหาการสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: เยี่ยมชมฟอรั่มชุมชน **[here](https://forum.aspose.com/c/tasks/15)** เพื่อถามคำถามและแบ่งปันความคิดเห็น  

## สรุป
คุณได้เรียนรู้วิธี **สร้าง SVG จาก MPP** ด้วย Java และการ **บันทึกโครงการเป็น SVG** อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks ความสามารถนี้ช่วยให้คุณผสานภาพโครงการคุณภาพสูงเข้าในพอร์ทัลเว็บ, แดชบอร์ดรายงาน, หรือที่ใดก็ตามที่ต้องการกราฟิกที่ปรับขนาดได้ ทดลองใช้ `SvgOptions` เพื่อปรับแต่งผลลัพธ์และคุณจะมีเครื่องมือที่ทรงพลังในชุดพัฒนาของคุณ  

---

**อัปเดตล่าสุด:** 2025-12-21  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}