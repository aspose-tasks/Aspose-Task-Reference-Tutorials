---
title: إدارة استثناءات التقويم في Aspose.Tasks
linktitle: إضافة وإزالة استثناءات التقويم في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إضافة استثناءات التقويم وإزالتها في Aspose.Tasks لـ Java بكفاءة. تعزيز سير عمل إدارة المشروع دون عناء.
type: docs
weight: 10
url: /ar/java/calendar-exceptions/add-remove/
---

## مقدمة
في إدارة المشاريع، يعد التعامل مع الاستثناءات ضمن التقويمات أمرًا بالغ الأهمية لجدولة المهام وإدارة الموارد بدقة. يوفر Aspose.Tasks for Java وظائف قوية لإضافة استثناءات التقويم وإزالتها بسهولة. في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة.
#### المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك
- تم تنزيل Aspose.Tasks لمكتبة Java وتكوينها في مشروعك
- الفهم الأساسي للغة برمجة Java ومفاهيم إدارة المشاريع

## حزم الاستيراد
أولاً، تأكد من استيراد الحزم الضرورية في فئة Java الخاصة بك للاستفادة من وظائف Aspose.Tasks بشكل فعال.
```java
import com.aspose.tasks.*;
```
## الخطوة 1: تحميل المشروع والوصول إلى التقويم
ابدأ بتحميل ملف مشروعك والوصول إلى التقويم الذي تريد إضافة الاستثناءات إليه أو إزالتها.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```
## الخطوة 2: إزالة الاستثناء
لإزالة استثناء موجود من التقويم، تحقق من وجود أي استثناءات ثم قم بإزالة الاستثناء المطلوب.
```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```
## الخطوة 3: إضافة استثناء
 لإضافة استثناء جديد إلى التقويم، قم بإنشاء`CalendarException` الكائن وتحديد تاريخ البدء والانتهاء.
```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```
## الخطوة 4: عرض الاستثناءات
وأخيرًا، يمكنك عرض الاستثناءات المضافة للتحقق أو المعالجة الإضافية.
```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From" + calExc1.getFromDate().toString());
    System.out.println("To" + calExc1.getToDate().toString());
}
```

## خاتمة
تعد إدارة استثناءات التقويم أمرًا ضروريًا لجدولة المشروع بدقة وتخصيص الموارد. باستخدام Aspose.Tasks for Java، يمكنك إضافة الاستثناءات وإزالتها بسهولة لضمان الحفاظ على الجداول الزمنية لمشروعك بشكل فعال.

## الأسئلة الشائعة
### س: هل يمكنني إضافة استثناءات متعددة إلى تقويم باستخدام Aspose.Tasks لـ Java؟

ج: نعم، يمكنك إضافة استثناءات متعددة إلى التقويم من خلال التكرار خلال قائمة الاستثناءات وإضافة كل استثناء على حدة.

### س: هل Aspose.Tasks for Java متوافق مع كافة إصدارات ملفات Microsoft Project؟

ج: يوفر Aspose.Tasks for Java التوافق مع الإصدارات المختلفة من ملفات Microsoft Project، مما يضمن التكامل السلس مع سير عمل إدارة المشروع الخاص بك.

### س: كيف يمكنني التعامل مع الاستثناءات المتكررة في تقويمات المشروع؟

ج: يوفر Aspose.Tasks for Java ميزات قوية للتعامل مع الاستثناءات المتكررة في تقويمات المشروع، مما يسمح لك بتحديد أنماط التكرار المعقدة بسهولة.

### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟

 ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks لـ Java من[موقع إلكتروني](https://releases.aspose.com/) لاستكشاف ميزاته قبل إجراء عملية الشراء.

### س: أين يمكنني طلب الدعم لأية مشكلات أو استفسارات تتعلق بـ Aspose.Tasks for Java؟

 ج: يمكنك زيارة منتدى Aspose.Tasks الخاص بـ Java على الموقع[موقع إلكتروني](https://reference.aspose.com/tasks/java/) لطلب المساعدة من المجتمع أو الاتصال مباشرة بفريق الدعم للحصول على مساعدة شخصية.
