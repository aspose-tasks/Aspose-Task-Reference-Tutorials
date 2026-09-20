---
date: 2026-09-20
description: تعلم كيفية إدارة task dependencies للمشروع باستخدام Aspose.Tasks for
  Java. يوضح لك هذا الدليل كيفية إضافة predecessor links، طباعة task names، وتعيين
  task dependencies بكفاءة.
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: إدارة تبعيات مهام المشروع عبر Aspose.Tasks for Java
og_description: تعلم كيفية إدارة task dependencies للمشروع باستخدام Aspose.Tasks for
  Java. يوضح لك هذا الدليل كيفية إضافة predecessor links، طباعة task names، وتعيين
  task dependencies بكفاءة.
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: إدارة تبعيات مهام المشروع عبر Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: إدارة تبعيات مهام المشروع عبر Aspose.Tasks for Java
url: /ar/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة تبعيات مهام المشروع عبر Aspose.Tasks for Java

## مقدمة
تُعد تبعيات مهام المشروع العمود الفقري لأي جدول زمني واقعي، حيث تتيح لك نمذجة أي عمل يجب أن ينتهي قبل أن يبدأ عمل آخر. في هذا البرنامج التعليمي ستتعلم كيفية إدارة **تبعيات مهام المشروع** باستخدام Aspose.Tasks for Java، بما في ذلك كيفية إضافة روابط سابقة، طباعة أسماء المهام، وتعيين تبعيات المهام برمجيًا.

## إجابات سريعة
- **ما هي الخطوة الأولى؟** حمّل ملف MPP الخاص بك إلى كائن `Project`.  
- **كيف تضيف سابقة؟** أنشئ `TaskLink` وعيّن قيم `PredecessorTaskUid` و `SuccessorTaskUid`.  
- **هل يمكنك سرد جميع الروابط؟** استخدم `project.getTaskLinks()` وتكرّر عبر المجموعة.  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت يكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **أي نسخة جافا مدعومة؟** Java 8 أو أعلى.

## ما هي تبعيات مهام المشروع؟
تحدد تبعيات مهام المشروع العلاقة المنطقية بين مهمتين، مثل Finish‑to‑Start أو Start‑to‑Start، وتحدد ترتيب تنفيذ العمل. من خلال إنشاء هذه الروابط، يلتزم الجدول الزمني تلقائيًا بالقيود الواقعية، ويمنع الأنشطة المتداخلة، ويضمن أن تبدأ المهام اللاحقة فقط عندما يتم استيفاء المتطلبات المسبقة لها.

## لماذا تستخدم Aspose.Tasks for Java؟
يدعم Aspose.Tasks for Java أكثر من ثلاثين تنسيق ملف مشروع، بما في ذلك أحدث إصدارات Microsoft Project، ويمكنه معالجة ملفات تصل إلى حجم جيجابايتين دون تحميل المستند بالكامل في الذاكرة. تتيح لك هذه القدرة عالية الأداء التعامل مع جداول زمنية ضخمة، وإنشاء تقارير، وإجراء تحديثات جماعية بكفاءة، مما يجعلها مثالية لحلول إدارة المشاريع على مستوى المؤسسات.

## المتطلبات المسبقة
- بيئة تطوير جافا: Java 8 أو أحدث مثبتة على جهازك.  
- مكتبة Aspose.Tasks for Java: قم بتنزيل وتثبيت مكتبة Aspose.Tasks من [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).  
- بيئة التطوير المتكاملة (IDE): Eclipse، IntelliJ IDEA، أو أي بيئة تطوير متوافقة مع جافا تفضلها.

## استيراد الحزم
تحتاج إلى استيراد الفئات الأساسية التي تمكّن من معالجة المشروع.

الفئة `Project` هي نقطة الدخول لتحميل وحفظ ملفات Microsoft Project.  
الفئة `TaskLink` تمثل تبعية بين مهمتين.  

## كيفية إضافة رابط سابقة بين مهمتين؟
أنشئ كائن `TaskLink`، وعيّن UID للمهمة السابقة وUID للمهمة اللاحقة، واختر `TaskLinkType` المناسب مثل Finish‑to‑Start، ثم أضف الرابط إلى مجموعة روابط المهام في المشروع. بمجرد الإضافة، يعكس الجدول الزمني فورًا علاقة التبعية الجديدة.

### الخطوة 1: تهيئة كائن المشروع
أنشئ مثالًا جديدًا من الفئة `Project` وقدم المسار إلى ملف المشروع الخاص بك (مثال: `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### الخطوة 2: الوصول إلى روابط المهام
استرجع جميع روابط المهام من المشروع باستخدام طريقة `getTaskLinks()`.

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### الخطوة 3: التكرار عبر روابط المهام
استخدم حلقة للتكرار عبر كل رابط مهمة في المجموعة وطباعة معلومات عن المهمة السابقة والمهمة اللاحقة.

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### الخطوة 4: إضافة رابط سابقة جديد (اختياري)
إذا كنت بحاجة لإنشاء تبعية جديدة، أنشئ كائن `TaskLink`، عيّن قيم `PredecessorTaskUid` و`SuccessorTaskUid` و`LinkType`، ثم أضفه إلى مجموعة روابط المشروع.

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

كرر هذه الخطوات حسب الحاجة لمتطلبات مشروعك المحددة.

## المشكلات الشائعة والحلول
- **فقدان المهمة السابقة بعد إضافة الرابط** – تأكد من استدعاء `project.updateTaskLinks()` (أو حفظ وإعادة تحميل) حتى يتم تحديث الرسم الداخلي.  
- **تباطؤ الأداء على الملفات الكبيرة** – استخدم `project.setReadOnly(true)` قبل عمليات الدفعة لتقليل استهلاك الذاكرة.  
- **نوع الرابط غير صحيح** – تحقق من أنك تستخدم قيمة enum الصحيحة `TaskLinkType` (مثال: `FinishToStart`) لتتناسب مع منطق الجدول الزمني الخاص بك.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java في مشروع جافا الحالي؟**  
ج: نعم، ما عليك سوى إضافة ملف JAR الخاص بـ Aspose.Tasks إلى مسار الفئات (classpath) أو إلى تبعيات Maven/Gradle.

**س: هل Aspose.Tasks متوافق مع تنسيقات ملفات المشروع المختلفة؟**  
ج: نعم، يدعم MPP، XML، CSV، وأكثر من 30 تنسيقًا إضافيًا.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: احصل على ترخيص مؤقت من [temporary license page](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks؟**  
ج: زر [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) للحصول على دعم المجتمع والنقاشات.

**س: هل يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Tasks for Java؟**  
ج: نعم، قم بتنزيل نسخة تجريبية مجانية من [Aspose free trial page](https://releases.aspose.com/).

---

**آخر تحديث:** 2026-09-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تبعيات مهام إدارة المشروع في Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [تحديد تاريخ بدء المشروع وإدارة المهام الأصلية والفرعية في Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [قراءة وتعيين أولويات المهام باستخدام Aspose.Tasks for Java](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}