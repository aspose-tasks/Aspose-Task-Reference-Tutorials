---
date: 2026-02-23
description: สำรวจ Aspose.Tasks สำหรับ Java เพื่อทำให้การจัดการโครงการด้วย Java ง่ายขึ้น
  และเรียนรู้วิธีคำนวณเปอร์เซ็นต์ของงานและติดตามความคืบหน้าอย่างมีประสิทธิภาพ.
linktitle: Percentage Complete Calculations for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'การจัดการโครงการ Java: ความคืบหน้าของงานเป็นเปอร์เซ็นต์โดยใช้ Aspose.Tasks'
url: /th/java/task-properties/percentage-complete-calculations/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการโครงการ Java: คำนวณเปอร์เซ็นต์ความสำเร็จของงานด้วย Aspose.Tasks

## บทนำ
ยินดีต้อนรับสู่คู่มือฉบับสมบูรณ์ของเราเกี่ยวกับ **project management java** โดยใช้ Aspose.Tasks for Java ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีอ่านไฟล์ Microsoft Project, คำนวณงานที่เสร็จแล้ว, และรับเปอร์เซ็นต์ความคืบหน้าที่แม่นยำสำหรับทุกงาน การคำนวณเหล่านี้ช่วยให้คุณอัปเดตผู้มีส่วนได้ส่วนเสียได้อย่างต่อเนื่องและทำให้โครงการของคุณอยู่ในกำหนดเวลา

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดจัดการไฟล์ Microsoft Project ใน Java?** Aspose.Tasks for Java.  
- **คุณสมบัติใดแสดงความคืบหน้ารวม?** `Tsk.PERCENT_COMPLETE`.  
- **ฉันจะอ่านไฟล์ .mpp อย่างไร?** โหลดด้วย `new Project(filePath)`.  
- **ฉันสามารถคำนวณงานที่เสร็จแล้วได้หรือไม่?** ได้, ใช้ `Tsk.PERCENT_WORK_COMPLETE`.  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในโปรดักชันหรือไม่?** จำเป็นต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้อง

## Project Management Java คืออะไร?
Project management java หมายถึงการใช้เครื่องมือและไลบรารีที่พัฒนาโดย Java — เช่น Aspose.Tasks — เพื่อสร้าง, อ่าน, และจัดการตารางโครงการโดยอัตโนมัติ วิธีนี้ช่วยให้สามารถสร้างรายงานอัตโนมัติ, แดชบอร์ดแบบกำหนดเอง, และการบูรณาการที่ราบรื่นกับแอปพลิเคชัน Java ที่มีอยู่แล้ว

## ทำไมต้องใช้ Aspose.Tasks สำหรับการคำนวณเปอร์เซ็นต์งาน?
- **การติดตามความคืบหน้าที่แม่นยำ** – ดึงฟิลด์ Project ดั้งเดิมโดยไม่ต้องพาร์สด้วยตนเอง  
- **รองรับ .mpp อย่างเต็มรูปแบบ** – อ่าน, แก้ไข, และบันทึกไฟล์ Microsoft Project โดยตรง  
- **การทำงานอัตโนมัติที่ขยายได้** – ประมวลผลงานหลายพันรายการในไม่กี่วินาที, เหมาะกับพอร์ตโฟลิโอขนาดใหญ่  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Java runtime ใดก็ได้, ตั้งแต่เดสก์ท็อปจนถึงบริการคลาวด์

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน, โปรดตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK)** ติดตั้งแล้ว (Java 8 หรือใหม่กว่า)  
- **Aspose.Tasks for Java** ไลบรารี – ดาวน์โหลดจาก [this link](https://releases.aspose.com/tasks/java/)  
- ตัวอย่างไฟล์ Microsoft Project (เช่น *Software Development.mpp*) ที่วางไว้ในไดเรกทอรีที่รู้จัก

## นำเข้าแพ็กเกจ
ก่อนอื่นให้นำเข้าคลาสที่จำเป็น ส่วนนี้ควรเพิ่มในคลาส Java ใดก็ได้ที่ทำงานกับ Aspose.Tasks

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดโฟลเดอร์ที่มีไฟล์ *.mpp* ของคุณ แทนที่ตัวแปรตำแหน่งที่เก็บไฟล์ด้วยพาธที่แท้จริงบนเครื่องของคุณ

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
สร้างอินสแตนซ์ `Project` และโหลดไฟล์ Microsoft Project ขั้นตอนนี้ **อ่านไฟล์ Microsoft Project** เพื่อให้คุณสามารถเข้าถึงงานต่าง ๆ ได้

```java
Project project = new Project(dataDir + "Software Development.mpp");
```

### ขั้นตอนที่ 3: ดึงคอลเลกชันของงาน
รับงานราก (root task) แล้วตามด้วยงานลูก คอลเลกชันนี้แทนงานระดับบนทั้งหมดในโครงการ

```java
TaskCollection alTasks = project.getRootTask().getChildren();
```

### ขั้นตอนที่ 4: พิมพ์ค่าเปอร์เซ็นต์ความสำเร็จ
วนลูปผ่านแต่ละงานและแสดงเมตริกความคืบหน้า 3 ประการ:

- **Percentage Complete** – ความคืบหน้ารวมของงาน  
- **Percentage Work Complete** – ความคืบหน้าตามงานที่ทำเสร็จ  
- **Physical Percentage Complete** – ความคืบหน้าทางกายภาพ (หากตั้งค่า)

```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```

รันลูปนี้สำหรับทุกงานที่คุณต้องการติดตาม ผลลัพธ์จะแสดงภาพรวมที่ชัดเจนของ **วิธีการรับความคืบหน้า** สำหรับแต่ละรายการงาน

## กรณีการใช้งานทั่วไป
- **การรายงานแดชบอร์ด:** ดึงเปอร์เซ็นต์และป้อนเข้าสู่เครื่องมือ BI  
- **การแจ้งเตือนอัตโนมัติ:** เรียกการแจ้งเตือนเมื่อ `PERCENT_COMPLETE` ของงานต่ำกว่าค่าที่กำหนด  
- **การปรับระดับทรัพยากร:** ปรับการมอบหมายงานตาม `PERCENT_WORK_COMPLETE` เพื่อให้ตารางเวลามีความเป็นจริง

## การแก้ไขปัญหาและเคล็ดลับ
- **ค่าที่เป็น Null:** ตรวจสอบให้แน่ใจว่าไฟล์โครงการมีฟิลด์ที่คุณเรียกใช้; ไฟล์ .mpp รุ่นเก่าอาจไม่มี `PHYSICAL_PERCENT_COMPLETE`  
- **ประสิทธิภาพ:** สำหรับโครงการขนาดใหญ่มาก, พิจารณาแบ่งหน้า `TaskCollection` หรือกรองตาม ID ของงานเพื่อประหยัดหน่วยความจำ  
- **ข้อผิดพลาดเรื่องลิขสิทธิ์:** หากพบคำเตือนเกี่ยวกับลิขสิทธิ์, ตรวจสอบว่าได้โหลดไฟล์ลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องก่อนสร้างอ็อบเจกต์ `Project`

## คำถามที่พบบ่อย

**ถาม: จะหาเอกสาร Aspose.Tasks ได้จากที่ไหน?**  
ตอบ: เอกสารพร้อมให้บริการ [ที่นี่](https://reference.aspose.com/tasks/java/)

**ถาม: จะดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
ตอบ: คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/tasks/java/)

**ถาม: มีรุ่นทดลองใช้งานฟรีหรือไม่?**  
ตอบ: มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีได้ [ที่นี่](https://releases.aspose.com/)

**ถาม: จะขอรับการสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
ตอบ: เยี่ยมชมฟอรั่มสนับสนุน [ที่นี่](https://forum.aspose.com/c/tasks/15)

**ถาม: จะขอรับลิขสิทธิ์ชั่วคราวได้อย่างไร?**  
ตอบ: คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

**คำถามเพิ่มเติม**

**ถาม: ฉันสามารถคำนวณเปอร์เซ็นต์งานโดยไม่ใช้ Aspose.Tasks ได้หรือไม่?**  
ตอบ: คุณอาจพาร์สไฟล์ .mpp ด้วยตนเอง, แต่ Aspose.Tasks ให้ API ที่เชื่อถือได้และรองรับทุกกรณีขอบ

**ถาม: Aspose.Tasks รองรับการอ่านไฟล์จาก Project Online หรือไม่?**  
ตอบ: รองรับ, คุณสามารถโหลดไฟล์ที่ส่งออกจาก Project Online ได้ตราบใดที่ไฟล์ถูกบันทึกในรูปแบบ .mpp

---

**อัปเดตล่าสุด:** 2026-02-23  
**ทดสอบกับ:** Aspose.Tasks for Java 24.11 (latest)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}