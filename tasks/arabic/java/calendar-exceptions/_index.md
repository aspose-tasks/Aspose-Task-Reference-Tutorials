---
date: 2026-08-18
description: إنشاء استثناءات تقويم مخصصة بسهولة، دمج تقويم MS Project، وإدارة، تعريف،
  معالجة واسترجاع استثناءات التقويم في مشاريع Java باستخدام Aspose.Tasks. تبسيط سير
  عمل المشروع لإدارة مشروع فعّالة.
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: استثناءات التقويم
og_description: تعلم كيفية إنشاء استثناءات التقويم، إدارة تقويم المشروع، وتحديد أيام
  غير عمل في Java باستخدام Aspose.Tasks. دليل سريع للمطورين.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: كيفية إنشاء استثناءات التقويم باستخدام Aspose.Tasks لـ Java
schemas:
- author: Aspose
  dateModified: '2026-08-18'
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
title: كيفية إنشاء استثناءات التقويم باستخدام Aspose.Tasks لـ Java
url: /ar/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء استثناءات التقويم باستخدام Aspose.Tasks للغة Java

## مقدمة

`Aspose.Tasks` هي مكتبة Java تمكّن من إنشاء ومعالجة وتحويل ملفات Microsoft Project برمجيًا. في هذا البرنامج التعليمي ستتعلم كيفية **إنشاء استثناءات التقويم** — فترات غير عمل مخصصة تتجاوز التقويم الافتراضي للمشروع. التحكم الدقيق في أيام العمل وأيام عدم العمل أمر أساسي لتوقع الجداول الزمنية بدقة، وتخصيص الموارد، والامتثال للعطلات الإقليمية. بنهاية هذا الدليل ستعرف أيضًا كيفية **دمج تقويم MS Project** في تطبيق Java الخاص بك واسترجاع أو تعديل استثنائه.

## إجابات سريعة
- **ما الذي يمكنني تحقيقه؟** إنشاء وتعديل واسترجاع استثناءات تقويم مخصصة في مشاريع Java.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks للغة Java (أحدث إصدار ثابت).  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام في الإنتاج.  
- **هل يمكنني العمل مع ملفات MS Project؟** بالطبع – يمكنك استيراد وتحرير وتصدير بيانات تقويم MS Project.  
- **هل هناك أي إعداد خاص مطلوب؟** فقط أضف ملف Aspose.Tasks JAR إلى مسار الفئة (classpath) واستورد الفئات ذات الصلة.  

## كيفية إنشاء استثناءات تقويم مخصصة في Aspose.Tasks للغة Java؟

`Project` تمثل ملف Microsoft Project وتوفر الوصول إلى محتوياته.  
`Calendar` يحدد أوقات العمل وأوقات عدم العمل للمشروع.  
`addException()` يضيف استثناء تقويم جديد إلى التقويم.

حمّل المشروع المستهدف باستخدام `Project project = new Project("example.mpp")`، احصل على كائن `Calendar` الخاص به، واستدعِ `addException()` مع نطاق التاريخ المطلوب وإعدادات وقت العمل. هذا النمط ذو الخطوتين ينشئ استثناءً جديدًا فورًا ويحفظه عند حفظ المشروع. بالنسبة للعطلات المتكررة، قم بتكوين `RecurrencePattern` على الاستثناء قبل الحفظ.

إنشاء استثناءات التقويم بهذه الطريقة يتيح لك **تحديد أيام عدم العمل** بدقة، سواء كانت إغلاقات لمرة واحدة أو عطلات سنوية. بعد إضافة الاستثناء، يمكنك استدعاء `project.save("updated.mpp")` لكتابة التغييرات إلى القرص.

### نظرة عامة على الخطوات
1. حمّل ملف المشروع.  
2. استرجع أو أنشئ كائن `Calendar`.  
3. حدد نطاق تاريخ الاستثناء ووقت العمل.  
4. (اختياري) قم بتكوين التكرار للعطلات السنوية.  
5. احفظ المشروع.  

## إدارة استثناءات التقويم في Aspose.Tasks
[تعلم كيفية إضافة وإزالة استثناءات التقويم في Aspose.Tasks للغة Java بفعالية](./add-remove/). عندما يتعلق الأمر بإدارة المشاريع، فإن المرونة هي الأساس. تمكنك Aspose.Tasks من إدارة استثناءات التقويم بسهولة، مما يسمح بتعديلات ديناميكية على جداول المشروع. يوفر هذا البرنامج التعليمي دليلًا خطوة بخطوة، لضمان استيعابك للعملية بفعالية. اكتشف كيفية تحسين سير عمل إدارة المشاريع بسهولة.

## تحديد أيام الأسبوع لاستثناءات التقويم باستخدام Aspose.Tasks
[إتقان فن تحديد أيام الأسبوع لاستثناءات التقويم في مشاريع Java](./define-weekdays/) باستخدام Aspose.Tasks. يتطلب جدولة المشروع بدقة اهتمامًا دقيقًا بالتفاصيل. مع Aspose.Tasks، يمكنك تحديد أيام الأسبوع لاستثناءات التقويم بدقة، مما يضمن توافق مشاريعك مع الجداول الزمنية المحددة بسلاسة. يزودك هذا البرنامج التعليمي بالمعرفة اللازمة لتحسين الجدولة، مما يمنحك السيطرة على جداول المشروع.

## معالجة التكرارات في استثناءات التقويم باستخدام Aspose.Tasks
[معالجة استثناءات التقويم بفعالية في مشاريع Java](./handle-occurrences/) مع Aspose.Tasks للغة Java. إدارة المشاريع عملية ديناميكية، غالبًا ما تتطلب تعديلات للتعامل مع الأحداث غير المتوقعة. تمكنك Aspose.Tasks من معالجة استثناءات التقويم بفعالية، مما يوفر نهجًا مبسطًا لإدارة المشاريع. تعلم فن إدارة عدم اليقين في المشاريع بسهولة من خلال هذا البرنامج التعليمي المفصل.

## استرجاع استثناءات التقويم باستخدام Aspose.Tasks
[تعلم كيفية استرجاع استثناءات التقويم من MS Project باستخدام Aspose.Tasks للغة Java](./retrieve/). قم بدمج استثناءات التقويم بسلاسة في عملية إدارة مشروعك باستخدام Aspose.Tasks. يرشدك هذا البرنامج التعليمي خلال عملية استرجاع استثناءات التقويم خطوة بخطوة، لضمان دمج سلس وفعّال في مشاريعك. استفد من قوة Aspose.Tasks لتعزيز قدرات إدارة مشروعك.

## كيفية دمج تقويم MS Project مع Aspose.Tasks؟

`Project` يحمل ملف Microsoft Project، ويكشف عن تقويماته وبيانات المشروع الأخرى. استورد ملف MS Project موجود باستخدام `new Project("source.mpp")`؛ تقوم المكتبة بتحميل تقويمه الافتراضي وأي استثناءات مخصصة تلقائيًا. يمكنك بعد ذلك قراءة أو تعديل أو دمج تلك الاستثناءات قبل حفظ المشروع مرة أخرى إلى القرص. تتيح لك هذه الطريقة **تعديل بيانات تقويم MS Project** برمجيًا دون الحاجة إلى تحرير يدوي في واجهة MS Project.

## حالات الاستخدام الشائعة
- **جدولة العطلات** – حدد العطلات الوطنية كأيام غير عمل عبر مشاريع متعددة.  
- **العمل بنظام النوبات** – أنشئ أسابيع عمل مخصصة للفرق التي تعمل بجداول غير قياسية.  
- **تقييد مراحل المشروع** – احجز فترات لا يجب جدولة أي عمل فيها، مثل نوافذ الصيانة.  
- **الهجرة من الأنظمة القديمة** – استورد التقويمات من ملفات MS Project القديمة وقم بتعديلها برمجيًا.  

## نصائح وأفضل الممارسات
- **نصيحة احترافية:** دائمًا استرجع التقويم الحالي قبل إضافة استثناءات جديدة لتجنب التكرارات.  
- **تحذير:** تغيير تقويم تم تعيينه بالفعل للمهام قد يغيّر تواريخ المهام؛ أعد حساب الجدول بعد التعديلات.  
- **الأداء:** قم بتجميع تحديثات استثناءات متعددة في معاملة واحدة لتقليل عبء إدخال/إخراج الملفات. تعالج Aspose.Tasks ملفات تصل إلى 500 ميغابايت دون تحميل المستند بالكامل في الذاكرة، وتتعامل مع أكثر من 50 استدعاء API مرتبطًا بالتقويم في الثانية على عتاد الخادم النموذجي.  

## دروس استثناءات التقويم
### [إدارة استثناءات التقويم في Aspose.Tasks](./add-remove/)
تعلم كيفية إضافة وإزالة استثناءات التقويم في Aspose.Tasks للغة Java بفعالية. حسّن سير عمل إدارة المشاريع بسهولة.
### [تحديد أيام الأسبوع لاستثناءات التقويم باستخدام Aspose.Tasks](./define-weekdays/)
تعلم كيفية تحديد أيام الأسبوع لاستثناءات التقويم في مشاريع Java باستخدام Aspose.Tasks لجدولة مشروع دقيقة.
### [معالجة التكرارات في استثناءات التقويم باستخدام Aspose.Tasks](./handle-occurrences/)
تعلم كيفية معالجة استثناءات التقويم بفعالية في مشاريع Java مع Aspose.Tasks للغة Java. قم بتبسيط عملية إدارة مشروعك الآن.
### [استرجاع استثناءات التقويم باستخدام Aspose.Tasks](./retrieve/)
تعلم كيفية استرجاع استثناءات التقويم من MS Project باستخدام Aspose.Tasks للغة Java. برنامج تعليمي خطوة بخطوة للدمج السلس.  

## الأسئلة المتكررة

**Q: هل يمكنني تعديل استثناءات التقويم بعد نشر المشروع بالفعل؟**  
A: نعم. استخدم واجهات برمجة التطبيقات add‑remove و define‑weekdays لتحديث التقويم، ثم أعد حفظ ملف المشروع.  

**Q: هل تدعم Aspose.Tasks الاستثناءات المتكررة (مثل كل أول اثنين من الشهر)؟**  
A: بالتأكيد. يغطي برنامج “handle occurrences” كيفية إعداد الأنماط المتكررة.  

**Q: كيف أضمن أن التقويم المخصص الخاص بي يُستخدم من قبل جميع المهام في المشروع؟**  
A: قم بتعيين التقويم كالتقويم الافتراضي للمشروع أو اضبطه صراحةً على خاصية `Calendar` لكل مهمة.  

**Q: هل من الممكن دمج تقويمات من ملفات MS Project متعددة؟**  
A: نعم. استرجع كل تقويم، ودمج استثناءاته برمجيًا، ثم عيّن التقويم المدمج إلى المشروع المستهدف.  

**Q: ما هو إصدار Aspose.Tasks المطلوب لهذه الميزات؟**  
A: جميع الميزات متاحة في الإصدار المستقر الحالي من Aspose.Tasks للغة Java (2025.x).  

---  
**آخر تحديث:** 2026-08-18  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

## دروس ذات صلة

- [إنشاء تقويم مشروع Aspose – تحديد أيام الأسبوع لاستثناءات التقويم](/tasks/java/calendar-exceptions/define-weekdays/)
- [استرجاع استثناءات التقويم باستخدام Aspose.Tasks – دليل asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [إنشاء استثناء تقويم Aspose للغة Java](/tasks/java/calendar-exceptions/add-remove/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}