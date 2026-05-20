---
date: 2026-05-20
description: تعلم كيفية إضافة مورد إلى المشروع وإنشاء تعيينات الموارد باستخدام Aspose.Tasks
  for Java، وهي مكتبة قوية لإدارة المشاريع بلغة Java.
keywords:
- add resource to project
- how to add task
- assign resource to task
- java project management library
linktitle: إنشاء تعيينات الموارد في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  headline: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  name: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  steps:
  - name: Create a Project Object
    text: 'The `Project` class is the top‑level container that represents a single
      project file in memory. Instantiate a `Project` object, which represents the
      project file you''re working with:'
  - name: Add a Task to the Project
    text: 'The `Task` class models an individual work item within the schedule. Add
      a task to the project using the `addChild` method of the root task:'
  - name: Add a Resource to the Project
    text: 'The `Resource` class defines a person, equipment, or material that can
      be assigned to tasks. Add a resource to the project using the `add` method of
      the `Resources` collection:'
  - name: Create a Resource Assignment
    text: 'The `ResourceAssignment` class links a `Task` and a `Resource` and stores
      allocation details such as work hours and cost. Create a resource assignment
      for the task and resource using the `add` method of the `ResourceAssignments`
      collection:'
  type: HowTo
- questions:
  - answer: Yes, you can update assignment properties such as `Work`, `Cost`, and
      `Start` using the setters provided by the `ResourceAssignment` class.
    question: Can I modify resource assignments after creation?
  - answer: Absolutely, Aspose.Tasks for Java supports MPP, XML, CSV, and many other
      formats, allowing seamless import and export.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Yes, a valid commercial license is required. A free evaluation license
      is available for testing purposes.
    question: Does Aspose.Tasks for Java require a license for commercial use?
  - answer: Yes, the library is fully thread‑safe and can be integrated into servlet‑based
      or Spring‑Boot web services.
    question: Can I use Aspose.Tasks for Java in my web applications?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for technical assistance and community discussions.
    question: Where can I find additional support for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية إضافة مورد إلى المشروع وإنشاء تعيينات الموارد في Aspose.Tasks
url: /ar/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مورد إلى المشروع – إنشاء تعيينات الموارد في Aspose.Tasks

## مقدمة
في إدارة المشاريع الحديثة، **إضافة مورد إلى المشروع** هي الأساس لتخطيط فعال والتحكم في التكاليف. توفر Aspose.Tasks for Java طريقة برمجية عالية الأداء لإدارة الموارد والمهام والتعيينات دون مغادرة بيئة التطوير المتكاملة الخاصة بك. في هذا الدرس ستتعرف على كيفية إضافة مورد إلى مشروع، ربطه بمهمة، وضبط تفاصيل التعيين — كل ذلك باستخدام كود Java نظيف وجاهز للإنتاج.

## إجابات سريعة
- **ما هي الخطوة الأولى؟** إنشاء مثيل `Project` يمثل ملف .mpp أو .xml الخاص بك.  
- **كيف أضيف مهمة؟** استخدم طريقة `addChild` للمهمة الجذرية وأعط المهمة اسمًا.  
- **كيف يمكنني إضافة مورد؟** استدعِ `project.getResources().add` مع كائن `Resource`.  
- **كيف أربط موردًا بمهمة؟** استخدم `project.getResourceAssignments().add(task, resource)`.  
- **هل أحتاج إلى ترخيص؟** نعم – يلزم وجود ترخيص صالح لـ Aspose.Tasks for Java للاستخدام الإنتاجي.

## ما هو “إضافة مورد إلى المشروع”؟
**إضافة مورد إلى المشروع** يعني إنشاء كائن `Resource` في ملف المشروع وربطه بواحدة أو أكثر من المهام بحيث يتم حساب العمل والتكلفة وبيانات التقويم تلقائيًا. هذه العملية هي العمود الفقري لأي تطبيق يعتمد على الجدولة.

## لماذا تختار Aspose.Tasks for Java؟
تدعم Aspose.Tasks for Java **أكثر من 30 تنسيقًا للإدخال والإخراج** (بما في ذلك MPP و XML و CSV) ويمكنها معالجة مشاريع تحتوي على **أكثر من 10,000 مهمة** مع الحفاظ على استهلاك الذاكرة أقل من 200 ميغابايت. تعمل المكتبة على Java 8‑17، لا تتطلب تثبيت Microsoft Project، وتوفر واجهات برمجة تطبيقات Thread‑Safe للأتمتة على الخادم.

## المتطلبات المسبقة
قبل الغوص في إنشاء تعيينات الموارد، تأكد من توفر ما يلي:

### بيئة تطوير جافا
تأكد من تثبيت مجموعة تطوير جافا (JDK) على نظامك. يمكنك تنزيل وتثبيت JDK من [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### مكتبة Aspose.Tasks for Java
قم بتنزيل مكتبة Aspose.Tasks for Java من [صفحة التنزيل](https://releases.aspose.com/tasks/java/). اتبع تعليمات التثبيت لإعداد المكتبة في مشروع Java الخاص بك.

## كيفية إضافة مورد إلى المشروع؟

حمّل مشروعك، أنشئ مهمة، أضف موردًا، وأخيرًا اربطهما معًا — كل ذلك في أربع خطوات مختصرة. توضح مقتطفات الشيفرة أدناه (نصوص نائبة) استدعاءات API الدقيقة؛ كل ما عليك هو استبدال النص النائب بمسارات الملفات والأسماء الخاصة بك.

### الخطوة 1: إنشاء كائن Project
فئة `Project` هي الحاوية العليا التي تمثل ملف مشروع واحد في الذاكرة.  
أنشئ كائن `Project`، الذي يمثل ملف المشروع الذي تعمل عليه:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

### الخطوة 2: إضافة مهمة إلى المشروع
فئة `Task` تمثل عنصر عمل فردي داخل الجدول الزمني.  
أضف مهمة إلى المشروع باستخدام طريقة `addChild` للمهمة الجذرية:
```java
Project project = new Project();
```

### الخطوة 3: إضافة مورد إلى المشروع
فئة `Resource` تعرف شخصًا أو معدات أو مادة يمكن تعيينها للمهام.  
أضف موردًا إلى المشروع باستخدام طريقة `add` لمجموعة `Resources`:
```java
Task task = project.getRootTask().getChildren().add("Task");
```

### الخطوة 4: إنشاء تعيين مورد
فئة `ResourceAssignment` تربط بين `Task` و `Resource` وتخزن تفاصيل التخصيص مثل ساعات العمل والتكلفة.  
أنشئ تعيين مورد للمهمة والموارد باستخدام طريقة `add` لمجموعة `ResourceAssignments`:
```java
Resource rsc = project.getResources().add("Rsc");
```

## المشكلات الشائعة والحلول
- **NullPointerException على `addChild`** – تأكد من استدعاء `project.getRootTask()` قبل إضافة الفروع.  
- **License not found** – ضع ملف `Aspose.Tasks.lic` في مسار الـ classpath أو اضبط الترخيص برمجيًا باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Large project slowdown** – استخدم `project.setReadOnly(true)` عندما تحتاج فقط إلى قراءة البيانات؛ هذا يقلل من استهلاك الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني تعديل تعيينات الموارد بعد إنشائها؟**  
ج: نعم، يمكنك تحديث خصائص التعيين مثل `Work` و `Cost` و `Start` باستخدام الدوال setter المتوفرة في فئة `ResourceAssignment`.

**س: هل Aspose.Tasks for Java متوافق مع تنسيقات ملفات المشروع المختلفة؟**  
ج: بالتأكيد، تدعم Aspose.Tasks for Java تنسيقات MPP و XML و CSV والعديد من التنسيقات الأخرى، مما يتيح استيراد وتصدير سلس.

**س: هل يتطلب Aspose.Tasks for Java ترخيصًا للاستخدام التجاري؟**  
ج: نعم، يلزم وجود ترخيص تجاري صالح. يتوفر ترخيص تجريبي مجاني لأغراض الاختبار.

**س: هل يمكنني استخدام Aspose.Tasks for Java في تطبيقات الويب الخاصة بي؟**  
ج: نعم، المكتبة Thread‑Safe بالكامل ويمكن دمجها في خدمات الويب القائمة على Servlets أو Spring‑Boot.

**س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks for Java؟**  
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة تقنية ومناقشات المجتمع.

---

**آخر تحديث:** 2026-05-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إنشاء موارد – إدارة الموارد مع Aspose.Tasks for Java](/tasks/java/resource-management/)
- [كيفية إضافة ملاحظات إلى تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [كيفية إضافة مورد إلى المشروع ومعالجة خصائص تأخير التسوية في Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}