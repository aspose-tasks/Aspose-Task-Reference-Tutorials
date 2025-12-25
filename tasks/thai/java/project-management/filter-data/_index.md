---
date: 2025-12-25
description: เรียนรู้วิธีกรองไฟล์ MPP ด้วย Aspose.Tasks for Java และปรับแต่งเกณฑ์การกรองเพื่อทำให้กระบวนการจัดการโครงการของคุณเป็นระเบียบและมีประสิทธิภาพมากขึ้น.
linktitle: How to Filter MPP Files Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: วิธีกรองไฟล์ MPP ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีกรองไฟล์ MPP ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
หากคุณทำงานกับไฟล์ Microsoft Project (.mpp) ในแอปพลิเคชัน Java คุณมักต้อง **กรอง** งาน, ทรัพยากร หรือการมอบหมายเพื่อโฟกัสที่ข้อมูลที่สำคัญจริง ๆ ในบทแนะนำนี้เราจะอธิบาย **วิธีกรองไฟล์ mpp** อย่างโปรแกรมเมติกด้วย Aspose.Tasks สำหรับ Java และแสดงวิธี **ปรับแต่งเงื่อนไขการกรอง** ให้ตรงกับความต้องการการรายงานของโครงการของคุณ เมื่ออ่านจบคุณจะได้ตัวอย่างขั้นตอน‑โดย‑ขั้นตอนที่สามารถนำไปใช้ในโค้ดของคุณได้ทันที

## คำตอบสั้น
- **“filter mpp” หมายถึงอะไร?** คือการดึงส่วนย่อยของข้อมูลโครงการตามเงื่อนไขที่กำหนด  
- **ไลบรารีที่ทำหน้าที่นี้คืออะไร?** Aspose.Tasks สำหรับ Java มี API ที่ครบครันสำหรับสร้างและใช้ฟิลเตอร์  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถกรองงาน, ทรัพยากร, และการมอบหมายได้หรือไม่?** ได้ – แต่ละประเภทมีคอลเลกชันฟิลเตอร์ของตนเอง  
- **ต้องใช้ Java 8 หรือสูงกว่าใช่หรือไม่?** Aspose.Tasks รองรับ Java 8 ขึ้นไป

## “how to filter mpp” ใน Java คืออะไร?
การกรองไฟล์ MPP หมายถึงการใช้ Aspose.Tasks API เพื่อกำหนดเงื่อนไข (เช่น วันที่เริ่มของงาน, ค่าใช้จ่าย, หรือฟิลด์กำหนดเอง) แล้วดึงเฉพาะรายการที่ตรงตามกฎเหล่านั้น วิธีนี้ช่วยให้คุณสร้างรายงานที่เน้นจุดสำคัญ, ทำการตรวจสอบสถานะอัตโนมัติ, หรือรวมข้อมูลโครงการกับระบบอื่น ๆ

## ทำไมต้องปรับแต่งเงื่อนไขการกรอง?
แต่ละโครงการมีลำดับความสำคัญของตนเอง การ **ปรับแต่งเงื่อนไขการกรอง** ทำให้คุณสามารถแยกงานที่มีความเสี่ยงสูง, รายการที่ล่าช้า, หรือทรัพยากรที่เกินงบประมาณได้ ทำให้แดชบอร์ดโครงการของคุณมีความกระชับและโค้ดของคุณนำกลับใช้ใหม่ได้ง่ายขึ้น

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า  
2. **Aspose.Tasks สำหรับ Java** – ดาวน์โหลดจาก [download page](https://releases.aspose.com/tasks/java/)  
3. **IDE** – IntelliJ IDEA, Eclipse หรือ NetBeans ก็ใช้ได้ดี  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณ:

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์
สร้างอินสแตนซ์ `Project` ที่ชี้ไปยังไฟล์ MPP ที่ต้องการทำงาน

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

### ขั้นตอนที่ 2: ดึงฟิลเตอร์
Aspose.Tasks มีฟิลเตอร์ที่กำหนดไว้ล่วงหน้า (เช่น “All Tasks”, “Critical Tasks”) ดึงฟิลเตอร์ที่ต้องการโดยใช้ดัชนีหรือชื่อ

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

> **เคล็ดลับ:** ใช้ `project.getTaskFilters().getByName("My Custom Filter")` หากคุณต้องการดึงฟิลเตอร์ตามชื่อ

### ขั้นตอนที่ 3: เข้าถึงเงื่อนไขฟิลเตอร์
เมื่อคุณมีอ็อบเจกต์ `Filter` แล้ว คุณสามารถตรวจสอบแถวเงื่อนไขและการดำเนินการเชิงตรรกะ (AND/OR) ที่ใช้รวมกันได้

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

### ขั้นตอนที่ 4: ดึงรายละเอียดเงื่อนไข
แต่ละแถวเงื่อนไขจะมีการทดสอบ (เช่น “Equals”, “GreaterThan”) และฟิลด์ที่ใช้ทดสอบ (เช่น “Start”, “Cost”)

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

### ขั้นตอนที่ 5: วนลูปผ่านแถวเงื่อนไข
ฟิลเตอร์ที่ซับซ้อนอาจมีเงื่อนไขซ้อนกัน ที่นี่เราจะเดินผ่านกลุ่มเงื่อนไขระดับที่สอง

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

### ขั้นตอนที่ 6: พิมพ์ข้อมูลเงื่อนไข
สุดท้ายให้แสดงรายละเอียดของแต่ละเงื่อนไขย่อยเพื่อให้คุณตรวจสอบตรรกะของฟิลเตอร์ได้

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **NullPointerException เมื่อเข้าถึงฟิลเตอร์** | ตรวจสอบว่าไฟล์โครงการมีฟิลเตอร์ของงานอยู่จริง; หากไม่มีคุณสามารถเพิ่มฟิลเตอร์โดยโปรแกรมได้ |
| **ชื่อฟิลด์ไม่ถูกต้อง** | ใช้ enum `ItemType` (เช่น `ItemType.Task`) เพื่อหลีกเลี่ยงการพิมพ์ผิด |
| **ฟิลเตอร์ไม่คืนผลลัพธ์** | ตรวจสอบตัวดำเนินการทดสอบและค่าที่กำหนดให้ตรงกับข้อมูลในไฟล์ MPP ของคุณ |

## คำถามที่พบบ่อย
### Q: Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project เวอร์ชันต่าง ๆ หรือไม่?
A: ใช่, Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project หลายเวอร์ชัน, ทำให้คุณสามารถทำงานได้อย่างยืดหยุ่นในงานจัดการโครงการ

### Q: สามารถปรับแต่งเงื่อนไขฟิลเตอร์ตามความต้องการเฉพาะของโครงการได้หรือไม่?
A: แน่นอน! Aspose.Tasks สำหรับ Java ให้คุณกำหนดเงื่อนไขฟิลเตอร์ให้ตรงกับความต้องการเฉพาะของโครงการ, ทำให้การจัดการข้อมูลเป็นไปอย่างมีเป้าหมาย

### Q: Aspose.Tasks สำหรับ Java เหมาะกับโครงการขนาดเล็กและขนาดใหญ่หรือไม่?
A: ใช่, ไม่ว่าคุณจะจัดการโครงการขนาดเล็กหรือพอร์ตโฟลิโอโครงการขนาดใหญ่, Aspose.Tasks สำหรับ Java มีความสามารถในการขยายและประสิทธิภาพที่จำเป็นสำหรับทุกสถานการณ์

### Q: Aspose.Tasks สำหรับ Java มีเอกสารและแหล่งสนับสนุนครบถ้วนหรือไม่?
A: มีแน่นอน! คุณสามารถอ้างอิง [documentation](https://reference.aspose.com/tasks/java/) เพื่อดูคู่มือและ API อย่างละเอียด นอกจากนี้ยังมีฟอรัมชุมชน Aspose.Tasks สำหรับสอบถามหรือแก้ไขปัญหาใด ๆ

### Q: สามารถทดลองใช้ Aspose.Tasks สำหรับ Java ก่อนตัดสินใจซื้อได้หรือไม่?
A: ได้เลย! คุณสามารถดาวน์โหลดรุ่นทดลองฟรีจาก [website](https://releases.aspose.com/) เพื่อสัมผัสคุณสมบัติและความสามารถของ Aspose.Tasks สำหรับ Java ด้วยตนเอง

## คำถามที่พบบ่อยเพิ่มเติม

**Q: จะสร้างฟิลเตอร์ใหม่จากศูนย์โดยโปรแกรมได้อย่างไร?**  
A: ใช้ `project.getTaskFilters().add(new Filter("My Filter"))` แล้วกำหนดคอลเลกชัน `FilterCriteria` ของมัน

**Q: สามารถใช้ฟิลเตอร์กับทรัพยากรแทนงานได้หรือไม่?**  
A: ใช่ – ใช้ `project.getResourceFilters()` เพื่อทำงานกับฟิลเตอร์ของทรัพยากร

**Q: สามารถรวมหลายฟิลเตอร์ด้วยตรรกะ OR ได้หรือไม่?**  
A: คุณสามารถสร้าง `FilterCriteria` พาเรนต์ที่มี `Operation` ตั้งเป็น `OR` แล้วเพิ่มเงื่อนไขย่อยเป็นลูกได้

**Q: Aspose.Tasks รองรับการกรองบนฟิลด์กำหนดเองหรือไม่?**  
A: รองรับอย่างเต็มที่ ฟิลด์กำหนดเองถือเป็นฟิลด์ทั่วไป; ให้อ้างอิงด้วยค่า enum `CustomField` ของมัน

**Q: การกรองมีผลต่อประสิทธิภาพเมื่อทำงานกับไฟล์ MPP ขนาดใหญ่หรือไม่?**  
A: การกรองทำงานในหน่วยความจำและโดยทั่วไปเร็ว, แต่สำหรับโครงการขนาดใหญ่มากอาจพิจารณาโหลดเฉพาะส่วนที่ต้องการโดยใช้ `ProjectReader`

---

**อัปเดตล่าสุด:** 2025-12-25  
**ทดสอบกับ:** Aspose.Tasks สำหรับ Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}