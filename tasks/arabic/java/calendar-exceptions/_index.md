---
date: 2026-11-06
description: إنشاء استثناءات تقويم مخصصة بسهولة، دمج تقويم MS Project، وإدارة وتعريف
  ومعالجة واسترجاع استثناءات التقويم في مشاريع Java باستخدام Aspose.Tasks. تبسيط سير
  عمل المشروع لإدارة مشروع فعّالة.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: استثناءات التقويم
og_description: تعلم كيفية إنشاء استثناءات التقويم في Java باستخدام Aspose.Tasks.
  إدارة تقويمات المشروع، تحديد أيام غير عمل، وتعديل تقويمات MS Project بكفاءة.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: إنشاء استثناءات التقويم باستخدام Aspose.Tasks للـ Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: كيفية إنشاء استثناءات التقويم باستخدام Aspose.Tasks للـ Java
url: /ar/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء استثناءات التقويم باستخدام Aspose.Tasks للـ Java

## المقدمة

`Aspose.Tasks` هي مكتبة Java تتيح إنشاء ملفات Microsoft Project ومعالجتها وتحويلها برمجيًا. في هذا البرنامج التعليمي ستتعلم كيفية **إنشاء استثناءات التقويم**—فترات غير عمل مخصصة تتجاوز التقويم الافتراضي للمشروع. التحكم الدقيق في أيام العمل وغير العمل أمر أساسي لتوقع الجداول الزمنية بدقة، وتخصيص الموارد، والامتثال للعطلات الإقليمية. بنهاية هذا الدليل ستعرف أيضًا كيفية **دمج تقويم MS Project** في تطبيق Java الخاص بك واسترجاع أو تعديل استثناءاته.

## إجابات سريعة
- **ماذا يمكنني أن أحقق؟** إنشاء، تعديل، واسترجاع استثناءات تقويم مخصصة في مشاريع Java.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks للـ Java (أحدث إصدار ثابت).  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في الإنتاج.  
- **هل يمكنني العمل مع ملفات MS Project؟** بالتأكيد – يمكنك استيراد، تعديل، وتصدير بيانات تقويم MS Project.  
- **هل هناك إعداد خاص مطلوب؟** فقط أضف ملف JAR الخاص بـ Aspose.Tasks إلى مسار الـ classpath واستورد الفئات ذات الصلة.

## كيفية إنشاء استثناءات تقويم مخصصة في Aspose.Tasks للـ Java؟

لإنشاء استثناءات تقويم مخصصة في Aspose.Tasks للـ Java، قم بتحميل المشروع المستهدف، استرجع تقويمه، حدد تواريخ بدء وانتهاء الاستثناء مع وقت العمل المطلوب، يمكنك اختيارياً ضبط نمط التكرار، ثم احفظ المشروع. هذه السلسلة تضيف الاستثناء فورًا وتخزنه في ملف .mpp.

فئة `Project` هي الكائن الأساسي في Aspose.Tasks الذي يمثل ملف Microsoft Project كامل. فئة `Project` تمثل ملف Microsoft Project وتوفر الوصول إلى محتوياته. كائن `Calendar` يحدد أوقات العمل وغير العمل للمشروع. فئة `Calendar` هي الحاوية لجميع قواعد أوقات العمل، بما في ذلك الاستثناءات. طريقة `addException()` تضيف استثناء تقويم جديد إلى التقويم. `addException()` هي واجهة API ذات نداء واحد تسجل فترة غير عمل للنطاق الزمني المحدد.

حمّل المشروع المستهدف باستخدام `Project project = new Project("example.mpp")`، احصل على كائن `Calendar` الخاص به، واستدعِ `addException()` مع نطاق التاريخ وإعدادات وقت العمل المطلوبة. هذا النمط ذو الخطوتين ينشئ استثناءً جديدًا فورًا ويخزنه عند حفظ المشروع. بالنسبة للعطلات المتكررة، اضبط `RecurrencePattern` على الاستثناء قبل الحفظ.

إنشاء استثناءات التقويم بهذه الطريقة يتيح لك **تحديد أيام غير العمل** بدقة، سواء كانت إغلاقات لمرة واحدة أو عطلات سنوية. بعد إضافة الاستثناء، يمكنك استدعاء `project.save("updated.mpp")` لكتابة التغييرات إلى القرص.

### نظرة عامة على الخطوات
1. حمّل ملف المشروع.  
2. استرجع أو أنشئ نسخة من فئة `Calendar`.  
3. حدد نطاق تاريخ الاستثناء ووقت العمل.  
4. (اختياري) اضبط التكرار للعطلات السنوية.  
5. احفظ المشروع.

## إدارة استثناءات التقويم في Aspose.Tasks
[تعلم كيفية إضافة وإزالة استثناءات التقويم في Aspose.Tasks للـ Java بكفاءة](./add-remove/). عندما يتعلق الأمر بإدارة المشاريع، المرونة هي المفتاح. تمكّنك Aspose.Tasks من إدارة استثناءات التقويم بسهولة، مما يسمح بتعديلات ديناميكية على جداول المشروع. يقدم هذا البرنامج التعليمي دليلًا خطوة بخطوة، لضمان فهمك للعملية بفعالية. اكتشف كيف تعزز سير عمل إدارة المشاريع بسهولة.

## تحديد أيام الأسبوع لاستثناءات التقويم باستخدام Aspose.Tasks
[إتقان فن تحديد أيام الأسبوع لاستثناءات التقويم في مشاريع Java](./define-weekdays/) باستخدام Aspose.Tasks. يتطلب جدولة المشروع بدقة اهتمامًا شديدًا بالتفاصيل. مع Aspose.Tasks، يمكنك تحديد أيام الأسبوع لاستثناءات التقويم بدقة، مما يضمن توافق مشاريعك مع الجداول الزمنية المحددة بسلاسة. يزودك هذا البرنامج التعليمي بالمعرفة اللازمة لتحسين الجدولة، مانحًا إياك السيطرة على جداول المشروع.

## معالجة التكرارات في استثناءات التقويم باستخدام Aspose.Tasks
[معالجة استثناءات التقويم بفعالية في مشاريع Java](./handle-occurrences/) باستخدام Aspose.Tasks للـ Java. إدارة المشاريع عملية ديناميكية، غالبًا ما تتطلب تعديلات للتعامل مع أحداث غير متوقعة. تمكّنك Aspose.Tasks من معالجة استثناءات التقويم بفعالية، مقدمة نهجًا مبسطًا لإدارة المشاريع. تعلم فن إدارة عدم اليقين في المشاريع بسهولة من خلال هذا الدليل التفصيلي.

## استرجاع استثناءات التقويم باستخدام Aspose.Tasks
[تعلم كيفية استرجاع استثناءات التقويم من MS Project باستخدام Aspose.Tasks للـ Java](./retrieve/). دمج استثناءات التقويم بسلاسة في عملية إدارة مشروعك مع Aspose.Tasks. يوجهك هذا البرنامج التعليمي خلال عملية استرجاع استثناءات التقويم خطوة بخطوة، لضمان دمج سلس وفعال في مشاريعك. استكشف قوة Aspose.Tasks لتعزيز قدرات إدارة مشروعك.

## كيفية دمج تقويم MS Project مع Aspose.Tasks؟

دمج تقويم MS Project مع Aspose.Tasks يتضمن تحميل ملف .mpp المصدر باستخدام فئة Project، الوصول إلى كائنات Calendar الافتراضية أو المخصصة، تعديل أو دمج الاستثناءات حسب الحاجة، ثم حفظ المشروع المحدث. هذا يتيح لك العمل برمجيًا مع تقاويم MS Project دون الحاجة لتفاعل يدوي مع واجهة المستخدم.

فئة `Project` هي الكائن الأساسي في Aspose.Tasks الذي يمثل ملف Microsoft Project كامل. استورد ملف MS Project موجود باستخدام `new Project("source.mpp")`؛ المكتبة تقوم تلقائيًا بتحميل تقويمه الافتراضي وأي استثناءات مخصصة. يمكنك بعد ذلك قراءة، تعديل، أو دمج تلك الاستثناءات قبل حفظ المشروع مرة أخرى إلى القرص. يتيح لك هذا النهج **تعديل بيانات تقويم MS Project** برمجيًا دون تحرير يدوي في واجهة MS Project.

## حالات الاستخدام الشائعة
- **جدولة العطلات** – تعريف العطلات الوطنية كأيام غير عمل عبر مشاريع متعددة.  
- **العمل بنظام الورديات** – إعداد أسابيع عمل مخصصة للفرق التي تعمل بجداول غير قياسية.  
- **تحديد مراحل المشروع** – حجب الفترات التي لا يجب جدولة أي عمل فيها، مثل فترات الصيانة.  
- **ترحيل الأنظمة القديمة** – استيراد تقاويم من ملفات MS Project أقدم وتعديلها برمجيًا.

## نصائح وأفضل الممارسات
- **نصيحة احترافية:** احرص دائمًا على استرجاع التقويم الحالي قبل إضافة استثناءات جديدة لتجنب التكرار.  
- **تحذير:** تغيير تقويم تم تعيينه بالفعل للمهام قد يؤدي إلى إزاحة تواريخ المهام؛ أعد حساب الجدول بعد التعديلات.  
- **الأداء:** اجمع تحديثات الاستثناءات المتعددة في معاملة واحدة لتقليل عبء I/O للملف. تقوم Aspose.Tasks بمعالجة ملفات تصل إلى 1 GB مع الحفاظ على استهلاك الذاكرة تحت 200 MB، ويمكنها معالجة أكثر من 30 نداء API متعلق بالتقويم في الثانية على خوادم عادية.

## دروس استثناءات التقويم
### [إدارة استثناءات التقويم في Aspose.Tasks](./add-remove/)
تعلم كيفية إضافة وإزالة استثناءات التقويم في Aspose.Tasks للـ Java بكفاءة. حسّن سير عمل إدارة المشاريع بسهولة.
### [تحديد أيام الأسبوع لاستثناءات التقويم باستخدام Aspose.Tasks](./define-weekdays/)
تعلم كيفية تحديد أيام الأسبوع لاستثناءات التقويم في مشاريع Java باستخدام Aspose.Tasks لجدولة دقيقة.
### [معالجة التكرارات في استثناءات التقويم باستخدام Aspose.Tasks](./handle-occurrences/)
تعلم كيفية معالجة استثناءات التقويم بفعالية في مشاريع Java مع Aspose.Tasks للـ Java. بسط عملية إدارة مشروعك الآن.
### [استرجاع استثناءات التقويم باستخدام Aspose.Tasks](./retrieve/)
تعلم كيفية استرجاع استثناءات التقويم من MS Project باستخدام Aspose.Tasks للـ Java. دليل خطوة بخطوة للتكامل السلس.

## الأسئلة المتكررة

**س: هل يمكنني تعديل استثناءات التقويم بعد نشر المشروع؟**  
ج: نعم. استخدم واجهات API لإضافة/إزالة وتحديد أيام الأسبوع لتحديث التقويم، ثم أعد حفظ ملف المشروع.

**س: هل تدعم Aspose.Tasks الاستثناءات المتكررة (مثل كل أول اثنين من الشهر)؟**  
ج: بالتأكيد. يغطي دليل “معالجة التكرارات” كيفية إعداد الأنماط المتكررة.

**س: كيف أضمن أن التقويم المخصص يُستخدم من قبل جميع المهام في المشروع؟**  
ج: عيّن التقويم كالتقويم الافتراضي للمشروع أو اضبطه صراحةً على خاصية `Calendar` لكل مهمة.

**س: هل يمكن دمج تقاويم من ملفات MS Project متعددة؟**  
ج: نعم. استرجع كل تقويم، ادمج استثناءاته برمجيًا، ثم عيّن التقويم المدمج للمشروع المستهدف.

**س: ما نسخة Aspose.Tasks المطلوبة لهذه الميزات؟**  
ج: جميع الميزات متوفرة في الإصدار المستقر الحالي من Aspose.Tasks للـ Java (2025.x).

## دروس ذات صلة

- [Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions](/tasks/java/calendar-exceptions/define-weekdays/)
- [Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Create Calendar Exception Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)

---

**آخر تحديث:** 2026-11-06  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.11  
**المؤلف:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}