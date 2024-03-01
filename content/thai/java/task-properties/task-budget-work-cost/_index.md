---
title: การจัดการงบประมาณ งาน และต้นทุนสำหรับงานใน Aspose.Tasks
linktitle: การจัดการงบประมาณ งาน และต้นทุนสำหรับงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: ปลดล็อกการจัดการงบประมาณและต้นทุนที่มีประสิทธิภาพในโปรเจ็กต์ Java ด้วย Aspose.Tasks สำรวจคำแนะนำทีละขั้นตอนเพื่อการบูรณาการที่ราบรื่น
type: docs
weight: 31
url: /th/java/task-properties/task-budget-work-cost/
---
## การแนะนำ
การจัดการงบประมาณ งาน และต้นทุนอย่างมีประสิทธิภาพเป็นสิ่งสำคัญสำหรับการดำเนินโครงการให้ประสบความสำเร็จ Aspose.Tasks for Java มอบโซลูชันที่มีประสิทธิภาพสำหรับการจัดการงานที่เกี่ยวข้องกับโปรเจ็กต์ รวมถึงการจัดทำงบประมาณและการจัดการต้นทุน ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้ Aspose.Tasks สำหรับ Java เพื่อให้บรรลุงบประมาณ งาน และการจัดการต้นทุนในโปรเจ็กต์ของคุณอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนระบบของคุณ
-  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับไลบรารี Java คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้เริ่มด้วยการอิมพอร์ตแพ็คเกจที่จำเป็น สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงฟังก์ชันการทำงานของ Aspose.Tasks ได้ รวมบรรทัดต่อไปนี้ไว้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```
## 1. ตั้งค่าไดเร็กทอรีเอกสาร
เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือที่จัดเก็บไฟล์โครงการของคุณ ใช้ข้อมูลโค้ดต่อไปนี้:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
```
## 2. โหลดโปรเจ็กต์
โหลดไฟล์โครงการโดยใช้ไลบรารี Aspose.Tasks แทนที่ "BudgetWorkAndCost.mpp" ด้วยชื่อไฟล์โครงการของคุณ
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```
## 3. ดึงข้อมูลงบประมาณโครงการและทรัพยากร
ดึงข้อมูลและแสดงงบประมาณโครงการและทรัพยากรโดยใช้รหัสต่อไปนี้:
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```
## 4. แสดงงบประมาณการมอบหมาย
ทำซ้ำผ่านการมอบหมายโครงการและแสดงข้อมูลงบประมาณ:
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```
ทำซ้ำขั้นตอนเหล่านี้ตามที่จำเป็นเพื่อรวมฟังก์ชันงบประมาณ งาน และการจัดการต้นทุนไว้ในโปรเจ็กต์ Aspose.Tasks สำหรับ Java ของคุณ
## บทสรุป
การจัดการงบประมาณ งาน และต้นทุนอย่างมีประสิทธิภาพเป็นสิ่งสำคัญสำหรับความสำเร็จของโครงการ Aspose.Tasks สำหรับ Java ช่วยให้กระบวนการนี้ง่ายขึ้น โดยมอบโซลูชันที่ครอบคลุมสำหรับความต้องการในการจัดการโครงการของคุณ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถรวมการจัดการงบประมาณและต้นทุนเข้ากับโปรเจ็กต์ Java ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับเฟรมเวิร์ก Java อื่นได้หรือไม่
ใช่ Aspose.Tasks สำหรับ Java เข้ากันได้กับเฟรมเวิร์ก Java ต่างๆ จึงมั่นใจได้ถึงความยืดหยุ่นในการบูรณาการ
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Tasks สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึง Aspose.Tasks for Java รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 สำรวจฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปราย
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบและประเมินผล
### มีแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Tasks สำหรับ Java หรือไม่
 โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tasks/java/) สำหรับข้อมูลเชิงลึกและตัวอย่าง