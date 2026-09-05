---
date: 2026-08-08
description: تعلم كيفية تعريف أيام الأسبوع في تقاويم MS Project باستخدام Aspose.Tasks
  للغة Java. يوضح هذا الدليل كيفية تعديل تقويم MS Project، وإنشاء تقويم مخصص Java،
  وجدولة أيام العمل بكفاءة.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: التقويمات
og_description: تعلم كيفية تعريف أيام الأسبوع في تقاويم MS Project باستخدام Aspose.Tasks
  للغة Java. إتقان إنشاء تقويم مخصص Java، تعديل تقويم MS Project، وجدولة أيام العمل
  بكفاءة.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: كيفية تعريف أيام الأسبوع في تقاويم MS Project – Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: كيفية تعريف أيام الأسبوع في تقاويم MS Project – Aspose.Tasks Java
url: /ar/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التقويمات

## مقدمة

إذا كنت مطور Java تبحث عن **تعريف أيام الأسبوع** في جدول مشروعك، فقد وصلت إلى المكان الصحيح. في هذه البوابة نجمع جميع دروس Aspose.Tasks for Java التي تُظهر **كيفية تعريف أيام الأسبوع** داخل تقاويم MS Project، وتعديل ساعات العمل، والحفاظ على جداولك الزمنية واضحة تمامًا. سواء كنت تبني محرك جدولة جديد أو تعدل خطة موجودة، فإن إتقان تعريف أيام الأسبوع يمنحك سيطرة دقيقة على أنماط أيام العمل، والعطلات، والنوبات المخصصة. يشرح هذا الدليل أيضًا **كيفية تعديل إعدادات تقويم MS Project** برمجيًا، حتى تتمكن من أتمتة إنشاء التقويمات عبر العشرات من المشاريع.

## إجابات سريعة
- **ما هو الغرض الأساسي من تعريف أيام الأسبوع؟**  
  لإخبار MS Project أي الأيام هي أيام عمل وما هي ساعات العمل الخاصة بها.
- **أي مكتبة تتعامل مع تعريف أيام الأسبوع في Java؟**  
  Aspose.Tasks for Java توفر API سلس للتعامل مع التقويم.
- **هل أحتاج إلى ترخيص؟**  
  ترخيص تجريبي مجاني يكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.
- **هل يمكنني تعريف تقاويم متعددة لفرق مختلفة؟**  
  نعم – يمكن لكل مشروع أن يحتوي على عدة تقاويم، كل منها بإعدادات أيام الأسبوع الخاصة به.
- **هل هناك مشروع مثال للبدء؟**  
  دليل “Define Weekdays in Calendar” المرتبطة أدناه تتضمن مثالًا جاهزًا للتشغيل.

## كيف يمكنني تعريف أيام الأسبوع في تقاويم MS Project؟

تمثل الفئة `Project` ملف MS Project وتوفر الوصول إلى هياكل بياناته. يخزن كائن `Calendar` تعريفات أوقات العمل والاستثناءات للمشروع. قم بتحميل مشروعك باستخدام `new Project("myproject.mpp")`، استرجع (أو أنشئ) كائن `Calendar`، ثم استدعِ `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. يخلق هذا السطر الواحد إدخال يوم عمل للاثنين بمدة 8 ساعات. كرّر ذلك للأيام الأخرى، وأخيرًا احفظ المشروع باستخدام `project.save("updated.mpp")`. يتيح لك هذا النمط المختصر تعريف، تعديل أو حذف أيام الأسبوع ببضع نداءات API فقط، مما يلغي الحاجة للتفاعل اليدوي مع الواجهة.

## ما هو كائن WeekDay؟

كائن `WeekDay` يمثل إدخالًا ليوم واحد من أيام الأسبوع داخل تقويم Aspose.Tasks، يخزن حالة العمل وفترات وقت العمل. يمكنك ضبط أوقات البدء/الانتهاء، تعيينه كغير عامل، أو إرفاق فترات عمل إضافية. يمكنه احتواء عدة فترات `WorkingTime` لنمذجة نوبات مقسمة، ويدعم علامات لأيام العمل الافتراضية. استخدم API `WeekDay` لتمكين أو تعطيل يوم، تعيين ساعات عادية، أو تحديد قواعد العمل الإضافي لسيناريوهات جدولة متقدمة.

## لماذا تستخدم Aspose.Tasks for Java لتعريف أيام الأسبوع؟

- **تحكم كامل عبر API** – لا توجد قيود واجهة مستخدم؛ يمكنك إنشاء، تعديل أو حذف إدخالات أيام الأسبوع برمجيًا.  
- **متعدد المنصات** – يعمل على أي بيئة متوافقة مع JVM، من تطبيقات سطح المكتب إلى الخدمات السحابية.  
- **دقة** – ضبط أوقات عمل مختلفة لكل يوم من أيام الأسبوع، إضافة استثناءات للعطلات، ومزامنة التقويمات عبر مشاريع متعددة.  
- **أداء** – معالجة المشاريع التي تحتوي على أكثر من 500 مهمة وتقويمات تشمل أكثر من 100 أسبوع دون تحميل الواجهة بالكامل، مع تحقيق أوقات تحويل أقل من ثانيتين على خادم قياسي بسرعة 2.5 GHz (ادعاء مُقنَّى بناءً على معيار Aspose).

## المتطلبات المسبقة
- تثبيت Java 8 أو أعلى.  
- مكتبة Aspose.Tasks for Java (تم تحميلها من موقع Aspose أو إضافتها عبر Maven/Gradle).  
- ترخيص Aspose.Tasks صالح (ترخيص تجريبي يكفي للتعلم).  

## إدارة خصائص تقويم MS Project في Aspose.Tasks

اكتشف الإمكانات الكاملة لإدارة خصائص تقويم MS Project في Java باستخدام Aspose.Tasks. يوجهك دليلنا عبر تفاصيل إدارة التقويم، مقدماً رؤى قيمة حول التخصيص والتحسين. من تعديل ساعات العمل إلى تعريف تواريخ خاصة، ستتمكن من إتقان كل ذلك.  
هل أنت مستعد للسيطرة على جداول مشروعك؟ [استكشف الدرس هنا](./properties/).

## إنشاء تقاويم MS Project باستخدام Aspose.Tasks

قم بتبسيط إدارة مشروعك بسهولة من خلال إنشاء تقاويم MS Project باستخدام Aspose.Tasks for Java. يبسط دليلنا العملية، مما يضمن قدرتك على إعداد تقاويم مخصصة لاحتياجات مشروعك الفريدة. اتخذ الخطوة الأولى نحو تخطيط وتنظيم مشروع فعال.  
هل أنت مستعد لإنشاء تقاويم بسهولة؟ [اطلع على الدرس](./create/).

## تعريف أيام الأسبوع في التقويم باستخدام Aspose.Tasks

خصص تقاويم MS Project الخاصة بك عن طريق تعريف أيام الأسبوع باستخدام Aspose.Tasks for Java. يوجهك هذا الدرس عبر عملية تعديل أيام العمل وتوقيتاتها، موفرًا لك المرونة اللازمة لإدارة مشروع ناجحة. اجعل تقاويمك تعمل لصالحك.  
هل أنت مستعد لتعريف أيام الأسبوع بسهولة؟ [ابدأ هنا](./define-weekdays/).

أثناء تنقلك عبر هذه الدروس، ستكتشف مواضيع إضافية تشمل استخراج ساعات العمل، إنشاء تقويم قياسي، قراءة أسابيع العمل، وتحديث التقويمات إلى صيغة MPP. كل درس صُنع لتزويدك بمعرفة عملية، لضمان قدرتك على تطبيق ما تعلمته مباشرةً في مشاريع Java الخاصة بك.

## استخراج ساعات العمل من التقويم باستخدام Aspose.Tasks

قم بتبسيط مهام إدارة مشروعك عن طريق استخراج ساعات العمل من تقاويم MS Project باستخدام Aspose.Tasks for Java. يزودك هذا الدرس بالمهارات اللازمة لتحسين جداول مشروعك بكفاءة.  
هل أنت مستعد لاستخراج ساعات العمل بسهولة؟ [استكشف الدرس](./working-hours/).

## إنشاء تقويم قياسي في Aspose.Tasks

عزز قدرات إدارة مشروعك بتعلم كيفية إنشاء تقويم MS Project قياسي في Java باستخدام Aspose.Tasks. يضمن لك هذا الدرس خطوة بخطوة تنفيذ نهج موحد لجداول مشروعك.  
هل أنت مستعد لإنشاء تقويم قياسي؟ [اطلع على الدرس](./make-standard/).

## قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks

احصل على رؤى شاملة حول قراءة أسابيع العمل من تقاويم MS Project باستخدام Aspose.Tasks for Java. يقدم هذا الدرس تعليمات مفصلة، مما يمكنك من إدارة جداول مشروعك بفعالية.  
هل أنت مستعد لقراءة أسابيع العمل بسهولة؟ [ابدأ هنا](./read-work-weeks/).

## تحديث تقاويم MS Project إلى صيغة MPP باستخدام Aspose.Tasks

قم بتحديث تقاويم MS Project إلى صيغة MPP بسهولة باستخدام Aspose.Tasks for Java. يقدم هذا الدرس نهجًا سلسًا لضمان أن بيانات مشروعك في الصيغة الصحيحة لتحقيق أقصى توافق.  
هل أنت مستعد لتحديث التقويمات إلى صيغة MPP؟ [استكشف الدرس](./update-to-mpp/).

اكتشف الإمكانات الكاملة لـ Aspose.Tasks for Java وارتق بمهاراتك في إدارة المشاريع. صُممت كل دورة لتناسب المطورين من جميع المستويات، مما يضمن تجربة تعلم سلسة. انغمس الآن وثور رحلتك في إدارة مشاريع Java!

## دروس التقويمات
### [إدارة خصائص تقويم MS Project في Aspose.Tasks](./properties/)
تعلم كيفية إدارة خصائص تقويم MS Project في Java باستخدام Aspose.Tasks. يقدم هذا إرشادات خطوة بخطوة للتقويم داخل تطبيقات Java الخاصة بك.
### [إنشاء تقاويم MS Project باستخدام Aspose.Tasks](./create/)
تعلم كيفية إنشاء تقاويم MS Project باستخدام Aspose.Tasks for Java. قم بتبسيط إدارة المشروع بسهولة.
### [تعريف أيام الأسبوع في التقويم باستخدام Aspose.Tasks](./define-weekdays/)
تعلم كيفية تعريف أيام الأسبوع في تقويم MS Project باستخدام Aspose.Tasks for Java. خصص أيام العمل وتوقيتاتها بسهولة.
### [استخراج ساعات العمل من التقويم باستخدام Aspose.Tasks](./working-hours/)
استخراج ساعات العمل من تقاويم MS Project بسهولة باستخدام Aspose.Tasks for Java. بسط مهام إدارة المشروع.
### [إنشاء تقويم قياسي في Aspose.Tasks](./make-standard/)
تعلم كيفية إنشاء تقويم MS Project قياسي في Java باستخدام Aspose.Tasks. عزز قدرات إدارة مشروعك من خلال هذا الدرس خطوة بخطوة.
### [قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks](./read-work-weeks/)
تعلم كيفية قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks for Java. احصل على تعليمات خطوة بخطوة في هذا الدرس الشامل.
### [تحديث تقاويم MS Project إلى صيغة MPP باستخدام Aspose.Tasks](./update-to-mpp/)
تعلم كيفية تحديث تقاويم MS Project إلى صيغة MPP بسهولة باستخدام Aspose.Tasks for Java.

## الأسئلة المتكررة

**س: هل يمكنني تعريف ساعات عمل مختلفة لكل يوم من أيام الأسبوع؟**  
A: نعم. يتيح لك Aspose.Tasks ضبط أوقات البدء والانتهاء بشكل فردي لكل من الاثنين إلى الأحد.

**س: كيف أتعامل مع العطلات أو الأيام غير العاملة؟**  
A: بعد تعريف أيام الأسبوع، يمكنك إضافة استثناءات (تواريخ) لتحديد العطلات أو فترات غير عاملة مخصصة.

**س: هل يمكن نسخ تعريف يوم أسبوع من تقويم إلى آخر؟**  
A: بالتأكيد. يمكنك استرجاع كائن `WeekDay` من تقويم موجود وإضافته إلى نسخة تقويم أخرى.

**س: هل أحتاج إلى إعادة تحميل المشروع بعد تحديث أيام الأسبوع؟**  
A: لا. تُطبق التغييرات مباشرة على كائن `Project` في الذاكرة؛ فقط احفظ المشروع عند الانتهاء.

**س: أي نسخة من Aspose.Tasks مطلوبة للتعامل مع أيام الأسبوع؟**  
A: جميع الإصدارات الحديثة (20.10 وما بعدها) تدعم واجهات برمجة تطبيقات أيام الأسبوع بالكامل. نوصي باستخدام أحدث إصدار ثابت للحصول على أفضل أداء.

**آخر تحديث:** 2026-08-08  
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