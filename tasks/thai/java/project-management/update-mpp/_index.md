---
date: 2025-12-28
description: เรียนรู้วิธีเพิ่มงานและอัปเดตไฟล์ MPP ด้วย Aspose.Tasks for Java ซึ่งเป็นไลบรารีการจัดการโครงการสำหรับ
  Java ทำตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อสร้างงานในไฟล์ MPP และบันทึกโครงการเป็นไฟล์
  MPP.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีเพิ่มงานและอัปเดตไฟล์ MPP ใน Aspose.Tasks
url: /th/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มงานและอัปเดตไฟล์ MPP ใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้ เราจะแสดงให้คุณเห็น **how to add task** และอัปเดตไฟล์ MPP ด้วย Aspose.Tasks for Java ซึ่งเป็น **java project management library** ชั้นนำ ไม่ว่าคุณจะกำลังสร้างตัวจัดตารางแบบกำหนดเองหรือจำเป็นต้องแก้ไขแผนโครงการที่มีอยู่โดยโปรแกรมมิ่ง คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การโหลดไฟล์จนถึงการบันทึกการเปลี่ยนแปลงเป็นเอกสาร MPP ใหม่.

## คำตอบสั้น
- **What does “how to add task” mean in this context?** หมายถึงการสร้างงานใหม่ภายในไฟล์ Microsoft Project (MPP) ที่มีอยู่โดยโปรแกรม  
- **Which library handles the operation?** Aspose.Tasks for Java, a robust java project management library.  
- **Do I need a license?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Can I save the result as MPP?** ใช่—ใช้ `project.save(..., SaveFileFormat.Mpp)` เพื่อ **save project as mpp**.  
- **What Java version is required?** Java 8 หรือใหม่กว่า.

## “how to add task” ในไฟล์ MPP คืออะไร?
การเพิ่มงานหมายถึงการแทรกรายการทำงานใหม่เข้าไปในโครงสร้างของโครงการ, กำหนดวันที่เริ่มต้น/สิ้นสุด, และบันทึกการเปลี่ยนแปลงกลับไปยังไฟล์ MPP. Aspose.Tasks แยกรายละเอียดระดับต่ำของรูปแบบไฟล์ออก, ทำให้คุณสามารถมุ่งเน้นที่ตรรกะธุรกิจได้.

## ทำไมต้องใช้ Aspose.Tasks for Java?
- **Full compatibility** กับไฟล์ Microsoft Project 2007‑2021  
- **No COM or Office installation** required—pure Java API.  
- **Rich feature set**: การเชื่อมโยงงาน, การจัดสรรทรัพยากร, ฟิลด์กำหนดเอง, และอื่น ๆ  
- **High performance** สำหรับไฟล์โครงการขนาดใหญ่, ทำให้เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์

## ข้อกำหนดเบื้องต้น
1. **Java Development Environment** – JDK 8+ ที่ติดตั้งและกำหนดค่าแล้ว.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดจาก [download page](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – ความคุ้นเคยกับคลาส, ออบเจ็กต์, และการจัดการวันที่.

## นำเข้าแพ็กเกจ
ก่อนอื่น, นำเข้าคลาสที่คุณต้องการ. สิ่งนี้จะให้คุณเข้าถึงการจัดการโครงการ, คุณสมบัติงาน, และการจัดการวันที่.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
แทนที่ `"Your Data Directory"` ด้วยเส้นทางเต็มที่ไฟล์ MPP ต้นฉบับของคุณอยู่.

## ขั้นตอนที่ 2: อ่านโครงการที่มีอยู่
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
คอนสตรัคเตอร์ `Project` โหลด **SampleMSP2010.mpp**, ให้คุณได้โมเดลอ็อบเจ็กต์ที่สามารถจัดการได้.

## ขั้นตอนที่ 3: สร้างงานใหม่ (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
บรรทัดนี้ **creates task in mpp** โดยเพิ่มงานลูกชื่อ *Task1* ไปยังงานราก.

## ขั้นตอนที่ 4: ตั้งค่าวันเริ่มต้นและสิ้นสุด
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
ที่นี่เรากำหนดกำหนดการสำหรับงานที่เพิ่มใหม่. ปรับวันที่ให้ตรงกับไทม์ไลน์ของโครงการของคุณ.

## ขั้นตอนที่ 5: บันทึกโครงการ (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
โครงการที่อัปเดตแล้ว, ตอนนี้มีงานใหม่, จะถูกบันทึกเป็น **AfterLinking.mpp**.

## ปัญหาทั่วไปและวิธีแก้
| Issue | Solution |
|-------|----------|
| **File not found** | ตรวจสอบว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`/` หรือ `\\`) และชื่อไฟล์ถูกต้อง. |
| **Incorrect dates** | จำว่าเดือนใน `Calendar` เริ่มจากศูนย์; `Calendar.JULY` คือเดือนกรกฎาคมที่ถูกต้อง. |
| **License exception** | ติดตั้งใบอนุญาต Aspose.Tasks ที่ถูกต้องก่อนเรียกใช้ API ใด ๆ เพื่อหลีกเลี่ยงลายน้ำการประเมิน. |

## คำถามที่พบบ่อย
### Q: Aspose.Tasks for Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?
A: ใช่, Aspose.Tasks for Java มีฟีเจอร์ที่แข็งแกร่งเพื่อจัดการโครงสร้างโครงการที่ซับซ้อนได้อย่างมีประสิทธิภาพ.  
### Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks for Java หรือไม่?
A: มี, คุณสามารถดาวน์โหลดการทดลองใช้ฟรีจาก [website](https://releases.aspose.com/).  
### Q: Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของไฟล์ Microsoft Project หรือไม่?
A: แน่นอน, Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของไฟล์ Microsoft Project รวมถึงรูปแบบ MPP, MPT, และ XML.  
### Q: ฉันสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks for Java ได้หรือไม่?
A: มี, ใบอนุญาตชั่วคราวพร้อมให้ใช้เพื่อการทดสอบ. คุณสามารถรับได้จาก [temporary license page](https://purchase.aspose.com/temporary-license/).  
### Q: ฉันสามารถขอความช่วยเหลือหรือสนับสนุนเกี่ยวกับ Aspose.Tasks for Java ได้จากที่ไหน?
A: คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือหรือสอบถามได้.

## คำถามที่พบบ่อย
**Q: ฉันจะเพิ่มหลายงานพร้อมกันได้อย่างไร?**  
A: วนลูปผ่านคอลเลกชันของชื่องานและทำซ้ำบล็อก “create task” ภายในลูป.

**Q: ฉันสามารถตั้งค่าฟิลด์กำหนดเองสำหรับงานใหม่ได้หรือไม่?**  
A: ใช่—ใช้ `task.set(Tsk.CUSTOM_FIELD_x, value)` โดยที่ *x* คือดัชนีของฟิลด์.

**Q: สามารถคัดลอกงานที่มีอยู่เป็นเทมเพลตได้หรือไม่?**  
A: ทำการโคลนงานต้นฉบับ (`Task cloned = sourceTask.clone();`) แล้วเพิ่มไปยังพาเรนต์ที่ต้องการ.

**Q: ถ้าฉันต้องการอัปเดตงานที่มีอยู่แทนการเพิ่มงานใหม่จะทำอย่างไร?**  
A: ดึงงานโดย ID (`Task existing = project.getRootTask().getChildren().getById(id);`) แล้วแก้ไขคุณสมบัติของมัน.

**Q: Aspose.Tasks รองรับการบันทึกเป็นรูปแบบอื่นเช่น PDF หรือ PNG หรือไม่?**  
A: ใช่—ใช้ `project.save("output.pdf", SaveFileFormat.Pdf);` หรือ `SaveFileFormat.Png` สำหรับการแสดงผลภาพ.

---

**อัปเดตล่าสุด:** 2025-12-28  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}