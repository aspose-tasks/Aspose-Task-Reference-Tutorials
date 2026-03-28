---
date: 2026-01-25
description: เรียนรู้วิธีใช้ Aspose Tasks Java สำหรับการจัดการงาน Java, การจัดการงานที่สำคัญและขับเคลื่อนด้วยความพยายามในโครงการของคุณ.
  เพิ่มประสิทธิภาพกระบวนการทำงานของโครงการด้วยคู่มือนี้.
linktitle: Aspose Tasks Java – Manage Critical and Effort‑Driven Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java – จัดการงานสำคัญและงานที่ขับเคลื่อนด้วยความพยายาม
url: /th/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java: จัดการงานที่สำคัญและงานที่ขับเคลื่อนด้วยความพยายาม

ในการจัดการโครงการสมัยใหม่, **aspose tasks java** ให้คุณมีพลังในการระบุและควบคุมงานที่สำคัญและงานที่ขับเคลื่อนด้วยความพยายามโดยตรงจากโค้ด Java ของคุณ ไม่ว่าคุณจะสร้างตัวกำหนดเวลา, เครื่องมือรายงาน, หรือแดชบอร์ดแบบกำหนดเอง การจัดการคุณสมบัติงานเหล่านี้อย่างถูกต้องอาจเป็นความแตกต่างระหว่างโครงการที่ดำเนินไปตามแผนและโครงการที่ล่มสลาย ในบทเรียนนี้เราจะอธิบายทุกอย่างที่คุณต้องรู้เพื่อทำงานกับงานที่สำคัญและงานที่ขับเคลื่อนด้วยความพยายามโดยใช้ Aspose Tasks Java.

## คำตอบอย่างรวดเร็ว
- **What does “critical” mean?** งานที่การล่าช้าจะทำให้วันที่สิ้นสุดโครงการล่าช้า  
- **What is “effort‑driven”?** งานที่ปรับระยะเวลาโดยอัตโนมัติเมื่อคุณเปลี่ยนปริมาณงาน  
- **Which library provides these features?** Aspose Tasks Java.  
- **Do I need a license for development?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตสำหรับการผลิต  
- **Can I run this on any OS?** ใช่ – ไลบรารีเป็นแบบแพลตฟอร์มอิสระ (Windows, Linux, macOS).  

## งานที่สำคัญและงานที่ขับเคลื่อนด้วยความพยายามคืออะไร?
งานที่สำคัญคืองานที่อยู่บนเส้นทางสำคัญของโครงการ; การล่าช้าใด ๆ จะส่งผลโดยตรงต่อกำหนดการโดยรวม งานที่ขับเคลื่อนด้วยความพยายามนั้นในทางกลับกันจะคำนวณระยะเวลาใหม่ตามปริมาณงานที่มอบหมาย ทำให้เหมาะกับทรัพยากรที่สามารถทำงานล่วงเวลา หรือแบ่งความพยายามระหว่างหลายการมอบหมายงาน

## ทำไมต้องใช้ Aspose Tasks Java สำหรับสิ่งนี้?
- **Full .NET‑style API in Java** – ไม่จำเป็นต้องเปลี่ยนภาษา.  
- **High performance** – ทำงานกับไฟล์โครงการขนาดใหญ่ที่เป็น XML โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.  
- **Rich property set** – เข้าถึง `IS_CRITICAL`, `IS_EFFORT_DRIVEN` และคุณลักษณะงานอื่น ๆ อีกมากมาย.  
- **Cross‑platform** – รันบนสภาพแวดล้อมที่รองรับ JVM ใดก็ได้.  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในบทเรียน, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
- Aspose.Tasks for Java Library: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).  
- Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว.  
- Integrated Development Environment (IDE): ใช้ IDE ที่คุณชื่นชอบสำหรับการพัฒนา Java.  
- Project File: เตรียมไฟล์โครงการในรูปแบบ XML ที่คุณจะใช้สำหรับการสาธิต.  

## นำเข้าแพ็กเกจ
ในโครงการ Java ของคุณ, นำเข้าแพ็กเกจที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันของ Aspose.Tasks for Java:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

### ขั้นตอนที่ 1: รวบรวมงานโดยใช้ `ChildTasksCollector`
สร้างอินสแตนซ์ `ChildTasksCollector` เพื่อรวบรวมงานทั้งหมดจากงานรากโดยใช้ `TaskUtils.apply`. สิ่งนี้ทำให้คุณเข้าถึงงานทุกงานภายในโครงการได้.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### ขั้นตอนที่ 2: วนลูปผ่านงานที่รวบรวมได้
วนลูปผ่านงานที่รวบรวมทั้งหมดโดยใช้ `for` loop. สำหรับแต่ละงาน, ตรวจสอบว่ามันเป็นงานที่ขับเคลื่อนด้วยความพยายามและเป็นงานสำคัญหรือไม่, แล้วพิมพ์สถานะที่เกี่ยวข้อง.

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

โดยทำตามขั้นตอนเหล่านี้, คุณสามารถจัดการงานที่สำคัญและงานที่ขับเคลื่อนด้วยความพยายามในโครงการของคุณได้อย่างมีประสิทธิภาพโดยใช้ **aspose tasks java**.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| `NullPointerException` on `tsk.get(Tsk.IS_CRITICAL)` | งานไม่มีการตั้งค่าคุณสมบัตินี้ (เช่น งานสรุป). | ตรวจสอบ `tsk.get(Tsk.TASK_TYPE)` ก่อนเข้าถึงแฟล็ก, หรือกรองงานสรุปออก. |
| Project file not found | เส้นทาง `dataDir` ไม่ถูกต้องหรือไม่มีส่วนขยายไฟล์. | ใช้ `Paths.get(dataDir, "project.xml").toString()` และตรวจสอบว่าไฟล์มีอยู่. |
| License not applied | ไลบรารีทำงานในโหมดประเมินผล ซึ่งจำกัดฟีเจอร์. | โหลดไฟล์ใบอนุญาตของคุณด้วย `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` ก่อนสร้างอ็อบเจ็กต์ `Project`. |

## คำถามที่พบบ่อย
### Q: ฉันสามารถใช้ Aspose.Tasks for Java ในสภาพแวดล้อม Windows และ Linux ได้หรือไม่?
A: ใช่, Aspose.Tasks for Java เป็นแบบแพลตฟอร์มอิสระและสามารถใช้ได้ทั้งใน Windows และ Linux.

### Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks for Java หรือไม่?
A: ใช่, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.Tasks for Java [ที่นี่](https://releases.aspose.com/).

### Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
A: เยี่ยมชม [ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา.

### Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks for Java ได้อย่างไร?
A: คุณสามารถรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

### Q: ฉันจะซื้อ Aspose.Tasks for Java ได้จากที่ไหน?
A: คุณสามารถซื้อ Aspose.Tasks for Java ได้จาก [หน้าซื้อสินค้า](https://purchase.aspose.com/buy).

**อัปเดตล่าสุด:** 2026-01-25  
**ทดสอบด้วย:** Aspose.Tasks Java 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}