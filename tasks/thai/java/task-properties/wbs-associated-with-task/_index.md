---
date: 2026-03-03
description: เรียนรู้วิธีการเปลี่ยนหมายเลข WBS ใน Aspose.Tasks สำหรับ Java จัดการการแบ่งงานและปรับแต่งโค้ด
  WBS อย่างมีประสิทธิภาพด้วยตัวอย่างขั้นตอนต่อขั้นตอน
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีเปลี่ยนหมายเลข WBS ใน Aspose.Tasks สำหรับ Java
url: /th/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการทำใหม่หมายเลข WBS ใน Aspose.Tasks สำหรับ Java

## บทนำ
หากคุณต้องการ **วิธีทำใหม่หมายเลข WBS** ในไฟล์ Microsoft Project ด้วย Aspose.Tasks สำหรับ Java คุณมาถูกที่แล้ว บทแนะนำนี้จะพาคุณผ่านการอ่านโค้ด WBS ที่มีอยู่ การปรับแต่ง และการทำใหม่หมายเลขของโครงสร้างลำดับชั้น เพื่อให้โครงการของคุณเป็นระเบียบ ไม่ว่าคุณจะทำความสะอาดตารางงานเก่าหรือสร้างใหม่ตั้งแต่ต้น การเข้าใจขั้นตอนเหล่านี้จะช่วยให้คุณ **จัดการโครงสร้างการแบ่งงาน** (work breakdown structures) ได้อย่างมั่นใจ

## คำตอบสั้น
- **การทำใหม่หมายเลข WBS ทำอะไร?** จะคำนวณหมายเลขลำดับชั้นของงานใหม่เพื่อสะท้อนการเปลี่ยนแปลงโครงสร้าง  
- **คลาสใดทำการทำใหม่หมายเลข?** `Project.renumberWBSCode`  
- **ต้องมีไลเซนส์เพื่อรันโค้ดหรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถปรับแต่งรูปแบบ WBS ได้หรือไม่?** ได้ — ใช้ `Task.set(Tsk.WBS, "...")` เพื่อกำหนดสตริงใดก็ได้ที่คุณต้องการ  
- **ข้อกำหนดเบื้องต้นคืออะไร?** Java JDK, ไลบรารี Aspose.Tasks สำหรับ Java, และไฟล์โครงการที่เป็น .mpp ที่ถูกต้อง

## Work Breakdown Structure (WBS) คืออะไร?
Work Breakdown Structure (WBS) คือการแสดงผลแบบลำดับชั้นของผลลัพธ์และงานในโครงการ แต่ละงานจะได้รับโค้ด (เช่น 1.2.3) ที่บ่งบอกตำแหน่งของมันในลำดับชั้น การทำใหม่หมายเลขจึงสำคัญเมื่อมีการเพิ่ม, ลบ, หรือจัดเรียงงานใหม่ เพื่อให้โค้ดยังคงมีความหมายและอ่านง่าย

## ทำไมต้องจัดการการแบ่งงานและปรับแต่งโค้ด WBS?
- **ความชัดเจน:** โค้ด WBS ที่ชัดเจนทำให้ผู้มีส่วนได้ส่วนเสียค้นหางานได้ง่าย  
- **การรายงาน:** เครื่องมือรายงานหลายตัวพึ่งพาการหมายเลขที่สอดคล้องกัน  
- **ความยืดหยุ่น:** โค้ดที่กำหนดเองช่วยให้คุณสอดคล้องโครงสร้างโครงการกับมาตรฐานภายใน  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงมือเขียนโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้แล้ว:

- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Tasks สำหรับ Java ถูกเพิ่มเข้าในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/tasks/java/)  

## นำเข้าแพ็กเกจ
ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าแพ็กเกจที่จำเป็นเพื่อเริ่มต้นโครงการของคุณ:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## อ่านโค้ด WBS
ก่อนอื่น เราจะอ่านโค้ด WBS ที่มีอยู่เพื่อให้คุณเห็นว่ากำลังทำงานกับอะไร

### ขั้นตอนที่ 1: โหลดโครงการ
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### ขั้นตอนที่ 2: เก็บรวบรวมงาน
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### ขั้นตอนที่ 3: แยกวิเคราะห์และปรับแต่ง
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

ส่วนโค้ดข้างต้นจะแสดง WBS ปัจจุบันและระดับของแต่ละงาน แล้วสาธิตการ **ปรับแต่งโค้ด WBS** โดยการกำหนดสตริงใหม่

## ทำใหม่หมายเลข WBS ของงาน
ต่อไปเราจะทำใหม่หมายเลขลำดับชั้นของ WBS จริง ๆ

### ขั้นตอนที่ 1: โหลดโครงการ (ตัวอย่างการทำใหม่หมายเลข)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### ขั้นตอนที่ 2: เลือกงานทั้งหมด
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### ขั้นตอนที่ 3: แสดงโค้ด WBS เริ่มต้น
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### ขั้นตอนที่ 4: ทำใหม่หมายเลข WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### ขั้นตอนที่ 5: แสดงโค้ด WBS ที่อัปเดต
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

โดยทำตามขั้นตอนเหล่านี้ คุณจะสามารถ **วิธีทำใหม่หมายเลข wbs** สำหรับชุดงานใด ๆ ในไฟล์โครงการของคุณได้อย่างมีประสิทธิภาพ

## ปัญหาที่พบบ่อยและวิธีแก้
- **WBS ไม่เปลี่ยนหลังจากเรียก `set`**: ตรวจสอบว่าคุณกำลังทำงานกับอินสแตนซ์งานที่ถูกต้องและว่าโครงการถูกบันทึกหลังจากแก้ไข  
- **`renumberWBSCode` ขว้างข้อยกเว้น**: ตรวจสอบว่ารายการ ID มีจำนวนเท่ากับจำนวนงานระดับบนสุด; หากไม่ตรงเมธอดจะไม่สามารถแมปหมายเลขใหม่ได้  
- **ค่า WBS ขาดหาย**: งานบางงานอาจมีค่า `null` หากถูกนำเข้าจากไฟล์ที่ไม่ได้กำหนดค่า ใช้ค่าตั้งสำรองก่อนพิมพ์ออก  

## คำถามที่พบบ่อย

**ถาม: จะหาเอกสารของ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
ตอบ: เอกสารพร้อมให้บริการ [ที่นี่](https://reference.aspose.com/tasks/java/)  

**ถาม: จะดาวน์โหลด Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
ตอบ: คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/tasks/java/)  

**ถาม: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks สำหรับ Java หรือไม่?**  
ตอบ: มี คุณสามารถรับการทดลองใช้ฟรีได้ [ที่นี่](https://releases.aspose.com/)  

**ถาม: จะหาการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
ตอบ: เยี่ยมชม [ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุน  

**ถาม: สามารถขอไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่?**  
ตอบ: ได้ รับไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

**ถาม: หลังจากทำใหม่หมายเลขแล้วสามารถเปลี่ยนรูปแบบ WBS ได้หรือไม่?**  
ตอบ: แน่นอน หลังจากเรียก `renumberWBSCode` คุณสามารถวนลูปงานและใช้ `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` เพื่อให้สอดคล้องกับรูปแบบการตั้งชื่อของคุณ  

**ถาม: การทำใหม่หมายเลขมีผลต่อการขึ้นต่อกันของงานหรือไม่?**  
ตอบ: ไม่ เมธอดจะอัปเดตเฉพาะสตริง WBS; ลิงก์และข้อจำกัดของงานจะคงเดิม  

---

**อัปเดตล่าสุด:** 2026-03-03  
**ทดสอบกับ:** Aspose.Tasks สำหรับ Java 24.12 (ล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}