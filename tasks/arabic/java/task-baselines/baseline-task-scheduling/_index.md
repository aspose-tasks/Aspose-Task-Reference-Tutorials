---
date: 2026-08-29
description: تعلم كيفية قراءة بيانات baseline وجدولة المهام باستخدام Aspose.Tasks
  for Java، حتى تتمكن من مقارنة التقدم المخطط به مقابل التقدم الفعلي بكفاءة.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: جدولة مهام baseline في Aspose.Tasks
og_description: تعلم كيفية قراءة بيانات baseline وجدولة المهام باستخدام Aspose.Tasks
  for Java، مما يتيح مقارنة دقيقة بين التقدم المخطط والتقدم الفعلي.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: كيفية قراءة baseline وجدولة المهام باستخدام Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: كيفية قراءة baseline وجدولة المهام باستخدام Aspose.Tasks
url: /ar/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة الخط الأساسي وجدولة المهام باستخدام Aspose.Tasks

في هذا الدليل ستكتشف **كيفية قراءة الخط الأساسي** ومعلوماته وجدولة المهام برمجيًا باستخدام Aspose.Tasks for Java. بحلول نهاية البرنامج التعليمي، ستكون قادرًا على التقاط خطة المشروع الأصلية، مقارنتها بالتقدم الفعلي، وإنشاء تقارير الفروقات — كل ذلك دون الحاجة إلى تثبيت Microsoft Project.

## مقدمة عن الخط الأساسي لإدارة المشاريع

إدارة **الخط الأساسي لإدارة المشاريع** هي حجر الزاوية في إدارة المشاريع الفعالة. إنها تتيح لك التقاط الخطة الأصلية ومقارنتها لاحقًا بـ **التقدم المخطط مقابل الفعلي** حتى تتمكن من اكتشاف الفروقات مبكرًا. في هذا البرنامج التعليمي، سنستعرض كيفية جدولة خطوط الأساس للمهام باستخدام Aspose.Tasks for Java، مما يمنحك الأدوات اللازمة **لإدارة خطوط أساس المشروع** بثقة والحفاظ على سير المشاريع وفقًا للخطة.

## إجابات سريعة
- **ماذا يمثل الخط الأساسي لإدارة المشاريع؟**  
  يسجل الجدول الزمني المعتمد، التكلفة، والنطاق عند بدء المشروع، موفرًا مرجعًا لتحليل الفروقات.  
- **أي مكتبة تتعامل مع جدولة الخط الأساسي في Java؟**  
  توفر Aspose.Tasks for Java واجهة برمجة تطبيقات pure‑Java تدعم أكثر من 45 صيغة إدخال وإخراج وتدعم مشاريع تصل إلى 100 000 مهمة.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟**  
  الإصدار التجريبي المجاني يكفي للاختبار؛ يتطلب الاستخدام في الإنتاج ترخيصًا تجاريًا.  
- **ما هي المتطلبات الأساسية؟**  
  مجموعة تطوير Java (JDK) 11+ ومكتبة Aspose.Tasks for Java.  
- **هل يمكنني عرض تواريخ الخط الأساسي بعد تعيينها؟**  
  نعم — استخدم كائن `TaskBaseline` لقراءة قيم البداية، الانتهاء، والمدة.

## ما هو الخط الأساسي لإدارة المشاريع؟
يسجل الخط الأساسي لإدارة المشاريع الجدول الزمني المعتمد، الميزانية، والنطاق في بداية التنفيذ. يعمل كنقطة مرجعية لقياس الأداء وتحديد الانحرافات طوال دورة حياة المشروع. يتضمن تواريخ البداية والانتهاء المخطط لها، التكلفة الإجمالية، وتفاصيل النطاق، موفرًا لمحة شاملة للمقارنة المستقبلية.

## لماذا نستخدم Aspose.Tasks لجدولة الخط الأساسي؟
توفر Aspose.Tasks واجهة برمجة تطبيقات pure‑Java تعمل دون الحاجة إلى تثبيت Microsoft Project. تدعم **أكثر من 45 صيغة إدخال وإخراج**، يمكنها معالجة مشاريع **تصل إلى 100 000 مهمة** في وضع توفير الذاكرة، وتوفر طرقًا مدمجة لقراءة وكتابة بيانات الخط الأساسي — مما يجعل إعداد التقارير الآلية والتكامل سهلًا.

## المتطلبات المسبقة
- **Java Development Kit (JDK)** – قم بتثبيت JDK 11 أو أحدث. يمكنك تنزيله من [الموقع](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java library** – قم بتنزيل أحدث إصدار من [صفحة التحميل](https://releases.aspose.com/tasks/java/) وأضف ملف JAR إلى مسار الفئات (classpath) في مشروعك.

## استيراد الحزم
تقع الفئات `Project` و `Task` و `TaskBaseline` في مساحة الأسماء `com.aspose.tasks`. استوردها في أعلى ملف المصدر الخاص بك:

فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف مشروع واحد في الذاكرة. توفر الوصول إلى المهام، الموارد، ومجموعات الخطوط الأساسية.

## كيف تقرأ الخط الأساسي؟
حمّل المشروع، ثم استعلم عن مجموعة `TaskBaseline` لكل مهمة. يعيد كائن `TaskBaseline` قيم البداية، الانتهاء، والمدة للخط الأساسي التي تم التقاطها عندما استدعيت `setBaseline`. يتيح لك هذا النهج المباشر قراءة قيم الخط الأساسي دون الحاجة إلى تحليل ملفات XML أو الثنائية.

## الخطوة 1: إنشاء نسخة مشروع جديدة
فئة `Project` تمثل ملف المشروع بالكامل في الذاكرة.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## الخطوة 2: تعريف مهمة وتعيين الخط الأساسي
`Task` تمثل عنصر عمل فردي، و `setBaseline` يلتقط جدوله الحالي كخط أساسي.
```java
Project project = new Project();
```

## الخطوة 3: الوصول إلى معلومات الخط الأساسي
`TaskBaseline` يحتفظ بقيم البداية، الانتهاء، والمدة المحفوظة للخط الأساسي.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## الخطوة 4: عرض مدة الخط الأساسي
`Duration` تمثل طول الوقت لمهمة أو خط أساسي.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## الخطوة 5: عرض تاريخ بداية الخط الأساسي
`Start` هو تاريخ بداية الخط الأساسي المجدول.
```java
System.out.println(baseline.getDuration().toString());
```

## الخطوة 6: عرض تاريخ انتهاء الخط الأساسي
`Finish` هو تاريخ انتهاء الخط الأساسي المجدول.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## المشكلات الشائعة والحلول
- **لم يتم تعيين الخط الأساسي:** تأكد من استدعاء `project.setBaseline(BaselineType.Baseline)` **بعد** إضافة المهام؛ وإلا ستكون مجموعة الخطوط الأساسية فارغة.  
- **قيم فارغة:** إذا أعاد `task.getBaselines()` قائمة فارغة، تحقق من أن المهمة أضيفت إلى هيكل المشروع قبل تعيين الخط الأساسي.  
- **تنسيق التاريخ:** تُعيد طريقتا `getStart()` و `getFinish()` كائنات `java.util.Date`. استخدم `SimpleDateFormat` إذا كنت بحاجة إلى تنسيق عرض مخصص.

## الأسئلة المتكررة

**س: كيف أنشئ نسخة مشروع جديدة في Aspose.Tasks؟**  
A: استدعِ فئة `Project` (`Project project = new Project();`). هذا ينشئ ملف مشروع جديد جاهز للمهام والخطوط الأساسية.

**س: ما الفرق بين `BaselineType.Baseline` وأنواع الخطوط الأساسية الأخرى؟**  
A: `BaselineType.Baseline` تشير إلى الخط الأساسي الرئيسي (Baseline 1). تدعم Aspose.Tasks أيضًا Baseline 2‑10 لالتقاطات إضافية.

**س: هل يمكنني تصدير بيانات الخط الأساسي إلى Excel أو CSV؟**  
A: نعم، يمكنك التكرار على كائنات `TaskBaseline` وكتابة القيم إلى ملف CSV باستخدام إدخال/إخراج Java القياسي.

**س: هل يؤثر تعيين الخط الأساسي على تواريخ المهام الحالية؟**  
A: تعيين الخط الأساسي يلتقط التواريخ الحالية لكنه لا يغيّر جدول المهمة النشط. لا يزال بإمكانك تعديل تواريخ البداية/الانتهاء بعد تعيين الخط الأساسي.

**س: هل يمكن مقارنة عدة خطوط أساسية برمجيًا؟**  
A: بالتأكيد. استرجع كل خط أساسي عبر `task.getBaselines().get(index)` وقارن بين خصائص `Start` و `Finish` و `Duration` الخاصة به.

---

**آخر تحديث:** 2026-08-29  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## دروس ذات صلة

- [إنشاء قائمة مهام Java – خط أساسي لمشروع MS باستخدام Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [كيفية تعيين مدة الخط الأساسي في Aspose.Tasks for Java](/tasks/java/task-baselines/task-baseline-duration/)
- [إنشاء مشروع MPP Java – تغيير تقدم المهمة باستخدام Aspose.Tasks](/tasks/java/task-properties/change-progress/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}