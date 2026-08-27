---
date: 2026-03-27
description: เรียนรู้วิธีส่งออกไฟล์ MPP เป็น SVG ใน Java ด้วย Aspose.Tasks คู่มือขั้นตอนโดยละเอียด
  ตัวอย่างโค้ดและเคล็ดลับเพื่อบันทึกโครงการเป็น SVG อย่างรวดเร็ว
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีส่งออกไฟล์ MPP เป็น SVG ใน Java ด้วย Aspose.Tasks
url: /th/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการส่งออก MPP เป็น SVG ใน Java

## การส่งออก MPP เป็น SVG – บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **export MPP to SVG** ไฟล์โดยใช้ Aspose.Tasks for Java การแปลงไฟล์ Microsoft Project (MPP) เป็นภาพ Scalable Vector Graphics (SVG) ช่วยให้คุณฝังไดอะแกรมคุณภาพสูงที่ไม่ขึ้นกับความละเอียดโดยตรงลงในหน้าเว็บ รายงาน หรือแดชบอร์ด เราจะอธิบายขั้นตอนการตั้งค่าที่จำเป็น แสดงโค้ดที่ต้องใช้อย่างแม่นยำ และอธิบายแต่ละขั้นตอนเพื่อให้คุณสามารถ **save project as SVG** ในแอปพลิเคชันของคุณได้อย่างมั่นใจ

## คำตอบสั้น
- **การ “export MPP to SVG” หมายถึงอะไร?**  
  มันแปลงไฟล์ Microsoft Project (.mpp) ให้เป็นภาพ SVG ที่สามารถแสดงบนเบราว์เซอร์ใดก็ได้โดยไม่สูญเสียคุณภาพ  
- **ไลบรารีใดที่จัดการการแปลง?**  
  Aspose.Tasks for Java ให้เมธอด `save` แบบบรรทัดเดียวเพื่อทำการแปลง  
- **ฉันต้องการใบอนุญาตหรือไม่?**  
  จำเป็นต้องมีใบอนุญาตชั่วคราวสำหรับการใช้งานเชิงพาณิชย์; มีการทดลองใช้ฟรี  
- **ข้อกำหนดเบื้องต้นคืออะไร?**  
  Java JDK 8 ขึ้นไปและไฟล์ JAR ของ Aspose.Tasks for Java  
- **การแปลงใช้เวลานานเท่าไหร่?**  
  โดยทั่วไปใช้เวลาน้อยกว่าวินาทีสำหรับไฟล์โปรเจกต์มาตรฐาน  

## การ “export MPP to SVG” คืออะไร?
การส่งออก MPP เป็น SVG หมายถึงการนำการแสดงผลภาพของกำหนดการโครงการ—งาน, ไทม์ไลน์, และทรัพยากร—และเขียนออกเป็นไฟล์ SVG SVG เป็นไฟล์ที่อิง XML, มีน้ำหนักเบา, และขยายได้อย่างสมบูรณ์บนหน้าจอความละเอียดสูง

## ทำไมต้องส่งออก MPP เป็น SVG ด้วย Aspose.Tasks?
- **ไม่ต้องติดตั้ง Microsoft Project** – ไลบรารีทำงานได้โดยอิสระ  
- **ความแม่นยำเต็มรูปแบบ** – แผนภูมิ, แถบ Gantt, และไมล์สโตนคงสไตล์เดิม  
- **ข้ามแพลตฟอร์ม** – รันโค้ดบน Windows, Linux หรือ macOS  
- **API บรรทัดเดียว** – การเรียกเดียวทำการบันทึกโครงการเป็น SVG, เข้ากับ pipeline ของ Java ที่มีอยู่อย่างเป็นธรรมชาติ  

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า ดาวน์โหลดจากเว็บไซต์ Oracle  
- **Aspose.Tasks for Java** – รับไลบรารีจากหน้าดาวน์โหลดอย่างเป็นทางการ **[ที่นี่](https://releases.aspose.com/tasks/java/)**  

## นำเข้าแพ็กเกจ
ก่อนอื่นให้นำเข้าคลาสที่คุณต้องการใช้ ส่วนบล็อก import จะคงเดิม

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
ระบุตำแหน่งที่ไฟล์ MPP ต้นฉบับของคุณอยู่และตำแหน่งที่ SVG จะถูกเขียนออกไป

```java
String dataDir = "Your Data Directory";
```

> **เคล็ดลับ:** ใช้เส้นทางแบบเต็มหรือเส้นทางสัมพันธ์กับโฟลเดอร์ resources ของโปรเจกต์เพื่อหลีกเลี่ยง `FileNotFoundException`.

## ขั้นตอนที่ 2: โหลดไฟล์ MPP
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ Microsoft Project ที่มีอยู่

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

บรรทัดนี้อ่านไฟล์ *HomeMovePlan.mpp* จากโฟลเดอร์ที่คุณกำหนดไว้ก่อนหน้า

## ขั้นตอนที่ 3: บันทึกโครงการเป็น SVG
ตอนนี้คุณสามารถ **export MPP to SVG** ด้วยคำสั่งเดียว

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

เมธอดจะเขียนไฟล์ `project5.svg` ไปยังไดเรกทอรีเดียวกัน SVG ที่ได้สามารถเปิดในเบราว์เซอร์สมัยใหม่ใดก็ได้หรือฝังโดยตรงใน HTML

## กรณีการใช้งานทั่วไป
- **แดชบอร์ดโครงการ** – ฝังแผนภูมิ Gantt แบบเรียลไทม์ในพอร์ทัลเว็บโดยไม่ต้องให้ลูกค้าติดตั้ง Microsoft Project  
- **การรายงานอัตโนมัติ** – สร้างภาพ SVG แบบทันทีสำหรับรายงาน PDF หรือ HTML  
- **การทำงานร่วมกันระหว่างทีม** – แชร์กำหนดการแบบภาพกับผู้มีส่วนได้ส่วนเสียที่ต้องการเพียงเบราว์เซอร์เพื่อดู  

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Reason | Fix |
|-------|--------|-----|
| **ไฟล์ไม่พบ** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่าสตริงของไดเรกทอรีลงท้ายด้วยตัวคั่น (`/` หรือ `\\`). |
| **ผลลัพธ์ SVG ว่าง** | โหลดโครงการโดยไม่มีมุมมอง | ตรวจสอบว่าไฟล์ MPP มีมุมมองแผนภูมิ Gantt ก่อนบันทึก |
| **ข้อยกเว้นใบอนุญาต** | ไม่มีใบอนุญาตที่ถูกต้อง | ใช้ใบอนุญาตชั่วคราวด้วย `License.setLicense("path/to/license.xml")` ก่อนเรียก `save` |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks for Java รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่?**  
A: ใช่, รองรับรูปแบบ MPP, MPT, และ XML ตั้งแต่รุ่นเก่าไปจนถึงรุ่นล่าสุดของ Project  

**Q: ฉันสามารถปรับแต่งลักษณะของผลลัพธ์ SVG ได้หรือไม่?**  
A: แน่นอน ใช้ `SvgOptions` เพื่อตั้งค่าแบบอักษร, สี, และตัวเลือกการจัดวางก่อนเรียก `save`.  

**Q: Aspose.Tasks for Java ต้องการใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่?**  
A: ใช่, จำเป็นต้องมีใบอนุญาตที่ถูกต้องสำหรับการผลิต คุณสามารถรับใบอนุญาตชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)**  

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks for Java ก่อนซื้อได้หรือไม่?**  
A: ได้, มีการทดลองใช้ฟรี **[ที่นี่](https://purchase.aspose.com/buy)**  

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: เยี่ยมชมฟอรั่มชุมชน **[ที่นี่](https://forum.aspose.com/c/tasks/15)** เพื่อถามคำถามและแบ่งปันข้อเสนอแนะ  

## สรุป
ตอนนี้คุณรู้วิธี **export MPP to SVG** ใน Java และ **save project as SVG** อย่างมีประสิทธิภาพด้วย Aspose.Tasks ความสามารถนี้ทำให้คุณสามารถรวมการแสดงผลโครงการที่สมบูรณ์แบบเข้าไปในพอร์ทัลเว็บ, แดชบอร์ดการรายงาน, หรือที่ใดก็ได้ที่ต้องการกราฟิกที่ขยายได้ ทดลองใช้ `SvgOptions` เพื่อปรับแต่งผลลัพธ์อย่างละเอียด และคุณจะมีเครื่องมือที่ทรงพลังในชุดพัฒนาของคุณ  

**อัปเดตล่าสุด:** 2026-03-27  
**ทดสอบกับ:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}