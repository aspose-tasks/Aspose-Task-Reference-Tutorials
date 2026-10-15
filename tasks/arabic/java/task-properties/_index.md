---
date: 2026-10-15
description: تعلم كيفية إنشاء مهام Java باستخدام Aspose.Tasks. استكشف دروسًا شاملة
  حول خصائص المهام، الأولويات، التكاليف، وأكثر لتحسين إدارة مشاريع Java الخاصة بك.
keywords:
- how to create tasks
- Aspose.Tasks Java
- task properties Java
lastmod: 2026-10-15
linktitle: خصائص المهمة
og_description: تعلم كيفية إنشاء المهام باستخدام Aspose.Tasks للغة Java. يغطي هذا
  الدليل خصائص المهام، الأولويات، التكاليف، وأفضل الممارسات لإدارة مشاريع Java.
og_image_alt: Developer guide showing how to create tasks using Aspose.Tasks Java
  library
og_title: كيفية إنشاء المهام باستخدام Aspose.Tasks للغة Java – خصائص المهمة
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create tasks aspose java using Aspose.Tasks. Explore comprehensive
    tutorials on task properties, priorities, costs, and more to optimize your Java
    project management.
  headline: How to create tasks with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create tasks aspose java using Aspose.Tasks. Explore comprehensive
    tutorials on task properties, priorities, costs, and more to optimize your Java
    project management.
  name: How to create tasks with Aspose.Tasks for Java
  steps:
  - name: '**Create a new project** – start with an empty `Project` object or load
      an existing file.'
    text: '**Create a new project** – start with an empty `Project` object or load
      an existing file.'
  - name: '**Add a task** – instantiate `Task`, set `Name`, `Duration`, and any custom
      fields you need.'
    text: '**Add a task** – instantiate `Task`, set `Name`, `Duration`, and any custom
      fields you need.'
  - name: '**Configure task properties** – adjust priority, cost, or extended attributes
      as required.'
    text: '**Configure task properties** – adjust priority, cost, or extended attributes
      as required.'
  - name: '**Save the project** – write the updated schedule back to `.mpp`, `.xml`,
      or any supported format.'
    text: '**Save the project** – write the updated schedule back to `.mpp`, `.xml`,
      or any supported format.'
  type: HowTo
- questions:
  - answer: No. The Aspose.Tasks Java API includes full support for task priorities;
      you can set them directly on the `Task` object.
    question: Do I need a separate library to handle task priorities?
  - answer: Yes. Use `Project project = new Project("input.mpp");` modify tasks, then
      `project.save("output.mpp");`.
    question: Can I import an existing .mpp file, modify tasks, and save it back?
  - answer: Absolutely. Iterate over `project.getRootTask().getChildren()` and apply
      changes in a loop for bulk operations.
    question: Is it possible to batch‑update many tasks at once?
  - answer: Create an `ExtendedAttributeDefinition`, add it to the project, then assign
      values to each task via `task.getExtendedAttributes().add(...)`.
    question: How do I handle custom extended attributes?
  - answer: Any Aspose.Tasks version released after 2022 fully supports Java 11 and
      newer.
    question: What version of Aspose.Tasks is required for Java 11?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create tasks
- Aspose.Tasks
- Java project management
title: كيفية إنشاء المهام باستخدام Aspose.Tasks للغة Java
url: /ar/java/task-properties/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# خصائص المهمة

## مقدمة

`Aspose.Tasks` هي مكتبة Java تمكّن من إنشاء ومعالجة ملفات Microsoft Project برمجيًا. باستخدام نهج **how to create tasks**، يمكنك بناء وتعديل وتحسين جداول المشروع مباشرةً من تطبيقات Java الخاصة بك، مما يمنحك التحكم الكامل في كل سمة من سمات المهمة. يشرح هذا الدليل المفاهيم الأساسية، وحالات الاستخدام الواقعية، ونصائح أفضل الممارسات التي تجعل إدارة خصائص المهمة سهلة.

**لماذا هذا مهم:** تدعم Aspose.Tasks أكثر من 30 تنسيقًا للإدخال والإخراج ويمكنها معالجة مشاريع تحتوي على ما يصل إلى 10,000 مهمة دون تحميل الملف بالكامل في الذاكرة، مما يوفر المرونة والأداء لتخطيط على مستوى المؤسسات.

## إجابات سريعة
- **ما الذي يتيح “create tasks aspose java”？** يتيح لك إضافة وتحديث وقراءة معلومات المهمة برمجيًا في ملفات Microsoft Project باستخدام مكتبة Aspose.Tasks Java.  
- **هل أحتاج إلى ترخيص؟** تتوفر نسخة تجريبية مجانية، لكن الترخيص التجاري مطلوب للاستخدام في الإنتاج.  
- **ما إصدارات Java المدعومة؟** تعمل Aspose.Tasks مع Java 8 وما بعدها.  
- **هل هناك شفرة نموذجية؟** نعم—كل دليل أدناه يتضمن أمثلة جاهزة للتنفيذ.  
- **هل يمكنني التصدير إلى MPP؟** بالتأكيد؛ المكتبة تقرأ وتكتب ملفات .mpp الأصلية.

## كيفية إنشاء مهام في Aspose.Tasks للـ Java؟

إنشاء مهام باستخدام Aspose.Tasks للـ Java يتضمن تهيئة كائن Project، إنشاء مثيل Task، تعيين الخصائص الأساسية مثل الاسم والمدة والموارد، إرفاق المهمة بهيكل المشروع، وأخيرًا حفظ المشروع بتنسيق مدعوم. هذا التدفق البسيط يعمل مع الملفات الجديدة والقائمة على حد سواء.

حمّل كائن `Project`، أنشئ `Task` جديدًا، عيّن الخصائص المطلوبة، أضف المهمة إلى جذر المشروع، وأخيرًا احفظ الملف. هذا النمط المكوّن من أربع خطوات هو جوهر **how to create tasks** ويعمل مع أي حجم مشروع.

### دليل خطوة بخطوة

1. **إنشاء مشروع جديد** – ابدأ بكائن `Project` فارغ أو حمّل ملفًا موجودًا.  
2. **إضافة مهمة** – أنشئ `Task`، عيّن `Name` و`Duration` وأي حقول مخصصة تحتاجها.  
3. **تكوين خصائص المهمة** – اضبط الأولوية أو التكلفة أو السمات الموسعة حسب الحاجة.  
4. **حفظ المشروع** – اكتب الجدول المحدث مرة أخرى إلى `.mpp` أو `.xml` أو أي تنسيق مدعوم.  

> **نصيحة احترافية:** عند إنشاء العديد من المهام في حلقة، عطل الحفظ التلقائي (`project.setAutoSave(false)`) واستدعِ `project.save(...)` مرة واحدة بعد الحلقة لتحسين الأداء.

## ما هو how to create tasks؟

المصطلح “how to create tasks” يصف الخطوات البرمجية المطلوبة لإضافة إدخالات مهام جديدة إلى ملف Microsoft Project باستخدام Aspose.Tasks Java API. يغطي إنشاء الكائنات، تعيين الخصائص، وضعها في الهرمية، والحفظ، مما يمنح المطورين تحكمًا دقيقًا في كل سمة من سمات كل مهمة.

## لماذا استخدام Aspose.Tasks لإنشاء المهام؟

توفر Aspose.Tasks **فوائد كمية**: تدعم أكثر من 30 تنسيقًا للملفات، يمكنها التعامل مع مشاريع تصل إلى 10,000 مهمة، وتُعالج جدولًا نموذجيًا مكوّنًا من 500 مهمة في أقل من ثانيتين على أجهزة عادية. تعمل المكتبة دون الحاجة إلى تثبيت Microsoft Project، مما يجعلها مثالية لتدفقات العمل الآلية على الخادم.

## المتطلبات المسبقة

- Java 8 أو أحدث مثبت على جهاز التطوير الخاص بك.  
- Maven أو Gradle لإدارة تبعية `aspose-tasks`.  
- ترخيص Aspose.Tasks صالح (النسخة التجريبية تعمل للتقييم).  

## إضافة سمات موسعة إلى المهام في Aspose.Tasks

استكشف قوة Aspose.Tasks Java في تخصيص ملفات Microsoft Project باستخدام السمات الموسعة. عزّز قدرات إدارة مشروعك بسهولة. [المزيد](./add-extended-attributes/).

## تغيير تقدم المهمة في Aspose.Tasks

حسّن إدارة مشاريع Java باستخدام Aspose.Tasks: تعلم تعديل تقدم المهمة بسلاسة في هذا الدليل خطوة بخطوة. حمّل الآن! [المزيد](./change-progress/).

## إنشاء مهام في Aspose.Tasks

إدارة مشاريع Java بسهولة باستخدام Aspose.Tasks: إنشاء مهام، مهام فرعية، وأكثر. اتبع دليلنا خطوة بخطوة لإدارة مشروع سلس. [ابدأ الآن](./create-tasks/).

## إدارة المهام الحرجة والمستندة إلى الجهد في Aspose.Tasks

إدارة المهام الحرجة والمستندة إلى الجهد في مشاريع Java الخاصة بك بسهولة باستخدام Aspose.Tasks. حمّل المكتبة وعزز قدرات إدارة مشروعك. [حمّل الآن](./critical-effort-driven-tasks/).

## التعامل مع المهام التقديرية ومهام المعلم في Aspose.Tasks

استكشف إدارة مشروع فعّالة باستخدام Aspose.Tasks للـ Java. تعامل مع المهام التقديرية ومهام المعلم بسهولة. حمّل المكتبة الآن! [المزيد](./estimated-milestone-tasks/).

## سمات مهمة موسعة في Aspose.Tasks

استكشف سمات المهمة الموسعة في Aspose.Tasks للـ Java. دليل خطوة بخطوة، أسئلة شائعة، ودعم. حسّن إدارة مشروعك اليوم! [المزيد](./extended-task-attributes/).

## التعامل مع أولويات المهام في Aspose.Tasks

إتقان أولويات المهام بسهولة باستخدام Aspose.Tasks للـ Java. اتبع هذا الدليل للتعامل السلس. ارتق بمهارات إدارة مشروعك! [إتقان الأولويات](./handle-priorities/).

## التعامل مع تباينات المهام في Aspose.Tasks

استكشف قوة Aspose.Tasks للـ Java في إدارة تباينات مهام المشروع. اتبع دليلنا الشامل للتكامل السلس والتعامل الفعّال. [المزيد](./handle-variances/).

## إدارة مدد المهام في Aspose.Tasks

استكشف Aspose.Tasks للـ Java وتعلم إدارة مدد المهام بسهولة. اتبع دليل خطوة بخطوة لتخطيط وتنفيذ مشروع فعّال. [إدارة المدّات](./manage-durations/).

## إدارة تكاليف المهام في Aspose.Tasks

تعلم كيفية إدارة تكاليف المهام في تطبيقات Java باستخدام Aspose.Tasks. اتبع دليل خطوة بخطوة لإدارة تكلفة المشروع بفعالية. [إدارة التكلفة](./manage-task-cost/).

## إدارة ملاحظات المهام في Aspose.Tasks

استكشف إدارة ملاحظات المهام في Aspose.Tasks للـ Java. دليل خطوة بخطوة لتطوير Java فعال. حمّل نسختك التجريبية المجانية الآن! [استكشاف الملاحظات](./task-notes/).

## العمل الإضافي في المهام باستخدام Aspose.Tasks

استكشف إدارة العمل الإضافي الفعّالة في مهام المشروع باستخدام Aspose.Tasks للـ Java. بسط تتبع وتخصيص الموارد بسهولة. [إدارة العمل الإضافي](./overtimes-in-tasks/).

## إدارة المهام الأصلية والفرعية في Aspose.Tasks

عزّز كفاءة إدارة المشروع باستخدام Aspose.Tasks للـ Java. تعلم إدارة المهام الأصلية والفرعية خطوة بخطوة. ابدأ الآن! [المزيد](./parent-child-tasks/).

## حساب النسبة المكتملة للمهام في Aspose.Tasks

استكشف Aspose.Tasks للـ Java وسهّل تتبع تقدم المشروع. احسب نسب إكمال المهام بسهولة لإدارة مشروع فعّالة. [استكشاف الحسابات](./percentage-complete-calculations/).

## قراءة وكتابة الخصائص العامة للمهام في Aspose.Tasks

استكشف قوة Aspose.Tasks للـ Java في إدارة خصائص المهام بسهولة. اقرأ واكتب بسهولة باستخدام دليلنا خطوة بخطوة. [قراءة وكتابة الخصائص](./read-write-general-properties/).

## عرض ورقة المهام في Aspose.Tasks

افتح إدارة مشروع فعّالة باستخدام Aspose.Tasks للـ Java. عرض أوراق المهام بسلاسة. استكشف الدليل الشامل الآن! [عرض ورقة المهام](./render-task-sheet/).

## تقسيم تاريخ انتهاء المهمة في Aspose.Tasks

تعلم كيفية تقسيم تواريخ انتهاء المهام بسهولة باستخدام Aspose.Tasks للـ Java. حسّن إدارة المشروع بجداول زمنية دقيقة. [تقسيم تواريخ الانتهاء](./split-task-finish-date/).

## تقسيم المهام في Aspose.Tasks

أتقن إدارة المهام في Java باستخدام Aspose.Tasks! تعلم كيفية تقسيم المهام بفعالية لجداول زمنية محسّنة. حمّل الآن! [تقسيم المهام](./split-tasks/).

## إيقاف واستئناف المهمة في Aspose.Tasks

استكشف قوة Aspose.Tasks للـ Java مع دليلنا خطوة بخطوة حول إيقاف واستئناف المهام. حسّن إدارة المشروع بسلاسة! [إيقاف واستئناف المهام](./stop-resume-task/).

## إدارة الميزانية والعمل والتكلفة للمهام في Aspose.Tasks

افتح إدارة ميزانية وتكلفة فعّالة في مشاريع Java باستخدام Aspose.Tasks. استكشف إرشادات خطوة بخطوة للتكامل السلس. [استكشاف الإدارة](./task-budget-work-cost/).

## مدة المهمة بوحدات مختلفة باستخدام Aspose.Tasks

استكشف إدارة مدة المهمة في مشاريع Java باستخدام Aspose.Tasks. احسب وحول المدّات بدقة بالدقائق، الأيام، الساعات، الأسابيع، والشهور. [إدارة المدّات](./task-duration-different-units/).

## المهام والتقويمات في Aspose.Tasks

استكشف قوة Aspose.Tasks للـ Java في إدارة المهام والتقويمات بفعالية. حمّل الآن لتجربة إدارة مشروع سلسة! [استكشاف المهام والتقويمات](./tasks-and-calendars/).

## بيانات الوقت المرحلية للمهمة في Aspose.Tasks

استكشف Aspose.Tasks للـ Java وتعلم إدارة بيانات الوقت المرحلية للمهمة. حمّل المكتبة، استمتع بنسخة تجريبية مجانية، وسهّل تتبع مشروعك. [استكشاف بيانات الوقت المرحلية](./task-timephased-data/).

## تحديث بيانات المهمة إلى تنسيق MPP في Aspose.Tasks

تعلم كيفية تحديث بيانات المهمة إلى تنسيق MPP باستخدام Aspose.Tasks للـ Java. اتبع دليلنا خطوة بخطوة لإدارة مشروع فعّالة. [تحديث بيانات المهمة](./update-task-data/).

## WBS المرتبط بالمهمة في Aspose.Tasks

أتقن WBS مع Aspose.Tasks للـ Java - تعلم قراءة وإعادة ترقيم رموز WBS للمهمة. عزّز كفاءة إدارة المشروع! [إتقان WBS](./wbs-associated-with-task/).

## دروس خصائص المهمة
### [إضافة سمات موسعة إلى المهام في Aspose.Tasks](./add-extended-attributes/)
استكشف قوة Aspose.Tasks Java في تخصيص ملفات Microsoft Project باستخدام السمات الموسعة. عزّز قدرات إدارة مشروعك بسهولة.
### [تغيير تقدم المهمة في Aspose.Tasks](./change-progress/)
حسّن إدارة مشاريع Java باستخدام Aspose.Tasks: تعلم تعديل تقدم المهمة بسلاسة في هذا الدليل خطوة بخطوة. حمّل الآن!
### [إنشاء مهام في Aspose.Tasks](./create-tasks/)
إدارة مشاريع Java بسهولة باستخدام Aspose.Tasks: إنشاء مهام، مهام فرعية، وأكثر. اتبع دليلنا خطوة بخطوة لإدارة مشروع سلس.
### [إدارة المهام الحرجة والمستندة إلى الجهد في Aspose.Tasks](./critical-effort-driven-tasks/)
إدارة المهام الحرجة والمستندة إلى الجهد في مشاريع Java الخاصة بك بسهولة باستخدام Aspose.Tasks. حمّل المكتبة وعزز قدرات إدارة مشروعك.
### [التعامل مع المهام التقديرية ومهام المعلم في Aspose.Tasks](./estimated-milestone-tasks/)
استكشف إدارة مشروع فعّالة باستخدام Aspose.Tasks للـ Java. تعامل مع المهام التقديرية ومهام المعلم بسهولة. حمّل المكتبة الآن!
### [سمات مهمة موسعة في Aspose.Tasks](./extended-task-attributes/)
استكشف سمات المهمة الموسعة في Aspose.Tasks للـ Java. دليل خطوة بخطوة، أسئلة شائعة، ودعم. حسّن إدارة مشروعك اليوم!
### [التعامل مع أولويات المهام في Aspose.Tasks](./handle-priorities/)
إتقان أولويات المهام بسهولة باستخدام Aspose.Tasks للـ Java. اتبع هذا الدليل للتعامل السلس. ارتق بمهارات إدارة مشروعك!
### [التعامل مع تباينات المهام في Aspose.Tasks](./handle-variances/)
استكشف قوة Aspose.Tasks للـ Java في إدارة تباينات مهام المشروع. اتبع دليلنا الشامل للتكامل السلس والتعامل الفعّال.
### [إدارة مدد المهام في Aspose.Tasks](./manage-durations/)
استكشف Aspose.Tasks للـ Java وتعلم إدارة مدد المهام بسهولة. اتبع دليل خطوة بخطوة لتخطيط وتنفيذ مشروع فعّال.
### [إدارة تكاليف المهام في Aspose.Tasks](./manage-task-cost/)
تعلم كيفية إدارة تكاليف المهام في تطبيقات Java باستخدام Aspose.Tasks. اتبع دليل خطوة بخطوة لإدارة تكلفة المشروع بفعالية.
### [إدارة ملاحظات المهام في Aspose.Tasks](./task-notes/)
استكشف إدارة ملاحظات المهام في Aspose.Tasks للـ Java. دليل خطوة بخطوة لتطوير Java فعال. حمّل نسختك التجريبية المجانية الآن!
### [العمل الإضافي في المهام مع Aspose.Tasks](./overtimes-in-tasks/)
استكشف إدارة العمل الإضافي الفعّالة في مهام المشروع باستخدام Aspose.Tasks للـ Java. بسط تتبع وتخصيص الموارد بسهولة.
### [إدارة المهام الأصلية والفرعية في Aspose.Tasks](./parent-child-tasks/)
عزّز كفاءة إدارة المشروع باستخدام Aspose.Tasks للـ Java. تعلم إدارة المهام الأصلية والفرعية خطوة بخطوة. ابدأ الآن!
### [حساب النسبة المكتملة للمهام في Aspose.Tasks](./percentage-complete-calculations/)
استكشف Aspose.Tasks للـ Java وسهّل تتبع تقدم المشروع. احسب نسب إكمال المهام بسهولة لإدارة مشروع فعّالة.
### [قراءة وكتابة الخصائص العامة للمهام في Aspose.Tasks](./read-write-general-properties/)
استكشف قوة Aspose.Tasks للـ Java في إدارة خصائص المهام بسهولة. اقرأ واكتب بسهولة باستخدام دليلنا خطوة بخطوة.
### [عرض ورقة المهام في Aspose.Tasks](./render-task-sheet/)
افتح إدارة مشروع فعّالة باستخدام Aspose.Tasks للـ Java. عرض أوراق المهام بسلاسة. استكشف الدليل الشامل الآن!
### [تقسيم تاريخ انتهاء المهمة في Aspose.Tasks](./split-task-finish-date/)
تعلم كيفية تقسيم تواريخ انتهاء المهام بسهولة باستخدام Aspose.Tasks للـ Java. حسّن إدارة المشروع بجداول زمنية دقيقة.
### [تقسيم المهام في Aspose.Tasks](./split-tasks/)
أتقن إدارة المهام في Java باستخدام Aspose.Tasks! تعلم كيفية تقسيم المهام بفعالية لجداول زمنية محسّنة. حمّل الآن!
### [إيقاف واستئناف المهمة في Aspose.Tasks](./stop-resume-task/)
استكشف قوة Aspose.Tasks للـ Java مع دليلنا خطوة بخطوة حول إيقاف واستئناف المهام. حسّن إدارة المشروع بسلاسة!
### [إدارة الميزانية والعمل والتكلفة للمهام في Aspose.Tasks](./task-budget-work-cost/)
افتح إدارة ميزانية وتكلفة فعّالة في مشاريع Java باستخدام Aspose.Tasks. استكشف إرشادات خطوة بخطوة للتكامل السلس.
### [مدة المهمة بوحدات مختلفة مع Aspose.Tasks](./task-duration-different-units/)
استكشف إدارة مدة المهمة في مشاريع Java باستخدام Aspose.Tasks. احسب وحول المدّات بدقة بالدقائق، الأيام، الساعات، الأسابيع، والشهور.
### [المهام والتقويمات في Aspose.Tasks](./tasks-and-calendars/)
استكشف قوة Aspose.Tasks للـ Java في إدارة المهام والتقويمات بفعالية. حمّل الآن لتجربة إدارة مشروع سلسة!
### [بيانات الوقت المرحلية للمهمة في Aspose.Tasks](./task-timephased-data/)
استكشف Aspose.Tasks للـ Java وتعلم إدارة بيانات الوقت المرحلية للمهمة. حمّل المكتبة، استمتع بنسخة تجريبية مجانية، وسهّل تتبع مشروعك.
### [تحديث بيانات المهمة إلى تنسيق MPP في Aspose.Tasks](./update-task-data/)
تعلم كيفية تحديث بيانات المهمة إلى تنسيق MPP باستخدام Aspose.Tasks للـ Java. اتبع دليلنا خطوة بخطوة لإدارة مشروع فعّالة.
### [WBS المرتبط بالمهمة في Aspose.Tasks](./wbs-associated-with-task/)
أتقن WBS مع Aspose.Tasks للـ Java - تعلم قراءة وإعادة ترقيم رموز WBS للمهمة. عزّز كفاءة إدارة المشروع!

## الأسئلة المتكررة

**س: هل أحتاج إلى مكتبة منفصلة للتعامل مع أولويات المهام؟**  
ج: لا. تشمل Aspose.Tasks Java API دعمًا كاملاً لأولويات المهام؛ يمكنك تعيينها مباشرةً على كائن `Task`.

**س: هل يمكنني استيراد ملف .mpp موجود، تعديل المهام، وحفظه مرة أخرى؟**  
ج: نعم. استخدم `Project project = new Project("input.mpp");` عدل المهام، ثم `project.save("output.mpp");`.

**س: هل من الممكن تحديث مجموعة كبيرة من المهام دفعة واحدة؟**  
ج: بالطبع. قم بالتكرار عبر `project.getRootTask().getChildren()` وطبق التغييرات في حلقة للعمليات الجماعية.

**س: كيف أتعامل مع السمات الموسعة المخصصة؟**  
ج: أنشئ `ExtendedAttributeDefinition`، أضفه إلى المشروع، ثم عيّن القيم لكل مهمة عبر `task.getExtendedAttributes().add(...)`.

**س: ما نسخة Aspose.Tasks المطلوبة لـ Java 11؟**  
ج: أي نسخة من Aspose.Tasks صدرت بعد 2022 تدعم بالكامل Java 11 وما بعدها.

---

**آخر تحديث:** 2026-10-15  
**تم الاختبار مع:** Aspose.Tasks 24.11 للـ Java  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء مشروع aspose.tasks – تعيين سمات مهمة جديدة](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [إنشاء تبعيات مهام إدارة المشروع في Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [قراءة وتعيين أولويات المهام باستخدام Aspose.Tasks للـ Java](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}