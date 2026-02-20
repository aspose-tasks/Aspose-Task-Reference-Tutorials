---
date: 2026-02-20
description: เรียนรู้วิธีคำนวณความแปรผันของต้นทุนโครงการและจัดการค่าใช้จ่ายของงานใน
  Java ด้วย Aspose.Tasks ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อกำหนดค่าใช้จ่ายและควบคุมงบประมาณ.
linktitle: Manage Task Costs in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: คำนวณส่วนต่างต้นทุนโครงการด้วย Aspose.Tasks สำหรับ Java
url: /th/java/task-properties/manage-task-cost/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# คำนวณส่วนต่างต้นทุนโครงการด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำที่ครอบคลุมนี้ คุณจะได้ค้นพบ **วิธีการคำนวณส่วนต่างต้นทุนโครงการ** และจัดการต้นทุนงานอย่างมีประสิทธิภาพภายในแอปพลิเคชัน Java ของคุณด้วย Aspose.Tasks ไม่ว่าคุณจะติดตามโครงการภายในขนาดเล็กหรือการเปิดตัวระดับองค์กรขนาดใหญ่ การเข้าใจส่วนต่างต้นทุนจะช่วยให้คุณควบคุมงบประมาณและตรวจจับการใช้จ่ายเกินกำหนดได้ตั้งแต่เนิ่นๆ

## คำตอบอย่างรวดเร็ว
- **ส่วนต่างต้นทุนคืออะไร?** ความแตกต่างระหว่างต้นทุนที่วางแผนไว้ (คงที่) กับต้นทุนจริง (ที่เหลืออยู่).  
- **เมธอด API ใดที่ตั้งค่าต้นทุนของงาน?** `task.set(Tsk.COST, BigDecimal.valueOf(...))`.  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีสามารถใช้สำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถดึงข้อมูลต้นทุนระดับโครงการได้หรือไม่?** ได้โดยการเข้าถึงคุณสมบัติต้นทุนของงานราก.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Aspose.Tasks ทำงานกับ Java 8 และใหม่กว่า.

## ส่วนต่างต้นทุนโครงการคืออะไร?
การคำนวณส่วนต่างต้นทุนโครงการหมายถึงการเปรียบเทียบ **ต้นทุนคงที่** ที่คุณวางแผนไว้ตั้งแต่แรกสำหรับงานหรือโครงการกับ **ต้นทุนที่เหลืออยู่** ซึ่งสะท้อนงานที่ยังต้องทำส่วนต่างนี้บอกคุณว่าตรงกับงบประมาณหรือเกินงบประมาณ เพื่อให้สามารถปรับเปลี่ยนได้อย่างเชิงรุก

## ทำไมต้องใช้ Aspose.Tasks เพื่อคำนวณส่วนต่างต้นทุนโครงการ?
- **API Java ที่ไม่ต้องพึ่งพา .NET** – ไม่ต้องใช้ไลบรารีเนทีฟ.  
- **คุณสมบัติการจัดการต้นทุนที่ครบครัน** (`COST`, `FIXED_COST`, `REMAINING_COST`, `COST_VARIANCE`).  
- **การบูรณาการที่ง่าย** กับโครงการ Maven/Gradle ที่มีอยู่แล้ว.  
- **การรายงานที่แม่นยำ** ที่สามารถส่งออกเป็นไฟล์ MS Project®.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – ติดตั้ง Java 8 หรือใหม่กว่า.  
2. **ไลบรารี Aspose.Tasks for Java** – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ **[ที่นี่](https://releases.aspose.com/tasks/java/)**.  
3. IDE หรือเครื่องมือสร้าง (IntelliJ, Eclipse, Maven, Gradle) เพื่อคอมไพล์และรันโค้ดตัวอย่าง.

## การนำเข้าแพ็กเกจ
เพิ่มคลาส Aspose.Tasks ที่จำเป็นลงในไฟล์ซอร์ส Java ของคุณเพื่อให้สามารถทำงานกับโครงการและงานได้

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Import Aspose.Tasks classes
```

## คู่มือแบบทีละขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
แรกสุด สร้างอินสแตนซ์ `Project` ใหม่และระบุโฟลเดอร์ที่คุณอาจเก็บไฟล์ที่สร้างขึ้น

```java
// Set the path to your document directory
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project();
```

### ขั้นตอนที่ 2: เพิ่มงานใหม่
เพิ่มงานภายใต้งานราก นี่คือที่เราจะกำหนดต้นทุน

```java
// Add a new task to the root task
Task task = project.getRootTask().getChildren().add("Task");
```

### ขั้นตอนที่ 3: ตั้งค่าต้นทุนของงาน – **วิธีตั้งค่าต้นทุน**
กำหนดต้นทุนที่วางแผนไว้ให้กับงาน ในสถานการณ์จริงอาจมาจากสเปรดชีตการจัดทำงบประมาณ

```java
// Set the task cost to 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```

### ขั้นตอนที่ 4: ดึงและแสดงข้อมูลต้นทุน – **วิธีจัดการต้นทุน**
ต่อไปเราจะอ่านคืนคุณสมบัติต้นทุนต่าง ๆ รวมถึงส่วนต่างต้นทุนที่คำนวณได้

```java
// Retrieve and print task information
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Retrieve and print project-level cost information
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```

**สิ่งที่คุณจะเห็น:**  
- `Remaining Cost` แสดงงานที่ยังไม่ได้ทำ.  
- `Fixed Cost` คือฐานที่คุณตั้งค่า (800 ในตัวอย่างนี้).  
- `Cost Variance` คำนวณอัตโนมัติเป็น **Fixed – Remaining**.  
- ค่าต่าง ๆ เหล่านี้สามารถเข้าถึงได้ระดับโครงการ (งานราก) ทำให้คุณ **คำนวณส่วนต่างต้นทุนโครงการ** ทั้งหมดได้

### ขั้นตอนที่ 5: ทำซ้ำสำหรับงานเพิ่มเติม (ไม่บังคับ)
หากโครงการของคุณมีหลายเฟส ให้ทำซ้ำขั้นตอน 2‑4 สำหรับแต่ละงาน การรวมส่วนต่างแต่ละรายการจะให้ส่วนต่างต้นทุนโครงการโดยรวม

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| `NullPointerException` เมื่อเข้าถึงคุณสมบัติของงาน | งานไม่ได้ถูกเพิ่มเข้าไปในโครงสร้างโครงการ | ตรวจสอบให้เรียก `project.getRootTask().getChildren().add(...)` ก่อนตั้งค่าต้นทุน. |
| ค่าต้นทุนแสดงเป็น `0` | ใช้ `int` แทน `BigDecimal` | ควรใช้ `BigDecimal.valueOf(...)` เสมอ ตามที่แสดง |
| ส่วนต่างที่ไม่คาดคิด (เป็นลบ) | `REMAINING_COST` มากกว่า `FIXED_COST`. | ตรวจสอบว่าคุณอัปเดตต้นทุนที่เหลือเมื่อทำงานต่อเนื่อง. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถหาเอกสารสำหรับ Aspose.Tasks for Java ได้ที่ไหน?**  
A: คุณสามารถเข้าถึงเอกสารได้ **[ที่นี่](https://reference.aspose.com/tasks/java/)**.

**Q: ฉันจะดาวน์โหลดไลบรารี Aspose.Tasks for Java ได้อย่างไร?**  
A: ดาวน์โหลดไลบรารีได้ **[ที่นี่](https://releases.aspose.com/tasks/java/)**.

**Q: ฉันสามารถซื้อ Aspose.Tasks for Java ได้ที่ไหน?**  
A: คุณสามารถซื้อได้ **[ที่นี่](https://purchase.aspose.com/buy)**.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: ใช่ คุณสามารถรับการทดลองใช้ฟรี **[ที่นี่](https://releases.aspose.com/)**.

**Q: ฉันสามารถขอรับการสนับสนุนสำหรับ Aspose.Tasks for Java ได้ที่ไหน?**  
A: เยี่ยมชมฟอรั่มสนับสนุน **[ที่นี่](https://forum.aspose.com/c/tasks/15)**.

---

**อัปเดตล่าสุด:** 2026-02-20  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}