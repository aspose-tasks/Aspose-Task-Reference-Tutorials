---
date: 2026-07-29
description: تعلم كيفية جدولة أيام عدم العمل عن طريق إنشاء تقويم مشروع باستخدام Aspose.Tasks
  for Java، وتعريف استثناءات أيام الأسبوع وإدارة جداول العطلات.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: جدولة أيام عدم العمل – إنشاء تقويم المشروع Aspose
og_description: جدولة أيام عدم العمل باستخدام Aspose.Tasks for Java. تعلم كيفية تعريف
  أيام الأسبوع، وإضافة استثناءات التقويم، وإدارة جداول العطلات بفعالية.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: جدولة أيام عدم العمل – إنشاء تقويم المشروع Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: جدولة أيام عدم العمل – إنشاء تقويم المشروع Aspose
url: /ar/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# جدولة أيام غير العمل – إنشاء تقويم مشروع Aspose

### مقدمة
عندما تحتاج إلى **جدولة أيام غير العمل** لمشروع، يجب أن تكون قادرًا على نمذجة العطلات، والنوبات الخاصة، أو الإغلاقات المؤقتة مباشرةً في خطة المشروع. توفر لك Aspose.Tasks for Java تحكمًا كاملاً في تعريفات التقويم، مما يتيح لك إضافة استثناءات تعكس الجداول الزمنية الواقعية. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة لتعريف أيام الأسبوع لاستثناءات التقويم، بحيث تظل جداول مشروعك دقيقة وموثوقة. في النهاية ستلاحظ أيضًا كيف يتناسب ذلك مع استراتيجية **جدولة أيام غير العمل** الأوسع لأي مشروع مؤسسي.

## إجابات سريعة
- **ماذا يعني “جدولة أيام غير العمل”؟**  
  يعني استخدام Aspose.Tasks لإنشاء تقويم يحدد تواريخ معينة كغير عاملة، مما يؤثر على تواريخ المهام تلقائيًا.  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟**  
  النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **ما هي بيئات التطوير المتكاملة (IDE) المدعومة؟**  
  IntelliJ IDEA، Eclipse، NetBeans، أو أي بيئة تطوير تدعم Java 8+.  
- **هل يمكنني إضافة استثناءات متعددة إلى نفس التقويم؟**  
  نعم – يمكنك إضافة عدد غير محدود من كائنات `CalendarException` حسب الحاجة.  
- **ما هي صيغ الملفات التي يمكنني حفظ المشروع بها؟**  
  XML، MPP، والعديد من الصيغ الأخرى التي يدعمها Aspose.Tasks.  

## ما هو تقويم المشروع في Aspose.Tasks؟
**تقويم المشروع** هو الكائن الأعلى مستوى في Aspose.Tasks الذي يحدد أيام وساعات العمل للمشروع. يؤثر مباشرةً على تواريخ بدء/إنهاء المهام، وتخصيص الموارد، وحسابات الجدول الزمني العامة. من خلال تخصيص تقويم، تضمن أن الجدول الزمني يحترم القيود الواقعية مثل عطلات الشركة أو سياسات العمل في عطلات نهاية الأسبوع.

## لماذا تعريف أيام الأسبوع لاستثناءات التقويم؟
يضمن تعريف استثناءات أيام الأسبوع أن محرك المشروع يتعامل مع تلك الأيام كغير عاملة، مما يمنع جدولة المهام تلقائيًا فيها ويحافظ على توافق الجدول الزمني مع القيود الواقعية مثل العطلات، وفترات الصيانة، أو أنماط النوبات الخاصة عبر المؤسسة.

- **جداول زمنية دقيقة:** لن تُوضع المهام في العطلات أو فترات الحظر.  
- **تخطيط الموارد:** تُخصص الموارد فقط في أيام العمل الصالحة، مما يمنع الإفراط في التخصيص.  
- **الامتثال:** تتبع الجداول تلقائيًا سياسات المنظمة أو تقاويم العطلات القانونية.  

## جدولة أيام غير العمل مع استثناءات التقويم
عند الحفاظ على **جدولة أيام غير العمل**، عادةً ما يكون لديك قائمة رئيسية بالعطلات، وفترات الصيانة، أو فترات الحظر الأخرى. إضافة تلك التواريخ ككائنات `CalendarException` يضمن أن كل حساب—سواء كان تحليل المسار الحرج أو موازنة الموارد—يتبع تلك القيود تلقائيًا. هذه الطريقة تلغي التعديلات اليدوية للتواريخ وتقلل من خطر انحراف الجدول الزمني.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – الإصدار 8 أو أحدث.  
2. **Aspose.Tasks for Java** – قم بتنزيله من صفحة [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة (IDE)** – IntelliJ IDEA، Eclipse، NetBeans، أو أي محرر متوافق مع Java.  

## كيفية جدولة أيام غير العمل باستخدام استثناءات التقويم
حمّل مشروعك، أنشئ تقويمًا مخصصًا، وأضف كائنات `CalendarException` التي تحدد أيام الأسبوع المطلوبة كغير عاملة. يمكن إكمال هذه العملية بالكامل في بضع خطوات بسيطة، وسيؤثر التقويم الناتج تلقائيًا على جميع منطق جدولة المهام.

### دليل خطوة بخطوة

### الخطوة 1: استيراد الحزم المطلوبة
نحتاج إلى فئات Aspose.Tasks الأساسية وحزمة Java `GregorianCalendar` لمعالجة التواريخ.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### الخطوة 2: تحديد دليل البيانات
حدد الموقع الذي سيتم حفظ ملف المشروع المُنشأ فيه.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 3: إنشاء مثيل للمشروع
`Project` هو الكائن الرئيسي الذي يحتوي على جميع بيانات المشروع، بما في ذلك المهام والموارد والتقويمات.

```java
Project project = new Project();
```

### الخطوة 4: تعريف تقويم
`Calendar` يمثل جدولًا لأوقات العمل وغير العمل داخل المشروع.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### الخطوة 5: تعريف استثناء أيام الأسبوع
`CalendarException` يمثل فترة تم تحديدها كغير عاملة في تقويم.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### الخطوة 6: حفظ المشروع
احفظ المشروع، بما في ذلك التقويم المخصص واستثنائه، إلى ملف XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **تواريخ الاستثناء غير مطبقة** | تأكد من `setEnteredByOccurrences(false)` والقيم الصحيحة لـ `FromDate/ToDate`. |
| **الملف المحفوظ فارغ** | تحقق من أن `dataDir` يشير إلى مجلد قابل للكتابة وأن اسم الملف ينتهي بـ `.xml`. |
| **التقويم غير منعكس في جدولة المهام** | قم بتعيين التقويم للمهام أو الموارد باستخدام `task.setCalendar(cal)` أو `resource.setCalendar(cal)`. |

## الأسئلة المتكررة

**س: هل يمكنني تعريف استثناءات متعددة لأيام أسبوع مختلفة داخل نفس التقويم؟**  
ج: نعم. أضف كائنات `CalendarException` إضافية إلى `cal.getExceptions()` لكل فترة أو قاعدة مميزة.

**س: هل Aspose.Tasks for Java متوافق مع بيئات تطوير Java المختلفة؟**  
ج: بالتأكيد. المكتبة تعمل مع IntelliJ IDEA، Eclipse، NetBeans، وأي بيئة تطوير تدعم مشاريع Java القياسية.

**س: هل يمكنني تخصيص أنواع استثناءات غير الاستثناءات اليومية؟**  
ج: نعم. استخدم `CalendarExceptionType.Weekly` أو `Monthly` أو `Yearly` لتلبية احتياجاتك الجدولية.

**س: كيف يمكنني التعامل مع الاستثناءات بشكل ديناميكي بناءً على متطلبات المشروع؟**  
ج: أنشئ كائنات الاستثناء برمجيًا—مثلاً، اقرأ تواريخ العطلات من قاعدة بيانات أو ملف إعدادات وأنشئ مثيلات `CalendarException` داخل حلقة.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من صفحة [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## الخلاصة
باتباعك لهذه الخطوات، أصبحت الآن تعرف كيفية **جدولة أيام غير العمل** من خلال إنشاء تقويم مشروع وتعريف استثناءات أيام الأسبوع التي تعكس بدقة العطلات أو الفترات غير العاملة الخاصة. تكوين التقويم بشكل صحيح أمر أساسي للجداول الزمنية الواقعية، وتخصيص الموارد، ونجاح المشروع ككل. استكشف المزيد بربط التقويم المخصص بالمهام أو الموارد وتجربة أنواع استثناءات أخرى لبناء **جدولة أيام غير العمل** شاملة لأي مشروع.

---

**آخر تحديث:** 2026-07-29  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [إضافة تقويم إلى المشروع باستخدام Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [إنشاء استثناء تقويم Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)
- [كيفية تعيين التقويم وتحديد أيام الأسبوع في MS Project باستخدام Aspose.Tasks](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}