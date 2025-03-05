---
title: إدارة خصائص مشروع MS بكفاءة في Aspose.Tasks
linktitle: إدارة خصائص المشروع الافتراضية في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إدارة خصائص MS Project الافتراضية باستخدام Aspose.Tasks لـ Java. قم بتبسيط سير عمل إدارة المشروع الخاص بك دون عناء.
type: docs
weight: 11
url: /ar/java/project-management/default-properties/
---
## مقدمة
هل تتطلع إلى تبسيط عملية إدارة مشروعك باستخدام Aspose.Tasks لـ Java؟ يمكن أن تؤدي إدارة الخصائص الافتراضية في ملفات Microsoft Project إلى تحسين الكفاءة بشكل كبير. في هذا البرنامج التعليمي، سنتعرف على إرشادات خطوة بخطوة حول كيفية إدارة خصائص MS Project الافتراضية باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل أن نخوض في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. مجموعة تطوير جافا (JDK)
   - تأكد من تثبيت JDK على نظامك.
   -  يمكنك تنزيله من[هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks لمكتبة جافا
   - قم بتنزيل مكتبة Aspose.Tasks لـ Java وتضمينها في مشروعك.
   -  يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية في ملف Java الخاص بك:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
دعونا نقسم العملية إلى خطوات يمكن التحكم فيها:
## الخطوة 1: تحميل ملف المشروع
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## الخطوة 2: عرض الخصائص الافتراضية
```java
// عرض الخصائص الافتراضية
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## الخطوة 3: تعيين الخصائص الافتراضية
```java
// تعيين الخصائص الافتراضية
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## الخطوة 4: حفظ المشروع بتنسيق XML
```java
// احفظ المشروع بتنسيق XML
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## الخطوة 5: عرض النتيجة
```java
// عرض نتيجة التحويل.
System.out.println("Process completed Successfully");
```
باتباع هذه الخطوات، يمكنك إدارة خصائص MS Project الافتراضية بكفاءة باستخدام Aspose.Tasks لـ Java.
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إدارة خصائص MS Project الافتراضية باستخدام Aspose.Tasks لـ Java. ومن خلال الاستفادة من هذه التقنيات، يمكنك تحسين سير عمل إدارة المشروع الخاص بك، وتعزيز الإنتاجية والتنظيم.
## الأسئلة الشائعة
### س1: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟
ج1: نعم، يدعم Aspose.Tasks لغات البرمجة المختلفة مثل .NET، وPython، وJava.
### س2: هل Aspose.Tasks مناسب للاستخدام الشخصي والمؤسسي؟
ج2: بالتأكيد! سواء كنت تدير مشاريع شخصية صغيرة أو مبادرات مؤسسية واسعة النطاق، فإن Aspose.Tasks يلبي احتياجات الجميع.
### س3: هل يقدم Aspose.Tasks دعمًا للعملاء؟
ج3: نعم، يمكنك العثور على المساعدة والدعم المجتمعي على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
### س4: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟
 ج4: بالطبع! يمكنك الاستفادة من النسخة التجريبية المجانية من[موقع إلكتروني](https://releases.aspose.com/).
### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟
 ج5: يمكنك الحصول على ترخيص مؤقت من[صفحة الشراء](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار والتقييم.