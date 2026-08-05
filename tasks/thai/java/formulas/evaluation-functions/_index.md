---
date: 2026-02-13
description: เรียนรู้วิธีสร้างรายงานโครงการโดยการสร้างอ็อบเจ็กต์โครงการใน Java, เพิ่มแอตทริบิวต์ที่ขยาย,
  และใช้ฟังก์ชันการประเมินร่วมกับ Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: สร้างรายงานโครงการ – สร้างอ็อบเจ็กต์โครงการ Java
url: /th/java/formulas/evaluation-functions/
weight: 10
---

.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สนับสนุนฟังก์ชันการประเมินค่าในสูตร Aspose.Tasks

## บทนำ
Aspose.Tasks for Java ให้คุณ **generate project report** โดยการสร้าง **project object** ใน Java และประเมินฟังก์ชันของ Microsoft Project โดยตรงในโค้ดของคุณ การฝังสูตรเหล่านี้ทำให้คุณสามารถทำการคำนวณที่ซับซ้อน, สร้างรายงานแบบกำหนดเอง, และอัตโนมัติการวิเคราะห์โครงการโดยไม่ต้องออกจากสภาพแวดล้อมการพัฒนา ในบทเรียนนี้เราจะอธิบายขั้นตอนการสร้าง project object, การเพิ่ม extended attribute, และการใช้ฟังก์ชันการประเมินค่าเพื่อ **add custom field task** data.

## คำตอบด่วน
- **What does “create project object java” mean?** It creates an in‑memory `Project` instance that you can manipulate programmatically.  
- **Which library is required?** Aspose.Tasks for Java (download from the official site).  
- **Do I need a license?** A temporary or full Aspose.Tasks license is required for production use; a free trial is available.  
- **Can I use custom fields?** Yes – you can **add extended attribute** to tasks and treat them as custom fields.  
- **Is this compatible with all Project file formats?** Aspose.Tasks supports MPP, MPT, and XML formats.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มต้น, โปรดตรวจสอบว่าคุณมี:

1. **Java Development Environment** – JDK 8+ และ IDE เช่น IntelliJ IDEA หรือ Eclipse.  
2. **Aspose.Tasks for Java Library** – ดาวน์โหลดและรวมไลบรารีจาก [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## นำเข้าแพ็กเกจ
เพิ่ม namespace ของ Aspose.Tasks ไปยังคลาส Java ของคุณเพื่อให้สามารถทำงานกับโครงการ, งาน, และ extended attributes:

```java
import com.aspose.tasks.*;
```

## สร้างรายงานโครงการ – Create Project Object Java
สร้างอ็อบเจ็กต์ `Project` ใหม่ ซึ่งจะทำหน้าที่เป็นคอนเทนเนอร์สำหรับงานทั้งหมด, ทรัพยากร, และข้อมูลกำหนดเองที่คุณจะกำหนด

```java
Project project = new Project();
```

บรรทัดด้านบน **creates project object java** ที่เริ่มต้นเป็นค่าว่างและพร้อมสำหรับการปรับแต่ง

## วิธีเพิ่ม Extended Attribute
กำหนด extended attribute ที่จะเก็บข้อมูลตัวเลขกำหนดเอง (เช่น ค่า sine) สำหรับแต่ละงาน

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

ที่นี่เรา **add extended attribute** ชนิด `Number` ชื่อ “Sine” และเชื่อมโยงกับงานต่าง ๆ

## เพิ่ม Extended Attribute ไปยัง Project
ลงทะเบียนการกำหนด attribute กับโปรเจกต์เพื่อให้ทุกงานสามารถอ้างอิงได้

```java
project.getExtendedAttributes().add(attr);
```

## สร้างงานใหม่
เพิ่มงานง่าย ๆ ชื่อ “Task” ใต้ root task ของโปรเจกต์

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## เชื่อมโยง Extended Attribute กับงาน
เชื่อมโยง extended attribute ที่กำหนดไว้ก่อนหน้านี้กับงานที่สร้างใหม่

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

ตอนนี้งานมีฟิลด์ “Sine” กำหนดเองที่คุณสามารถใช้ในสูตรหรือการคำนวณได้ นี่เป็นวิธีที่คุณ **add custom field task** data อย่างโปรแกรมเมติก

## ทำไมต้องใช้ฟังก์ชันการประเมินค่า?
การฝังฟังก์ชัน MS Project ในสูตร Aspose.Tasks ทำให้คุณสามารถ:

- ทำการคำนวณแบบ on‑the‑fly (เช่น `Sin([Start])`) โดยไม่ต้องใช้เครื่องมือภายนอก.  
- เก็บตรรกะของโครงการทั้งหมดไว้ในโค้ดเบสเดียวที่ดูแลรักษาได้.  
- สร้างรายงานแบบไดนามิกที่สะท้อนการเปลี่ยนแปลงของข้อมูลแบบเรียลไทม์ ช่วยให้คุณ **generate project report** โดยอัตโนมัติ

## ปัญหาทั่วไปและวิธีแก้
| Issue | Solution |
|-------|----------|
| **Formula returns `NaN`** | ตรวจสอบว่าประเภทฟิลด์กำหนดเองตรงกับประเภทตัวเลขที่คาดหวัง. |
| **Extended attribute not visible** | ตรวจสอบว่าการกำหนด attribute ถูกเพิ่มไปยังโปรเจกต์ **before** การสร้างงาน. |
| **License exception** | ติดตั้งใบอนุญาต temporary หรือ full **Aspose.Tasks license**; โหมดทดลองอาจจำกัดฟีเจอร์บางอย่าง. |
| **Missing temporary license** | รับ **temporary Aspose license** จากเว็บไซต์ Aspose. |

## คำถามที่พบบ่อย

**Q: Can Aspose.Tasks for Java handle complex MS Project formulas?**  
A: ใช่, Aspose.Tasks for Java รองรับการประเมินฟังก์ชัน MS Project ชนิดต่าง ๆ ทำให้สามารถทำการคำนวณซับซ้อนได้ภายในแอปพลิเคชัน Java

**Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project files?**  
A: ใช่, Aspose.Tasks for Java รองรับหลายเวอร์ชันของไฟล์ Microsoft Project รวมถึงรูปแบบ MPP, MPT, และ XML

**Q: Can I try Aspose.Tasks for Java before purchasing?**  
A: ใช่, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีของ Aspose.Tasks for Java จากเว็บไซต์ [here](https://purchase.aspose.com/buy)

**Q: How can I get support for Aspose.Tasks for Java?**  
A: คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน Aspose.Tasks ที่ [here](https://forum.aspose.com/c/tasks/15)

**Q: Is there a temporary license available for Aspose.Tasks for Java?**  
A: ใช่, คุณสามารถขอรับ temporary license สำหรับการทดสอบจากเว็บไซต์ Aspose ที่ [here](https://purchase.aspose.com/temporary-license/)

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณได้เรียนรู้วิธี **create project object**, **add extended attribute**, และใช้ฟังก์ชันการประเมินค่าเพื่อ **generate project report** อย่างอัตโนมัติ ตอนนี้คุณสามารถต่อยอดพื้นฐานนี้เพื่อสร้างการวิเคราะห์โครงการที่ลึกซึ้งขึ้น, แดชบอร์ดกำหนดเอง, หรือเครื่องมือจัดตารางอัตโนมัติ—all powered by Aspose.Tasks for Java.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}