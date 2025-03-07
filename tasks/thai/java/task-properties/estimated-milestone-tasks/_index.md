---
title: จัดการงานโดยประมาณและงานสำคัญใน Aspose.Tasks
linktitle: จัดการงานโดยประมาณและงานสำคัญใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจการจัดการโครงการอย่างมีประสิทธิภาพด้วย Aspose.Tasks สำหรับ Java จัดการงานโดยประมาณและเหตุการณ์สำคัญได้อย่างง่ายดาย ดาวน์โหลดห้องสมุดทันที!
weight: 15
url: /th/java/task-properties/estimated-milestone-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการงานโดยประมาณและงานสำคัญใน Aspose.Tasks

## การแนะนำ
Aspose.Tasks for Java เป็นไลบรารีอันทรงพลังที่ช่วยอำนวยความสะดวกในการจัดการงาน จัดการโปรเจ็กต์ และจัดการข้อมูลโปรเจ็กต์ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะมุ่งเน้นไปที่ส่วนสำคัญของการจัดการโครงการ – การจัดการงานโดยประมาณและงานหลักโดยใช้ Aspose.Tasks สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/java/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Eclipse หรือ IntelliJ
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ Aspose.Tasks สำหรับฟังก์ชัน Java
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;

```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์ ChildTasksCollector
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
```
## ขั้นตอนที่ 2: รวบรวมงานทั้งหมดจาก RootTask โดยใช้ TaskUtils
```java
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## ขั้นตอนที่ 3: แยกวิเคราะห์งานที่รวบรวมไว้ทั้งหมด
```java
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```
ในขั้นตอนเหล่านี้ เราใช้ Aspose.Tasks สำหรับ Java เพื่อรวบรวมและวิเคราะห์งาน โดยดึงข้อมูลที่เกี่ยวข้องกับว่างานนั้นเน้นความพยายามและมีความสำคัญหรือไม่
โดยการแบ่งตัวอย่างออกเป็นขั้นตอนเหล่านี้ เรามุ่งมั่นที่จะทำให้กระบวนการมีความชัดเจนและสามารถจัดการได้สำหรับผู้ใช้ในระดับทักษะต่างๆ
## บทสรุป
การเรียนรู้การจัดการงานโดยประมาณและเหตุการณ์สำคัญใน Aspose.Tasks สำหรับ Java เปิดโอกาสให้การจัดการโครงการมีประสิทธิผล เมื่อคุณเจาะลึกบทช่วยสอนนี้ อย่าลังเลที่จะทดลองและสำรวจฟังก์ชันเพิ่มเติมที่นำเสนอโดยไลบรารี Aspose.Tasks

## คำถามที่พบบ่อย
### Aspose.Tasks เหมาะสำหรับการจัดการโครงการขนาดใหญ่หรือไม่
อย่างแน่นอน! Aspose.Tasks ได้รับการออกแบบมาเพื่อรองรับโปรเจ็กต์ที่มีขนาดแตกต่างกัน โดยมีฟังก์ชันการทำงานที่แข็งแกร่งสำหรับการจัดการโปรเจ็กต์ที่มีประสิทธิภาพ
### ฉันสามารถรวม Aspose.Tasks เข้ากับโปรเจ็กต์ Java ที่มีอยู่ของฉันได้หรือไม่
ใช่ คุณสามารถผสานรวม Aspose.Tasks เข้ากับโปรเจ็กต์ Java ของคุณได้อย่างราบรื่นโดยปฏิบัติตามเอกสารที่ให้มา
### ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้ที่ไหน
 ฟอรัมชุมชน Aspose.Tasks ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เป็นสถานที่ที่ดีเยี่ยมในการขอความช่วยเหลือและแบ่งปันประสบการณ์
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถเข้าถึง Aspose.Tasks รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
