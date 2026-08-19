---
date: 2026-02-28
description: เรียนรู้วิธีจัดการงบประมาณ งาน และค่าใช้จ่ายสำหรับงานในโครงการ Java ด้วย
  Aspose.Tasks คู่มือนี้ยังแสดงวิธีคำนวณค่าใช้จ่ายของงานอย่างมีประสิทธิภาพ
linktitle: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีจัดการงบประมาณ งาน และค่าใช้จ่ายใน Aspose.Tasks Java
url: /th/java/task-properties/task-budget-work-cost/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีจัดการงบประมาณ งาน และค่าใช้จ่ายใน Aspose.Tasks Java

การจัดการการเงินของโครงการเป็นหน้าที่หลักของผู้จัดการโครงการทุกคน ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีจัดการงบประมาณ** สำหรับ tasks, work, และ resources โดยใช้ Aspose.Tasks Java API และยังจะเห็นวิธี **คำนวณค่าใช้จ่ายของงาน** เมื่อคุณต้องการรายงานการเงินที่แม่นยำ เมื่อจบคู่มือคุณจะสามารถอ่าน แสดง และจัดการฟิลด์ที่เกี่ยวกับงบประมาณโดยตรงจากไฟล์ Microsoft Project ของคุณได้

## คำตอบอย่างรวดเร็ว
- **“budget work” หมายถึงอะไร?** จำนวนงาน (เป็นชั่วโมง) ที่จัดสรรให้กับงานหรือทรัพยากร.  
- **ฉันสามารถดึงค่าใช้จ่ายงบประมาณโดยโปรแกรมได้หรือไม่?** ใช่ โดยใช้ฟิลด์ `BUDGET_COST` บน tasks, resources, หรือ assignments.  
- **ฉันต้องการไลเซนส์สำหรับ Aspose.Tasks หรือไม่?** จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง; มีรุ่นทดลองฟรีให้ใช้.  
- **เวอร์ชัน Java ใดที่รองรับ?** Aspose.Tasks ทำงานกับ Java 8 และใหม่กว่า.  
- **สามารถคำนวณค่าใช้จ่ายของงานจากการมอบหมายได้หรือไม่?** แน่นอน – ให้รวมค่าของ `BUDGET_COST` ของการมอบหมายแต่ละรายการ.

## การจัดการงบประมาณใน Aspose.Tasks คืออะไร?
Aspose.Tasks เก็บข้อมูลงบประมาณในฟิลด์เฉพาะ (`BUDGET_WORK`, `BUDGET_COST`) สำหรับ tasks, resources, และ assignments ฟิลด์เหล่านี้ช่วยให้คุณวางแผนความพยายามและค่าใช้จ่ายทางการเงินที่คาดว่าจะเกิดขึ้นก่อนที่งานใดจะเริ่มทำ ทำให้สามารถพยากรณ์และวิเคราะห์ความแตกต่างได้อย่างแม่นยำ

## ทำไมต้องคำนวณค่าใช้จ่ายของงาน?
การคำนวณค่าใช้จ่ายของงานช่วยให้คุณ:
- ติดตามผลการเงินเทียบกับประมาณการต้นฉบับ
- สร้างรายงานตามค่าใช้จ่ายสำหรับผู้มีส่วนได้ส่วนเสีย
- ระบุงานที่ใช้เกินงบประมาณตั้งแต่เนิ่นๆ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด ให้แน่ใจว่าคุณมี:

- สภาพแวดล้อมการพัฒนา Java (JDK 8+).
- ไลบรารี Aspose.Tasks for Java – ดาวน์โหลดได้ **[here](https://releases.aspose.com/tasks/java/)**.
- ไฟล์ตัวอย่าง Microsoft Project (เช่น `BudgetWorkAndCost.mpp`) ที่วางไว้ในไดเรกทอรีที่รู้จัก

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ ให้เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็น ซึ่งจะทำให้คุณเข้าถึงฟังก์ชันของ Aspose.Tasks ได้ รวมบรรทัดต่อไปนี้ไว้ที่ส่วนเริ่มต้นของไฟล์ Java ของคุณ:
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

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
เริ่มต้นโดยตั้งค่าพาธไปยังไดเรกทอรีเอกสารของคุณ ซึ่งเป็นที่เก็บไฟล์โปรเจกต์ของคุณ
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: โหลดโปรเจกต์
โหลดไฟล์โปรเจกต์โดยใช้ไลบรารี Aspose.Tasks แทนที่ `"BudgetWorkAndCost.mpp"` ด้วยชื่อไฟล์โปรเจกต์ของคุณ
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```

## ขั้นตอนที่ 3: ดึงข้อมูลงบประมาณของโปรเจกต์และทรัพยากร
ดึงและแสดงงบประมาณระดับโปรเจกต์และระดับทรัพยากร ขั้นตอนนี้จะแสดงวิธี **คำนวณค่าใช้จ่ายของงาน** โดยการอ่านค่าที่จัดเก็บไว้
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```

## ขั้นตอนที่ 4: แสดงงบประมาณการมอบหมาย
วนลูปผ่านการมอบหมายของงานสรุป (หรืองานใดๆ) และแสดงข้อมูลงบประมาณของแต่ละการมอบหมาย ซึ่งทำให้คุณเห็นค่าใช้จ่ายที่จัดสรรให้แต่ละทรัพยากร
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```

## ปัญหาทั่วไป & เคล็ดลับมืออาชีพ
- **ค่า null:** หากฟิลด์งบประมาณคืนค่า `null` ไฟล์โปรเจกต์อาจไม่มีข้อมูลนั้น ใช้การตรวจสอบ `project.getRootTask().get(Tsk.BUDGET_WORK) != null` ก่อนทำการพิมพ์
- **UID ไม่ถูกต้อง:** ตรวจสอบให้แน่ใจว่า UID ของทรัพยากรที่คุณเรียก (`getByUid(2)`) มีอยู่; หากไม่จะเกิด `NullPointerException`
- **การจัดรูปแบบสกุลเงิน:** `BUDGET_COST` คืนค่าเป็น double ดิบ ให้จัดรูปแบบโดยใช้ `NumberFormat.getCurrencyInstance()` เพื่อแสดงผลที่เป็นมิตรกับผู้ใช้

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks for Java กับเฟรมเวิร์ก Java อื่นได้หรือไม่?**  
A: ใช่, Aspose.Tasks for Java เข้ากันได้กับเฟรมเวิร์ก Java ต่างๆ ทำให้การผสานรวมมีความยืดหยุ่น

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีของ Aspose.Tasks for Java **[here](https://releases.aspose.com/)**.

**Q: ฉันจะหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: สำรวจฟอรั่มชุมชน Aspose.Tasks **[here](https://forum.aspose.com/c/tasks/15)** เพื่อรับการสนับสนุนและการสนทนา

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks for Java ได้อย่างไร?**  
A: รับไลเซนส์ชั่วคราว **[here](https://purchase.aspose.com/temporary-license/)** เพื่อการทดสอบและประเมินผล

**Q: มีแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: ดูเอกสาร **[here](https://reference.aspose.com/tasks/java/)** เพื่อข้อมูลเชิงลึกและตัวอย่าง

---

**อัปเดตล่าสุด:** 2026-02-28  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}