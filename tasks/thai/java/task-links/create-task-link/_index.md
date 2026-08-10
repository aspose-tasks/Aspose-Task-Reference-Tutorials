---
date: 2026-07-05
description: เรียนรู้วิธีสร้างการเชื่อมโยงงานการจัดการโครงการด้วย Java โดยใช้ Aspose.Tasks.
  ทำตาม step‑by‑step guide พร้อม code snippets.
keywords:
- project management task dependencies
- Aspose.Tasks Java
- task linking tutorial
linktitle: สร้างการเชื่อมโยงงานการจัดการโครงการด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  headline: Create Project Management Task Dependencies in Aspose.Tasks
  type: TechArticle
- description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  name: Create Project Management Task Dependencies in Aspose.Tasks
  steps:
  - name: Set Document Directory
    text: Define the directory where your documents are stored to ensure Aspose.Tasks
      locates and processes files correctly. The `java.nio.file.Paths` utility helps
      you build platform‑independent file paths. java // The path to the documents
      directory. String dataDir = "Your Document Directory";
  - name: Initialize Project and Tasks
    text: Create a new project and initialize tasks within it. In this example, "Task
      1" and "Task 2" are added to the root task. The `Task` class represents an individual
      work item; each task can have its own ID, name, and schedule. java Project project
      = new Project(dataDir + "project5.mpp"); Task pred = pr
  - name: Establish Task Link
    text: Utilize the `getTaskLinks()` method to add a link between two tasks. This
      example demonstrates linking "Task 1" as a predecessor to "Task 2." The `TaskLink`
      object defines the type of dependency (Finish‑to‑Start, Start‑to‑Start, etc.)
      and optional lag. java TaskLink link = project.getTaskLinks().add
  - name: Display Result
    text: Print a message indicating the successful completion of the task link creation
      process. This step is crucial for debugging and verification. A simple `System.out.println`
      call confirms that the link was added without errors. java // Display the result
      of the conversion. System.out.println("Task Link
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks seamlessly integrates with Spring, Jakarta EE, Android,
      and any standard Java environment.
    question: Can I use Aspose.Tasks for Java with other Java frameworks?
  - answer: Yes, explore the functionalities with the [free trial](https://releases.aspose.com/)
      before making a commitment.
    question: Is there a free trial available before purchasing the library?
  - answer: Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: Yes, check the documentation for comprehensive sample projects and code
      snippets.
    question: Are there any sample projects available for reference?
  - answer: Secure your copy by visiting the [purchase page](https://purchase.aspose.com/buy)
      and explore licensing options.
    question: What is the recommended way to purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: สร้างการเชื่อมโยงงานการจัดการโครงการด้วย Aspose.Tasks
url: /th/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างการเชื่อมโยงงานการจัดการโครงการใน Aspose.Tasks

## บทนำ
การเชื่อมโยงงานการจัดการโครงการเป็นโครงกระดูกของตารางเวลาที่มีโครงสร้างดี ช่วยให้คำนวณวันที่เริ่มต้น วันที่สิ้นสุด และเส้นทางสำคัญโดยอัตโนมัติ ในบทเรียนนี้คุณจะได้เรียนรู้วิธีสร้าง **การเชื่อมโยงงานการจัดการโครงการ** ด้วย Java โดยใช้ Aspose.Tasks ซึ่งเป็นไลบรารีที่รองรับไฟล์กว่า 50 รูปแบบและสามารถจัดการโครงการที่มีงานหลายพันรายการได้โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำตามขั้นตอนด้านล่างเพื่อเชื่อมโยงงาน ตรวจสอบลิงก์ และผสานโซลูชันเข้ากับแอปพลิเคชันในโลกจริง

## คำตอบอย่างรวดเร็ว
- **หัวข้อที่สอนในบทเรียนคืออะไร?** การสร้างการเชื่อมโยงงาน (dependencies) ด้วย Aspose.Tasks สำหรับ Java.  
- **ต้องใช้บรรทัดโค้ดกี่บรรทัด?** ตรรกะการเชื่อมโยงหลักใช้เพียงสองคำสั่ง.  
- **ต้องมีไลเซนส์เพื่อทดลองหรือไม่?** มีการทดลองฟรี 30 วัน; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **รองรับเวอร์ชัน Java ใดบ้าง?** รองรับ Java 8 ถึง 17 อย่างเต็มที่.  
- **สามารถเชื่อมโยงมากกว่าสองงานได้หรือไม่?** ได้ – ทำซ้ำรูปแบบการเชื่อมโยงสำหรับคู่งานผู้ก่อนหน้า‑ผู้ตามจำนวนใดก็ได้.

## การเชื่อมโยงงานการจัดการโครงการคืออะไร?
การเชื่อมโยงงานการจัดการโครงการกำหนดว่าการเริ่มต้นหรือการสิ้นสุดของงานหนึ่งสัมพันธ์กับงานอื่นอย่างไร ซึ่งบังคับให้ทำงานตามลำดับที่กำหนด Aspose.Tasks แสดงความสัมพันธ์เหล่านี้ผ่านอ็อบเจกต์ `TaskLink` ซึ่งคุณสามารถสร้าง แก้ไข หรือทำลบได้โดยโปรแกรม

## ทำไมต้องใช้ Aspose.Tasks สำหรับการเชื่อมโยงงาน?
Aspose.Tasks รองรับ **รูปแบบไฟล์เข้าและออกกว่า 50 แบบ** (รวมถึง MPP, XML, CSV) และสามารถประมวลผลโครงการที่มี **งานกว่า 10,000 รายการ** โดยใช้หน่วยความจำน้อยกว่า 200 MB บนเซิร์ฟเวอร์ทั่วไป API ของมันให้การควบคุมละเอียดต่อประเภทลิงก์ เวลาแฝง และการจัดการข้อจำกัดโดยไม่ต้องติดตั้ง Microsoft Project

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
- สภาพแวดล้อมการพัฒนา Java: ตั้งค่าสภาพแวดล้อมการพัฒนา Java ที่ทำงานได้บนเครื่องของคุณ.  
- ไลบรารี Aspose.Tasks: ดาวน์โหลดและรวมไลบรารี Aspose.Tasks สำหรับ Java ซึ่งมีให้ดาวน์โหลด [ที่นี่](https://releases.aspose.com/tasks/java/).

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ ซึ่งเป็นขั้นตอนสำคัญสำหรับการเข้าถึงฟังก์ชันของ Aspose.Tasks

คลาส `Project` เป็นจุดเริ่มต้นของ Aspose.Tasks ที่แสดงไฟล์โครงการทั้งหมดในหน่วยความจำ.  
```text
```java
import com.aspose.tasks.*;
```
```

## วิธีสร้างการเชื่อมโยงงานด้วย Aspose.Tasks สำหรับ Java?
โหลดหรือสร้างอินสแตนซ์ `Project` เพิ่มงานที่ต้องการ แล้วเรียก `getTaskLinks().add()` เพื่อสร้างความสัมพันธ์ วิธีนี้จะสร้างอ็อบเจกต์ `TaskLink` ที่เชื่อมต่องานผู้ก่อนหน้าและผู้ตาม พร้อมให้คุณระบุประเภทลิงก์และเวลาแฝงได้ ขั้นตอนต่อไปนี้จะแสดงโค้ดที่คุณต้องใช้โดยไม่มีโค้ดส่วนเกิน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดไดเรกทอรีที่เก็บเอกสารของคุณเพื่อให้ Aspose.Tasks สามารถค้นหาและประมวลผลไฟล์ได้อย่างถูกต้อง

ยูทิลิตี้ `java.nio.file.Paths` ช่วยคุณสร้างเส้นทางไฟล์ที่เป็นอิสระต่อแพลตฟอร์ม.  
```text
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
```

### ขั้นตอนที่ 2: เริ่มต้นโครงการและงาน
สร้างโครงการใหม่และกำหนดงานภายใน ในตัวอย่างนี้ "Task 1" และ "Task 2" ถูกเพิ่มเข้าไปในงานราก

คลาส `Task` แสดงรายการงานแต่ละรายการ; งานแต่ละงานสามารถมี ID, ชื่อ, และกำหนดการของตนเอง.  
```text
```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```
```

### ขั้นตอนที่ 3: สร้างการเชื่อมโยงงาน
ใช้เมธอด `getTaskLinks()` เพื่อเพิ่มลิงก์ระหว่างสองงาน ตัวอย่างนี้แสดงการเชื่อม "Task 1" เป็นผู้ก่อนหน้าให้กับ "Task 2"

อ็อบเจกต์ `TaskLink` กำหนดประเภทของความสัมพันธ์ (Finish‑to‑Start, Start‑to‑Start, ฯลฯ) และเวลาแฝง (lag) ที่เป็นตัวเลือก.  
```text
```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```
```

### ขั้นตอนที่ 4: แสดงผลลัพธ์
พิมพ์ข้อความเพื่อบ่งบอกว่ากระบวนการสร้างการเชื่อมโยงงานสำเร็จ ขั้นตอนนี้สำคัญสำหรับการดีบักและตรวจสอบ

การเรียก `System.out.println` อย่างง่ายจะยืนยันว่าลิงก์ถูกเพิ่มโดยไม่มีข้อผิดพลาด.  
```text
```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```
```

ทำซ้ำขั้นตอนเหล่านี้สำหรับสถานการณ์การเชื่อมโยงงานที่ซับซ้อนมากขึ้น ปรับแต่งชื่องาน และสร้างความสัมพันธ์ตามความต้องการของโครงการของคุณ

อ้างอิงที่ [Aspose.Tasks Documentation](https://reference.aspose.com/tasks/java/) สำหรับข้อมูล API อย่างละเอียด.  
สำหรับการสนับสนุนจากชุมชน เยี่ยมชม [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15).

## ปัญหาที่พบบ่อยและวิธีแก้
เมธอด `save` จะเขียนโครงการไปยังเส้นทางไฟล์ที่ระบุ โดยบันทึกการเปลี่ยนแปลงทั้งหมดรวมถึงลิงก์ที่เพิ่มเข้ามา. การนับประเภท `TaskLinkType` กำหนดประเภทความสัมพันธ์ เช่น `FinishToStart` สำหรับความสัมพันธ์แบบจบ‑เริ่ม.

- **ลิงก์ไม่ปรากฏในไฟล์ที่บันทึก** – ตรวจสอบให้แน่ใจว่าคุณเรียก `project.save(outputPath)` หลังจากเพิ่มลิงก์.  
- **ประเภทลิงก์ไม่ถูกต้อง** – ใช้ `TaskLinkType.FinishToStart`, `StartToStart` ฯลฯ ให้ตรงกับตรรกะการกำหนดเวลาของคุณ.  
- **โครงการขนาดใหญ่ทำให้หน่วยความจำพุ่งสูง** – เปิดใช้งาน `project.setReadOnly(true)` ก่อนโหลดเพื่อทำงานในโหมดสตรีมมิ่ง.

## คำถามที่พบบ่อย
**Q: สามารถใช้ Aspose.Tasks สำหรับ Java ร่วมกับเฟรมเวิร์ก Java อื่นได้หรือไม่?**  
A: ได้, Aspose.Tasks ผสานรวมอย่างราบรื่นกับ Spring, Jakarta EE, Android และสภาพแวดล้อม Java มาตรฐานใด ๆ

**Q: มีการทดลองใช้ฟรีก่อนซื้อไลเซนส์หรือไม่?**  
A: มี, สำรวจฟังก์ชันการทำงานด้วย [free trial](https://releases.aspose.com/) ก่อนตัดสินใจซื้อ

**Q: จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร?**  
A: รับไลเซนส์ชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล

**Q: มีตัวอย่างโครงการสำหรับอ้างอิงหรือไม่?**  
A: มี, ตรวจสอบเอกสารสำหรับตัวอย่างโครงการและโค้ดสแนปช็อตที่ครอบคลุม

**Q: วิธีการซื้อ Aspose.Tasks สำหรับ Java ที่แนะนำคืออะไร?**  
A: ซื้อได้โดยเยี่ยมชม [purchase page](https://purchase.aspose.com/buy) และสำรวจตัวเลือกการไลเซนส์

---

**อัปเดตล่าสุด:** 2026-07-05  
**ทดสอบกับ:** Aspose.Tasks 24.12 for Java  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้างงาน Aspose Java – คุณสมบัติงาน](/tasks/java/task-properties/)
- [Baseline การจัดการโครงการ – การกำหนดเวลางานด้วย Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)
- [วิธีสร้างทรัพยากร – การจัดการทรัพยากรด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}