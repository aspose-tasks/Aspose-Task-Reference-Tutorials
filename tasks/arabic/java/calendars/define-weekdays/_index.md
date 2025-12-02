---
date: 2025-12-02
description: تعلم كيفية ضبط التقويم، تعريف أيام الأسبوع في MS Project وتعيين أيام
  عمل مخصصة باستخدام Aspose.Tasks للغة Java. احفظ المشروع كملف XML ببضع أسطر من الشيفرة
  فقط.
language: ar
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تعيين التقويم وتحديد أيام الأسبوع في MS Project باستخدام Aspose.Tasks
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضبط التقويم وتحديد أيام الأسبوع في MS Project باستخدام Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي ستكتشف **how to set calendar** إعدادات التقويم برمجياً وتحدد أيام الأسبوع في ملف Microsoft Project باستخدام مكتبة Aspose.Tasks للغة Java. سواء كنت بحاجة إلى إنشاء أسبوع عمل قياسي، أو إضافة أيام عمل في عطلة نهاية الأسبوع، أو تكوين جدول قصير ليوم الجمعة، فإن هذا الدليل سيرشدك خطوة بخطوة—from إنشاء المشروع إلى حفظ الملف بصيغة XML.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java  
- **هل يمكنني إضافة أيام عمل في عطلة نهاية الأسبوع؟** نعم – فقط أضف السبت والأحد كأيام عمل.  
- **كيف أحفظ المشروع؟** استخدم `prj.save(..., SaveFileFormat.Xml)`.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى.

## ما هو “how to set calendar” في سياق MS Project؟
ضبط التقويم في MS Project يعني تحديد أي الأيام هي أيام عمل، وساعات العمل اليومية، وأي استثناءات مثل العطلات. هذا التقويم يوجه جدولة المهام، وتخصيص الموارد، والجدول الزمني العام للمشروع.

## لماذا استخدام Aspose.Tasks لتعديل التقويم؟
- **تحكم كامل** – إنشاء، تعديل أو حذف التقويمات برمجياً دون فتح الواجهة.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **يدعم جميع صيغ الملفات** – MPP، MPT، وXML، بحيث يمكنك *save project as XML* للتكامل السهل مع الأنظمة الأخرى.  
- **بدون تبعيات COM** – على عكس مكتبة Microsoft Project Interop.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود:

1. **Java Development Kit (JDK) 8+** – حمّل من [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – احصل على أحدث JAR من [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. بيئة تطوير متكاملة أو أداة بناء (Maven/Gradle) لإضافة JAR الخاص بـ Aspose.Tasks إلى مسار الفئات في مشروعك.

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. هذه الاستيرادات تمنحك الوصول إلى كائنات المشروع، التقويم، وأوقات العمل.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء كائن Project
أنشئ كائن `Project` جديد. هذا الكائن يمثل ملف MS Project الذي ستقوم بتحريره.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### الخطوة 2: تعريف تقويم جديد
أضف تقويمًا جديدًا إلى المشروع. إعطاؤه اسمًا واضحًا يساعد عندما يكون لديك تقاويم متعددة.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### الخطوة 3: إضافة أيام العمل القياسية (الإثنين‑الخميس)
استخدم المساعد المدمج `WeekDay.createDefaultWorkingDay` لضبط جدول 9 ص‑5 م الافتراضي لأيام العمل الأساسية.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### الخطوة 4: إضافة أيام عمل في عطلة نهاية الأسبوع
إذا كان مشروعك يعمل في عطلات نهاية الأسبوع، ببساطة أضف السبت والأحد كأيام عمل عادية. هذا يوضح **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### الخطوة 5: ضبط يوم عمل قصير مخصص (الجمعة)
هنا ن **set custom working days** للجمعة: فترة صباحية (9 ص‑12 م) وفترة بعد الظهر (1 م‑4 م).

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
أخيرًا، احفظ التغييرات. خيار `SaveFileFormat.Xml` يتيح لك **save project as XML**، وهو مفيد للتكامل مع أدوات أخرى.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Working times not applied** | تأكد من استدعاء `setDayWorking(true)` على الـ `WeekDay` المخصص. |
| **File not found when saving** | تحقق من أن `dataDir` يشير إلى مجلد موجود وأن تطبيقك يملك أذونات الكتابة. |
| **Calendar not reflected in tasks** | عيّن التقويم الجديد للموارد أو المهام باستخدام `task.setCalendar(cal)`. |

## الأسئلة المتكررة

**س: هل يمكنني تعريف أيام غير عمل مخصصة باستخدام Aspose.Tasks for Java؟**  
ج: نعم. اضبط الخاصية `DayWorking` إلى `false` لأي `WeekDay` تريد اعتباره يومًا غير عمل.

**س: كيف يمكنني إضافة عطلات أو استثناءات على مستوى الشركة؟**  
ج: أنشئ كائنات `CalendarException`، حدد تواريخ الاستثناء، وأضفها إلى `cal.getExceptions()`.

**س: هل المكتبة متوافقة مع إصدارات MS Project القديمة؟**  
ج: بالتأكيد. Aspose.Tasks يدعم صيغ MPP، MPT، وXML عبر إصدارات متعددة من Project.

**س: هل يمكنني تعديل تقويم موجود في مشروع مستورد؟**  
ج: حمّل المشروع باستخدام `new Project("existing.mpp")`، استخرج التقويم المطلوب، أجرِ التغييرات، ثم احفظه.

**س: هل يتعامل Aspose.Tasks مع المهام المتكررة أيضًا؟**  
ج: نعم، يمكنك إنشاء وتعديل مهام متكررة باستخدام الفئة `RecurringTask`.

## الخاتمة
أنت الآن تعرف **how to set calendar**، **define weekdays MS Project**، إضافة أيام عمل في عطلة نهاية الأسبوع، وإنشاء جدول قصير ليوم الجمعة — كل ذلك باستخدام Aspose.Tasks للغة Java. احفظ النتيجة كملف XML ودمج منطق التقويم في أي حل لإدارة المشاريع مبني على Java.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}