---
date: 2026-01-05
description: เรียนรู้วิธีเพิ่มทรัพยากรลงในโครงการและสร้างการมอบหมายทรัพยากรใน Aspose.Tasks
  สำหรับ Java. เชี่ยวชาญเทคนิคการจัดสรรทรัพยากรใน Java ด้วยคู่มือขั้นตอนต่อขั้นตอนนี้.
linktitle: Add Resource to Project – Create Resource Assignments with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: เพิ่มทรัพยากรลงในโครงการ – สร้างการมอบหมายทรัพยากรด้วย Aspose.Tasks
url: /th/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มทรัพยากรลงในโครงการ – สร้างการมอบหมายทรัพยากรด้วย Aspose.Tasks

## Introduction
ในการจัดการโครงการ การมอบหมายทรัพยากรมีบทบาทสำคัญในการจัดสรรทรัพยากรอย่างมีประสิทธิภาพให้กับงานต่าง ๆ Aspose.Tasks for Java ให้โซลูชันที่ทรงพลังสำหรับการจัดการทรัพยากรโครงการและการมอบหมายของพวกมันโดยโปรแกรม ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **add resource to project** และการมอบหมายทรัพยากรให้กับงานโดยใช้ขั้นตอนที่ชัดเจนและเป็นลำดับ

## Quick Answers
- **What does “add resource to project” mean?** หมายถึงการสร้างเอนทิตีทรัพยากรในไฟล์โครงการและเชื่อมโยงกับหนึ่งหรือหลายงาน  
- **Which API method creates the assignment?** `project.getResourceAssignments().add(task, resource)`  
- **Do I need a license?** ใช่ จำเป็นต้องมีใบอนุญาต Aspose.Tasks for Java ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **Can I use this with Maven?** แน่นอน – เพียงเพิ่ม dependency ของ Aspose.Tasks ลงในไฟล์ `pom.xml` ของคุณ  
- **Is the code compatible with Java 11+?** ใช่ ตัวอย่างทำงานได้กับ Java 8 และเวอร์ชันใหม่กว่า

## How to add resource to project using Aspose.Tasks
ด้านล่างนี้คุณจะพบเวิร์กโฟลว์เต็มรูปแบบ ตั้งแต่การเตรียมสภาพแวดล้อมจนถึงการสร้างการมอบหมาย แต่ละขั้นตอนจะมีคำอธิบายสั้น ๆ ตามด้วยโค้ดที่ต้องคัดลอกอย่างแม่นยำ

## Prerequisites
ก่อนที่เราจะลงลึกในการสร้างการมอบหมายทรัพยากรด้วย Aspose.Tasks for Java โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

### Java Development Environment
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จาก [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)

### Aspose.Tasks for Java Library
ดาวน์โหลดไลบรารี Aspose.Tasks for Java จาก [download page](https://releases.aspose.com/tasks/java/) แล้วทำตามคำแนะนำการติดตั้งเพื่อกำหนดค่าไลบรารีในโปรเจกต์ Java ของคุณ

## Import Packages
ในโค้ด Java ของคุณ ให้ import แพ็กเกจที่จำเป็นจาก Aspose.Tasks for Java เพื่อใช้ประโยชน์จากฟังก์ชันต่าง ๆ:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

## Step 1: Create a Project Object
สร้างอ็อบเจ็กต์ `Project` ซึ่งเป็นตัวแทนของไฟล์โครงการที่คุณกำลังทำงานอยู่:
```java
Project project = new Project();
```

## Step 2: Add a Task to the Project
เพิ่มงานลงในโครงการโดยใช้เมธอด `addChild` ของงานราก (root task) ซึ่งเป็นการสาธิตการทำงาน **add task to project**:
```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Step 3: Add a Resource to the Project
เพิ่มทรัพยากรลงในโครงการโดยใช้เมธอด `add` ของคอลเลกชัน `Resources` นี่คือหัวใจของ **resource allocation java**:
```java
Resource rsc = project.getResources().add("Rsc");
```

## Step 4: Create a Resource Assignment
สร้างการมอบหมายทรัพยากรสำหรับงานและทรัพยากรโดยใช้เมธอด `add` ของคอลเลกชัน `ResourceAssignments` ขั้นตอนนี้ **assigns resources to tasks**:
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

## Common Issues and Solutions
- **NullPointerException when adding a task** – ตรวจสอบให้แน่ใจว่าได้สร้างอ็อบเจ็กต์โปรเจกต์ก่อนเข้าถึง `getRootTask()`  
- **License exception** – โหลดใบอนุญาต Aspose.Tasks ของคุณตั้งแต่ต้นแอปพลิเคชัน (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`)  
- **Incorrect resource IDs** – ใช้อ็อบเจ็กต์ทรัพยากรที่คืนค่าจากเมธอด `add` แทนการสร้าง `Resource` ใหม่ด้วยตนเอง

## FAQ's
### Q: Can I modify resource assignments after creation?
A: ใช่ คุณสามารถอัปเดตการมอบหมายทรัพยากรได้โดยใช้เมธอดของ Aspose.Tasks for Java ที่ให้มาในไลบรารี

### Q: Is Aspose.Tasks for Java compatible with different project file formats?
A: แน่นอน Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการหลายประเภทรวมถึง MPP, XML และอื่น ๆ

### Q: Does Aspose.Tasks for Java require a license for commercial use?
A: ใช่ คุณต้องมีใบอนุญาตที่ถูกต้องเพื่อใช้ Aspose.Tasks for Java ในโครงการเชิงพาณิชย์ คุณสามารถขอรับใบอนุญาตได้จากเว็บไซต์ Aspose

### Q: Can I use Aspose.Tasks for Java in my web applications?
A: ใช่ คุณสามารถผสานรวม Aspose.Tasks for Java เข้าไปในเว็บแอปพลิเคชันของคุณเพื่อจัดการทรัพยากรโครงการแบบไดนามิก

### Q: Where can I find additional support for Aspose.Tasks for Java?
A: คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือทางเทคนิคหรือสอบถามเกี่ยวกับไลบรารีได้

## Frequently Asked Questions
**Q: How do I save the project after adding assignments?**  
A: เรียก `project.save("MyProject.mpp", SaveFileFormat.MPP);` เพื่อบันทึกการเปลี่ยนแปลง

**Q: Can I assign the same resource to multiple tasks?**  
A: ใช่ เพียงเรียก `project.getResourceAssignments().add(anotherTask, rsc);` สำหรับแต่ละงานเพิ่มเติม

**Q: Is it possible to set work or cost for an assignment?**  
A: แน่นอน – ใช้ `assn.setWork(work);` หรือ `assn.setCost(cost);` หลังจากสร้างการมอบหมายแล้ว

## Conclusion
ในบทแนะนำนี้ เราได้เรียนรู้วิธี **add resource to project**, สร้างงาน, และ **assign resources to tasks** ด้วย Aspose.Tasks for Java โดยทำตามขั้นตอนเหล่านี้ คุณจะสามารถจัดการการจัดสรรทรัพยากรในแอปพลิเคชันการจัดการโครงการของคุณได้อย่างมีประสิทธิภาพและใช้ประโยชน์จาก API การจัดสรรทรัพยากร Java อย่างเต็มที่

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---