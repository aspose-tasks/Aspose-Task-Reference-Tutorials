---
date: 2026-06-25
description: تعلم كيفية إضافة مهمة وتحديث ملفات MPP باستخدام Aspose.Tasks for Java،
  مكتبة إدارة المشاريع بلغة Java التي تتيح لك إنشاء ملفات Microsoft Project وحفظ المشروع
  كملف MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: كيفية إضافة مهمة وتحديث ملف MPP في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية إضافة مهمة وتحديث ملف MPP في Aspose.Tasks
url: /ar/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مهمة وتحديث ملف MPP في Aspose.Tasks

## مقدمة
في هذا الدرس ستتعلم **كيفية إضافة مهمة** إلى ملف Microsoft Project (MPP) موجود ثم حفظ الجدول المحدث باستخدام Aspose.Tasks for Java، وهي **java project management library** رائدة. سواءً كنت تبني جدولًا زمنيًا مخصصًا، أو تقوم بأتمتة تحديثات جماعية، أو تدمج بيانات المشروع في نظام أكبر، فإن الدليل خطوة بخطوة أدناه يوضح بالضبط كيفية تحميل مشروع، وإدراج مهمة جديدة، وتعيين تواريخها، وحفظ النتيجة كملف MPP جديد.

## إجابات سريعة
- **ما معنى “how to add task” في هذا السياق؟** يعني إنشاء عنصر عمل جديد برمجيًا داخل ملف MPP موجود.  
- **أي مكتبة تتعامل مع العملية؟** Aspose.Tasks for Java، مكتبة java project management قوية.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يكفي للتطوير؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل يمكنني حفظ النتيجة كملف MPP؟** نعم—استخدم `project.save(..., SaveFileFormat.Mpp)` لـ **save project as mpp**.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أحدث.

## ما هو “how to add task” في ملف MPP؟
إضافة مهمة تعني إدراج عنصر عمل جديد في هيكل المشروع، وتحديد تواريخ البدء/الانتهاء، وحفظ التغيير مرة أخرى في ملف MPP. تقوم Aspose.Tasks بتجريد تفاصيل تنسيق الملف منخفض المستوى، مما يتيح لك التركيز على منطق الأعمال مع معالجة التخصيصات للموارد، والتقويمات، وحساب الاعتمادات تلقائيًا. كما تقوم بتحديث أي تخصيصات ذات صلة وإعادة حساب جدول المشروع للحفاظ على التناسق بين المهام التابعة.

## لماذا تستخدم Aspose.Tasks for Java؟
- **توافق كامل**: يدعم 100٪ من الميزات عبر Microsoft Project 2007‑2021 (أكثر من 150 نوع مهمة و200 حقل مورد).  
- **بدون تبعيات**: لا تحتاج إلى COM أو Office أو مكتبات أصلية—واجهة برمجة تطبيقات Java النقية تعمل في أي بيئة JRE.  
- **مجموعة ميزات غنية**: تشمل ربط المهام، تخصيص الموارد، الحقول المخصصة، وتقارير مدمجة.  
- **أداء عالي**: يعالج المشاريع التي تصل إلى 10,000 مهمة باستخدام أقل من 200 ميغابايت من الذاكرة RAM، مما يجعله مثاليًا لأتمتة الخوادم.

## المتطلبات المسبقة
1. **بيئة تطوير Java** – JDK 8+ مثبت ومُكوَّن.  
2. **Aspose.Tasks for Java** – حمّل من [صفحة التحميل](https://releases.aspose.com/tasks/java/).  
3. **معرفة أساسية بـ Java** – الإلمام بالفئات، الكائنات، ومعالجة التواريخ.  

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. هذا يمنحك إمكانية التلاعب بالمشروع، خصائص المهمة، ومعالجة التواريخ.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` يمثل ملف Microsoft Project محمَّل في الذاكرة. `SaveFileFormat` يعدد الصيغ التي يمكنك الحفظ إليها، مثل MPP أو PDF. `Task` نمذج عنصر عمل فردي داخل هيكل المشروع. `Tsk` يوفر ثوابت لحقول المهمة المستخدمة عند ضبط أو استرجاع القيم. `Calendar` يقدم أدوات تاريخ‑وقت لتحديد الجداول.

## الخطوة 1: تعريف دليل البيانات
```java
String dataDir = "Your Data Directory";
```  
استبدل `"Your Data Directory"` بالمسار المطلق حيث يقع ملف MPP المصدر الخاص بك.

## الخطوة 2: قراءة المشروع الموجود
فئة `Project` هي الكائن الأساسي في Aspose.Tasks الذي يمثل ملف Microsoft Project في الذاكرة.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
المُنشئ يحمل **SampleMSP2010.mpp**، مما يمنحك نموذج كائن قابل للتلاعب بالكامل.

## الخطوة 3: إنشاء مهمة جديدة (how to add task)
فئة `Task` تمثل عنصر عمل فردي داخل هيكل المشروع.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
هذا السطر **creates task in mpp** بإضافة عنصر فرعي باسم *Task1* إلى المهمة الجذرية.

## الخطوة 4: تعيين تواريخ البدء والانتهاء
فئة `Calendar` توفر أدوات تاريخ‑وقت؛ الأشهر مُرقَّمة من الصفر (مثال، `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
هنا نحدد الجدول الزمني للمهمة التي أُضيفت حديثًا. عدّل التواريخ لتتناسب مع خط زمني مشروعك.

## الخطوة 5: حفظ المشروع (save project as mpp)
`SaveFileFormat.Mpp` يخبر Aspose.Tasks بكتابة الملف مرة أخرى بصيغة Microsoft Project الأصلية.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
المشروع المحدث، الذي يحتوي الآن على المهمة الجديدة، يُحفظ كـ **AfterLinking.mpp**.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **الملف غير موجود** | تحقق من أن `dataDir` ينتهي بفاصل مسار (`/` أو `\\`) وأن اسم الملف صحيح. |
| **تواريخ غير صحيحة** | تذكر أن أشهر `Calendar` مُرقَّمة من الصفر؛ `Calendar.JULY` هو الصحيح لشهر يوليو. |
| **استثناء الترخيص** | ثبّت ترخيص Aspose.Tasks صالح قبل استدعاء أي API لتجنب علامات مائية للتقييم. |

## الأسئلة المتكررة
**س: كيف يمكنني إضافة مهام متعددة مرة واحدة؟**  
ج: كرّر حلقة على مجموعة من أسماء المهام وأعد تنفيذ كتلة “إنشاء مهمة” داخل الحلقة.

**س: هل يمكنني ضبط حقول مخصصة للمهمة الجديدة؟**  
ج: نعم—استخدم `task.set(Tsk.CUSTOM_FIELD_x, value)` حيث *x* هو مؤشر الحقل.

**س: هل من الممكن نسخ مهمة موجودة كقالب؟**  
ج: استنسخ المهمة المصدر (`Task cloned = sourceTask.clone();`) ثم أضفها إلى الوالد المطلوب.

**س: ماذا لو احتجت إلى تحديث مهمة موجودة بدلاً من إضافة جديدة؟**  
ج: استرجع المهمة بالمعرف (`Task existing = project.getRootTask().getChildren().getById(id);`) وعدّل خصائصها.

**س: هل تدعم Aspose.Tasks الحفظ بصيغ أخرى مثل PDF أو PNG؟**  
ج: نعم—استخدم `project.save("output.pdf", SaveFileFormat.Pdf);` أو `SaveFileFormat.Png` لتمثيلات بصرية.

**آخر تحديث:** 2026-06-25  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بصيغة MPP باستخدام Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [كيفية إنشاء مشروع – ضبط سمات مهمة جديدة باستخدام Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [إنشاء قائمة مهام Java – خط أساس مشروع MS باستخدام Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}