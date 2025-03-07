---
title: تحديد أيام الأسبوع في التقويم باستخدام Aspose.Tasks
linktitle: تحديد أيام الأسبوع في التقويم باستخدام Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحديد أيام الأسبوع في MS Project Calendar باستخدام Aspose.Tasks لـ Java. تخصيص أيام العمل والتوقيت دون عناء.
weight: 12
url: /ar/java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديد أيام الأسبوع في التقويم باستخدام Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنتعرف على عملية تحديد أيام الأسبوع في MS Project Calendar باستخدام Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة Java قوية تمكن المطورين من التعامل مع ملفات Microsoft Project برمجياً.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) إذا لم تكن قد فعلت ذلك بالفعل.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java من[صفحة التحميل](https://releases.aspose.com/tasks/java/). اتبع تعليمات التثبيت المتوفرة في الوثائق.

## حزم الاستيراد
للبدء، قم باستيراد الحزم اللازمة للعمل مع Aspose.Tasks في مشروع Java الخاص بك:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## الخطوة 1: إنشاء مثيل المشروع
قم بإنشاء مثيل لكائن Project، الذي يمثل ملف MS Project الذي ستعمل معه:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## الخطوة 2: تحديد التقويم
قم بإنشاء مثيل تقويم جديد وأضفه إلى المشروع:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## الخطوة 3: إضافة أيام العمل
حدد أيام العمل بإضافة الاثنين إلى الخميس مع التوقيت الافتراضي:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## الخطوة 4: تحديد يوم عمل مخصص
تحديد يومي السبت والأحد كأيام عمل:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## الخطوة 5: تحديد يوم عمل قصير
حدد يوم الجمعة كيوم عمل قصير مع أوقات عمل مخصصة:
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## الخطوة 6: احفظ المشروع
احفظ المشروع المعدل في ملف XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## خاتمة
تهانينا! لقد قمت بتحديد أيام الأسبوع بنجاح في تقويم MS Project باستخدام Aspose.Tasks لـ Java. يمكنك الآن دمج هذه الوظيفة في تطبيقات Java الخاصة بك لمعالجة ملفات MS Project برمجيًا.
## الأسئلة الشائعة
### س1: هل يمكنني تحديد أيام التوقف عن العمل المخصصة باستخدام Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك تحديد أيام غير العمل المخصصة عن طريق تعيين`DayWorking` الملكية ل`false` لأيام الأسبوع المعنية.
### س2: كيف يمكنني إضافة أيام العطل إلى التقويم؟
 ج: يمكنك إضافة أيام العطل عن طريق إنشاء مثيلات`CalendarExceptions`وتحديد مواعيد عدم العمل.
### س 3: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات MS Project؟
ج: نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات MS Project، بما في ذلك تنسيقات MPP وMPT وXML.
### س4: هل يمكنني تعديل التقويمات الموجودة في ملف MS Project؟
ج: نعم، يمكنك تحميل مشروع موجود بالتقويمات وإجراء التعديلات ثم حفظ التغييرات مرة أخرى في الملف الأصلي.
### س5: هل يوفر Aspose.Tasks الدعم للمهام المتكررة؟
ج: نعم، يتيح لك Aspose.Tasks العمل مع المهام المتكررة، بما في ذلك تحديد أنماط ومدة التكرار الخاصة بها.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
