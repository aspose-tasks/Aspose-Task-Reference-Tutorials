---
date: 2026-08-08
description: تعلم كيفية ضبط تقويم ms project، وتحديد ساعات العمل اليومية، وإضافة أيام
  عمل في عطلة نهاية الأسبوع باستخدام Aspose.Tasks للغة Java. احفظ المشروع كملف XML
  ببضع أسطر من الشيفرة.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: كيفية ضبط تقويم ms project وتحديد أيام الأسبوع
og_description: ضبط تقويم ms project، وتحديد أيام الأسبوع، وإضافة أيام عمل في عطلة
  نهاية الأسبوع باستخدام Aspose.Tasks للغة Java. اتبع هذا الدليل خطوة بخطوة واحفظه
  كملف XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: ضبط تقويم ms project باستخدام Aspose.Tasks – دليل Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: كيفية ضبط تقويم ms project وتحديد أيام الأسبوع
url: /ar/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين تقويم ms project وتحديد أيام الأسبوع

في هذا البرنامج التعليمي ستتعلم **كيفية تعيين تقويم ms project** برمجيًا، وتحديد أيام الأسبوع، وتكوين أيام عمل مخصصة باستخدام مكتبة Aspose.Tasks للغة Java. سواءً كنت تبني محرك جدولة، أو تدمج مع أنظمة ERP، أو تحتاج ببساطة إلى إنشاء خطة مشروع دون فتح Microsoft Project، تُظهر الخطوات أدناه كيفية إنشاء تقويم، وتعيين ساعات العمل اليومية، وإضافة أيام عمل في عطلة نهاية الأسبوع ببضع أسطر من الشيفرة.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java.  
- **هل يمكنني إضافة أيام عمل في عطلة نهاية الأسبوع؟** نعم – فقط ضع علامة على السبت والأحد كأيام عمل.  
- **كيف أحفظ المشروع؟** استدعِ `prj.save(..., SaveFileFormat.Xml)`.  
- **هل تحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتقييم؛ الترخيص مطلوب للاستخدام في الإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.

## ما هو تعيين تقويم ms project؟
تحديد التقويم في MS Project يحدد أي الأيام تُعتبر أيام عمل، وعدد ساعات العمل لكل يوم، وأي استثناءات خاصة مثل العطلات أو إغلاق الشركة. هذه المعلومات تُوجه جدولة المهام، وتخصيص الموارد، والجداول الزمنية للمشروع ككل، مما يضمن أن الحسابات تحترم أنماط العمل الفعلية للمنظمة.

## لماذا نستخدم Aspose.Tasks لتعديل التقويم؟
توفر Aspose.Tasks لك التحكم البرمجي في التقويمات دون تشغيل واجهة Microsoft Project. تعمل على أي نظام تشغيل يدعم Java، وتدعم أكثر من 50 صيغة إدخال وإخراج، ويمكنها معالجة مشاريع مئات الصفحات دون تحميل الملف بالكامل في الذاكرة، مما يجعلها مثالية للأتمتة على الخادم.

## المتطلبات المسبقة
- **Java Development Kit (JDK) 8+** – قم بتنزيله من [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – احصل على أحدث JAR من [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- بيئة تطوير متكاملة أو أداة بناء (Maven/Gradle) لإضافة Aspose.Tasks JAR إلى classpath الخاص بك.

## استيراد الحزم
استورد الفئات التي توفر الوصول إلى المشاريع، التقويمات، وكائنات وقت العمل.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء مثال مشروع
أنشئ كائن `Project`، الذي يمثل ملف MS Project الذي ستقوم بتعديله.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### الخطوة 2: تعريف تقويم جديد
`Calendar` يمثل مجموعة من أوقات العمل، الاستثناءات، والعطلات لمشروع.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### الخطوة 3: إضافة أيام عمل قياسية (من الاثنين إلى الخميس)
`WeekDay` يحدد وقت العمل ليوم محدد من الأسبوع.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### الخطوة 4: إضافة أيام عمل في عطلة نهاية الأسبوع
إذا كان مشروعك يعمل في عطلات نهاية الأسبوع، أضف السبت والأحد كأيام عمل عادية. هذا يوضح **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### الخطوة 5: تعيين يوم عمل قصير مخصص (الجمعة)
قم بتكوين الجمعة بنوبة صباحية (9 ص‑12 م) ونوبة بعد الظهر (1 م‑4 م) لتوضيح **set daily working hours** ويوم عمل قصير مخصص.

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

### الخطوة 6: حفظ المشروع كملف XML
`SaveFileFormat` يعدد صيغ الملفات المدعومة عند حفظ مشروع، مثل XML أو MPP.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **أوقات العمل غير مطبقة** | تأكد من استدعاء `setDayWorking(true)` لكل `WeekDay` مخصص. |
| **الملف غير موجود عند الحفظ** | تحقق من أن `dataDir` يشير إلى مجلد موجود وأن التطبيق لديه أذونات كتابة. |
| **التقويم غير منعكس في المهام** | قم بتعيين التقويم الذي تم إنشاؤه حديثًا للموارد أو المهام باستخدام `task.setCalendar(cal)`. |

## الأسئلة المتكررة

**س: هل يمكنني تعريف أيام غير عمل مخصصة باستخدام Aspose.Tasks for Java؟**  
ج: نعم. اضبط الخاصية `DayWorking` إلى `false` لأي `WeekDay` تريد اعتباره يومًا غير عمل.

**س: كيف يمكنني إضافة عطلات أو استثناءات على مستوى الشركة؟**  
ج: أنشئ كائنات `CalendarException`، حدد تواريخ الاستثناء، وأضفها إلى `cal.getExceptions()`.

**س: هل المكتبة متوافقة مع إصدارات MS Project القديمة؟**  
ج: بالتأكيد. Aspose.Tasks يدعم صيغ MPP و MPT و XML عبر إصدارات متعددة من Project.

**س: هل يمكنني تعديل تقويم موجود في مشروع مستورد؟**  
ج: حمّل المشروع باستخدام `new Project("existing.mpp")`، استخرج التقويم المطلوب، أجرِ التغييرات، واحفظ.

**س: هل يتعامل Aspose.Tasks مع المهام المتكررة أيضًا؟**  
ج: نعم، يمكنك إنشاء وتعديل المهام المتكررة باستخدام الفئة `RecurringTask`.

## الخلاصة
أنت الآن تعرف **كيفية تعيين تقويم ms project**، وتحديد أيام الأسبوع، وإضافة أيام عمل في عطلة نهاية الأسبوع، وتكوين جدول جمعة قصير — كل ذلك باستخدام Aspose.Tasks for Java. احفظ النتيجة كملف XML ودمج منطق التقويم في أي حل لإدارة المشاريع مبني على Java.

---

**آخر تحديث:** 2026-08-08  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [إضافة تقويم إلى المشروع باستخدام Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [تحديد أيام العمل وساعات العمل باستخدام Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [إضافة عطلات إلى التقويم وحفظه كملف MPP باستخدام Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}