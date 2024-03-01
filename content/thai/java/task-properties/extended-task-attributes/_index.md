---
title: คุณสมบัติงานเพิ่มเติมใน Aspose.Tasks
linktitle: คุณสมบัติงานเพิ่มเติมใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจคุณลักษณะของงานเพิ่มเติมใน Aspose.Tasks สำหรับ Java คำแนะนำทีละขั้นตอน คำถามที่พบบ่อย และการสนับสนุน เพิ่มประสิทธิภาพการจัดการโครงการของคุณวันนี้!
type: docs
weight: 16
url: /th/java/task-properties/extended-task-attributes/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมของเราเกี่ยวกับการใช้ประโยชน์จากคุณลักษณะของงานเพิ่มเติมใน Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังที่ช่วยให้คุณทำงานกับเอกสาร Microsoft Project ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกคุณลักษณะของงานเพิ่มเติม และสาธิตวิธีที่คุณสามารถใช้เพื่อปรับปรุงความสามารถในการจัดการโครงการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ หรือ Eclipse
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นโปรเจ็กต์ Aspose.Tasks ของคุณ:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
ตอนนี้ เราจะแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการ:
## ขั้นตอนที่ 1: การเข้าถึงงานและคุณสมบัติเพิ่มเติม
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## ขั้นตอนที่ 2: การดึง ID ฟิลด์และ GUID ค่า
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## ขั้นตอนที่ 3: การจัดการแอตทริบิวต์ประเภทต่างๆ
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
ทำซ้ำขั้นตอนเหล่านี้สำหรับแต่ละงานในโครงการของคุณเพื่อสำรวจและจัดการคุณลักษณะของงานเพิ่มเติม
## บทสรุป
โดยสรุป การทำความเข้าใจและการใช้ประโยชน์จากคุณลักษณะของงานเพิ่มเติมใน Aspose.Tasks สำหรับ Java จะช่วยเพิ่มความสามารถในการจัดการโครงการของคุณได้อย่างมาก คู่มือนี้เป็นรากฐานที่มั่นคงเพื่อให้คุณเริ่มต้นการเดินทางครั้งนี้
## คำถามที่พบบ่อย
### ฉันสามารถแก้ไขคุณลักษณะของงานเพิ่มเติมโดยทางโปรแกรมได้หรือไม่
ใช่ คุณสามารถแก้ไขคุณลักษณะของงานเพิ่มเติมได้โดยใช้ Aspose.Tasks สำหรับ Java โปรดดูเอกสารประกอบสำหรับคำแนะนำโดยละเอียด
### มีรุ่นทดลองใช้งานหรือไม่?
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 สำหรับการสนับสนุนโปรดไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.Tasks สำหรับ Java เวอร์ชันเต็มได้ที่ไหน
 คุณสามารถซื้อเวอร์ชันเต็มได้[ที่นี่](https://purchase.aspose.com/buy).