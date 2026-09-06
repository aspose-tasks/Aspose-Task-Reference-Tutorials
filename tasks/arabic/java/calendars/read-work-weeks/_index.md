---
date: 2026-08-13
description: تعلم كيفية قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks
  for Java. اتبع الدليل خطوة بخطوة مع أمثلة الكود ونصائح استكشاف الأخطاء وإصلاحها.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: قراءة أسابيع العمل من التقويم باستخدام Aspose.Tasks
og_description: كيفية قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks
  for Java. اتبع البرنامج التعليمي المختصر مع خطوات الإعداد ومقاطع الكود ونصائح استكشاف
  الأخطاء وإصلاحها.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: كيفية قراءة أسابيع العمل من تقويم MS باستخدام Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: كيفية قراءة أسابيع العمل من تقويم MS باستخدام Aspose.Tasks
url: /ar/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة أسابيع العمل من تقويم MS باستخدام Aspose.Tasks

## مقدمة
في هذا الدرس ستتعلم **كيفية قراءة أسابيع العمل** من تقويم Microsoft Project باستخدام مكتبة Aspose.Tasks للغة Java. سواءً كنت تبني لوحة تقارير، أو تُزامن الجداول مع نظام ERP، أو تُؤتمت استخراج البيانات للتحليلات، فإن الوصول البرمجي إلى تعريفات أسابيع العمل يوفر ساعات يدوية لا تُحصى. تدعم Aspose.Tasks **أكثر من 50 تنسيقًا للإدخال والإخراج** ويمكنها معالجة ملفات مشاريع مئات الصفحات دون تحميل الملف بالكامل في الذاكرة، مما يمنحك كلًا من المرونة والأداء.

## إجابات سريعة
- **ماذا يعني “قراءة أسابيع العمل”?** يشير إلى استخراج تعريفات أسابيع العمل (التواريخ وقواعد أوقات العمل اليومية) من ملف Project عبر كود Java.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks للغة Java (يتوفر إصدار تجريبي مجاني).  
- **هل أحتاج إلى ترخيص للتطوير؟** الإصدار التجريبي يعمل للاختبار؛ يلزم ترخيص تجاري للنشر في بيئة الإنتاج.  
- **ما صيغ الملفات المدعومة؟** يتم التعامل مع كل من *.mpp* وملفات Project XML، بالإضافة إلى أكثر من 50 صيغة أخرى للاستيراد/التصدير.  
- **كم يستغرق تنفيذ ذلك؟** عادةً أقل من 10 دقائق بمجرد إعداد المكتبة.

## ما هو أسبوع العمل في MS Project؟
أسبوع العمل يحدد قواعد التقويم التي تحدد متى تكون الموارد متاحة خلال فترة معينة. يشمل تاريخ بدء، تاريخ انتهاء، وفواصل زمنية يومية للعمل (مثال: من 9 ص إلى 5 م). في MS Project، يمكن لكل تقويم أن يحتوي على عدة أسابيع عمل، مما يتيح لك نمذجة العطلات، أنماط الورديات، أو الجداول الموسمية.

## كيف تقرأ Aspose.Tasks أسابيع العمل من تقويم؟
تُظهر Aspose.Tasks الخاصية `WorkWeekCollection` لكائن `Calendar`. من خلال إنشاء مثيل `Project`، واختيار التقويم المطلوب (عن طريق UID أو الاسم)، والتكرار عبر `WorkWeekCollection` الخاصة به، يمكنك استرجاع تسمية كل أسبوع عمل، نطاق التاريخ الفعّال، والفواصل الزمنية اليومية المفصلة. تتعامل API تلقائيًا مع جميع تحويلات التاريخ‑الوقت وتحترم إعدادات المنطقة الزمنية للمشروع.

## لماذا قراءة أسابيع العمل Java من تقويم Microsoft Project؟
قراءة أسابيع العمل برمجيًا تُلغي النسخ واللصق اليدوي، وتضمن أن الأنظمة المتصلة (ERP، HR، التقارير) تستخدم نفس قواعد الجدولة بالضبط، وتضمن التناسق عبر عدة مشاريع. كما أن الأتمتة تقلل الأخطاء البشرية وتسرّع خطوط التكامل، خاصةً عندما تحتاج إلى معالجة عشرات ملفات المشروع كل ليلة.

## المتطلبات المسبقة
قبل أن نغوص في الكود، تأكد من أن لديك:

1. **Java Development Kit (JDK)** – الإصدار 8 أو أحدث مثبت.  
2. **Aspose.Tasks للغة Java** – قم بتحميل أحدث ملف JAR من الموقع الرسمي: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. ملف **مشروع عينة** (`ReadWorkWeeksInformation.mpp`) موجود في مجلد معروف على جهازك.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها للتعامل مع التقويمات وأسابيع العمل:

`Project` يمثل ملف Microsoft Project، `Calendar` يوفر تقويماته، `WorkWeek` يعرّف أسبوع العمل، و `WeekDay` يمثل اليوم.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## الخطوة 1: إعداد دليل البيانات الخاص بك
حدد المجلد الذي يحتوي على ملف `.mpp`. استبدل العنصر النائب بالمسار الفعلي على جهازك:

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: إنشاء مثيل Project والوصول إلى التقويم
`Project` تمثل ملف Microsoft Project وتوفر الوصول إلى هياكل البيانات الخاصة به، بما في ذلك التقويمات، والمهام، والموارد.  
قم بإنشاء كائن `Project`، اختر التقويم الذي تريد (عن طريق UID)، واحصل على `WorkWeekCollection` الخاصة به:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **نصيحة احترافية:** إذا لم تكن متأكدًا من UID التقويم، قم بالتكرار عبر `project.getCalendars()` واطبع اسم كل تقويم وUID أولاً.

## الخطوة 3: التكرار عبر أسابيع العمل
`WorkWeek` يضم تعريف أسبوع العمل، يحتوي على تواريخ البدء/الانتهاء وإعدادات أوقات العمل اليومية.  
قم بالتكرار عبر كل `WorkWeek` لعرض اسمه، وتواريخ البدء/الانتهاء، وأوقات العمل اليومية:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**ما ستراه:** يطبع الطرفية تسمية كل أسبوع عمل (مثال: “Standard”)، نطاق تاريخ الفعالية، ويمكنك التعمق إلى ساعات العمل الدقيقة لكل يوم.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| `NullPointerException` عند الوصول إلى `calendar` | UID غير صحيح أو التقويم غير موجود | تحقق من UID باستخدام `project.getCalendars().size()` وقم بسرد التقويمات المتاحة أولاً. |
| لا يوجد إخراج لأسابيع العمل | التقويم المختار لا يحتوي على أسابيع عمل مخصصة (يستخدم الافتراضي) | استخدم التقويم الافتراضي (`project.getDefaultCalendar()`) أو أنشئ أسبوع عمل برمجيًا. |
| تنسيق التاريخ يبدو غريبًا | `System.out.println` يستخدم تنسيق `java.util.Date` الافتراضي | استخدم `SimpleDateFormat` لتنسيق التواريخ حسب الحاجة. |

## الأسئلة المتكررة
**س: هل يمكنني تعديل معلومات أسابيع العمل باستخدام Aspose.Tasks للغة Java؟**  
ج: نعم. توفر API الدوال `addWorkWeek()`، `removeWorkWeek()`، ومُعدِّلات الخصائص لتغيير الأسماء، التواريخ، وأوقات العمل.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: بالتأكيد. يدعم ملفات MPP من Project 98 حتى أحدث الإصدارات، بالإضافة إلى ملفات Project XML.

**س: هل يمكنني دمج Aspose.Tasks مع أطر عمل Java أخرى؟**  
ج: نعم. المكتبة مكتوبة بلغة Java فقط، لذا يمكنك استخدامها جنبًا إلى جنب مع Spring، Jakarta EE، أو أي إطار عمل آخر.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية لمدة 30 يومًا من الموقع الرسمي: [Aspose.Tasks trial](https://releases.aspose.com/).

**س: أين يمكنني العثور على دعم Aspose.Tasks؟**  
ج: منتدى مجتمع Aspose هو أفضل مكان: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2026-08-13  
**تم الاختبار باستخدام:** Aspose.Tasks للغة Java 24.12 (أحدث إصدار وقت كتابة هذا)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إضافة تقويم إلى المشروع باستخدام Aspose.Tasks للغة Java](/tasks/java/calendars/create/)
- [استرجاع استثناءات التقويم باستخدام Aspose.Tasks – درس Aspose.Tasks Java](/tasks/java/calendar-exceptions/retrieve/)
- [كيفية تعيين التقويم وتعريف أيام الأسبوع في MS Project باستخدام Aspose.Tasks](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}