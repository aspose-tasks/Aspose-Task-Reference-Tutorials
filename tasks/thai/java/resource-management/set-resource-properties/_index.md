---
date: 2026-01-18
description: เรียนรู้วิธีตั้งอัตรามาตรฐานและคุณสมบัติอื่น ๆ ของทรัพยากรใน MS Project
  ด้วย Aspose.Tasks for Java รวมถึงวิธีเพิ่มทรัพยากรใน MS Project และจัดการทรัพยากรอย่างมีประสิทธิภาพ
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีตั้งอัตรามาตรฐานสำหรับทรัพยากรใน Aspose.Tasks
url: /th/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าอัตรามาตรฐานสำหรับทรัพยากรใน Aspose.Tasks

## บทนำ
หากคุณกำลังพัฒนาแอปพลิเคชัน Java ที่ต้องโต้ตอบกับไฟล์ Microsoft Project, **การตั้งค่าอัตรามาตรฐาน** สำหรับทรัพยากรเป็นหนึ่งในงานที่พบบ่อยที่สุด ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **ตั้งค่าอัตรามาตรฐาน** และคุณสมบัติอื่น ๆ ของทรัพยากรโดยใช้ Aspose.Tasks for Java เมื่อจบคู่มือคุณจะสามารถสร้างอ็อบเจ็กต์โปรเจกต์, เพิ่มทรัพยากรลงในไฟล์ MS Project, และจัดการทรัพยากรของ MS Project ได้อย่างมั่นใจ

## คำตอบอย่างรวดเร็ว
- **คลาสหลักที่ใช้ทำงานกับไฟล์ Project คืออะไร?** `Project`
- **เมธอดใดที่เพิ่มทรัพยากรใหม่?** `project.getResources().add()`
- **จะตั้งค่าอัตรามาตรฐานอย่างไร?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในโปรดักชันหรือไม่?** ใช่, จำเป็นต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้อง
- **รองรับเวอร์ชัน Java ใด?** Java 8+ (แนะนำให้ใช้ JDK เวอร์ชันล่าสุด)

## “ตั้งค่าอัตรามาตรฐาน” คืออะไร?
การทำงาน *ตั้งค่าอัตรามาตรฐาน* จะกำหนดค่าใช้จ่ายต่อชั่วโมงเริ่มต้นให้กับทรัพยากร ผู้จัดการโครงการใช้ค่านี้เพื่อคำนวณค่าแรง, สร้างรายงานค่าใช้จ่าย, และคาดการณ์งบประมาณ

## ทำไมต้องตั้งค่าอัตราด้วย Aspose.Tasks?
- **ไม่ต้องติดตั้ง Microsoft Project** – จัดการไฟล์โดยตรงจาก Java
- **ความแม่นยำเต็มรูปแบบ** – ฟิลด์ทรัพยากรทั้งหมด รวมถึงค่าโอเวอร์ไทม์และอัตราค่าใช้จ่าย จะถูกเก็บรักษาไว้ครบถ้วน
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS
- **เหมาะกับการทำอัตโนมัติ** – เหมาะสำหรับการประมวลผลเป็นชุดหรือการรวมกับ pipeline CI

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

### การตั้งค่าสภาพแวดล้อมการพัฒนา Java
1. ติดตั้ง JDK: ตรวจสอบว่าคุณมี Java Development Kit (JDK) ติดตั้งบนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
2. ตั้งค่า IDE: เลือก Integrated Development Environment (IDE) เช่น IntelliJ IDEA, Eclipse, หรือ NetBeans แล้วตั้งค่าให้พร้อมใช้งานบนเครื่องของคุณ

### การติดตั้ง Aspose.Tasks for Java
1. ดาวน์โหลด Aspose.Tasks for Java: ไปที่ [download page](https://releases.aspose.com/tasks/java/) แล้วรับเวอร์ชันล่าสุดของ Aspose.Tasks for Java
2. ผสานรวมกับโปรเจกต์: เพิ่มไลบรารี Aspose.Tasks for Java เข้าไปในโปรเจกต์ Java ของคุณโดยการเพิ่มเป็น dependency

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น คุณต้องนำเข้าแพ็กเกจที่จำเป็นจาก Aspose.Tasks for Java ไปยังโปรเจกต์ของคุณ ขั้นตอนนี้ทำให้คุณเข้าถึงฟังก์ชันที่ต้องการได้

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Project
การสร้าง **อ็อบเจ็กต์โปรเจกต์** เป็นขั้นตอนแรกของการจัดการไฟล์ MS Project ใด ๆ มันเป็นตัวแทนของไฟล์โปรเจกต์ทั้งหมดในหน่วยความจำ

```java
Project project = new Project();
```

## ขั้นตอนที่ 2: เพิ่มทรัพยากร (add resource ms project)
ต่อไปเราจะ **เพิ่มทรัพยากร MS Project** โดยใช้คอลเลกชัน Resources ชื่อทรัพยากรสามารถตั้งเป็นอะไรก็ได้ที่สื่อความหมายกับตารางเวลาของคุณ

```java
Resource rsc = project.getResources().add("Rsc");
```

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติของทรัพยากร (how to set rates)
ที่นี่เราจะ **ตั้งค่าอัตรามาตรฐาน** และยังแสดงวิธีตั้งค่าอัตราโอเวอร์ไทม์อีกด้วย อัตราเหล่านี้จะถูกเก็บเป็นค่า `BigDecimal` เพื่อรักษาความแม่นยำ

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| `NullPointerException` เมื่อเรียก `set` | ไม่ได้เพิ่มทรัพยากรอย่างถูกต้อง | ตรวจสอบให้แน่ใจว่า `project.getResources().add()` คืนค่า `Resource` ที่ไม่เป็น `null` |
| อัตราแสดงเป็น 0 ในไฟล์ที่บันทึก | ใช้ `int` แทน `BigDecimal` | ใช้ `BigDecimal.valueOf()` สำหรับค่าการเงินเสมอ |
| ไม่พบลิขสิทธิ์ | ไฟล์ลิขสิทธิ์ไม่ได้โหลดก่อนสร้าง `Project` | โหลดลิขสิทธิ์ (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) ที่จุดเริ่มต้นของโปรแกรม |

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณได้เรียนรู้วิธี **สร้างอ็อบเจ็กต์โปรเจกต์**, **เพิ่มทรัพยากร MS Project**, และ **ตั้งค่าอัตรามาตรฐาน** พร้อมคุณสมบัติอื่น ๆ ของทรัพยากร ซึ่งทำให้คุณสามารถอัตโนมัติการคำนวณค่าใช้จ่าย, สร้างรายงานแบบกำหนดเอง, และจัดการทรัพยากรของ MS Project จาก Java ได้อย่างเต็มที่

## คำถามที่พบบ่อย
### Aspose.Tasks for Java สามารถจัดการไฟล์ MS Project ที่ซับซ้อนได้หรือไม่?
ใช่, Aspose.Tasks for Java สามารถจัดการไฟล์ MS Project ในรูปแบบต่าง ๆ รวมถึงไฟล์ที่มีโครงสร้างงานซับซ้อนและลำดับชั้นงานจำนวนมาก

### มีรุ่นทดลองฟรีสำหรับ Aspose.Tasks for Java หรือไม่?
มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Tasks for Java ได้จาก [here](https://releases.aspose.com/)

### จะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
คุณสามารถขอความช่วยเหลือและเข้าร่วมการสนทนาเกี่ยวกับ Aspose.Tasks for Java ได้ที่ [support forum](https://forum.aspose.com/c/tasks/15)

### จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Tasks for Java ได้อย่างไร?
คุณสามารถขอรับลิขสิทธิ์ชั่วคราวจาก [temporary license page](https://purchase.aspose.com/temporary-license/) เพื่อใช้ในการประเมินผล

### จะซื้อเวอร์ชันที่มีลิขสิทธิ์ของ Aspose.Tasks for Java ได้จากที่ไหน?
คุณสามารถซื้อเวอร์ชันที่มีลิขสิทธิ์ของ Aspose.Tasks for Java ได้จาก [purchase page](https://purchase.aspose.com/buy)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose