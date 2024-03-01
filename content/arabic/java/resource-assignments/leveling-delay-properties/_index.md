---
title: التعامل مع خصائص تأخير التسوية في Aspose.Tasks
linktitle: التعامل مع خصائص تأخير التسوية لتعيينات الموارد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية التعامل مع خصائص تأخير التسوية لتعيينات الموارد في Aspose.Tasks لـ Java باستخدام هذا البرنامج التعليمي الشامل.
type: docs
weight: 17
url: /ar/java/resource-assignments/leveling-delay-properties/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعرف على عملية التعامل مع خصائص تأخير التسوية لتعيينات الموارد في Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة Java قوية تسمح لك بالعمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project على نظامك.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت Java JDK على نظامك. يمكنك تنزيله وتثبيته من[موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks لـ Java من[صفحة التحميل](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك لاستخدام وظائف Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## الخطوة 1: إنشاء كائن المشروع
 إنشاء مثيل أ`Project` هدف:
```java
Project prj = new Project();
```
## الخطوة 2: إنشاء مهمة
إضافة مهمة إلى المشروع:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## الخطوة 3: قم بتعيين تاريخ بدء المهمة ومدتها
قم بتعيين تاريخ البدء والمدة للمهمة:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## الخطوة 4: إضافة مورد
إضافة مورد إلى المشروع:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## الخطوة 5: إنشاء تعيين الموارد
إنشاء تعيين مورد للمهمة والمورد:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## الخطوة 6: ضبط تأخير التسوية
تعيين تأخير التسوية للمهمة:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## الخطوة 7: عرض النتائج
اطبع تأخير التسوية والمعلومات الأخرى ذات الصلة:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع خصائص تأخير التسوية لتعيينات الموارد في Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك إدارة تعيينات الموارد بكفاءة في مشاريع Java الخاصة بك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks مع مكتبات Java الأخرى؟

ج: نعم، يمكن دمج Aspose.Tasks مع مكتبات Java الأخرى لتعزيز قدرات إدارة المشروع.

### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات Microsoft Project؟

ج: نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.

### س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks؟

 ج: يمكنك العثور على الدعم والموارد على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).

### س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟

 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من[صفحة الإصدارات](https://releases.aspose.com/).

### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟

 ج: يمكنك طلب ترخيص مؤقت من[صفحة الترخيص المؤقتة](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.