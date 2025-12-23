---
date: 2025-12-23
description: เรียนรู้วิธีสร้างความสัมพันธ์ระหว่างงานและคำนวณเส้นทางสำคัญใน MS Project
  ด้วย Aspose.Tasks สำหรับ Java คู่มือทีละขั้นตอนสำหรับการจัดการโครงการ
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: สร้างการเชื่อมโยงงานและคำนวณเส้นทางสำคัญใน Aspose.Tasks
url: /th/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างการเชื่อมโยงงานและคำนวณ Critical Path ใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้ **คุณจะได้เรียนรู้วิธีสร้างการเชื่อมโยงงาน** และคำนวณ critical path ในไฟล์ MS Project ด้วย Aspose.Tasks for Java การเข้าใจและมองเห็น critical path จะช่วยให้คุณรักษาโครงการให้เป็นไปตามกำหนดเวลาได้ ในขณะที่การเชื่อมโยงงานอย่างถูกต้องทำให้การล่าช้าใด ๆ ปรากฏทันที มาดูขั้นตอนทั้งหมดตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการแสดงผล critical path สุดท้ายกัน

## คำตอบสั้น
- **ขั้นตอนแรกคืออะไร?** ตั้งค่าโปรเจค Java ของคุณและเพิ่มไลบรารี Aspose.Tasks  
- **ต้องเปิดโหมดใด?** `CalculationMode.Automatic` (ตั้งให้คำนวณอัตโนมัติ)  
- **จะเชื่อมโยงงานอย่างไร?** ใช้ `project.getTaskLinks().add(...)` เพื่อสร้างการเชื่อมโยงงาน  
- **จะดู critical path อย่างไร?** วนลูป `project.getCriticalPath()` และพิมพ์ชื่อแต่ละงาน  
- **ต้องใช้ไลเซนส์หรือไม่?** ใช่ ต้องมีไลเซนส์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์

## “สร้างการเชื่อมโยงงาน” คืออะไร?
การสร้างการเชื่อมโยงงานหมายถึงการกำหนดความสัมพันธ์ (เช่น Finish‑to‑Start) ระหว่างงานต่าง ๆ เพื่อให้ตารางเวลาแสดงข้อจำกัดตามความเป็นจริง ใน Aspose.Tasks ทำได้ผ่านอ็อบเจ็กต์ `TaskLink`

## ทำไมต้องคำนวณ critical path ใน MS Project?
**critical path ของ MS Project** แสดงลำดับที่ยาวที่สุดของงานที่เชื่อมโยงกันซึ่งกำหนดระยะเวลาขั้นต่ำของโครงการ การคำนวณมันจะช่วยให้คุณระบุงานที่ไม่สามารถล่าช้าได้โดยไม่กระทบต่อไทม์ไลน์โดยรวม—เป็นสิ่งสำคัญสำหรับแอปพลิเคชัน **project management Java** ที่มีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอน ตรวจสอบให้คุณมี:

1. Java Development Kit (JDK) ติดตั้งบนระบบของคุณ  
2. ไลบรารี Aspose.Tasks for Java ดาวน์โหลดและเพิ่มเข้าในโปรเจคของคุณ สามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/tasks/java/)  

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น ให้นำเข้าแพ็กเกจที่จำเป็นในคลาส Java ของคุณ:
```java
import com.aspose.tasks.*;
```

## ตั้งค่าการคำนวณอัตโนมัติอย่างไร?
การตั้งค่าโหมดคำนวณเป็นอัตโนมัติทำให้การเปลี่ยนแปลงใด ๆ กับงานหรือการเชื่อมโยงจะอัปเดตตารางเวลาโดยทันที รวมถึง critical path ด้วย
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์ข้อมูล
กำหนดพาธไปยังโฟลเดอร์ที่มีไฟล์ MS Project ของคุณ
```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์ MS Project
โหลดไฟล์โปรเจคที่มีอยู่ (เช่น *New project 2013.mpp*) ด้วย Aspose.Tasks
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### ขั้นตอนที่ 3: เพิ่มงาน
สร้างงานย่อยสามงานง่าย ๆ ที่เราจะเชื่อมโยงต่อไป
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### ขั้นตอนที่ 4: สร้างการเชื่อมโยงงาน (create task dependencies)
กำหนดการเชื่อมโยงระหว่างงาน ที่นี่เราใช้ลิงก์ Finish‑to‑Start ซึ่งเป็นประเภทที่พบบ่อยที่สุด
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### ขั้นตอนที่ 5: แสดง Critical Path (display critical path)
ดึงและพิมพ์ critical path เมธอด `getCriticalPath()` จะคืนรายการงานที่เป็นส่วนหนึ่งของสายสำคัญ
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### ขั้นตอนที่ 6: ยืนยันการเสร็จสิ้น
แสดงข้อความยินดีเมื่อกระบวนการเสร็จสมบูรณ์
```java
System.out.println("Process completed Successfully");
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **Critical path ว่างเปล่า** | ตรวจสอบให้แน่ใจว่าได้ตั้ง `CalculationMode.Automatic` ก่อนเพิ่มลิงก์ |
| **งานไม่ถูกเชื่อมโยง** | ยืนยันว่าคุณได้เพิ่มอ็อบเจ็กต์ `TaskLink` สำหรับแต่ละการเชื่อมโยง |
| **ข้อยกเว้นไลเซนส์** | โหลดไลเซนส์ Aspose.Tasks ที่ถูกต้องก่อนสร้างอินสแตนซ์ `Project` |

## คำถามที่พบบ่อย
### ถ: สามารถใช้ Aspose.Tasks for Java กับไฟล์ MS Project เวอร์ชันใดก็ได้หรือไม่?
ค: ใช่ Aspose.Tasks for Java รองรับไฟล์ MS Project หลากหลายเวอร์ชัน รวมถึงไฟล์ .mpp ตั้งแต่ MS Project 2003 ถึง MS Project 2019  

### ถ: มีรุ่นทดลองฟรีสำหรับ Aspose.Tasks for Java หรือไม่?
ค: มี คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้จาก [ที่นี่](https://releases.aspose.com/)  

### ถ: จะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
ค: คุณสามารถหาแหล่งสนับสนุนได้ที่ [ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)  

### ถ: สามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks for Java ได้หรือไม่?
ค: ได้ คุณสามารถซื้อไลเซนส์ชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)  

### ถ: จะซื้อ Aspose.Tasks for Java ได้อย่างไร?
ค: คุณสามารถซื้อ Aspose.Tasks for Java ได้จากเว็บไซต์ [ที่นี่](https://purchase.aspose.com/buy)  

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณได้ **สร้างการเชื่อมโยงงาน**, ตั้งค่า **การคำนวณอัตโนมัติ**, และ **แสดง critical path** ของไฟล์ MS Project เรียบร้อยแล้ว กระบวนการนี้ให้คุณควบคุมตรรกะของตารางเวลาอย่างเต็มที่และช่วยให้โครงการของคุณเดินหน้าได้อย่างมีประสิทธิภาพด้วยโค้ด **project management** บน Java

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบกับ:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}