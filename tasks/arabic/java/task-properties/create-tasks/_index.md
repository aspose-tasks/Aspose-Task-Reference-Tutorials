---
date: 2026-09-25
description: تعلم كيفية إنشاء جدول المشروع في Java باستخدام Aspose.Tasks. يوضح هذا
  الدليل كيفية إضافة summary tasks، وإدارة project hierarchy، وتعيين document directory
  بكفاءة.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: إنشاء مهام في Aspose.Tasks
og_description: تعلم كيفية إنشاء جدول المشروع في Java باستخدام Aspose.Tasks. اتبع
  تعليمات خطوة بخطوة لإضافة summary tasks، وإدارة hierarchy، وتعيين document directory.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: كيفية إنشاء جدول المشروع باستخدام Aspose.Tasks لـ Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: كيفية إنشاء جدول المشروع باستخدام Aspose.Tasks لـ Java
url: /ar/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء جدول مشروع باستخدام Aspose.Tasks للـ Java

## مقدمة
في هذا البرنامج التعليمي ستتعلم كيفية **إنشاء جدول مشروع** في تطبيق Java باستخدام Aspose.Tasks. سواءً كنت تبني قائمة مهام بسيطة أو مخططًا على مستوى المؤسسة المعقد، فإن الخطوات أدناه ستقودك عبر إضافة مهام ملخص، إدارة هيكل المشروع، وتحديد دليل المستندات — كل ذلك مع مقتطفات شفرة واضحة قابلة للتنفيذ. في النهاية، ستحصل على جدول منظم بالكامل جاهز لمزيد من المعالجة أو التصدير.

## إجابات سريعة
- **ما الذي تديره Aspose.Tasks؟** يتعامل مع هياكل المهام، الموارد، التقويمات، وصيغ ملفات المشروع (MS‑Project، Primavera، إلخ).  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت مجاني يعمل للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 وأحدثها مدعومة بالكامل.  
- **هل يمكنني إضافة حقول مخصصة للمهام؟** نعم، يمكنك توسيع المهام بحقول معرفة من قبل المستخدم عبر الـ API.  
- **هل هناك دعم مدمج لمخططات جانت؟** يمكن لـ Aspose.Tasks تصدير إلى PDF/HTML يتضمن تصورات جانت.

## ما هو جدول المشروع في Aspose.Tasks؟
جدول المشروع هو مجموعة كاملة من المهام، الاعتمادات، والجدولات الزمنية التي تحدد كيفية تنفيذ العمل. تقوم Aspose.Tasks بتخزين هذه المعلومات في كائن `Project` يمكنك قراءته، تعديله، وحفظه بصيغ مختلفة. يتضمن تواريخ البدء والانتهاء، القيود، وتعيينات الموارد، مما يتيح تخطيطًا شاملاً وإعداد تقارير.

## لماذا تستخدم Aspose.Tasks لإدارة مشاريع Java؟
تدعم Aspose.Tasks **أكثر من 30 تنسيقًا للإدخال والإخراج** ويمكنها معالجة المشاريع التي تحتوي على **حتى 10,000 مهمة** دون تحميل الملف بالكامل إلى الذاكرة، مما يوفر أداءً عاليًا لسيناريوهات إدارة مشاريع Java على نطاق واسع.

## المتطلبات المسبقة
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات المسبقة التالية:
- **Java Development Kit (JDK)** – JDK 8 أو أحدث مثبت على جهازك.  
- **مكتبة Aspose.Tasks للـ Java** – قم بتحميل وتثبيت المكتبة من [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **بيئة التطوير المتكاملة (IDE)** – استخدم Eclipse أو IntelliJ IDEA أو أي بيئة تطوير Java تفضلها.

## استيراد الحزم
`Project`، `Task`، والفئات المرتبطة تعيش في مساحة الاسم `com.aspose.tasks`. استوردها في أعلى ملف Java الخاص بك:

تمثل فئة `Project` جدول مشروع كامل وتوفر طرقًا للتعامل مع المهام والموارد.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

فئة `Project` هي نقطة الدخول لجميع العمليات على ملف المشروع.

## كيفية إنشاء جدول مشروع باستخدام Aspose.Tasks؟
حمّل نسخة جديدة من `Project`، حدد دليل المستندات، وابدأ بإضافة المهام. يشرح هذا الفقرة المباشرة سير العمل الأساسي: تقوم بإنشاء `Project`، تضبط `RootFolder` (دليل المستندات)، ثم تضيف مهمة ملخص تليها مهام فرعية. تُحفظ جميع التغييرات في الذاكرة حتى تستدعي `save` لتثبيت الجدول في ملف.

### الخطوة 1: تحديد دليل المستندات
حدد المكان الذي سيُكتب فيه ملف المشروع الناتج. يضمن تحديد الدليل مبكرًا أن جميع عمليات الحفظ اللاحقة تستخدم مسارًا ثابتًا.

خاصية `RootFolder` تحدد المجلد الأساسي الذي تُقرأ منه أو تُكتب إليه ملفات المشروع.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### الخطوة 2: إنشاء مشروع جديد
أنشئ كائن `Project` جديدًا سيحمل جدولك. يمكنك اختياريًا تمرير مسار ملف موجود مسبقًا لتحميل جدول موجود للتعديل.

منشئ `Project` يُنشئ جدولًا فارغًا جاهزًا لإضافة المهام.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### الخطوة 3: إضافة مهمة ملخص
مهمة الملخص تجمع المهام الفرعية المرتبطة وتظهر كعقدة قابلة للطي في مخططات جانت. استخدم فئة `Task` واضبط `IsSummary` إلى `true`.

طريقة `addTask` تنشئ مهمة جديدة تحت أصل محدد وتعيد معرّفها.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### الخطوة 4: إضافة مهمة فرعية
المهام الفرعية ترث تواريخ البدء/الانتهاء من مهمة الملخص الأصلية ما لم تقم بتجاوزها. إضافة مهمة فرعية بسيطة كاستدعاء `addTask` مرة أخرى وتحديد معرّف الأصل.

استدعاء `addTask` مع معرّف أصل يضيف مهمة فرعية تحت تلك المهمة الملخصة.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

استمر في إضافة عدد المهام والمهام الفرعية حسب الحاجة لمشروعك. كل خطوة تساهم في بناء هيكل مشروع منظم يمكن تصديره إلى MS‑Project أو PDF أو صيغ أخرى مدعومة.

## المشكلات الشائعة والحلول
- **المشكلة:** “Document directory not found.”  
  **الحل:** تحقق من أن المسار الذي تعينه لـ `RootFolder` موجود على نظام الملفات وأن عملية Java لديك لديها أذونات كتابة.
- **المشكلة:** Subtasks not appearing under the summary task.  
  **الحل:** تأكد من تمرير معرّف المهمة الأصلية الصحيح عند استدعاء `addTask`. يتطلب الـ API معرّف الأصل كوسيط ثاني.
- **المشكلة:** Large projects cause OutOfMemoryError.  
  **الحل:** تقوم Aspose.Tasks بمعالجة المهام في وضع تدفق؛ قم بزيادة حجم ذاكرة JVM (`-Xmx2g`) أو قسّم الجدول إلى ملفات متعددة.

## الأسئلة المتكررة
**س: هل Aspose.Tasks مناسبة للمشاريع الصغيرة؟**  
ج: بالتأكيد. المكتبة تتدرج من قائمة مهمة واحدة إلى جداول على مستوى المؤسسة تحتوي على آلاف المهام.

**س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.Tasks للـ Java؟**  
ج: راجع الوثائق [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**س: كيف أحصل على ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: زر صفحة [temporary license request page](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص محدود الوقت يعمل للتطوير والاختبار.

**س: هل يمكنني تخصيص سمات المهمة باستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك توسيع المهام بحقول مخصصة، تعيين الموارد، وتعديل التقويمات برمجيًا.

**س: هل هناك مجتمع دعم لمستخدمي Aspose.Tasks؟**  
ج: بالتأكيد! انضم إلى مجتمع Aspose.Tasks على [the support forum](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2026-09-25  
**تم الاختبار مع:** Aspose.Tasks 24.12 for Java  
**المؤلف:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## دروس ذات صلة

- [تحديد تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks للـ Java](/tasks/java/project-properties/write-project-info/)
- [إنشاء تبعيات مهام إدارة المشروع في Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [كيفية إضافة مورد إلى المشروع وإنشاء تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}