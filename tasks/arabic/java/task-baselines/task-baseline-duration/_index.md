---
date: 2026-08-29
description: تعلم كيفية ضبط baseline duration وتتبع project progress باستخدام Aspose.Tasks
  for Java. هذا الدليل خطوة بخطوة يساعدك على إدارة task baselines بفعالية.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: كيفية ضبط Baseline Duration في Aspose.Tasks for Java
og_description: تعلم كيفية ضبط baseline duration وتتبع project progress باستخدام Aspose.Tasks
  for Java. اتبع هذا الدليل المفصل لإدارة task baselines بفعالية.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: كيفية ضبط baseline duration لتتبع project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: كيفية ضبط baseline duration لتتبع project progress
url: /ar/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين مدة الخط الأساسي لتتبع تقدم المشروع

## مقدمة
يبدأ تتبع تقدم المشروع بخط أساسي ثابت. في هذا الدرس ستكتشف **كيفية تعيين مدة الخط الأساسي** للمهام في ملفات Microsoft Project باستخدام مكتبة Aspose.Tasks للغة Java، وتفهم لماذا يساعد إنشاء الخط الأساسي مبكرًا في مراقبة انحراف الجدول الزمني، وتفاوت التكاليف، وإفراط تخصيص الموارد طوال دورة حياة المشروع.

## إجابات سريعة
- **ماذا يعني “set baseline”?** يسجل البداية الأصلية، النهاية، والمدة للمهام بحيث يمكنك مقارنة التغييرات المستقبلية.  
- **أي فئة Aspose.Tasks تنشئ مشروعًا؟** فئة `Project` – ستتعلم أيضًا كيفية **إنشاء نسخة من المشروع** بشكل صحيح.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** ترخيص التقييم المجاني يعمل للاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني استرجاع الخطوط الأساسية المرحلية؟** نعم، تتيح لك Aspose.Tasks الاستعلام عن الخطوط الأساسية المرحلية وتكاليفها الثابتة.  
- **ما نسخة Java المطلوبة؟** يوصى باستخدام Java 8 أو أحدث.  
- **كيف يساعدني ذلك في تتبع تقدم المشروع؟** بمجرد تعيين الخط الأساسي، يمكنك مقارنة التواريخ الفعلية بالخطة الأصلية فورًا باستخدام ميزات التقارير المدمجة.

## ما هو الخط الأساسي للمهمة ولماذا يتم تعيينه؟
الخط الأساسي للمهمة يلتقط الجدول الزمني المخطط (تاريخ البدء، تاريخ الانتهاء، والمدة) في نقطة زمنية محددة. من خلال تعيين خط أساسي، تنشئ نقطة مرجعية تجعل من السهل اكتشاف انحراف الجدول الزمني، وتجاوز التكاليف، وإفراط تخصيص الموارد مع تطور المشروع.

## لماذا تستخدم Aspose.Tasks لإدارة الخطوط الأساسية؟
توفر Aspose.Tasks **توافق كامل مع .mpp** – يمكنك قراءة وكتابة ملفات Microsoft Project الأصلية دون الحاجة إلى تثبيت Microsoft Office. تتيح لك الواجهة البرمجية الوصول البرمجي إلى **أكثر من 50 تنسيق إدخال وإخراج**، وتدعم **الخطوط الأساسية المرحلية 1‑10**، ويمكنها معالجة **مشاريع مئات الصفحات** دون تحميل الملف بالكامل إلى الذاكرة، وهو أمر أساسي لمعالجة الدُفعات ذات الأداء العالي.

## المتطلبات المسبقة
1. **بيئة تطوير Java** – JDK 8+ مثبت ومُعد.  
2. **Aspose.Tasks للغة Java** – قم بتنزيل المكتبة من [صفحة تنزيل Aspose.Tasks للغة Java](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة أو أداة بناء** – Maven، Gradle، أو أي بيئة تطوير متكاملة تفضلها.

## استيراد الحزم
الاستيرادات التالية تجلب فئات Aspose.Tasks الأساسية اللازمة للعمل مع المشاريع، والمهام، والخطوط الأساسية، وبيانات الوقت المرحلية.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## الخطوة 1: إنشاء نسخة من المشروع
فئة `Project` تمثل ملف Microsoft Project في الذاكرة وتعد نقطة الدخول لجميع العمليات.

```java
Project project = new Project();
```

## الخطوة 2: إنشاء خط أساسي للمهمة
`TaskBaseline` يخزن البداية المخططة، النهاية، والمدة لمهمة محددة.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## الخطوة 3: عرض معلومات الخط الأساسي للمهمة
طريقة `getBaselines()` تُعيد مجموعة الخطوط الأساسية المرتبطة بمهمة.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## الخطوة 4: التحقق من الخط الأساسي المرحلي والتكلفة الثابتة
`BaselineType` تُعدد الخطوط الأساسية الأولية والمرحلية (Baseline، Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## الخطوة 5: طباعة البيانات المرحلية
`TimephasedData` تمثل جزءًا من معلومات الجدول الزمني لفترة زمنية محددة.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

باتباع هذه الخطوات، يمكنك **تعيين مدة الخط الأساسي** لأي مهمة واسترجاع معلومات تفصيلية عن الخط الأساسي باستخدام Aspose.Tasks للغة Java، مما يمنحك طريقة موثوقة **لتتبع تقدم المشروع** طوال دورة حياة المشروع.

## المشكلات الشائعة والحلول
- **الخط الأساسي لا يظهر في MS Project:** تأكد من استدعاء `project.setBaseline(BaselineType.Baseline)` **بعد** إضافة المهمة.  
- **NullPointerException على `getBaselines()`:** تحقق من أن المهمة أضيفت إلى المشروع قبل تعيين الخط الأساسي.  
- **عدم تطابق وحدة الوقت:** استخدم `TimeUnitType` لتنسيق المدة بشكل صحيح، خاصةً عند العمل مع تقاويم مخصصة.

## الأسئلة المتكررة
### ما هو الخط الأساسي للمهمة في MS Project؟
الخط الأساسي للمهمة في MS Project هو لقطة للجدول الزمني المخطط الأولي للمهمة، بما في ذلك تاريخ البدء، تاريخ الانتهاء، والمدة.

### لماذا إدارة الخطوط الأساسية للمهام مهمة؟
تساعد إدارة الخطوط الأساسية للمهام في مقارنة الجدول المخطط مع التقدم الفعلي للمشروع، مما يسهل تتبعًا أفضل واتخاذ قرارات أكثر فعالية.

### هل يمكنني تعديل الخط الأساسي للمهمة بمجرد تعيينه؟
نعم، يمكنك تعديل الخطوط الأساسية للمهام في MS Project لتعكس التغييرات في خطة المشروع. ومع ذلك، من الضروري توثيق أي انحرافات عن الخط الأساسي الأصلي.

### هل تدعم Aspose.Tasks وظائف إدارة مشاريع أخرى؟
نعم، تقدم Aspose.Tasks مجموعة واسعة من الميزات لإدارة المشاريع، بما في ذلك جدولة المهام، تخصيص الموارد، وإنشاء مخططات جانت.

### أين يمكنني العثور على دعم Aspose.Tasks؟
يمكنك العثور على دعم Aspose.Tasks في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15)، حيث يمكنك طرح الأسئلة والتفاعل مع المستخدمين الآخرين.

## أسئلة متكررة إضافية
**س: هل أحتاج إلى استدعاء `setBaseline` لكل مهمة على حدة؟**  
ج: لا. استدعاء `project.setBaseline(BaselineType.Baseline)` يسجل الخط الأساسي لجميع المهام في المشروع مرة واحدة.

**س: كيف يمكنني تعيين خط أساسي مرحلي لمهمة محددة؟**  
ج: استخدم `project.setBaseline(BaselineType.Baseline1)` (أو Baseline2‑Baseline10) بعد تحديث جدول المهمة.

**س: هل يمكن تصدير بيانات الخط الأساسي إلى CSV؟**  
ج: نعم. قم بالتكرار على `task.getBaselines()` واكتب الحقول المطلوبة إلى ملف CSV باستخدام I/O القياسي في Java.

**س: هل يمكنني قراءة ملف .mpp موجود يحتوي بالفعل على خطوط أساسية؟**  
ج: بالتأكيد. حمّل الملف باستخدام `new Project("myproject.mpp")` ثم وصول إلى خطوط الأساس لكل مهمة كما هو موضح أعلاه.

**س: هل تدعم Aspose.Tasks ملفات متعددة المشاريع؟**  
ج: تعمل Aspose.Tasks مع ملفات .mpp لمشروع واحد. بالنسبة لسيناريوهات متعددة المشاريع، يمكنك دمج المشاريع برمجيًا.

---

**آخر تحديث:** 2026-08-29  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء قائمة مهام Java – خط أساسي لمشروع MS باستخدام Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [إنشاء مشروع MPP Java – تغيير تقدم المهمة باستخدام Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [خط أساسي لإدارة المشروع – جدولة المهام باستخدام Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}