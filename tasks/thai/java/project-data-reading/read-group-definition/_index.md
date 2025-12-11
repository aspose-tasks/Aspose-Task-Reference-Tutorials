---
date: 2025-12-11
description: เรียนรู้วิธีอ่านข้อมูลการกำหนดกลุ่มจากไฟล์ Microsoft Project ด้วย Aspose.Tasks
  for Java. ติดตามบทเรียนแบบขั้นตอนของเรา.
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: อ่านข้อมูลการกำหนดกลุ่มใน Aspose.Tasks
url: /th/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านข้อมูลการกำหนดกลุ่มใน Aspose.Tasks

## บทนำ
Aspose.Tasks for Java เป็นไลบรารีที่ทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project ได้อย่างง่ายดาย ในบทเรียนนี้ **คุณจะได้เรียนรู้วิธีการอ่านข้อมูลการกำหนดกลุ่ม** จากไฟล์โครงการอย่างเป็นขั้นตอน เพื่อให้คุณสามารถดึงและทำงานกับข้อมูลกลุ่มงานในแอปพลิเคชัน Java ของคุณได้

## คำตอบอย่างรวดเร็ว
- **อะไรหมายถึง “read group definition”?** หมายถึงการสกัดนิยามของกลุ่มงาน (ชื่อ, เกณฑ์, การจัดรูปแบบ) จากไฟล์ Microsoft Project  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks for Java  
- **ต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **IDE ที่รองรับมีอะไรบ้าง?** IDE ของ Java ใดก็ได้ เช่น IntelliJ IDEA หรือ Eclipse  
- **ต้องเขียนโค้ดเท่าไหร่?** น้อยกว่า 30 บรรทัดของโค้ด Java เพื่อโหลดโครงการและแสดงรายละเอียดของกลุ่ม

## การอ่านการกำหนดกลุ่มคืออะไร?
*group definition* ใน Microsoft Project อธิบายว่าหน้าที่ต่าง ๆ ถูกจัดกลุ่มเข้าด้วยกันอย่างไรโดยอิงตามเกณฑ์ (เช่น สถานะ, ความสำคัญ) การอ่านนิยามนี้ทำให้คุณสามารถตรวจสอบตรรกะการจัดกลุ่ม, สี, ฟอนต์, และลำดับการจัดเรียงที่ใช้ในไฟล์โครงการได้โดยโปรแกรม

## ทำไมต้องอ่านข้อมูลการกำหนดกลุ่ม?
- **Automation:** สร้างรายงานแบบกำหนดเองที่สะท้อนการจัดกลุ่มที่คุณเห็นใน Project  
- **Migration:** ย้ายกฎการจัดกลุ่มไปยังโครงการอื่นหรือระบบการจัดการโครงการที่แตกต่าง  
- **Validation:** ตรวจสอบให้แน่ใจว่ากลุ่มที่คาดหวังมีอยู่ก่อนทำการอัปเดตเป็นกลุ่มใหญ่  
- **Customization:** ใช้ตรรกะธุรกิจเพิ่มเติมโดยอิงจากการตั้งค่าฟอนต์หรือสีของกลุ่ม  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Java Development Kit (JDK)** – เวอร์ชันล่าสุดใดก็ได้ (8 หรือใหม่กว่า)  
2. **Aspose.Tasks for Java Library** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/)  
3. **IDE** – IntelliJ IDEA, Eclipse หรือโปรแกรมแก้ไขใด ๆ ที่คุณต้องการ  

## นำเข้าแพ็กเกจ
ก่อนอื่น, นำเข้าแพ็กเกจหลักของ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูลของคุณ
กำหนดโฟลเดอร์ที่บรรจุไฟล์ `.mpp` ที่คุณต้องการตรวจสอบ

```java
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยเส้นทางเต็มไปยังตำแหน่งไฟล์โครงการของคุณ

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
สร้างอินสแตนซ์ `Project` โดยชี้ไปยังไฟล์ `.mpp` ของคุณ

```java
Project project = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 3: ดึงจำนวนกลุ่มงาน
พิมพ์จำนวนรวมของกลุ่มงานที่กำหนดในโครงการ

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### ขั้นตอนที่ 4: ดึงข้อมูลกลุ่มงานเฉพาะ
ดึงกลุ่มเฉพาะ (ดัชนี 1 ในตัวอย่างนี้) และแสดงชื่อของมันพร้อมจำนวนเกณฑ์ที่มี

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### ขั้นตอนที่ 5: ดึงข้อมูลเกณฑ์ของกลุ่ม
แต่ละกลุ่มอาจมีหนึ่งหรือหลายเกณฑ์ โค้ดตัวอย่างด้านล่างจะสกัดรายละเอียดเช่น ฟิลด์ที่ใช้สำหรับการจัดกลุ่ม, โหมดการจัดกลุ่ม, สีของเซลล์, และรูปแบบ

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### ขั้นตอนที่ 6: ตรวจสอบกลุ่มแม่
บางครั้งเกณฑ์อาจเป็นของกลุ่มแม่ การตรวจสอบนี้ยืนยันความสัมพันธ์นั้น

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### ขั้นตอนที่ 7: ดึงข้อมูลฟอนต์ของเกณฑ์
เกณฑ์ของกลุ่มอาจมีการจัดรูปแบบฟอนต์แบบกำหนดเอง โค้ดต่อไปนี้จะแสดงฟอนต์, ขนาด, สไตล์, และทิศทางการจัดเรียง

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## ปัญหาทั่วไปและวิธีแก้ไข
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **`NullPointerException` on `criterion.getParentGroup()`** | เกณฑ์อาจไม่มีกลุ่มแม่. | เพิ่มการตรวจสอบ null ก่อนทำการเปรียบเทียบ. |
| **File not found** | เส้นทาง `dataDir` ไม่ถูกต้อง. | ใช้ `Paths.get(dataDir, "project.mpp").toAbsolutePath()` เพื่อตรวจสอบ. |
| **License not set** | ไลบรารี Aspose ทำงานในโหมดประเมินผลและอาจจำกัดผลลัพธ์. | ลงทะเบียนไลเซนส์ของคุณด้วย `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasksล์โครงการได้หรือไม่?**  
A: ได้, ไลบรารีนี้ให้ความสามารถในการอ่าน/เขียนเต็มรูปแบบสำหรับไฟล์ Microsoft Project  

**Q: Aspose.Tasks for Java รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่?**  
A: รองรับไฟล์ MPP, XML, และรูปแบบ Project ที่พบบ่อยอื่น ๆ ในหลายเวอร์ชัน  

**Q: ฉันจะจัดการข้อผิดพลาดขณะทำงานกับ Aspose.Tasks for Java อย่างไร?**  
A: ห่อการดำเนินการไฟล์ด้วยบล็อก `try‑catch` และตรวจสอบ `TasksException` เพื่อดูข้อความรายละเอียด  

**Q: Aspose.Tasks for Java มีการสนับสนุนการส่งออกข้อมูลโครงการเป็นรูปแบบอื่นหรือไม่?**  
A: แน่นอน – คุณสามารถส่งออกเป็น PDF, XLSX, CSV, และอื่น ๆ ด้วย API การส่งออกของไลบรารี  

**Q: ฉันจะหาแหล่งข้อมูลและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) เพื่อดูเอกสาร API ทั้งหมดและ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือจากชุมชน  

## สรุป
ในบทเรียนนี้ เราได้อธิบายวิธี **อ่านข้อมูลการกำหนดกลุ่ม** จากไฟล์ Microsoft Project ด้วย Aspose.Tasks for Java โดยการทำตามขั้นตอนข้างต้นคุณสามารถสกัดชื่อกลุ่ม, เกณฑ์, การจัดรูปแบบ, และความสัมพันธ์ของกลุ่มแม่ได้ ซึ่งช่วยให้คุณสร้างรายงานแบบกำหนดเอง, ย้ายการตั้งค่า, หรือทำอัตโนมัติการตรวจสอบตรรกะในแอปพลิเคชัน Java ของคุณ

---

**อัปเดตล่าสุด:** 2025-12-11  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}