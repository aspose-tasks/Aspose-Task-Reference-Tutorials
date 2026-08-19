---
date: 2026-03-03
description: เรียนรู้วิธีสร้างงานโครงการด้วย Java และจัดการบันทึกงานโดยใช้ Aspose.Tasks
  for Java ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อเพิ่มบันทึกงานอย่างมีประสิทธิภาพ
linktitle: Task Notes Management in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: สร้างงานโครงการ Java – บันทึกงานด้วย Aspose.Tasks
url: /th/java/task-properties/task-notes/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Project Task Java – บันทึกงานด้วย Aspose.Tasks

## คำแนะนำ
Aspose.Tasks for Java ให้โซลูชันที่แข็งแกร่งซึ่งช่วยให้คุณ **สร้าง project task java** objects และจัดการบันทึกที่เกี่ยวข้องได้ ในบทแนะนำนี้ เราจะเจาะลึกการจัดการบันทึกงานอย่างมีประสิทธิภาพด้วย Aspose.Tasks for Java ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือขั้นตอน‑โดย‑ขั้นตอนนี้จะพาคุณผ่านกระบวนการเพิ่มและดึงบันทึกงานได้อย่างราบรื่น

## คำตอบสั้น
- **ฉันสามารถจัดการอะไรได้บ้างด้วย Aspose.Tasks?** งานโครงการ, ทรัพยากร, ตารางเวลา, และบันทึกงาน  
- **ฉันตั้งบันทึกอย่างไร?** ใช้ฟิลด์ `Tsk.NOTES_RTF` บนวัตถุ `Task`  
- **ฟอร์แมตใดที่รองรับสำหรับบันทึก?** Rich Text Format (RTF) ได้รับการสนับสนุนเต็มรูปแบบ  
- **ฉันต้องมีลิขสิทธิ์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ต้องใช้ Java เวอร์ชันใด?** JDK 8 หรือสูงกว่า

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทแนะนำนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมแล้ว:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณ
- ดาวน์โหลดและตั้งค่าไลบรารี Aspose.Tasks for Java คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/tasks/java/)
- มีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## นำเข้าแพ็กเกจ
ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าแพ็กเกจที่จำเป็นในโครงการ Java ของคุณ:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## วิธีสร้าง Project Task Java
### ขั้นตอนที่ 1: สร้าง Project และ Task
ก่อนอื่นคุณต้องสร้างอินสแตนซ์ `Project` ใหม่และเพิ่ม task เข้าไปที่รากของมัน นี่คือขั้นตอนพื้นฐานเมื่อคุณ **สร้าง project task java** objects
```java
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task");
```

## วิธีเพิ่มบันทึกงาน
### ขั้นตอนที่ 2: ตั้งบันทึกในรูปแบบ RTF
เมื่อ task มีอยู่แล้ว คุณสามารถแนบบันทึกได้ ตัวอย่างต่อไปนี้แสดง **วิธีเพิ่มบันทึกงาน** ใน Rich Text Format
```java
String rtf = "{\\rtf1\\ansi\\ansicpg1252\\deff0\\deflang1033{\\fonttbl{\\f0\\fnil\\fcharset134 SimSun;}{\\f1\\fnil\\fcharset0 Calibri;}}\r\n"
        + "{\\*\\generator Msftedit 5.41.21.2510;}\\viewkind4\\uc1\\pard\\sa200\\sl276\\slmult1\\lang9\\f0\\fs22\\'d4\\'e7\\'c9\\'cf\\'ba\\'c3\\f1\\par\r\n"
        + "}\r\n"
        + "; // 早上好";
task.set(Tsk.NOTES_RTF, rtf);
```

### ขั้นตอนที่ 3: ดึงและแสดงบันทึก
เพื่อยืนยันว่าบันทึกถูกบันทึกอย่างถูกต้อง ให้อ่านฟิลด์ `NOTES_RTF` และพิมพ์ออกมา
```java
System.out.println("Notes RTF: " + task.get(Tsk.NOTES_RTF));
```

## ปัญหาทั่วไปและวิธีแก้
- **บันทึกแสดงผลเป็นอักขระแปลก:** ตรวจสอบให้แน่ใจว่า string RTF ถูก escape อย่างถูกต้องและใช้การเข้ารหัส Unicode ที่เหมาะสม
- **เกิด Null pointer เมื่อเข้าถึง task:** ยืนยันว่าได้เพิ่ม task เข้าไปในโครงสร้างของ project ก่อนตั้งบันทึก
- **ข้อยกเว้นลิขสิทธิ์:** ใช้ไฟล์ลิขสิทธิ์ที่ถูกต้องหรือเวอร์ชันทดลอง; มิฉะนั้น Aspose อาจโยนข้อผิดพลาดเรื่องลิขสิทธิ์

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks for Java ได้ฟรีหรือไม่?
ได้, คุณสามารถดาวน์โหลดเวอร์ชันทดลองได้ [ที่นี่](https://releases.aspose.com/)

### ฉันจะหาเอกสารรายละเอียดได้จากที่ไหน?
ดูเอกสารได้ [ที่นี่](https://reference.aspose.com/tasks/java/)

### ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks for Java ได้อย่างไร?
เยี่ยมชมฟอรั่มสนับสนุน [ที่นี่](https://forum.aspose.com/c/tasks/15)

### มีลิขสิทธิ์ชั่วคราวหรือไม่?
มี, คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

### ฉันจะซื้อ Aspose.Tasks for Java ได้จากที่ไหน?
คุณสามารถซื้อผลิตภัณฑ์ได้ [ที่นี่](https://purchase.aspose.com/buy)

#### คำถามและคำตอบเพิ่มเติม
**ถาม: ฉันสามารถเก็บบันทึกเป็นข้อความธรรมดาแทน RTF ได้หรือไม่?**  
ตอบ: ได้, คุณสามารถใช้ฟิลด์ `Tsk.NOTES` สำหรับบันทึกแบบข้อความธรรมดา, แต่ RTF จะรักษาการจัดรูปแบบไว้

**ถาม: สามารถอัปเดตบันทึกหลังจากบันทึก task แล้วได้หรือไม่?**  
ตอบ: แน่นอน. เรียก `task.set(Tsk.NOTES_RTF, newRtf)` แล้วบันทึกโปรเจกต์ต่อ

**ถาม: Aspose.Tasks รองรับบันทึกหลายภาษาไหม?**  
ตอบ: รองรับ, ตราบใดที่ string RTF ถูกเข้ารหัสอย่างถูกต้อง (UTF‑8) และมีฟอนต์ที่เหมาะสมพร้อมใช้งาน

## สรุป
การจัดการบันทึกงานใน Aspose.Tasks for Java เป็นกระบวนการที่ตรงไปตรงมาทันทีที่คุณรู้ **วิธีสร้าง project task java** objects และแนบบันทึก RTF คุณมีโค้ดสำคัญสำหรับการเพิ่ม, ดึง, และแก้ไขปัญหาบันทึกงานในแอปพลิเคชัน Java ของคุณแล้ว

---

**อัปเดตล่าสุด:** 2026-03-03  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11 (ล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}