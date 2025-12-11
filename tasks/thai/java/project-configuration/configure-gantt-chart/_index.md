---
date: 2025-12-09
description: เรียนรู้วิธีตั้งค่าไดเรกทอรีข้อมูลและกำหนดค่าการแสดงแผนภูมิแกนท์ใน Aspose.Tasks
  ด้วย Java คู่มือนี้ยังแสดงวิธีปรับแต่งฟิลด์ตารางและกำหนดค่าโครงการ Java ของแผนภูมิแกนท์แบบทีละขั้นตอน
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ตั้งค่าไดเรกทอรีข้อมูลสำหรับมุมมองแผนภูมิแกนท์ใน Aspose.Tasks
url: /th/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าไดเรกทอรีข้อมูลสำหรับมุมมองแผนภูมิ Gantt ใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีตั้งค่าไดเรกทอรีข้อมูล** และกำหนดค่ามุมมองแผนภูมิ Gantt MS Project ในโครงการ Aspose.Tasks ด้วย Java. Aspose.Tasks เป็น Java API ที่แข็งแรงซึ่งช่วยให้คุณจัดการไฟล์ Microsoft Project อย่างอัตโนมัติ. เมื่อจบคู่มือคุณจะสามารถ **ปรับแต่งฟิลด์ตาราง**, ปรับไดเรกทอรีข้อมูล, และแสดงผลโครงการของคุณตามที่ต้องการได้.

## คำตอบอย่างรวดเร็ว
- **ขั้นตอนแรกคืออะไร?** ตั้งค่าพาธของไดเรกทอรีข้อมูลที่ไฟล์โครงการของคุณอยู่.  
- **ต้องใช้ไลบรารีใด?** Aspose.Tasks สำหรับ Java (ดาวน์โหลดได้จากเว็บไซต์ทางการ).  
- **ฉันสามารถเพิ่มแอตทริบิวต์ที่กำหนดเองได้หรือไม่?** ได้ – คุณสามารถกำหนดแอตทริบิวต์ขยายและแสดงในแผนภูมิ Gantt.  
- **ต้องการใบอนุญาตสำหรับการทดสอบหรือไม่?** มีใบอนุญาตชั่วคราวสำหรับการประเมิน.  
- **IDE ใดที่เหมาะสมที่สุด?** IDE Java ใดก็ได้ (IntelliJ IDEA, Eclipse, NetBeans) จะทำงานได้.

## อะไรคือ “ตั้งค่าไดเรกทอรีข้อมูล” และทำไมจึงสำคัญ?
การตั้งค่าไดเรกทอรีข้อมูลบอก Aspose.Tasks ว่าจะอ่านและเขียนไฟล์โครงการที่ใด. หากไม่มีพาธที่ถูกต้อง API จะไม่สามารถค้นหาไฟล์ `.mpp` ของคุณได้ ทำให้เกิดข้อผิดพลาด FileNotFound. การกำหนดไดเรกทอรีนี้ตั้งแต่ต้นของโค้ดทำให้ขั้นตอนการทำงานต่อไปสะอาดและทำซ้ำได้.

## ทำไมต้องปรับแต่งฟิลด์ตารางในแผนภูมิ Gantt?
ฟิลด์ตารางที่กำหนดเองช่วยให้คุณแสดงข้อมูลเพิ่มเติม—เช่นแอตทริบิวต์ที่กำหนดเอง, ข้อมูลทรัพยากร, หรือบันทึกเฉพาะโครงการ—โดยตรงในมุมมอง Gantt. สิ่งนี้ทำให้แผนภูมิมีข้อมูลที่ชัดเจนยิ่งขึ้นสำหรับผู้มีส่วนได้ส่วนเสียและลดความจำเป็นในการสลับระหว่างรายงานหลายฉบับ.

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่ม, ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชันล่าสุดใดก็ได้ (8+).  
2. **Aspose.Tasks Library** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไข Java ที่คุณชื่นชอบ.

## นำเข้าแพ็กเกจ
ก่อนอื่น, นำเข้า namespace ของ Aspose.Tasks เพื่อให้คุณสามารถทำงานกับคลาสของมันได้:

```java
import com.aspose.tasks.*;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดโฟลเดอร์ที่บรรจุไฟล์โครงการของคุณ. นี่คือขั้นตอน **ตั้งค่าไดเรกทอรีข้อมูล** ที่บทแนะนำมุ่งเน้นที่.

```java
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยพาธเต็มของโฟลเดอร์ที่เก็บ `project.mpp`.

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ Microsoft Project ที่มีอยู่.

```java
Project project = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 3: เพิ่มกิจกรรมใหม่
แทรกงาน (กิจกรรม) ใหม่เข้าไปในรากของโครงการ.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### ขั้นตอนที่ 4: กำหนดแอตทริบิวต์ที่กำหนดเอง
สร้างการกำหนดแอตทริบิวต์ที่กำหนดเองที่คุณสามารถแนบเข้ากับงานในภายหลัง.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### ขั้นตอนที่ 5: เพิ่มแอตทริบิวต์ที่กำหนดเองให้กับงาน
กำหนดแอตทริบิวต์ที่เพิ่งสร้างให้กับงานที่คุณสร้างขึ้น.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### ขั้นตอนที่ 6: ปรับแต่งตาราง – **customize table fields**
เพิ่มแอตทริบิวต์ที่กำหนดเองเป็นคอลัมน์ในตารางแผนภูมิ Gantt โดยระบุความกว้าง, ชื่อคอลัมน์, และการจัดตำแหน่ง.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### ขั้นตอนที่ 7: บันทึกโครงการ
บันทึกการเปลี่ยนแปลงลงในไฟล์ใหม่ที่สามารถเปิดใน Microsoft Project ได้.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **FileNotFoundException** เมื่อโหลดโครงการ | พาธ **set data directory** ไม่ถูกต้องหรือขาดสแลชท้าย. | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและรวมตัวคั่นไฟล์ที่เหมาะสม (`/` หรือ `\\`). |
| แอตทริบิวต์ที่กำหนดเองไม่แสดงในมุมมอง Gantt | ฟิลด์ตารางถูกเพิ่มที่ตำแหน่งดัชนีผิดหรือความกว้างของคอลัมน์เล็กเกินไป. | ตรวจสอบว่า `table.getTableFields().add(3, attrField);` ใช้ดัชนีที่ถูกต้องและปรับ `setWidth` ตามต้องการ. |
| LicenseException ขณะบันทึก | ไม่ได้ใช้ใบอนุญาตที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์. | ใช้ใบอนุญาตชั่วคราวหรือถาวรก่อนเรียก `project.save()`. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: ได้, Aspose.Tasks มีให้สำหรับหลายภาษาโปรแกรมรวมถึง .NET, Java, และ C++.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks หรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้จาก [here](https://releases.aspose.com/).

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
A: คุณสามารถหาแหล่งสนับสนุนและถามคำถามได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Tasks ได้อย่างไร?**  
A: คุณสามารถซื้อใบอนุญาตได้จาก [here](https://purchase.aspose.com/buy).

**Q: ฉันต้องการใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่?**  
A: ใช่, คุณสามารถรับใบอนุญาตชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/).

## สรุป
คุณได้เรียนรู้วิธี **ตั้งค่าไดเรกทอรีข้อมูล**, เพิ่มกิจกรรมใหม่, กำหนดและแนบแอตทริบิวต์ที่กำหนดเอง, และ **ปรับแต่งฟิลด์ตาราง** ในมุมมองแผนภูมิ Gantt ด้วย Aspose.Tasks สำหรับ Java. ขั้นตอนเหล่านี้ให้คุณควบคุมการแสดงผลข้อมูลโครงการได้อย่างเต็มที่ ทำให้แผนภูมิ Gantt ของคุณมีข้อมูลที่ชัดเจนและตรงกับความต้องการของผู้มีส่วนได้ส่วนเสีย.

---

**อัปเดตล่าสุด:** 2025-12-09  
**ทดสอบด้วย:** Aspose.Tasks Java 24.12 (latest)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}