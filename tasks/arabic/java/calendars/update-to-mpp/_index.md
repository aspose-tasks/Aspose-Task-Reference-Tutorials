---
date: 2026-08-13
description: تعلم كيفية إضافة أيام العطلة إلى التقويم، وتعيين التقويم لمشروع، وحفظ
  ملف MS Project كملف MPP باستخدام Aspose.Tasks for Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: تحديث التقويم إلى صيغة MPP في Aspose.Tasks
og_description: إضافة أيام العطلة إلى التقويم، وتعيينه لمشروع، وتحويل الجدول الزمني
  إلى MPP باستخدام Aspose.Tasks for Java. تعلم خطوة بخطوة الأتمتة.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: إضافة أيام العطلة إلى التقويم وحفظه كملف MPP باستخدام Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: إضافة أيام العطلة إلى التقويم وحفظه كملف MPP باستخدام Aspose.Tasks
url: /ar/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة أيام العطلة إلى التقويم وحفظه كملف MPP باستخدام Aspose.Tasks

## مقدمة

في إدارة المشاريع الحديثة، غالبًا ما تحتاج إلى **إضافة أيام العطلة إلى التقويم**، وإنشاء **تقويم MS Project**، ثم مشاركة الجدول الزمني بصيغة MPP الأصلية. سواءً كنت تجمع الجداول الزمنية من مصادر متعددة أو تقوم بترحيل البيانات القديمة، فإن إنشاء تقويم برمجيًا يزيل الأخطاء اليدوية ويسرّع التسليم. يشرح هذا البرنامج التعليمي العملية الكاملة لإنشاء تقويم في MS Project، وتخصيصه بأيام العطلة، **تعيين التقويم للمشروع**، وأخيرًا **تحويل المشروع إلى MPP** باستخدام Aspose.Tasks Java API.

## إجابات سريعة
- **ما الذي يغطيه هذا البرنامج التعليمي؟** إضافة أيام العطلة إلى تقويم، وتعيينه لمشروع، وحفظ النتيجة كملف MPP باستخدام Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى (JDK 8+).  
- **هل يمكنني تخصيص التقويم؟** نعم – يمكنك إضافة أوقات العمل، الاستثناءات، وأيام العطلة.  
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 10‑15 دقيقة لتقويم أساسي.  

## ما هو “إنشاء تقويم MS Project”؟

إنشاء تقويم MS Project يعني تعريف أيام العمل، الساعات، والاستثناءات التي تتحكم في جدولة المهام داخل ملف Microsoft Project. باستخدام Aspose.Tasks يمكنك بناء هذا التقويم برمجيًا، وتحديد أيام العطلة، ودمجه في مشروع دون فتح واجهة MS Project.

## لماذا نستخدم Aspose.Tasks لهذه المهمة؟

يجب عليك استخدام Aspose.Tasks لأنه يوفر توافقًا كاملًا مع Java، ولا حاجة إلى Microsoft Office، ويسمح لك بإنشاء وحفظ ملفات MPP الأصلية مباشرةً من الشيفرة. تدعم المكتبة جميع ميزات التقويم، وتعمل في أي بيئة خادم، وتُعالج المشاريع التي تصل إلى 10,000 مهمة في أقل من ثانية.

## المتطلبات المسبقة

1. **Java Development Kit (JDK) 8+** – تأكد من أن `java -version` يُظهر 1.8 أو أحدث.  
2. **Aspose.Tasks for Java** – حمّل أحدث ملف JAR من [موقع Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA أو Eclipse أو أي محرر تفضله.  
4. **معرفة أساسية بـ Java** – الإلمام بالفئات، والطرق، وإدخال/إخراج الملفات.

## كيفية إضافة أيام العطلة إلى التقويم

لإضافة أيام العطلة، تقوم بإنشاء كائن `Calendar` جديد، تسترجع مجموعة `Exceptions` الخاصة به، وتضيف إدخالات `DateException` لكل تاريخ عطلة. تمثل `DateException` تاريخًا غير عملي أو نطاقًا في التقويم. بعد ذلك، تتعامل Aspose.Tasks مع تلك التواريخ كأيام غير عملية، مما يضمن جدولة المهام حول العطلات المحددة.

### الخطوة 1: استيراد الحزم المطلوبة

أولاً، استورد فئات Aspose.Tasks وأدوات Java إلى النطاق.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### الخطوة 2: إعداد دليل البيانات

حدد مكان وجود قالب الإدخال وملفات الإخراج. استبدل العنصر النائب بالمسار الفعلي على جهازك.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 3: تعريف أسماء ملفات الإدخال والإخراج

سنقوم بتحميل ملف MPP موجود (أو مشروع فارغ) وكتابة النتيجة إلى ملف جديد.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### الخطوة 4: تحميل المشروع وإضافة تقويم جديد

فئة `Project` تمثل ملف MS Project في الذاكرة وتوفر الوصول إلى تقويماته، ومهامه، وموارده.

أنشئ نسخة `Project` من ملف المصدر وأضف تقويمًا باسم **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### الخطوة 5: تخصيص التقويم (اختياري)

كائن `Calendar` يحدد أيام العمل، الساعات، والاستثناءات لجدول مشروع.

إذا كنت بحاجة إلى أوقات عمل محددة، أو أيام عطلة، أو استثناءات، استدعِ طريقة المساعدة الخاصة بك. يستخدم المثال `GetTestCalendar` كعنصر نائب.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **نصيحة احترافية:** يمكنك تعديل `cal1.getWeekDays()` مباشرةً لتعيين ساعات العمل لكل يوم من أيام الأسبوع، أو استخدام `cal1.getExceptions()` **لإضافة أيام العطلة إلى التقويم**.

### الخطوة 6: تعيين التقويم للمشروع

أخبر المشروع باستخدام التقويم الذي تم إنشاؤه حديثًا لجميع حسابات الجدولة.

```java
project.set(Prj.CALENDAR, cal1);
```

### الخطوة 7: حفظ المشروع كملف MPP

تحدد تعداد `SaveFileFormat` صيغة الإخراج، حيث يشير `Mpp` إلى صيغة Microsoft Project الأصلية.

الآن **قم بتحويل المشروع إلى MPP** عن طريق حفظه باستخدام الخيار `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### الخطوة 8: تأكيد إكمال العملية بنجاح

رسالة بسيطة في وحدة التحكم تخبرك بأن العملية انتهت دون أخطاء.

```java
System.out.println("Process completed Successfully");
```

## حالات الاستخدام الشائعة

- **إنشاء جدول زمني تلقائي** للمشاريع المتكررة (مثل السبرينت الأسبوعية).  
- **ترحيل تقاويم CSV أو Excel القديمة** إلى ملف MS Project كامل المميزات.  
- **تقارير من جانب الخادم** حيث تُعيد خدمة ويب ملف MPP عند الطلب.  

## استكشاف الأخطاء وإصلاحها والمشكلات الشائعة

| المشكلة | السبب | الحل |
|-------|-------|-----|
| `NullPointerException` عند `project.save` | `dataDir` يشير إلى مجلد غير موجود | تأكد من وجود المجلد أو أنشئه برمجيًا. |
| لم يتم تطبيق التقويم على المهام | المهام لا تزال تشير إلى التقويم الافتراضي | بعد ضبط `Prj.CALENDAR`، قم أيضًا بتحديث `Task.CALENDAR` لكل مهمة إذا كانت قد تم تجاوزها مسبقًا. |
| ملف الإخراج حجمه 0 KB | عدم وجود أذونات كتابة | شغّل JVM بأذونات نظام ملفات مناسبة أو اختر مسارًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من MS Project؟**  
ج: نعم، يدعم Aspose.Tasks جميع صيغ ملفات Microsoft Project من Project 2007 حتى Project 2024، بما يتجاوز 10 إصدارات.

**س: هل يمكنني تخصيص التقويمات وفقًا لمتطلبات المشروع المحددة؟**  
ج: بالتأكيد. يمكنك تحديد أيام العمل، وضبط أسابيع عمل مخصصة، وإضافة أيام عطلة، وحتى إنشاء تقاويم متعددة داخل ملف مشروع واحد.

**س: هل يوفر Aspose.Tasks for Java دعمًا لاستكشاف الأخطاء والمساعدة؟**  
ج: نعم، يمكنك الحصول على المساعدة من منتدى مجتمع Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Tasks for Java؟**  
ج: نعم، تتوفر نسخة تجريبية مجانية كاملة الوظائف [Aspose.Tasks free trial](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks for Java؟**  
ج: يمكن طلب تراخيص مؤقتة عبر موقع Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-08-13  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إضافة تقويم إلى المشروع باستخدام Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [كيفية تعريف أيام الأسبوع في تقاويم MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [إنشاء استثناءات تقويم مخصصة باستخدام Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}