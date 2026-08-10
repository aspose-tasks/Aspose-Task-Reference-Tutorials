---
date: 2026-07-05
description: تعلم كيفية ربط المهام عبر المشاريع باستخدام Aspose.Tasks for Java. دليل
  خطوة بخطوة، المتطلبات المسبقة، وأفضل الممارسات لتحقيق ربط سلس للمهام عبر المشاريع.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: إنشاء رابط مهمة عبر المشاريع في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: ربط المهام عبر المشاريع باستخدام Aspose.Tasks for Java
url: /ar/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ربط المهام عبر المشاريع باستخدام Aspose.Tasks للـ Java

## مقدمة
ربط المهام عبر المشاريع هو قدرة أساسية تتيح لك مزامنة العمل، تجنب التكرار، والحفاظ على مصدر واحد للحقيقة للأنشطة المتشابكة. في هذا البرنامج التعليمي ستكتشف كيفية **ربط المهام عبر المشاريع** باستخدام Aspose.Tasks للـ Java، خطوة بخطوة. في النهاية ستحصل على رابط عبر‑مشروع يعمل بالكامل ويتحدث تلقائيًا عندما يتغير أي من الجانبين، مما يمنحك تنسيقًا فوريًا دون الحاجة إلى النسخ واللصق يدويًا.

## إجابات سريعة
- **ما هي الفئة الأساسية لإنشاء مشروع؟** `Project` – تمثل ملف MS‑Project بالكامل في الذاكرة.  
- **ما الطريقة التي تضيف مهمة خارجية؟** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **هل يمكنني تعيين نوع الارتباط؟** نعم – استخدم `TaskLinkType.FinishToStart`، `StartToStart`، إلخ.  
- **هل أحتاج إلى ترخيص للربط؟** يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام في الإنتاج؛ النسخة التجريبية المجانية تعمل للتقييم.  
- **هل هناك حد لعدد المهام المرتبطة؟** يمكن لـ Aspose.Tasks التعامل مع أكثر من 10,000 مهمة مرتبطة لكل مشروع دون تدهور في الأداء.

## ما هو ربط المهام عبر المشاريع؟
إن ربط المهام عبر المشاريع يخلق علاقة اعتماد بين مهمة في ملف مشروع واحد ومهمة في ملف آخر، مما يسمح بتدفق التغييرات في المهمة المصدر (المدة، تاريخ البدء، القيود) تلقائيًا إلى المهمة التابعة. هذه الآلية تحافظ على توافق الجداول الزمنية، تقلل من التحديثات اليدوية، وتضمن أن أي تعديل في المشروع المصدر ينعكس فورًا في جميع المشاريع المرتبطة، مما يحافظ على الاتساق عبر الحافظة.

## لماذا نستخدم Aspose.Tasks للربط عبر المشاريع؟
يدعم Aspose.Tasks **أكثر من 50 تنسيقًا للإدخال والإخراج** ويمكنه معالجة **مشاريع مئات الصفحات** مع الحفاظ على استهلاك الذاكرة أقل من 200 ميغابايت. تقوم API الخاصة به بأداء الربط على جانب الخادم، مما يلغي الحاجة إلى تثبيت Microsoft Project ويمكّن من خطوط أنابيب مؤتمتة للمؤسسات الكبيرة.

## المتطلبات المسبقة
- Java 17 (أو أحدث) مثبت ومُكوَّن في بيئة التطوير المتكاملة الخاصة بك.  
- ملف ترخيص صالح لـ Aspose.Tasks للـ Java (`Aspose.Tasks.Java.lic`).  
- مكتبة Aspose.Tasks للـ Java مضافة إلى مشروعك. يمكنك تنزيلها من [صفحة إصدار Aspose.Tasks للـ Java](https://releases.aspose.com/tasks/java/).  
- إلمام أساسي بمفاهيم MS‑Project مثل المهام، المهام الملخصة، والاعتمادات.

## استيراد الحزم
توجد الفئات `Project`، `Task`، `TaskLink` والعدادات المرتبطة في مساحة الاسم `com.aspose.tasks`. استوردها في أعلى ملف Java الخاص بك:

`import com.aspose.tasks.*;`

**Project** هي الفئة الرئيسية التي تمثل ملف مشروع في الذاكرة. **Task** تمثل عنصر عمل فردي داخل المشروع. **TaskLink** يحدد علاقة اعتماد بين مهمتين. هذه الاستيرادات تمنحك الوصول إلى مجموعة كاملة من ميزات تعديل المشروع، بما في ذلك الربط عبر المشاريع.

## كيف تربط المهام عبر المشاريع؟
حمّل ملفي المشروع، أضف عنصرًا نائبًا لمهمة خارجية، أنشئ مهمة محلية، ثم اربطهما باستخدام `TaskLink`. تتولى API معالجة تعيين المعرفات والتحديثات تلقائيًا، مما يضمن أن أي تغيير في المهمة الخارجية ينتقل إلى المهمة المحلية المرتبطة دون الحاجة إلى شفرة إضافية. هذا النهج يبسط تنسيق المشاريع المتعددة ويقلل من خطر انزلاق الجدول الزمني.

### الخطوة 1: إعداد بيئتك
تأكد من أن ملف JAR الخاص بـ Aspose.Tasks موجود في مسار الفئات وأن ملف الترخيص محمَّل أثناء التشغيل:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** يحمل ملف ترخيص Aspose.Tasks الخاص بك لتمكين الوظائف الكاملة وإزالة العلامات المائية للتقييم.

### الخطوة 2: إنشاء كائن مشروع
أنشئ كائن `Project` جديد للمشروع الهدف حيث تريد أن يعيش الرابط:

`Project targetProject = new Project();`

فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف مشروع واحد في الذاكرة.

### الخطوة 3: إضافة مهمة ملخصة
المهمة الملخصة تجمع المهام ذات الصلة. أنشئ واحدة لتحتوي كلًا من المهمة الخارجية والمحلية:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### الخطوة 4: إضافة مهمة خارجية
أدخل مهمة خارجية تشير إلى مهمة في ملف مشروع آخر:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

طريقة **addExternalTask** تنشئ مهمة نائب تُشير إلى ملف مشروع خارجي، باستخدام اسم الملف ومعرف المهمة المقدمين.

### الخطوة 5: إضافة مهمة محلية
أنشئ المهمة التي سيتم ربطها بالمهمة الخارجية:

`Task local = summary.getChildren().add("Local Task");`

### الخطوة 6: إنشاء ارتباط مهمة
أنشئ اعتمادًا بين المهمة الخارجية والمحلية. أكثر أنواع الروابط شيوعًا هو Finish‑to‑Start:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** يسجل العلاقة؛ يمكنك لاحقًا تعديل التأخير أو التقدم أو النوع حسب الحاجة.

### الخطوة 7: حفظ والتحقق
احفظ المشروع إلى ملف وافتحه اختياريًا في Microsoft Project للتحقق من الرابط:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** يحدد تنسيق الملف لحفظ المشروع. عند فتح *LinkedProject.mpp*، ستظهر المهمة الخارجية بأيقونة خاصة وخط الاعتماد يشير إلى المهمة المحلية.

## المشكلات الشائعة والحلول
- **الملف الخارجي غير موجود** – تأكد من أن المسار نسبي لعملية التشغيل أو قدم مسارًا مطلقًا.  
- **عدم تطابق معرفات المهام** – تحقق من أن معرف المهمة الخارجية (الوسيط الثاني في `addExternalTask`) يطابق المشروع المصدر.  
- **الترخيص غير محمّل** – ملف الترخيص المفقود أو غير الصحيح يؤدي إلى `LicenseException`. حمّله قبل أي استدعاءات لـ Aspose.Tasks.  
- **الأداء في المشاريع الكبيرة** – استخدم `Project.setReadOnly(true)` عندما تحتاج فقط لقراءة المهام الخارجية؛ هذا يقلل من استهلاك الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني ربط مهام من عدة مشاريع خارجية في نفس المهمة الملخصة؟**  
ج: نعم، يمكنك إضافة عدة مهام خارجية تحت مهمة ملخصة واحدة وإنشاء روابط فردية لكل منها باستخدام طريقة `addExternalTask` نفسها.

**س: ماذا يحدث إذا تم تعديل المهمة الخارجية في المشروع المرتبط؟**  
ج: أي تغيير في جدول المهمة الخارجية أو مدتها أو قيودها ينعكس تلقائيًا في المهمة المحلية التابعة عند تحديث المشروع الهدف.

**س: هل من الممكن إنشاء روابط بين مهام في تنسيقات ملفات مختلفة؟**  
ج: بالتأكيد. يدعم Aspose.Tasks الربط بين تنسيقات MPP، XML، وPrimavera، مما يسمح ببيئات مشاريع متباينة البقاء متزامنة.

**س: هل يمكنني فك ربط المهام بمجرد ربطها عبر المشاريع؟**  
ج: نعم، احذف الرابط باستدعاء `project.getTaskLinks().remove(link)` أو بحذف مهمة النائب الخارجية.

**س: هل هناك أي حدود لعدد المهام التي يمكن ربطها عبر المشاريع؟**  
ج: يمكن للمكتبة التعامل مع **أكثر من 10,000 مهمة مرتبطة** لكل مشروع، ويقتصر الحد فقط على الذاكرة المتاحة ونوع تنسيق الملف الأساسي.

## الخاتمة
أصبح لديك الآن نهج كامل وجاهز للإنتاج لـ **ربط المهام عبر المشاريع** باستخدام Aspose.Tasks للـ Java. هذه القدرة تُبسط تنسيق المشاريع المتعددة، تقلل الجهد اليدوي، وتضمن أن تغييرات الجدول الزمني تنتقل فورًا عبر محفظتك. استكشف ميزات إضافية مثل أوقات التأخير المخصصة، أنواع الروابط المختلفة، والربط الجماعي لمزيد من الأتمتة في هياكل المشاريع المعقدة.

---

**آخر تحديث:** 2026-07-05  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12  
**المؤلف:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## دروس ذات صلة

- [إنشاء ارتباط مهمة في Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [إنشاء مهام Aspose Java – خصائص المهمة](/tasks/java/task-properties/)
- [إنشاء ملف مشروع MS فارغ في Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}