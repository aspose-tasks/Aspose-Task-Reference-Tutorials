---
title: WBS ที่เกี่ยวข้องกับงานใน Aspose.Tasks
linktitle: WBS ที่เกี่ยวข้องกับงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เชี่ยวชาญ WBS ด้วย Aspose.Tasks สำหรับ Java - เรียนรู้การอ่านและกำหนดหมายเลขรหัส WBS ของงานใหม่ เพิ่มประสิทธิภาพการจัดการโครงการ!
type: docs
weight: 36
url: /th/java/task-properties/wbs-associated-with-task/
---
## การแนะนำ
ยินดีต้อนรับสู่โลกแห่งการจัดการโครงการด้วย Aspose.Tasks สำหรับ Java! ในบทช่วยสอนนี้ เราจะเจาะลึกความซับซ้อนของโครงสร้างการแบ่งงาน (WBS) ที่เกี่ยวข้องกับงานที่ใช้ Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือนี้จะช่วยให้คุณเข้าใจถึงสิ่งสำคัญในการจัดการโค้ด WBS ได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
-  Aspose.Tasks สำหรับไลบรารี Java ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ของคุณ คุณสามารถรับได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าคุณนำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นโปรเจ็กต์ของคุณ:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## อ่านรหัส WBS
เริ่มต้นด้วยการอ่านรหัส WBS ที่เกี่ยวข้องกับงาน ทำตามขั้นตอนเหล่านี้:
## ขั้นตอนที่ 1: โหลดโครงการ
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## ขั้นตอนที่ 2: รวบรวมงาน
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## ขั้นตอนที่ 3: แยกวิเคราะห์และปรับแต่ง
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
ตัวอย่างนี้จะอ่านและปรับแต่งรหัส WBS ที่เกี่ยวข้องกับงานในโครงการของคุณ
## กำหนดหมายเลขรหัสงาน WBS ใหม่
ตอนนี้ เรามาสำรวจการกำหนดหมายเลขรหัส WBS ใหม่สำหรับงาน:
## ขั้นตอนที่ 1: โหลดโครงการ
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## ขั้นตอนที่ 2: เลือกงานทั้งหมด
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## ขั้นตอนที่ 3: ส่งออกรหัส WBS เริ่มต้น
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## ขั้นตอนที่ 4: กำหนดหมายเลขรหัส WBS ใหม่
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## ขั้นตอนที่ 5: เอาต์พุตรหัส WBS ที่อัปเดตแล้ว
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะกำหนดหมายเลขรหัส WBS ใหม่สำหรับงานในโครงการของคุณได้อย่างมีประสิทธิภาพ
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีทำงานกับโค้ด WBS โดยใช้ Aspose.Tasks สำหรับ Java เรียบร้อยแล้ว ความรู้นี้จะช่วยให้คุณจัดการและปรับแต่งลำดับชั้นงานของโครงการได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/tasks/java/).
### ถาม: ฉันจะดาวน์โหลด Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/java/).
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุน
### ถาม: ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่
 ตอบ: ได้ รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).