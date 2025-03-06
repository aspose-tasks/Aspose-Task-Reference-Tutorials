---
title: ระบุงานข้ามโครงการใน Aspose.Tasks
linktitle: ระบุงานข้ามโครงการใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจการระบุงานข้ามโครงการด้วย Aspose.Tasks สำหรับ Java การบูรณาการที่ราบรื่นและการจัดการที่มีประสิทธิภาพ ดาวน์โหลดเดี๋ยวนี้!
weight: 14
url: /th/java/task-links/identify-cross-project-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ระบุงานข้ามโครงการใน Aspose.Tasks

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมของเราเกี่ยวกับการระบุงานข้ามโครงการอย่างมีประสิทธิภาพด้วย Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ คู่มือนี้จะแนะนำคุณตลอดกระบวนการรวมฟังก์ชันการทำงานนี้เข้ากับโปรเจ็กต์ Java ของคุณอย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Tasks สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็น แพ็คเกจเหล่านี้มีความสำคัญอย่างยิ่งต่อการใช้ฟังก์ชันการทำงานของ Aspose.Tasks ในแอปพลิเคชัน Java ของคุณ
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ ซึ่งเป็นที่ตั้งของไฟล์โปรเจ็กต์ของคุณ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดโครงการภายนอก
ใช้ Aspose.Tasks เพื่อโหลดไฟล์โครงการภายนอก ในตัวอย่างของเรา เราถือว่าโปรเจ็กต์ภายนอกชื่อ "External.mpp"
```java
Project externalProject = new Project(dataDir + "External.mpp");
```
## ขั้นตอนที่ 3: ดึงข้อมูลงานภายนอก
เข้าถึงงานรูทของโปรเจ็กต์ภายนอกและเรียกข้อมูลงานด้วย UID (Unique Identifier) เฉพาะเจาะจง ในตัวอย่างของเรา เราใช้ UID 1
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```
## ขั้นตอนที่ 4: แสดง ID งานภายนอก
 พิมพ์ ID ของงานในโครงการภายนอกโดยใช้`externalTask.get(Tsk.ID).toString()`.
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```
## ขั้นตอนที่ 5: แสดง ID งานดั้งเดิม
 ในทำนองเดียวกัน ให้พิมพ์ ID ของงานในโครงการต้นฉบับโดยใช้`externalTask.get(Tsk.EXTERNAL_ID).toString()`.
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```
ทำซ้ำขั้นตอนเหล่านี้ตามความจำเป็นเพื่อระบุและจัดการงานข้ามโครงการอย่างมีประสิทธิภาพ
## บทสรุป
การเรียนรู้การระบุงานข้ามโครงการอย่างเชี่ยวชาญด้วย Aspose.Tasks สำหรับ Java จะเปิดโอกาสใหม่ๆ สำหรับการจัดการโครงการในแอปพลิเคชันของคุณ ด้วยการทำตามคำแนะนำทีละขั้นตอนของเรา คุณสามารถรวมคุณสมบัตินี้เข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับภาษาการเขียนโปรแกรมหลายภาษา รวมถึง Java, .NET และอื่นๆ อีกมากมาย
### ถาม: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Tasks for Java ได้ที่ไหน
 ตอบ: โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tasks/java/).
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับสิทธิ์การใช้งานชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: ขอรับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ต้องการความช่วยเหลือหรือมีคำถามเฉพาะเจาะจง?
ตอบ: ไปที่ฟอรัมสนับสนุน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
