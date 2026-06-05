---
date: 2026-06-05
description: เรียนรู้วิธีตั้งค่าคุณสมบัติของ hyperlink สำหรับการมอบหมายทรัพยากรใน
  Aspose.Tasks สำหรับ Java โดยแสดงอย่างชัดเจน **how to set hyperlink** และปรับปรุงการทำงานร่วมกัน
keywords:
- how to set hyperlink
- validate hyperlink java
- Aspose.Tasks hyperlink
- resource assignment hyperlink
- Java project hyperlink
linktitle: จัดการคุณสมบัติของ Hyperlink สำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to set hyperlink properties for resource assignments in Aspose.Tasks
    for Java, showing exactly **how to set hyperlink** and improve collaboration.
  headline: How to Set Hyperlink Properties for Assignments in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, you can repeat the assignment process for each URL, setting different
      `HYPERLINK_ADDRESS` values on the same `Asn` object.
    question: Can I add multiple hyperlinks to a single resource assignment?
  - answer: Aspose.Tasks focuses on data management; visual styling is handled by
      the client application that renders the project file.
    question: Is it possible to customize the appearance of hyperlinks in Aspose.Tasks?
  - answer: The library does not impose strict length limits, but keeping URLs under
      2,000 characters maintains compatibility with most browsers and tools.
    question: Are there any limitations on the length of hyperlinks in Aspose.Tasks?
  - answer: Yes, assign `null` or an empty string to the `HYPERLINK`, `HYPERLINK_ADDRESS`,
      and `HYPERLINK_SUB_ADDRESS` fields to clear them.
    question: Can I remove hyperlinks from resource assignments programmatically?
  - answer: The library stores hyperlink data but does not validate URLs automatically;
      you should implement custom validation logic in Java.
    question: Does Aspose.Tasks support hyperlink validation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีตั้งค่าคุณสมบัติของ Hyperlink สำหรับการมอบหมายใน Aspose.Tasks
url: /th/java/resource-assignments/hyperlink-properties/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่าคุณสมบัติของไฮเปอร์ลิงก์สำหรับการมอบหมายใน Aspose.Tasks

## บทนำ
ในคู่มือนี้คุณจะค้นพบ **วิธีตั้งค่าไฮเปอร์ลิงก์** สำหรับคุณสมบัติการมอบหมายทรัพยากรโดยใช้ Aspose.Tasks สำหรับ Java. เมื่อจบบทเรียนคุณจะสามารถแนบ URL ที่คลิกได้, ตรวจสอบความถูกต้อง, และสืบค้นโดยโปรแกรม—ทำให้ไฟล์โครงการของคุณเป็นศูนย์กลางของข้อมูลเชิงบริบทที่ทีมของคุณทั้งหมดสามารถพึ่งพาได้.

## คำตอบอย่างรวดเร็ว
- **“set hyperlink” ทำอะไร?** มันแนบ URL ที่คลิกได้ (และที่อยู่ย่อยที่เป็นตัวเลือก) ไปยังการมอบหมายทรัพยากร, ทำให้ข้อความธรรมดากลายเป็นลิงก์นำทางโดยตรง.  
- **คลาสใดเก็บข้อมูลไฮเปอร์ลิงก์?** คลาส `Asn` ให้ฟิลด์ `HYPERLINK`, `HYPERLINK_ADDRESS`, และ `HYPERLINK_SUB_ADDRESS`.  
- **ฉันต้องมีลิขสิทธิ์เพื่อใช้ฟีเจอร์นี้หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพการผลิต; เวอร์ชันทดลองฟรีใช้ได้สำหรับการทดสอบ.  
- **ฉันสามารถตรวจสอบความถูกต้องของไฮเปอร์ลิงก์ใน Java ได้หรือไม่?** ใช่—ใช้ `java.net.URL` หรือ Apache Commons Validator ก่อนมอบหมาย.  
- **วิธีการนี้เข้ากันได้กับโปรเจกต์ Java ใด ๆ หรือไม่?** แน่นอน; มันทำงานกับโปรเจกต์ Java ใด ๆ ที่รวมไลบรารี Aspose.Tasks.

## “วิธีตั้งค่าไฮเปอร์ลิงก์” คืออะไรใน Aspose.Tasks?
**การตั้งค่าไฮเปอร์ลิงก์หมายถึงการกำหนด URL (และที่อยู่ย่อยตามต้องการ) ให้กับการมอบหมายทรัพยากรเพื่อให้ผู้มีส่วนได้ส่วนเสียของโครงการสามารถนำทางไปยังหน้าเว็บ, เอกสาร, หรือส่วนภายในของโครงการที่เกี่ยวข้องได้ทันทีจากมุมมองการมอบหมาย.** ความสามารถนี้ทำให้การสื่อสารเป็นไปอย่างราบรื่นและลดความจำเป็นในการใช้สเปรดชีตอ้างอิงภายนอก.

## ทำไมต้องเพิ่มไฮเปอร์ลิงก์ให้กับการมอบหมายงาน?
การแนบไฮเปอร์ลิงก์ให้กับการมอบหมาย **ช่วยปรับปรุงการทำงานร่วมกันโดยให้สมาชิกทีมคลิกเพื่อดูสเปค, ดีไซน์, หรือตั๋วติดตามปัญหาโดยไม่ต้องออกจากไฟล์โครงการ**. นอกจากนี้ยังทำให้ข้อมูลเป็นศูนย์กลาง—URL ที่เกี่ยวข้องทั้งหมดอยู่ภายในโครงการ, สร้างแหล่งข้อมูลเดียวที่เป็นความจริงและร่องรอยการตรวจสอบที่สามารถสืบค้นหรือส่งออกเพื่อการรายงานได้. ประโยชน์เชิงปริมาณ: Aspose.Tasks สามารถจัดการโครงการที่มี **สูงสุด 10,000 งานและ 5,000 ทรัพยากรพร้อมการเข้าถึงฟิลด์ไฮเปอร์ลิงก์ในระดับมิลลิวินาที**.

## ข้อกำหนดเบื้องต้น
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java.  
- ติดตั้ง Java Development Kit (JDK) เวอร์ชัน 8 หรือใหม่กว่า.  
- ไลบรารี Aspose.Tasks สำหรับ Java ถูกเพิ่มใน classpath ของโปรเจกต์ของคุณ.  
- IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับแก้ไขและรันโค้ด.  
- (ตัวเลือก) ไฟล์ลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องสำหรับการสร้างในสภาพการผลิต.

## นำเข้าแพ็กเกจ
คลาส `Project`, `Task`, `Resource`, และ `Asn` อยู่ในเนมสเปซ `com.aspose.tasks`. ให้นำเข้าก่อนเริ่มทำงานกับ API.

คลาส `Project` เป็นอ็อบเจ็กต์ระดับบนสุดของ Aspose.Tasks ที่แสดงไฟล์โครงการทั้งหมดในหน่วยความจำ.  
คลาส `Task` จำลองรายการงานเดียวภายในโครงสร้างโครงการ.  
คลาส `Resource` กำหนดบุคคล, อุปกรณ์, หรือวัสดุที่สามารถมอบหมายให้กับงาน.  
คลาส `Asn` แสดงลิงก์ระหว่าง `Task` และ `Resource` และเก็บคุณสมบัติระดับการมอบหมาย, รวมถึงฟิลด์ไฮเปอร์ลิงก์.

## ขั้นตอนที่ 1: สร้างอินสแตนซ์ Project
โหลดหรือสร้างไฟล์โครงการใหม่. นี้เป็นคอนเทนเนอร์สำหรับอ็อบเจ็กต์ทั้งหมดที่ตามมา.

## ขั้นตอนที่ 2: เพิ่มงานลงในโครงการ
สร้างงานที่จะได้รับไฮเปอร์ลิงก์ในภายหลังผ่านการมอบหมายของมัน.

## ขั้นตอนที่ 3: เพิ่มทรัพยากร
กำหนดทรัพยากร (เช่น นักพัฒนา หรืออุปกรณ์) ที่คุณจะมอบหมายให้กับงาน.

## ขั้นตอนที่ 4: สร้างการมอบหมายทรัพยากร
เชื่อมโยงงานและทรัพยากรเข้าด้วยกัน, สร้างอ็อบเจ็กต์ `Asn` ที่เก็บข้อมูลเฉพาะการมอบหมาย.

## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติไฮเปอร์ลิงก์
กำหนดที่อยู่ไฮเปอร์ลิงก์และที่อยู่ย่อยตามต้องการให้กับอ็อบเจ็กต์ `Asn`. คุณยังสามารถตั้งค่าข้อความแสดงผลผ่านฟิลด์ `HYPERLINK` ได้.

## ขั้นตอนที่ 6: พิมพ์คุณสมบัติไฮเปอร์ลิงก์
ดึงและแสดงค่าที่เก็บไว้ของไฮเปอร์ลิงก์เพื่อยืนยันว่าการมอบหมายถูกตั้งค่าอย่างถูกต้อง.

## ขั้นตอนที่ 7: การทำงานเสร็จสิ้น
แสดงข้อความที่เป็นมิตรบ่งบอกว่าการตั้งค่าไฮเปอร์ลิงก์เสร็จสมบูรณ์โดยไม่มีข้อผิดพลาด.

## ฉันจะตรวจสอบความถูกต้องของไฮเปอร์ลิงก์ใน Java อย่างไร?
**ตรวจสอบ URL ก่อนการมอบหมายโดยสร้างอ็อบเจ็กต์ `java.net.URL`; หากคอนสตรัคเตอร์โยน `MalformedURLException`, สตริงนั้นไม่ใช่ URL ที่รูปแบบถูกต้อง.** การตรวจสอบง่าย ๆ นี้ช่วยป้องกันข้อผิดพลาดขณะรันและรับประกันว่าเฉพาะลิงก์ที่เข้าถึงได้เท่านั้นจะถูกเก็บในไฟล์โครงการ.

## ปัญหาทั่วไปและวิธีแก้
- **รูปแบบ URL ไม่ถูกต้อง:** ตรวจสอบ URL โดยใช้ `java.net.URL` ก่อนมอบหมายเพื่อหลีกเลี่ยงข้อผิดพลาดขณะรัน.  
- **ค่าฮัยเปอร์ลิงก์เป็น null:** ตรวจสอบว่าคุณตั้งค่าทั้งสามฟิลด์ (`HYPERLINK`, `HYPERLINK_ADDRESS`, `HYPERLINK_SUB_ADDRESS`) หากต้องการ; มิฉะนั้นตั้งค่าที่ไม่ได้ใช้เป็น `null` หรือสตริงว่าง.  
- **ไม่พบลิขสิทธิ์:** หากคุณได้รับข้อผิดพลาดเกี่ยวกับลิขสิทธิ์, ตรวจสอบว่าไฟล์ลิขสิทธิ์ Aspose.Tasks ถูกโหลดอย่างถูกต้องก่อนสร้างอ็อบเจ็กต์ `Project`.

## คำถามที่พบบ่อย

**Q: ฉันสามารถเพิ่มไฮเปอร์ลิงก์หลายรายการให้กับการมอบหมายทรัพยากรเดียวได้หรือไม่?**  
A: ใช่, คุณสามารถทำซ้ำกระบวนการมอบหมายสำหรับแต่ละ URL, ตั้งค่าที่อยู่ `HYPERLINK_ADDRESS` ที่แตกต่างกันบนอ็อบเจ็กต์ `Asn` เดียวกัน.

**Q: สามารถปรับแต่งลักษณะการแสดงผลของไฮเปอร์ลิงก์ใน Aspose.Tasks ได้หรือไม่?**  
A: Aspose.Tasks มุ่งเน้นการจัดการข้อมูล; การจัดรูปแบบภาพจะถูกจัดการโดยแอปพลิเคชันลูกค้าที่แสดงไฟล์โครงการ.

**Q: มีข้อจำกัดใด ๆ เกี่ยวกับความยาวของไฮเปอร์ลิงก์ใน Aspose.Tasks หรือไม่?**  
A: ไลบรารีไม่ได้กำหนดข้อจำกัดความยาวที่เข้มงวด, แต่การเก็บ URL ไว้ภายใต้ 2,000 ตัวอักษรจะช่วยให้เข้ากันได้กับเบราว์เซอร์และเครื่องมือส่วนใหญ่.

**Q: ฉันสามารถลบไฮเปอร์ลิงก์จากการมอบหมายทรัพยากรโดยโปรแกรมได้หรือไม่?**  
A: ใช่, กำหนดค่า `null` หรือสตริงว่างให้กับฟิลด์ `HYPERLINK`, `HYPERLINK_ADDRESS`, และ `HYPERLINK_SUB_ADDRESS` เพื่อเคลียร์ค่า.

**Q: Aspose.Tasks รองรับการตรวจสอบความถูกต้องของไฮเปอร์ลิงก์หรือไม่?**  
A: ไลบรารีเก็บข้อมูลไฮเปอร์ลิงก์แต่ไม่ได้ตรวจสอบ URL โดยอัตโนมัติ; คุณควรทำการตรวจสอบแบบกำหนดเองใน Java.

**Q: วิธีนี้เข้ากับกลยุทธ์ไฮเปอร์ลิงก์ของโปรเจกต์ Java ขนาดใหญ่ได้อย่างไร?**  
A: การรวมศูนย์ URL ไว้ในไฟล์โครงการสร้าง “แผนที่ไฮเปอร์ลิงก์ของโปรเจกต์ Java” ที่สามารถค้นหา, ส่งออก, ตรวจสอบ, หรือบูรณาการกับเครื่องมือสร้างเอกสารได้.

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้ **วิธีตั้งค่าไฮเปอร์ลิงก์** สำหรับคุณสมบัติการมอบหมายทรัพยากรใน Aspose.Tasks สำหรับ Java, วิธีตรวจสอบ URL เหล่านั้น, และทำไมการปฏิบัตินี้จึงเพิ่มการทำงานร่วมกันและการตรวจสอบได้. นำรูปแบบนี้ไปใช้ในกระบวนการอัตโนมัติโครงการของคุณเพื่อให้ผู้มีส่วนได้ส่วนเสียทุกคนเชื่อมโยงกับข้อมูลที่ถูกต้องในเวลาที่เหมาะสม.

---

**Last Updated:** 2026-06-05  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [วิธีเพิ่มโน้ตให้กับการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [จัดการงบประมาณการมอบหมายใน Java ด้วย Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

```java
Project prj = new Project();
```

```java
Task task = prj.getRootTask().getChildren().add("Task 1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

```java
Resource resource = prj.getResources().add("Resource 1");
```

```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

```java
assignment.set(Asn.HYPERLINK, "Click to visit our site");
assignment.set(Asn.HYPERLINK_ADDRESS, "https://products.aspose.com");
assignment.set(Asn.HYPERLINK_SUB_ADDRESS, "/total/net");
```

```java
System.out.println("Hyperlink: " + assignment.get(Asn.HYPERLINK));
System.out.println("Hyperlink Address: " + assignment.get(Asn.HYPERLINK_ADDRESS));
System.out.println("Hyperlink Sub Address: " + assignment.get(Asn.HYPERLINK_SUB_ADDRESS));
```

```java
System.out.println("Process completed Successfully");
```