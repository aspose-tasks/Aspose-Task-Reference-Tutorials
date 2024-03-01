---
title: จัดการงานที่สำคัญและขับเคลื่อนด้วยความพยายามใน Aspose.Tasks
linktitle: จัดการงานที่สำคัญและขับเคลื่อนด้วยความพยายามใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: จัดการงานที่สำคัญและต้องใช้ความพยายามในโปรเจ็กต์ Java ของคุณได้อย่างง่ายดายด้วย Aspose.Tasks ดาวน์โหลดไลบรารีและปรับปรุงความสามารถในการจัดการโครงการของคุณ
type: docs
weight: 14
url: /th/java/task-properties/critical-effort-driven-tasks/
---
ในโลกของการจัดการโครงการที่เปลี่ยนแปลงไปอย่างรวดเร็ว การจัดการงานที่สำคัญและขับเคลื่อนด้วยความพยายามอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับการดำเนินโครงการให้สำเร็จ Aspose.Tasks for Java มอบโซลูชันที่มีประสิทธิภาพในการจัดการงานเหล่านี้ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการใช้ Aspose.Tasks สำหรับ Java เพื่อจัดการงานที่สำคัญและต้องใช้ความพยายามในโปรเจ็กต์ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- Aspose.Tasks สำหรับ Java Library: ดาวน์โหลดและติดตั้งไลบรารีจากไฟล์[Aspose.Tasks สำหรับเอกสาร Java](https://reference.aspose.com/tasks/java/).
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE ที่คุณต้องการสำหรับการพัฒนา Java
- ไฟล์โครงการ: เตรียมไฟล์โครงการในรูปแบบ XML ที่คุณจะใช้ในการสาธิต
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.Tasks สำหรับ Java:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```
ตอนนี้ เราจะแจกแจงแต่ละขั้นตอนเป็นคำแนะนำที่ครอบคลุม:
## ขั้นตอนที่ 1: รวบรวมงานโดยใช้ ChildTasksCollector
 สร้างก`ChildTasksCollector` อินสแตนซ์เพื่อรวบรวมงานทั้งหมดจากงานรูทที่ใช้`TaskUtils.apply`. สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงงานทั้งหมดภายในโครงการได้
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// สร้างอินสแตนซ์ ChildTasksCollector
ChildTasksCollector collector = new ChildTasksCollector();
// รวบรวมงานทั้งหมดจาก RootTask โดยใช้ TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## ขั้นตอนที่ 2: ทำซ้ำผ่านงานที่รวบรวมไว้
 แยกวิเคราะห์งานที่รวบรวมทั้งหมดโดยใช้`for` วนซ้ำ สำหรับแต่ละงาน ให้พิจารณาว่างานนั้นเน้นความพยายามและมีความสำคัญหรือไม่ โดยพิมพ์สถานะตามลำดับ
```java
// แยกวิเคราะห์งานที่รวบรวมทั้งหมด
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการงานที่สำคัญและขับเคลื่อนด้วยความพยายามในโปรเจ็กต์ของคุณได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java
## บทสรุป
โดยสรุป Aspose.Tasks สำหรับ Java ช่วยให้นักพัฒนา Java สามารถจัดการงานที่สำคัญและต้องใช้ความพยายามในการจัดการโครงการได้อย่างมีประสิทธิภาพ ด้วยคุณสมบัติที่ใช้งานง่ายและฟังก์ชันการทำงานที่แข็งแกร่ง การจัดการสถานการณ์โครงการที่ซับซ้อนจึงกลายเป็นเรื่องง่าย
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java ได้ทั้งในสภาพแวดล้อม Windows และ Linux ได้หรือไม่
ใช่ Aspose.Tasks สำหรับ Java ไม่ขึ้นอยู่กับแพลตฟอร์มและสามารถใช้ได้ทั้งในสภาพแวดล้อม Windows และ Linux
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึง Aspose.Tasks for Java รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะซื้อ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 คุณสามารถซื้อ Aspose.Tasks สำหรับ Java ได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).