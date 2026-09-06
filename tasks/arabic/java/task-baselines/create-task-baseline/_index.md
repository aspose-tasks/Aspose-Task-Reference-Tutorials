---
date: 2026-08-29
description: تعلم كيفية إضافة task إلى project في Java، إنشاء قائمة task، وتعيين baseline
  دون Microsoft Project باستخدام Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: إنشاء Task Baseline في Aspose.Tasks
og_description: تعلم كيفية إضافة task إلى project في Java وتعيين baseline باستخدام
  Aspose.Tasks. يوضح هذا الدليل الكود خطوة بخطوة دون الحاجة إلى Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: كيفية إضافة task إلى project في Java وتعيين baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: كيفية إضافة task إلى project في Java وتعيين baseline
url: /ar/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مهمة إلى المشروع في Java وتعيين خط أساس

## مقدمة
في هذا البرنامج التعليمي ستقوم **بإضافة مهمة إلى المشروع** برمجيًا، وتوليد خط أساس لمهمة Microsoft Project، وحفظ الملف—كل ذلك دون فتح Microsoft Project أبدًا. توفر Aspose.Tasks for Java واجهة برمجة تطبيقات Java صافية تعمل على أي منصة، مما يجعلها مثالية لأنابيب البناء الآلية، وخدمات التقارير، أو أي حل من جانب الخادم يحتاج إلى معالجة ملفات .mpp.

## إجابات سريعة
- **ما الذي تفعله Aspose.Tasks؟** توفر واجهة برمجة تطبيقات Java لإنشاء وقراءة وتحرير ملفات Microsoft Project دون الحاجة إلى Microsoft Project.  
- **هل أحتاج إلى تثبيت Microsoft Project؟** لا، المكتبة تعمل بشكل مستقل تمامًا.  
- **ما نسخة Java المطلوبة؟** JDK 8 أو أعلى.  
- **هل يمكنني تعيين خط أساس لمهمة واحدة؟** نعم – استدعِ `setBaseline` على قائمة تحتوي فقط على المهام التي تريدها.  
- **هل تحتاج إلى ترخيص للإنتاج؟** نعم، الترخيص التجاري يزيل حدود التقييم ويفتح جميع الميزات.

## ما هو خط أساس المهمة؟
خط أساس المهمة يلتقط تاريخ البدء المخطط أصلاً، وتاريخ الانتهاء، وجهد العمل للمهمة في الوقت الذي يتم فيه حفظ الجدول لأول مرة. يعمل هذا اللقطة كمرجع، مما يسمح لمديري المشروع بمقارنة التقدم الفعلي والتكاليف مع الخطة الأولية، وحساب الفروقات لتحليل الأداء.

## لماذا تستخدم Aspose.Tasks لإضافة مهمة إلى مشروع في Java؟
يمكنك إنشاء وتعديل وتعيين خطوط أساس للمهام دون أي تثبيت سطح مكتب، مما يتيح سير عمل مؤتمت بالكامل. تدعم Aspose.Tasks **أكثر من 50 تنسيق إدخال وإخراج** ويمكنها التعامل مع مشاريع تحتوي على **مئات المهام** مع الحفاظ على استهلاك الذاكرة أقل من 200 ميغابايت، مما يجعلها مثالية للخدمات السحابية وأنابيب CI/CD.

## المتطلبات المسبقة
1. **Java Development Kit (JDK)** – قم بتثبيت JDK 8 أو أحدث.  
2. **Aspose.Tasks for Java** – قم بتنزيل المكتبة من [رابط التحميل](https://releases.aspose.com/tasks/java/).  

## استيراد الحزم
لبدء العمل مع Aspose.Tasks في مشروع Java الخاص بك، استورد الحزم اللازمة:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## الخطوة 1: إنشاء كائن مشروع
الفئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project في الذاكرة. إنشاء نسخة منه يمنحك مشروعًا فارغًا يمكنك ملؤه بالمهام والموارد والتقويمات.

```java
Project project = new Project();
```
هنا نقوم بإنشاء كائن `Project` جديد – هذا يمثل ملف MS Project الذي سيحمل قائمة مهامنا.

## الخطوة 2: إضافة مهمة إلى المشروع
الفئة `Task` تمثل عنصر عمل فردي في جدول المشروع. يمكن لكل `Task` أن يكون لها مدة، تاريخ بدء، وتعيينات موارد خاصة بها.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
باستخدام `getRootTask()` نصل إلى جذر هيكل المشروع ونقوم **بإضافة مهمة إلى Microsoft Project**. السلسلة `"Task"` هي اسم المهمة؛ يمكنك استبدالها بأي وصف تحتاجه.

## الخطوة 3: تعيين خط أساس للمهام المحددة
`BaselineType` هو تعداد يحدد أي خانة خط أساس (Baseline, Baseline1 … Baseline10) تريد الكتابة فيها. بتمرير قائمة من المهام يمكنك تعيين خط أساس فقط للعناصر التي تختارها.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
لـ **تعيين خط أساس دون MS Project**، أنشئ قائمة بالمهام التي تريد تعيين خط أساس لها (هنا `myList`) ومررها إلى `setBaseline`. املأ `myList` بالمهام التي أضفتها إذا كنت تحتاج إلى خط أساس انتقائي فقط.

## الخطوة 4: تعيين خط أساس للمشروع بالكامل
`setBaseline` يكتب قيم خط الأساس المختارة إلى كل مهمة في المشروع.  
إذا كنت تفضل تعيين خط أساس للمشروع بالكامل في استدعاء واحد، ما عليك سوى استدعاء `setBaseline` مع `BaselineType` المطلوب.

```java
project.setBaseline(BaselineType.Baseline);
```
هذا الاستدعاء يكتب قيم خط الأساس المختارة **لكل مهمة** في المشروع، مما يضمن لقطة كاملة للجدول الأصلي.

## كيفية إضافة مهمة إلى Microsoft Project باستخدام Aspose.Tasks
الدالة `add()` تنشئ مهمة فرعية جديدة تحت المهمة الأم المحددة وتعيد كائن `Task` الذي تم إنشاؤه حديثًا.  
تضيف مهمة عن طريق استدعاء `add()` على كائن `Task` أب (عادةً المهمة الجذر). تُعيد الطريقة كائن `Task` جديد يمكنك تعديل خصائصه—المدة، تاريخ البدء، الموارد، أو الحقول المخصصة—قبل حفظ ملف المشروع.

## كيفية تعيين خط أساس دون MS Project
تمكنك Aspose.Tasks من إنشاء خط أساس بالكامل عبر الشيفرة. اختر `BaselineType` (مثلًا `BaselineType.Baseline`) واستدعِ `setBaseline`. يمكنك تكرار ذلك مع `Baseline1`‑`Baseline10` للحفاظ على عدة إصدارات من خطوط الأساس، كل ذلك دون فتح Microsoft Project.

## المشكلات الشائعة والحلول
- **عدم ظهور خط الأساس:** تأكد من استدعاء `project.save("output.mpp")` بعد تعيين خط الأساس (تم حذف خطوة الحفظ هنا للاختصار).  
- **قائمة المهام تظهر فارغة:** تحقق من أنك تضيف المهام إلى الوالد الصحيح (`getRootTask()` أو مهمة فرعية).  
- **أخطاء عدم توافق الإصدارات:** استخدم أحدث ملف JAR لـ Aspose.Tasks لضمان التوافق مع تنسيقات .mpp الأحدث.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java دون تثبيت Microsoft Project؟**  
ج: نعم، تعمل Aspose.Tasks بشكل مستقل ولا تتطلب وجود Microsoft Project على الجهاز المضيف.

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من Microsoft Project؟**  
ج: بالتأكيد. تدعم المكتبة ملفات Project من 2007 حتى أحدث إصدارات 2024.

**س: هل يمكنني معالجة موارد المشروع باستخدام Aspose.Tasks for Java؟**  
ج: نعم، يمكنك إضافة وتحديث وحذف الموارد برمجيًا، تمامًا كما هو الحال مع المهام.

**س: هل تدعم Aspose.Tasks for Java تعيين تبعيات المهام؟**  
ج: نعم، يمكنك تعريف علاقات السلف‑الخلف باستخدام الفئة `TaskLink`.

**س: هل يتوفر دعم فني لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على المساعدة عبر [منتدى الدعم](https://forum.aspose.com/c/tasks/15)، حيث يرد فريق Aspose والمجتمع على الاستفسارات.

## الخلاصة
باتباع هذه الخطوات تعلمت كيفية **إضافة مهمة إلى المشروع** في Java، إنشاء قائمة مهام، و**تعيين خط أساس دون MS Project** باستخدام Aspose.Tasks. يسهّل هذا النهج أتمتة المشاريع، يزيل الحاجة إلى تثبيت سطح المكتب، ويمنحك تحكمًا برمجيًا كاملاً في كل جانب من جوانب جدولك الزمني.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## دروس ذات صلة

- [كيفية إنشاء مشروع aspose.tasks – تعيين سمات مهمة جديدة](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [كيفية تعيين مدة خط الأساس في Aspose.Tasks for Java](/tasks/java/task-baselines/task-baseline-duration/)
- [إنشاء مهام Aspose Java – خصائص المهمة](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}