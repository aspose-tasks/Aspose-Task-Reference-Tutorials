---
date: 2026-01-15
description: เรียนรู้วิธีทำงานกับต้นทุนที่กำหนดงบประมาณในงานที่กำหนดเวลาในไฟล์ Microsoft
  Project ด้วย Aspose.Tasks สำหรับ Java. ปฏิบัติตามคู่มือขั้นตอนโดยละเอียดของเรา.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: งานต้นทุนที่กำหนดงบประมาณและกำหนดเวลาโดยใช้ Aspose.Tasks สำหรับ Java
url: /th/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# งานที่กำหนดค่าใช้จ่ายตามกำหนดการ (BCWS) กับ Aspose.Tasks for Java

## บทนำ

การจัดการ **budgeted cost work scheduled** (BCWS) มีความสำคัญต่อการทำให้โครงการดำเนินไปตามแผนและทำให้การคาดการณ์ทางการเงินสอดคล้องกับงานที่วางแผนไว้ ใน Microsoft Project, BCWS แสดงจำนวนเงินที่ควรจะใช้ไปสำหรับงานที่กำหนดตามกำหนดการจนถึงวันที่ระบุ Aspose.Tasks for Java ให้คุณควบคุมค่าเหล่านี้ได้อย่างเต็มรูปแบบผ่านโปรแกรม สามารถอ่าน, แก้ไข, และรายงานค่าใช้จ่ายของทรัพยากรโดยไม่ต้องเปิดไฟล์ .mpp ด้วยตนเอง ในบทเรียนนี้เราจะเดินผ่านตัวอย่างเต็มรูปแบบที่แสดงวิธีโหลดโครงการ, วนลูปผ่านทรัพยากร, และแสดงค่า budgeted cost work scheduled พร้อมกับเมตริกค่าใช้จ่ายสำคัญอื่น ๆ

## คำตอบสั้น ๆ
- **BCWS หมายถึงอะไร?** Budgeted Cost Work Scheduled – ค่าใช้จ่ายที่วางแผนไว้สำหรับงานที่กำหนดตามกำหนดการจนถึงปัจจุบัน  
- **API property ใดที่ดึงค่า BCWS?** `Rsc.BCWS` บนวัตถุ `Resource`  
- **ต้องมีลิขสิทธิ์เพื่อรันตัวอย่างหรือไม่?** ลิขสิทธิ์ทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง  
- **สามารถแก้ไขค่า BCWS ได้หรือไม่?** ได้, คุณสามารถตั้งค่า `Rsc.BCWS` เหมือนกับฟิลด์ตัวเลขอื่น ๆ  
- **รองรับเวอร์ชันของ Project ใดบ้าง?** ทุกเวอร์ชันของ Microsoft Project ตั้งแต่ 2000 จนถึงรูปแบบ .mpp ล่าสุด

## Budgeted Cost Work Scheduled คืออะไร?

**Budgeted Cost Work Scheduled (BCWS)** เป็นการวัดผลการดำเนินงานที่สะท้อนค่าใช้จ่ายที่ควรเกิดขึ้นสำหรับงานที่วางแผนไว้จนถึงจุดเวลาหนึ่ง มันเป็นหัวใจของ Earned Value Management (EVM) และช่วยผู้จัดการโครงการเปรียบเทียบระหว่างค่าใช้จ่ายที่วางแผนกับค่าใช้จ่ายจริง

## ข้อกำหนดเบื้องต้น

ก่อนจะลงมือเขียนโค้ด, โปรดตรวจสอบว่าคุณมี:

1. ความเข้าใจพื้นฐานใน Java อย่างมั่นคง  
2. Aspose.Tasks for Java ถูกเพิ่มเข้าในโปรเจกต์ของคุณ (Maven/Gradle หรือ JAR)  
3. ไฟล์ Microsoft Project (`.mpp`) ที่มีทรัพยากรพร้อมข้อมูลค่าใช้จ่าย (เช่น *ResourceCosts.mpp*)

## นำเข้าแพ็กเกจ

เริ่มต้นด้วยการนำเข้าคลาสของ Aspose.Tasks ที่จำเป็นสำหรับการจัดการโครงการและทรัพยากร:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล

```java
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยพาธแบบเต็มหรือแบบสัมพันธ์ที่ไฟล์ *ResourceCosts.mpp* อยู่

## ขั้นตอนที่ 2: โหลดไฟล์ MS Project

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

คอนสตรัคเตอร์ `Project` จะอ่านไฟล์ .mpp และสร้างอ็อบเจกต์ในหน่วยความจำที่คุณสามารถสอบถามได้

## ขั้นตอนที่ 3: วนลูปผ่านทรัพยากร

```java
for (Resource res : prj.getResources()) {
```

ลูปนี้จะเดินผ่านทุกทรัพยากรที่กำหนดในโครงการ, ให้คุณเข้าถึงฟิลด์ค่าใช้จ่ายของแต่ละรายการ

## ขั้นตอนที่ 4: ตรวจสอบชื่อทรัพยากรและค่าใช้จ่าย

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

ภายในบล็อก `if` เราจะ:

* พิมพ์ **total cost** (`Rsc.COST`)  
* พิมพ์ **actual cost of work performed** (`Rsc.ACWP`)  
* พิมพ์ **budgeted cost work scheduled** (`Rsc.BCWS`) – เมตริกหลักที่เรามุ่งเน้น  
* พิมพ์ **budgeted cost work performed** (`Rsc.BCWP`)

สี่ค่าดังกล่าวให้ภาพรวมอย่างรวดเร็วเกี่ยวกับสถานะการเงินของโครงการ

## ทำไมการตรวจสอบ budgeted cost work scheduled จึงสำคัญ

* **การเตือนล่วงหน้า:** หาก BCWS สูงกว่าค่าใช้จ่ายจริงอย่างมีนัยสำคัญ, คุณอาจกำลังจัดสรรทรัพยากรเกินความจำเป็น  
* **การวิเคราะห์ Earned Value:** BCWS เป็นข้อมูลสำคัญสำหรับการคำนวณ Cost Variance (CV) และ Schedule Variance (SV)  
* **การคาดการณ์:** ข้อมูล BCWS ที่แม่นยำช่วยทำนายความต้องการเงินสดในอนาคตและสนับสนุนการรายงานต่อผู้มีส่วนได้ส่วนเสีย

## ปัญหาที่พบบ่อยและการแก้ไข

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| `null` printed for BCWS | Resource has no cost rate table defined | Define a cost rate table for the resource in Microsoft Project or set it programmatically via `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` when iterating resources | Project file corrupted or contains empty resource entries | Validate the .mpp file in Microsoft Project and remove empty resources |
| Unexpected values (e.g., negative BCWS) | Custom fields overriding standard cost fields | Ensure you’re accessing the standard `Rsc.BCWS` and not a custom field with the same name |

## คำถามที่พบบ่อย

**Q: สามารถอัปเดตค่า BCWS ผ่านโปรแกรมได้หรือไม่?**  
A: ได้. ใช้ `res.set(Rsc.BCWS, newValue)` แล้วบันทึกโครงการด้วย `prj.save("Updated.mpp")`.

**Q: Aspose.Tasks รองรับโครงการหลายสกุลเงินหรือไม่?**  
A: แน่นอน. ฟิลด์ค่าใช้จ่ายจะเคารพการตั้งค่าสกุลเงินที่กำหนดในไฟล์ Project

**Q: มีวิธีส่งออกเมตริกค่าใช้จ่ายเหล่านี้เป็น CSV หรือไม่?**  
A: คุณสามารถวนลูปผ่านทรัพยากรและเขียนค่าลงใน `StringBuilder` หรือใช้ไลบรารี CSV เพื่อสร้างไฟล์

**Q: BCWS แตกต่างจาก BCWP อย่างไร?**  
A: BCWS คือค่าใช้จ่ายที่วางแผนสำหรับงานที่กำหนดตามกำหนดการ, ส่วน BCWP (Budgeted Cost Work Performed) แสดงค่าใช้จ่ายที่วางแผนสำหรับงานที่ทำเสร็จแล้วจริง ๆ

**Q: ต้องมีลิขสิทธิ์พิเศษเพื่ออ่านข้อมูลค่าใช้จ่ายหรือไม่?**  
A: ลิขสิทธิ์ทดลองให้การเข้าถึงแบบอ่าน/เขียนเต็มรูปแบบ; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต

## สรุป

ด้วยการใช้ Aspose.Tasks for Java คุณจะได้เข้าถึง **budgeted cost work scheduled** และเมตริกค่าใช้จ่ายสำคัญอื่น ๆ อย่างแม่นยำผ่านโปรแกรม ซึ่งช่วยให้คุณสร้างแดชบอร์ดแบบกำหนดเอง, อัตโนมัติรายงาน Earned Value, และทำให้โครงการของคุณอยู่ในเส้นทางการเงินที่ถูกต้อง—ทั้งหมดโดยไม่ต้องโต้ตอบกับ Microsoft Project ด้วยตนเอง

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-15  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest)  
**ผู้เขียน:** Aspose