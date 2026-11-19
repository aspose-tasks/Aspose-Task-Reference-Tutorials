---
date: 2026-11-19
description: تعلم كيفية إنشاء تقويم مخصص في Java باستخدام Aspose.Tasks. يوضح لك هذا
  الدليل كيفية تعريف أيام العمل، وتحديد ساعات العمل، وتعديل تقويمات MS Project برمجياً.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: التقويمات
og_description: تعلم كيفية إنشاء تقويم مخصص في Java باستخدام Aspose.Tasks. إتقان تعريف
  أيام العمل، وتحديد ساعات العمل، وتعديل تقويمات MS Project بفعالية.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: كيفية إنشاء تقويم مخصص في Java باستخدام Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: كيفية إنشاء تقويم مخصص في Java باستخدام Aspose.Tasks
url: /ar/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التقويمات

## مقدمة

إذا كنت مطور Java يرغب في **إنشاء حلول تقويم مخصصة بلغة Java**، فقد وصلت إلى المكان الصحيح. يجمع هذا المركز جميع دروس Aspose.Tasks for Java التي توضح كيفية **تعريف أيام العمل في MS Project**، **تحديد ساعات العمل في MS Project**، وتعديل إعدادات التقويم برمجياً. سواء كنت تبني محرك جدولة جديد أو توسّع خطة موجودة، فإن إتقان هذه الـ APIs يمنحك تحكمًا دقيقًا في أنماط أيام العمل، العطلات، والنوبات المخصصة—دون الحاجة إلى فتح واجهة MS Project.

## إجابات سريعة
- **ما هو الغرض الأساسي من تعريف أيام الأسبوع؟**  
  لإخبار MS Project أي الأيام هي أيام عمل وما هي ساعات عملها.  
- **أي مكتبة تتعامل مع تعريف أيام الأسبوع في Java؟**  
  Aspose.Tasks for Java توفر API سلسة لتعامل مع التقويم.  
- **هل أحتاج إلى ترخيص؟**  
  ترخيص تقييم مجاني يكفي للاختبار؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل يمكنني تعريف تقاويم متعددة لفرق مختلفة؟**  
  نعم – يمكن لكل مشروع أن يحتوي على عدة تقاويم، كل منها بإعدادات أيام الأسبوع الخاصة به.  
- **هل هناك مشروع عينة للبدء؟**  
  درس “Define Weekdays in Calendar” المرتبط أدناه يتضمن مثالًا جاهزًا للتنفيذ.

## كيف تنشئ تقويمًا مخصصًا بلغة Java؟

حمّل مشروعًا، أنشئ أو استرجع تقويمًا، أضف تعريفات أيام الأسبوع، واحفظ الملف—كل ذلك في عدد قليل من استدعاءات الـ API. يزيل هذا النهج خطوات الواجهة اليدوية، ويسمح لك بأتمتة إنشاء التقويم عبر عشرات المشاريع، ويضمن نمط أيام عمل متسق عبر مؤسستك.

## ما هو الـ Project class؟

فئة `Project` هي الكائن المركزي لتحميل، تحرير، وحفظ ملفات MS Project. تحتفظ بمجموعات من المهام، الموارد، والتقويمات، وتوفر طرقًا تسمح لك بقراءة وتعديل كل جانب من جوانب المشروع برمجيًا. باستخدام هذه الفئة، يمكنك الوصول إلى مجموعة تقاويم المشروع، تعديل أوقات العمل، وحفظ التغييرات مرة أخرى إلى ملف MPP أو XML.

## كيف أعرف تعريف أيام الأسبوع في تقاويم MS Project؟

فئة `Project` تمثل ملف MS Project وتوفر الوصول إلى هياكله. كائن `Calendar` يخزن تعريفات أوقات العمل والاستثناءات للمشروع. حمّل مشروعك باستخدام `new Project("myproject.mpp")`، استرجع (أو أنشئ) كائن `Calendar`، ثم استدعِ `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. هذا السطر الواحد ينشئ إدخال يوم عمل للاثنين بمدة 8 ساعات. كرّر ذلك لبقية الأيام، وأخيرًا احفظ المشروع بـ `project.save("updated.mpp")`. يتيح لك هذا النمط المختصر تعريف، تعديل، أو حذف أيام الأسبوع ببضع استدعاءات API فقط، دون الحاجة إلى التفاعل مع الواجهة اليدوية.

## ما هو كائن WeekDay؟

كائن `WeekDay` يمثل إدخالًا ليوم واحد من أيام الأسبوع داخل تقويم. يخزن ما إذا كان اليوم عملًا، فترات أوقات العمل لهذا اليوم، وعلامات للسلوك الافتراضي. يمكنك إرفاق واحد أو أكثر من فترات `WorkingTime` لنمذجة نوبات مقسمة، تعيين اليوم كغير عامل، أو وراثة الإعدادات الافتراضية من التقويم الأب.

## كيف تعرف أيام العمل في MS Project؟

تعرّف أيام العمل بإضافة كائنات `WeekDay` إلى مجموعة `WeekDays` الخاصة بالتقويم. كل `WeekDay` يحدد ما إذا كان اليوم عملًا ونطاقات الوقت التي تُعتبر وقت عمل. على سبيل المثال، لجعل السبت نصف يوم، أضف `WeekDay` مع `WorkingTime` واحد من 10:00 إلى 14:00. تقوم الـ API تلقائيًا بتحديث حسابات جدول المشروع.

## كيف تحدد ساعات العمل في MS Project؟

حدد ساعات العمل بإنشاء واحد أو أكثر من فترات `WorkingTime` لكل `WeekDay`. تأخذ `WorkingTime` قيم ساعة البداية، دقيقة البداية، ساعة النهاية، ودقيقة النهاية. يمكنك تعيين فترات متعددة ليوم واحد لنمذجة نوبات مقسمة (مثل 08:00‑12:00 و13:00‑17:00). بعد ضبط جميع أيام الأسبوع، استدعِ `project.save(...)` لحفظ التغييرات.

## لماذا نستخدم Aspose.Tasks for Java لتعريف أيام الأسبوع؟

- **تحكم كامل عبر الـ API** – لا قيود للواجهة؛ يمكنك إنشاء، تعديل، أو حذف إدخالات أيام الأسبوع برمجيًا.  
- **متعدد المنصات** – يعمل على أي بيئة متوافقة مع JVM، من تطبيقات سطح المكتب إلى الخدمات السحابية.  
- **دقة** – ضبط أوقات عمل مختلفة لكل يوم، إضافة استثناءات للعطلات، ومزامنة التقويمات عبر مشاريع متعددة.  
- **أداء** – معالجة مشاريع تحتوي على أكثر من 500 مهمة وتقويمات تشمل أكثر من 100 أسبوع دون تحميل الواجهة بالكامل، مع أوقات تحويل أقل من ثانيتين على خادم 2.5 GHz (ادعاء مستند إلى معيار Aspose).  
- **دعم صيغ واسع** – Aspose.Tasks يدعم أكثر من 30 واجهة برمجة تطبيقات متعلقة بالتقويم ويمكنه الاستيراد/التصدير إلى أكثر من 20 صيغة ملف، مما يتيح تكاملًا سلسًا مع خطوط أنابيب بيانات المشروع الحالية.

## المتطلبات المسبقة
- تثبيت Java 8 أو أعلى.  
- مكتبة Aspose.Tasks for Java (تم تحميلها من موقع Aspose أو إضافتها عبر Maven/Gradle).  
- ترخيص Aspose.Tasks صالح (ترخيص التقييم يكفي للتعلم).  

## إدارة خصائص تقويم MS Project في Aspose.Tasks

اكتشف الإمكانات الكاملة لإدارة خصائص تقويم MS Project في Java باستخدام Aspose.Tasks. يقدّم دليلنا خطوة بخطوة تفاصيل إدارة التقويم، مع رؤى قيّمة حول التخصيص والتحسين. من ضبط ساعات العمل إلى تعريف تواريخ خاصة، ستتقن كل ذلك.

هل أنت مستعد للسيطرة على جداول مشروعك؟ [استكشف الدرس هنا](./properties/).

## إنشاء تقاويم MS Project باستخدام Aspose.Tasks

قم بتبسيط إدارة مشروعك عبر إنشاء تقاويم MS Project باستخدام Aspose.Tasks for Java. يُبسّط دليلنا العملية، مما يضمن إعداد تقاويم مخصّصة لاحتياجات مشروعك الفريدة. ابدأ الآن نحو تخطيط مشروع فعال ومنظم.

هل تريد إنشاء تقاويم بسهولة؟ [اطلع على الدرس](./create/).

## تعريف أيام الأسبوع في التقويم باستخدام Aspose.Tasks

خصّص تقاويم MS Project الخاصة بك عبر تعريف أيام الأسبوع باستخدام Aspose.Tasks for Java. يوجّهك هذا الدرس خلال عملية تعديل أيام العمل وتوقيتاتها، موفرًا لك المرونة اللازمة لإدارة مشروع ناجح. اجعل تقاويمك تعمل لصالحك.

هل ترغب في تعريف أيام الأسبوع بسهولة؟ [ابدأ هنا](./define-weekdays/).

أثناء تنقلك عبر هذه الدروس، ستكتشف مواضيع إضافية تشمل استخراج ساعات العمل، إنشاء تقويم قياسي، قراءة أسابيع العمل، وتحديث التقويمات إلى صيغة MPP. كل درس صُمم لتزويدك بمعرفة عملية، مما يضمن تطبيق ما تتعلمه مباشرةً في مشاريع Java الخاصة بك.

## استخراج ساعات العمل من التقويم باستخدام Aspose.Tasks

بسّط مهام إدارة مشروعك عبر استخراج ساعات العمل من تقاويم MS Project باستخدام Aspose.Tasks for Java. يزوّدك هذا الدرس بالمهارات اللازمة لتحسين جداول مشروعك بفعالية.

هل تريد استخراج ساعات العمل بسهولة؟ [استكشف الدرس](./working-hours/).

## إنشاء تقويم قياسي في Aspose.Tasks

عزّز قدرات إدارة مشروعك عبر تعلم كيفية إنشاء تقويم MS Project قياسي في Java باستخدام Aspose.Tasks. يقدّم هذا الدرس خطوة بخطوة نهجًا موحدًا لتطبيق جداول مشروعك.

هل ترغب في إنشاء تقويم قياسي؟ [اطلع على الدرس](./make-standard/).

## قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks

احصل على رؤى شاملة حول قراءة أسابيع العمل من تقاويم MS Project باستخدام Aspose.Tasks for Java. يقدّم هذا الدرس إرشادات مفصّلة، مما يمكّنك من إدارة جداول مشروعك بفعالية.

هل تريد قراءة أسابيع العمل بسهولة؟ [ابدأ هنا](./read-work-weeks/).

## تحديث تقاويم MS Project إلى صيغة MPP باستخدام Aspose.Tasks

قم بتحديث تقاويم MS Project إلى صيغة MPP بسهولة باستخدام Aspose.Tasks for Java. يوفّر هذا الدرس نهجًا سلسًا لضمان أن بيانات مشروعك في الصيغة الصحيحة لتحقيق أقصى توافق.

هل تريد تحديث التقويمات إلى صيغة MPP؟ [استكشف الدرس](./update-to-mpp/).

اكتشف الإمكانات الكاملة لـ Aspose.Tasks for Java وارتق بمهارات إدارة مشروعك. صُممت كل دروس لتناسب المطورين من جميع المستويات، مما يضمن تجربة تعلم سلسة. انغمس الآن وثوّر رحلتك في إدارة مشاريع Java!

## دروس التقويمات
### [إدارة خصائص تقويم MS Project في Aspose.Tasks](./properties/)
تعرّف على كيفية إدارة خصائص تقويم MS Project في Java باستخدام Aspose.Tasks. يقدم هذا دليلًا خطوة بخطوة للتقويم داخل تطبيقات Java الخاصة بك.
### [إنشاء تقاويم MS Project باستخدام Aspose.Tasks](./create/)
تعرّف على كيفية إنشاء تقاويم MS Project باستخدام Aspose.Tasks for Java. سهل إدارة المشروع بسهولة.
### [تعريف أيام الأسبوع في التقويم باستخدام Aspose.Tasks](./define-weekdays/)
تعرّف على كيفية تعريف أيام الأسبوع في تقويم MS Project باستخدام Aspose.Tasks for Java. خصّص أيام العمل وتوقيتاتها بسهولة.
### [استخراج ساعات العمل من التقويم باستخدام Aspose.Tasks](./working-hours/)
استخرج ساعات العمل من تقاويم MS Project بسهولة باستخدام Aspose.Tasks for Java. بسط مهام إدارة المشروع.
### [إنشاء تقويم قياسي في Aspose.Tasks](./make-standard/)
تعرّف على كيفية إنشاء تقويم MS Project قياسي في Java باستخدام Aspose.Tasks. حسّن قدرات إدارة مشروعك عبر هذا الدرس خطوة بخطوة.
### [قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks](./read-work-weeks/)
تعرّف على كيفية قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks for Java. احصل على إرشادات خطوة بخطوة في هذا الدرس الشامل.
### [تحديث تقاويم MS Project إلى صيغة MPP بسهولة باستخدام Aspose.Tasks for Java](./update-to-mpp/)
تعرّف على كيفية تحديث تقاويم MS Project إلى صيغة MPP بسهولة باستخدام Aspose.Tasks for Java.

## الأسئلة المتكررة

**س: هل يمكنني تعريف ساعات عمل مختلفة لكل يوم من أيام الأسبوع؟**  
ج: نعم. يتيح لك Aspose.Tasks ضبط أوقات البدء والانتهاء لكل من الاثنين إلى الأحد بشكل منفصل.

**س: كيف أتعامل مع العطلات أو الأيام غير العاملة؟**  
ج: بعد تعريف أيام الأسبوع، يمكنك إضافة استثناءات (تواريخ) لتحديد العطلات أو فترات غير عاملة مخصصة.

**س: هل يمكن نسخ تعريف يوم أسبوع من تقويم إلى آخر؟**  
ج: بالتأكيد. يمكنك استرجاع كائن `WeekDay` من تقويم موجود وإضافته إلى تقويم آخر.

**س: هل أحتاج إلى إعادة تحميل المشروع بعد تحديث أيام الأسبوع؟**  
ج: لا. تُطبق التغييرات مباشرة على كائن `Project` في الذاكرة؛ فقط احفظ المشروع عند الانتهاء.

**س: أي نسخة من Aspose.Tasks مطلوبة لتعديل أيام الأسبوع؟**  
ج: جميع الإصدارات الحديثة (20.10 وما بعدها) تدعم واجهات برمجة تطبيقات أيام الأسبوع بالكامل. نوصي باستخدام أحدث إصدار مستقر لأفضل أداء.

---

**آخر تحديث:** 2026-11-19  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [إضافة تقويم إلى المشروع باستخدام Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [تحديد أيام العمل وساعات العمل باستخدام Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [إنشاء استثناءات تقويم مخصصة باستخدام Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}