---
date: 2026-08-13
description: تعلم كيفية إنشاء تقويم قياسي لـ MS Project باستخدام Java و Aspose.Tasks.
  يوضح لك هذا الدليل خطوة بخطوة كيفية إنشاء تقويم قياسي لـ MS Project، إضافته كافتراضي،
  وحفظ الملف.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: إنشاء تقويم قياسي في Aspose.Tasks
og_description: كيفية إنشاء تقويم في Java باستخدام Aspose.Tasks. تعلم كيفية بناء تقويم
  قياسي لـ MS Project، تعيينه كافتراضي، وحفظ ملف المشروع في دقائق.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: كيفية إنشاء تقويم – إنشاء تقويم قياسي في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: كيفية إنشاء تقويم – إنشاء تقويم قياسي في Aspose.Tasks
url: /ar/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيف تنشئ تقويم – إنشاء تقويم قياسي في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي ستتعلم **كيفية إنشاء كائنات تقويم** لملفات Microsoft Project باستخدام مكتبة Aspose.Tasks للغة Java. سنستعرض إنشاء تقويم MS Project قياسي، وجعله التقويم الافتراضي (القياسي)، وحفظ ملف المشروع. في نهاية الدليل ستكون قادرًا على دمج إنشاء التقويم في أي حل لإدارة المشاريع مبني على Java.

## إجابات سريعة
- **ماذا يعني “تقويم قياسي”؟** إنه تعريف وقت العمل الافتراضي المطبق على المهام التي لا يمتلك تقويمًا مخصصًا مخصصًا لها.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks للغة Java – واجهة برمجة تطبيقات Java صافية تعمل دون الحاجة لتثبيت Microsoft Project.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ الترخيص التجاري مطلوب للنشر في بيئات الإنتاج.  
- **ما صيغة الملف الناتج؟** ملف Microsoft Project مبني على XML (`.xml`).  
- **كم تستغرق عملية التنفيذ؟** حوالي 5‑10 دقائق لإعداد تقويم أساسي.

## ما هو التقويم القياسي في Microsoft Project؟
التقويم القياسي يحدد أيام وساعات العمل الافتراضية للمشروع، عادةً من الاثنين إلى الجمعة، من 8 ص إلى 5 م. عندما تضيف تقويمًا قياسيًا، أي مهمة لا تمتلك تقويمًا مخصصًا ستحصل على هذه أوقات العمل، مما يضمن جدولة متسقة عبر المشروع.

## لماذا نستخدم Aspose.Tasks لإنشاء تقويم؟
Aspose.Tasks للغة Java يدعم **أكثر من 50 تنسيقًا للإدخال والإخراج** ويمكنه معالجة مشاريع تصل إلى **10,000 مهمة** دون تحميل الملف بالكامل في الذاكرة. هذه المكتبة الصافية تسمح لك بأتمتة إنشاء ملفات Project على الخوادم، خطوط CI، أو أي تطبيق Java، مما يلغي الحاجة إلى تثبيت Microsoft Project مرخص.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر ما يلي:

### تثبيت مجموعة تطوير جافا (JDK)
قم بتثبيت أحدث JDK من موقع Oracle أو من توزيعة OpenJDK.

### مكتبة Aspose.Tasks للغة Java
حمّل المكتبة من [صفحة التحميل](https://releases.aspose.com/tasks/java/). أضف ملف JAR إلى مسار الفئة (classpath) في مشروعك.

## استيراد الحزم
نحتاج إلى استيراد واحد فقط لهذا البرنامج التعليمي:

```java
import com.aspose.tasks.*;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل البيانات
حدد المكان الذي سيُحفظ فيه ملف المشروع المُنشأ.

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق على جهازك (مثال: `C:/Projects/Output/`).

### الخطوة 2: إنشاء نسخة مشروع
`Project` هو الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project واحد في الذاكرة. إن إنشائه يمنحك حاوية للتقويمات، والمهام، والموارد، وغيرها من بيانات المشروع.

```java
Project project = new Project();
```

### الخطوة 3: تعريف وجعل التقويم قياسيًا
`Calendar` هو الصنف الذي يُنمذج جدول وقت العمل. إضافة تقويم جديد باسم **“My Cal”** واستدعاء `makeStandardCalendar` يرقّيه إلى التقويم الافتراضي للمشروع بأكمله.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **نصيحة احترافية:** طريقة `makeStandardCalendar` تُعلِّم تلقائيًا التقويم المُقدم كافتراضي للمشروع، وهو بالضبط ما تحتاجه عندما تريد **إضافة وظيفة تقويم قياسي**.

### الخطوة 4: حفظ المشروع
`SaveFileFormat` هو تعداد يحدد صيغة الملف المستخدمة عند حفظ المشروع.  
احفظ المشروع (بما في ذلك التقويم الجديد) إلى ملف XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

يمكنك تغيير اسم الملف أو الصيغة (`SaveFileFormat.Pp`) إذا كنت تفضّل نسخة Project مختلفة.

### الخطوة 5: عرض رسالة الانتهاء
امنح نفسك إشارة بصرية بأن العملية انتهت دون أخطاء.

```java
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| **الملف غير موجود** | `dataDir` يشير إلى مجلد غير موجود | أنشئ المجلد أو استخدم مسارًا مطلقًا |
| **استثناء الترخيص** | تشغيل بدون ترخيص Aspose.Tasks صالح في بيئة الإنتاج | تطبيق ملف الترخيص عبر `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **تقويم فارغ** | نسيان إضافة تعريفات وقت العمل | استخدم `cal1.getWeekDays().add(WeekDay.DayType.Monday)` إلخ، إذا كنت تحتاج ساعات عمل مخصصة |

## الأسئلة المتكررة

**س: هل Aspose.Tasks متوافق مع جميع إصدارات Microsoft Project؟**  
ج: نعم، يدعم Aspose.Tasks مجموعة واسعة من إصدارات Microsoft Project، من 2000 حتى أحدث الإصدارات.

**س: هل يمكنني تخصيص إعدادات التقويم أكثر؟**  
ج: بالتأكيد! يمكنك تعديل أيام العمل، وإضافة استثناءات، وتعريف أوقات عمل محددة باستخدام صفي `WeekDay` و `WorkingTime`.

**س: هل Aspose.Tasks مناسب لتطبيقات على مستوى المؤسسة؟**  
ج: بالطبع. صُممت المكتبة لبيئات عالية الأداء وقابلة للتوسع وتوفر دعمًا شاملاً لملفات Project الكبيرة.

**س: هل يقدم Aspose.Tasks دعمًا فنيًا للمطورين؟**  
ج: نعم، توفر Aspose منتديات مخصصة، ودعمًا عبر نظام التذاكر، ووثائق واسعة لمساعدتك في حل أي مشكلة بسرعة.

**س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟**  
ج: نعم، يمكنك تجربة النسخة التجريبية المجانية المتاحة على [الموقع الإلكتروني](https://purchase.aspose.com/buy)، مما يتيح لك تقييم جميع الميزات قبل الالتزام.

---

**آخر تحديث:** 2026-08-13  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [إضافة تقويم إلى المشروع باستخدام Aspose.Tasks للغة Java](/tasks/java/calendars/create/)
- [كيفية تعيين تقويم المشروع في Java باستخدام Aspose.Tasks](/tasks/java/calendars/properties/)
- [إنشاء استثناءات تقويم مخصصة باستخدام Aspose.Tasks للغة Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}