---
date: 2026-01-28
description: เรียนรู้วิธีอ่านแอตทริบิวต์งานที่ขยายโดยใช้ Aspose.Tasks สำหรับ Java
  และสลับประเภทฟิลด์กำหนดเองอย่างมีประสิทธิภาพ
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: อ่านคุณลักษณะงานที่ขยายด้วย Aspose.Tasks สำหรับ Java
url: /th/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านคุณลักษณะงานที่ขยายด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำเชิงลึกนี้คุณจะได้ค้นพบวิธี **อ่านคุณลักษณะงานที่ขยาย** จากไฟล์ Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะกำลังสร้างเครื่องมือรายงาน, ซิงโครไนซ์ข้อมูล, หรือเพียงต้องการข้อมูลเชิงลึกเพิ่มเติมจากฟิลด์ที่กำหนดเอง การเชี่ยวชาญคุณลักษณะนี้จะทำให้คุณสามารถดึงข้อมูลทุกส่วนที่เก็บไว้ในโปรเจกต์ได้ เราจะเดินผ่านขั้นตอนการตั้งค่าที่จำเป็น, แสดงวิธีสลับประเภทฟิลด์ที่กำหนดเองเมื่อประมวลผลคุณลักษณะ, และให้เคล็ดลับปฏิบัติเพื่อหลีกเลี่ยงข้อผิดพลาดทั่วไป

## คำตอบสั้น
- **“อ่านคุณลักษณะงานที่ขยาย” หมายถึงอะไร?** หมายถึงการสกัดค่าฟิลด์ที่กำหนดเองที่เกินกว่าคุณสมบัติงานเริ่มต้นในไฟล์ Project  
- **คลาสใดให้เข้าถึงคุณลักษณะเหล่านี้?** คลาส `ExtendedAttribute` ใน Aspose.Tasks  
- **ต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถเปลี่ยนประเภทคุณลักษณะได้ขณะรันไทม์หรือไม่?** ได้ – ใช้คำสั่ง `switch` เพื่อ **สลับประเภทฟิลด์ที่กำหนดเอง** ตาม `CustomFieldType`  
- **รองรับ Java 8 ขึ้นไปหรือไม่?** แน่นอน, API รองรับ JDK 8+

## คุณลักษณะงานที่ขยายคืออะไร?
คุณลักษณะงานที่ขยายคือฟิลด์ที่ผู้ใช้กำหนดเอง (ข้อความ, วันที่, ตัวเลข, ธง, ฯลฯ) ที่เสริมคุณสมบัติงานมาตรฐานใน Microsoft Project Aspose.Tasks เปิดเผยฟิลด์เหล่านี้ผ่านคอลเลกชัน `ExtendedAttribute` ที่แนบกับอ็อบเจ็กต์ `Task` แต่ละตัว, ทำให้คุณสามารถอ่านหรือแก้ไขค่าของมันได้โดยโปรแกรม

## ทำไมต้องอ่านคุณลักษณะงานที่ขยาย?
- **มองเห็นทั้งหมด:** เข้าใจข้อมูลที่ผู้มีส่วนได้ส่วนเสียเพิ่มเข้าไปในตารางเวลา  
- **อัตโนมัติ:** เติมข้อมูลแดชบอร์ด, สร้างรายงานที่กำหนดเอง, หรือย้ายข้อมูลไปยังระบบอื่นโดยไม่ต้องส่งออกด้วยมือ  
- **ยืดหยุ่น:** ทำงานกับฟิลด์ที่กำหนดเองทุกประเภท—ข้อความ, วันที่, ระยะเวลา, ค่าใช้จ่าย, ธง—โดยจัดการแต่ละกรณีอย่างเหมาะสม

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:
- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็นสำหรับโครงการ Aspose.Tasks:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## ขั้นตอนที่ 1: การเข้าถึง Task และคุณลักษณะที่ขยาย
โหลดไฟล์ Project และวนลูปผ่านแต่ละงานเพื่อเข้าถึงคุณลักษณะที่ขยายของมัน:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## ขั้นตอนที่ 2: การดึงค่า Field ID และ Value GUID
พิมพ์ตัวระบุภายในที่ช่วยให้คุณเข้าใจว่าฟิลด์ที่กำหนดเองใดกำลังทำงานอยู่:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## ขั้นตอนที่ 3: วิธีสลับประเภทฟิลด์ที่กำหนดเองเมื่ออ่านคุณลักษณะงานที่ขยาย
ใช้คำสั่ง `switch` บน `CustomFieldType` เพื่อจัดการแต่ละประเภทข้อมูลอย่างถูกต้อง:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

ทำซ้ำขั้นตอนเหล่านี้สำหรับทุกงานในโปรเจกต์ของคุณเพื่อสำรวจและจัดการคุณลักษณะงานที่ขยายทั้งหมด

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Solution |
|-------|----------|
| **Null values returned** | Verify that the custom field is actually populated in the source .mpp file. |
| **Incorrect type displayed** | Ensure you are using the correct `CustomFieldType` in the `switch` statement; mismatched types will cause default values. |
| **Performance slowdown on large projects** | Process tasks in batches or filter only the tasks you need by using `project.getRootTask().getChildren().stream()` with appropriate predicates. |

## คำถามที่พบบ่อย
### ฉันสามารถแก้ไขคุณลักษณะงานที่ขยายโดยโปรแกรมได้หรือไม่?
ได้, คุณสามารถแก้ไขคุณลักษณะงานที่ขยายโดยใช้ Aspose.Tasks สำหรับ Java ดูเอกสารสำหรับคำแนะนำโดยละเอียด

### มีเวอร์ชันทดลองหรือไม่?
มี, คุณสามารถเข้าถึงเวอร์ชันทดลองได้ **[ที่นี่](https://releases.aspose.com/)**

### จะหาการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?
สำหรับการสนับสนุน, เยี่ยมชม **[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)**

### จะขอรับลิขสิทธิ์ชั่วคราวได้อย่างไร?
คุณสามารถขอรับลิขสิทธิ์ชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)**

### จะซื้อเวอร์ชันเต็ม.Tasks สำหรับ Java ได้จากที่ไหน?
คุณสามารถซื้อเวอร์ชันเต็ม **[ที่นี่](https://purchase.aspose.com/buy)**

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks Java API (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}