---
title: إدارة مدة المهام في Aspose.Tasks
linktitle: إدارة مدة المهام في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: استكشف Aspose.Tasks لـ Java وتعلم كيفية إدارة فترات المهام دون عناء. اتبع دليلنا خطوة بخطوة للتخطيط والتنفيذ الفعال للمشروع.
type: docs
weight: 20
url: /ar/java/task-properties/manage-durations/
---
## مقدمة
يوفر Aspose.Tasks for Java حلاً قويًا لإدارة مهام المشروع ومدده بكفاءة. في هذا البرنامج التعليمي، سنستكشف كيفية إدارة فترات المهام باستخدام Aspose.Tasks، وإرشادك خلال كل خطوة. سواء كنت مطورًا متمرسًا أو مبتدئًا، سيساعدك هذا الدليل على فهم أساسيات العمل مع فترات المهام في مشاريعك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Java Development Kit (JDK): تأكد من تثبيت Java على جهازك. يمكنك تنزيله[هنا](https://www.oracle.com/java/technologies/javase-downloads.html).
- مكتبة Aspose.Tasks: قم بتنزيل مكتبة Aspose.Tasks وتضمينها في مشروعك. يمكنك العثور على المكتبة[هنا](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة للعمل مع Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## الخطوة 1: قم بإعداد مشروعك
```java
// إنشاء مشروع جديد
Project project = new Project();
```
## الخطوة 2: إضافة مهمة جديدة
```java
// إضافة مهمة جديدة إلى المشروع
Task task = project.getRootTask().getChildren().add("Task");
```
## الخطوة 3: الحصول على مدة المهمة وتحويلها
```java
// الحصول على مدة المهمة بالأيام (وحدة الوقت الافتراضية)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// تحويل المدة إلى ساعات وحدة زمنية
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## الخطوة 4: قم بتحديث مدة المهمة إلى أسبوع واحد
```java
// زيادة مدة المهمة إلى أسبوع واحد
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## الخطوة 5: تقليل مدة المهمة
```java
// تقليل مدة المهمة
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
باتباع هذه الخطوات، تكون قد تمكنت بنجاح من إدارة فترات المهام في مشروع Aspose.Tasks for Java.
## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية أساسيات إدارة فترات المهام باستخدام Aspose.Tasks لـ Java. الآن، يمكنك دمج هذه التقنيات بثقة في مشاريعك لإدارة فعالة لمدة المهام.
## الأسئلة الشائعة
### هل Aspose.Tasks متوافق مع جميع إصدارات Java؟
Aspose.Tasks متوافق مع Java 6 والإصدارات الأحدث.
### هل يمكنني استخدام Aspose.Tasks للمشاريع التجارية؟
 نعم، يمكنك استخدام Aspose.Tasks لكل من المشاريع الشخصية والتجارية. يزور[هنا](https://purchase.aspose.com/buy) للحصول على تفاصيل الترخيص.
### أين يمكنني العثور على دعم وموارد إضافية؟
 قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع والمناقشات.
### كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/) لاستكشاف Aspose.Tasks قبل إجراء عملية شراء.