---
title: การอ่านข้อมูลออนไลน์ของ MS Project ได้อย่างง่ายดายด้วย Aspose.Tasks
linktitle: การอ่านข้อมูลโครงการออนไลน์ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอ่านข้อมูล Microsoft Project Online ได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ Java ปรับปรุงความสามารถในการจัดการโครงการของคุณ
weight: 13
url: /th/java/project-data-reading/read-project-online/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การอ่านข้อมูลออนไลน์ของ MS Project ได้อย่างง่ายดายด้วย Aspose.Tasks

## การแนะนำ
ในขอบเขตของการจัดการโครงการ การจัดการข้อมูล Microsoft Project Online อย่างมีประสิทธิภาพเป็นสิ่งสำคัญสำหรับการดำเนินงานที่มีประสิทธิภาพ Aspose.Tasks for Java มอบโซลูชันที่มีประสิทธิภาพสำหรับการอ่านข้อมูลดังกล่าวได้อย่างง่ายดาย บทช่วยสอนนี้จะเจาะลึกเกี่ยวกับการใช้ประโยชน์จาก Aspose.Tasks เพื่อเข้าถึงและจัดการข้อมูล MS Project Online ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ติดตั้ง JDK เพื่อคอมไพล์และรันโปรแกรม Java
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและรวมไลบรารี Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ คุณสามารถรับมันได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. บัญชี Microsoft Project Online: รับข้อมูลประจำตัวที่ถูกต้องสำหรับการเข้าถึงข้อมูล MS Project Online
4. ที่อยู่โดเมน SharePoint: ที่อยู่โดเมน SharePoint ที่มีข้อมูล MS Project Online ของคุณอยู่
5. ชื่อผู้ใช้และรหัสผ่าน: ข้อมูลประจำตัวสำหรับการตรวจสอบการเข้าถึง MS Project Online
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจ Aspose.Tasks ที่จำเป็นสำหรับการผสานรวมที่ราบรื่น:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## ขั้นตอนที่ 1: ตั้งค่าที่อยู่โดเมน SharePoint ชื่อผู้ใช้ และรหัสผ่าน
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 แทนที่`"https://contoso.sharepoint.com"` ด้วยที่อยู่โดเมน SharePoint ของคุณ`"admin@contoso.onmicrosoft.com"` ด้วยชื่อผู้ใช้ของคุณและ`"MyPassword"` ด้วยรหัสผ่านของคุณ
## ขั้นตอนที่ 2: ตรวจสอบสิทธิ์ด้วยข้อมูลรับรองเซิร์ฟเวอร์โครงการ
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 สร้าง`ProjectServerCredentials` วัตถุที่มีที่อยู่โดเมน SharePoint ชื่อผู้ใช้และรหัสผ่าน จากนั้นเริ่มต้น`ProjectServerManager` ด้วยหนังสือรับรองเหล่านี้
## ขั้นตอนที่ 3: ดึงรายการโครงการและแสดงข้อมูล
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 วนซ้ำรายการโครงการที่ได้รับจาก`reader.getProjectList()` และแสดงรายละเอียดโครงการ เช่น ชื่อ วันที่สร้าง และวันที่บันทึกล่าสุด
## ขั้นตอนที่ 4: โหลดแต่ละโครงการและจำนวนทรัพยากรเอาต์พุต
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 สำหรับแต่ละโปรเจ็กต์ ให้โหลดโดยใช้`reader.getProject(p.getId())` และส่งออกชื่อโครงการพร้อมกับจำนวนทรัพยากรที่เกี่ยวข้อง

## บทสรุป
Aspose.Tasks สำหรับ Java ช่วยให้กระบวนการอ่านข้อมูล MS Project Online ง่ายขึ้น โดยนำเสนอชุดเครื่องมืออันทรงพลังแก่นักพัฒนาเพื่อปรับปรุงงานการจัดการโครงการ เมื่อทำตามบทช่วยสอนนี้ คุณจะสามารถผสานรวม Aspose.Tasks เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ เพื่อเข้าถึงและจัดการข้อมูลโปรเจ็กต์ได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java เพื่อแก้ไขข้อมูล MS Project Online ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks มอบความสามารถที่ครอบคลุมไม่เพียงแต่การอ่านเท่านั้น แต่ยังแก้ไขข้อมูล MS Project Online โดยทางโปรแกรมอีกด้วย
### ถาม: Aspose.Tasks รองรับไฟล์การจัดการโปรเจ็กต์รูปแบบอื่นหรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks รองรับไฟล์ได้หลากหลายรูปแบบ รวมถึง MPP, XML และอื่นๆ อีกมากมาย ทำให้มั่นใจได้ถึงความเข้ากันได้กับระบบการจัดการโครงการที่หลากหลาย
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้งานฟรีได้จาก[ที่นี่](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติและฟังก์ชันการทำงานของ Aspose.Tasks
### ถาม: ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.Tasks for Java ได้ที่ไหน
 ตอบ: คุณสามารถดูเอกสารโดยละเอียดได้[ที่นี่](https://reference.aspose.com/tasks/java/)สำหรับคำแนะนำที่ครอบคลุมเกี่ยวกับการใช้ Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ
### ถาม: Aspose.Tasks for Java มีตัวเลือกการสนับสนุนใดบ้าง
 ตอบ: หากคุณพบปัญหาหรือมีข้อสงสัย คุณสามารถขอความช่วยเหลือได้จากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
