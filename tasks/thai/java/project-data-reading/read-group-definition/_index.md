---
date: 2026-02-18
description: เรียนรู้วิธีอ่านข้อมูลการกำหนดกลุ่มจากไฟล์ Microsoft Project ด้วย Aspose.Tasks
  สำหรับ Java บทแนะนำนี้แสดงวิธีอ่านรายละเอียดของกลุ่มและสกัดข้อมูลการจัดกลุ่มงานออกมา
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีอ่านข้อมูลการกำหนดกลุ่มใน Aspose.Tasks
url: /th/java/project-data-reading/read-group-definition/
weight: 10
---

 2026-02-18. Should translate "Last Updated" part.

Similarly "Tested With" -> "ทดสอบด้วย". "Author" -> "ผู้เขียน". Keep bold.

Also translate "Read Group Definition Data in Aspose.Tasks" heading.

Proceed.

Let's craft translation.

Be careful with bullet lists, keep markdown.

Also translate "Quick Answers" heading etc.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านข้อมูลการกำหนดกลุ่มใน Aspose.Tasks

## Introduction
Aspose.Tasks for Java เป็นไลบรารีที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project ได้อย่างง่ายดาย ในบทแนะนำนี้ **คุณจะได้เรียนรู้วิธีอ่านข้อมูลการกำหนดกลุ่ม** จากไฟล์โครงการขั้นตอนต่อขั้นตอน เพื่อให้คุณสามารถสกัดและทำงานกับข้อมูลกลุ่มงานในแอปพลิเคชัน Java ของคุณได้ การเข้าใจ **วิธีอ่านรายละเอียดของกลุ่ม** จะทำให้คุณสามารถอัตโนมัติการรายงาน, ย้ายการตั้งค่า, และตรวจสอบโครงสร้างโครงการโดยโปรแกรมได้

## Quick Answers
- **“read group definition” หมายถึงอะไร?** หมายถึงการสกัดการกำหนดของกลุ่มงาน (ชื่อ, เกณฑ์, การจัดรูปแบบ) จากไฟล์ Microsoft Project  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks for Java  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **IDE ที่รองรับคืออะไร?** IDE ของ Java ใด ๆ เช่น IntelliJ IDEA หรือ Eclipse  
- **ต้องเขียนโค้ดกี่บรรทัด?** น้อยกว่า 30 บรรทัดของ Java เพื่อโหลดโครงการและแสดงรายละเอียดกลุ่ม

## How to Read Group Definition Data
ด้านล่างเป็นขั้นตอนสั้น ๆ ที่แสดง **วิธีอ่านข้อมูลกลุ่ม** จากไฟล์ `.mpp` แต่ละขั้นตอนจะมีคำอธิบายสั้น ๆ ตามด้วยโค้ดที่ต้องใช้จริง

## What is read group definition?
*group definition* ใน Microsoft Project อธิบายว่าหน้าที่จะถูกจัดกลุ่มอย่างไรตามเกณฑ์ (เช่น สถานะ, ความสำคัญ) การอ่านการกำหนดนี้ทำให้คุณสามารถตรวจสอบตรรกะการจัดกลุ่ม, สี, ฟอนต์, และลำดับการเรียงที่ใช้ในไฟล์โครงการได้โดยโปรแกรม

## Why read group definition data?
- **Automation:** สร้างรายงานแบบกำหนดเองที่สะท้อนการจัดกลุ่มใน Project  
- **Migration:** ย้ายกฎการจัดกลุ่มไปยังโครงการอื่นหรือระบบจัดการโครงการอื่น  
- **Validation:** ตรวจสอบว่ากลุ่มที่คาดหวังมีอยู่ก่อนทำการอัปเดตเป็นจำนวนมาก  
- **Customization:** ใช้ตรรกะธุรกิจเพิ่มเติมตามฟอนต์หรือการตั้งค่าสีของกลุ่ม  
- **Insight:** การรู้ **วิธีอ่านข้อมูลกลุ่ม** ช่วยให้คุณแก้ไขปัญหาเลย์เอาต์ของงานที่ไม่คาดคิดได้

## Prerequisites
ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Java Development Kit (JDK)** – เวอร์ชันล่าสุด (8 หรือใหม่กว่า)  
2. **Aspose.Tasks for Java Library** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/)  
3. **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขอื่นที่คุณชอบ  

## Import Packages
เริ่มต้นด้วยการนำเข้าแพ็กเกจหลักของ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Data Directory
กำหนดโฟลเดอร์ที่มีไฟล์ `.mpp` ที่คุณต้องการตรวจสอบ

```java
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยพาธเต็มที่ชี้ไปยังตำแหน่งไฟล์โครงการของคุณ

### Step 2: Load the Project File
สร้างอินสแตนซ์ `Project` โดยระบุพาธไฟล์ `.mpp` ของคุณ

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Task Groups Count
พิมพ์จำนวนกลุ่มงานทั้งหมดที่กำหนดในโครงการ

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Step 4: Retrieve Specific Task Group Information
ดึงกลุ่มงานที่ต้องการ (ดัชนี 1 ในตัวอย่างนี้) แล้วแสดงชื่อและจำนวนเกณฑ์ที่มี

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Step 5: Retrieve Group Criterion Information
แต่ละกลุ่มอาจมีหนึ่งหรือหลายเกณฑ์ โค้ดด้านล่างสกัดรายละเอียดเช่น ฟิลด์ที่ใช้จัดกลุ่ม, โหมดการจัดกลุ่ม, สีเซลล์, และแพทเทิร์น

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Step 6: Check Parent Group
บางครั้งเกณฑ์อาจเป็นส่วนหนึ่งของกลุ่มแม่ การตรวจสอบนี้ช่วยยืนยันความสัมพันธ์

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Step 7: Retrieve Criterion's Font Information
เกณฑ์ของกลุ่มสามารถกำหนดสไตล์ฟอนต์ได้ โค้ดต่อไปนี้จะแสดงฟอนต์, ขนาด, สไตล์, และทิศทางการเรียงลำดับ

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **`NullPointerException` on `criterion.getParentGroup()`** | เกณฑ์อาจไม่มีกลุ่มแม่ | เพิ่มการตรวจสอบค่า null ก่อนเปรียบเทียบ |
| **File not found** | พาธ `dataDir` ไม่ถูกต้อง | ใช้ `Paths.get(dataDir, "project.mpp").toAbsolutePath()` เพื่อตรวจสอบ |
| **License not set** | ไลบรารี Aspose ทำงานในโหมดประเมินผลและอาจจำกัดผลลัพธ์ | ลงทะเบียนลิขสิทธิ์ด้วย `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## Frequently Asked Questions

**Q: สามารถใช้ Aspose.Tasks for Java แก้ไขไฟล์โครงการได้หรือไม่?**  
A: ได้, ไลบรารีนี้ให้ความสามารถอ่าน/เขียนเต็มรูปแบบสำหรับไฟล์ Microsoft Project

**Q: Aspose.Tasks for Java รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่?**  
A: รองรับ MPP, XML และรูปแบบ Project ที่พบบ่อยในหลายเวอร์ชัน

**Q: จะจัดการข้อผิดพลาดขณะใช้ Aspose.Tasks for Java อย่างไร?**  
A: ห่อการทำงานกับไฟล์ด้วยบล็อก `try‑catch` และตรวจสอบ `TasksException` เพื่อดูข้อความรายละเอียด

**Q: Aspose.Tasks for Java มีการสนับสนุนการส่งออกข้อมูลโครงการเป็นรูปแบบอื่นหรือไม่?**  
A: แน่นอน – สามารถส่งออกเป็น PDF, XLSX, CSV และรูปแบบอื่น ๆ ผ่าน API การส่งออกของไลบรารี

**Q: จะหาแหล่งข้อมูลและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) เพื่อดูเอกสาร API อย่างเต็มรูปแบบและ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือจากชุมชน

## Conclusion
ในบทแนะนำนี้เราได้เดินผ่าน **วิธีอ่านข้อมูลการกำหนดกลุ่ม** จากไฟล์ Microsoft Project ด้วย Aspose.Tasks for Java โดยทำตามขั้นตอนข้างต้น คุณสามารถสกัดชื่อกลุ่ม, เกณฑ์, การจัดรูปแบบ, และความสัมพันธ์ของกลุ่มแม่ได้ ซึ่งช่วยให้คุณสร้างรายงานแบบกำหนดเอง, ย้ายการตั้งค่า, หรืออัตโนมัติการตรวจสอบตรรกะในแอปพลิเคชัน Java ของคุณ

---

**อัปเดตล่าสุด:** 2026-02-18  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}