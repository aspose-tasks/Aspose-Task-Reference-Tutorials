---
date: 2026-07-05
description: تعلم كيفية إنشاء تبعيات مهام إدارة المشروع في Java باستخدام Aspose.Tasks.
  اتبع هذا الدليل خطوة بخطوة مع code snippets.
keywords:
- project management task dependencies
- Aspose.Tasks Java
- task linking tutorial
linktitle: إنشاء تبعيات مهام إدارة المشروع في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  headline: Create Project Management Task Dependencies in Aspose.Tasks
  type: TechArticle
- description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  name: Create Project Management Task Dependencies in Aspose.Tasks
  steps:
  - name: Set Document Directory
    text: Define the directory where your documents are stored to ensure Aspose.Tasks
      locates and processes files correctly. The `java.nio.file.Paths` utility helps
      you build platform‑independent file paths. java // The path to the documents
      directory. String dataDir = "Your Document Directory";
  - name: Initialize Project and Tasks
    text: Create a new project and initialize tasks within it. In this example, "Task
      1" and "Task 2" are added to the root task. The `Task` class represents an individual
      work item; each task can have its own ID, name, and schedule. java Project project
      = new Project(dataDir + "project5.mpp"); Task pred = pr
  - name: Establish Task Link
    text: Utilize the `getTaskLinks()` method to add a link between two tasks. This
      example demonstrates linking "Task 1" as a predecessor to "Task 2." The `TaskLink`
      object defines the type of dependency (Finish‑to‑Start, Start‑to‑Start, etc.)
      and optional lag. java TaskLink link = project.getTaskLinks().add
  - name: Display Result
    text: Print a message indicating the successful completion of the task link creation
      process. This step is crucial for debugging and verification. A simple `System.out.println`
      call confirms that the link was added without errors. java // Display the result
      of the conversion. System.out.println("Task Link
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks seamlessly integrates with Spring, Jakarta EE, Android,
      and any standard Java environment.
    question: Can I use Aspose.Tasks for Java with other Java frameworks?
  - answer: Yes, explore the functionalities with the [free trial](https://releases.aspose.com/)
      before making a commitment.
    question: Is there a free trial available before purchasing the library?
  - answer: Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: Yes, check the documentation for comprehensive sample projects and code
      snippets.
    question: Are there any sample projects available for reference?
  - answer: Secure your copy by visiting the [purchase page](https://purchase.aspose.com/buy)
      and explore licensing options.
    question: What is the recommended way to purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: إنشاء تبعيات مهام إدارة المشروع في Aspose.Tasks
url: /ar/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تبعيات مهام إدارة المشروع في Aspose.Tasks

## المقدمة
تُعد تبعيات مهام إدارة المشروع العمود الفقري لأي جدول منظم جيدًا، حيث تتيح حسابًا تلقائيًا لتواريخ البدء والانتهاء والمسارات الحرجة. في هذا البرنامج التعليمي ستتعلم كيفية إنشاء **project management task dependencies** في Java باستخدام Aspose.Tasks، وهي مكتبة تدعم أكثر من 50 تنسيق ملف ويمكنها التعامل مع مشاريع تحتوي على آلاف المهام دون تحميل الملف بالكامل في الذاكرة. اتبع الخطوات أدناه لربط المهام، والتحقق من الروابط، وتكامل الحل في تطبيقات العالم الحقيقي.

## إجابات سريعة
- **ماذا يغطي البرنامج التعليمي؟** إنشاء روابط المهام (التبعيات) باستخدام Aspose.Tasks للغة Java.  
- **كم عدد أسطر الشيفرة المطلوبة؟** منطق الربط الأساسي يكتفي بعبارتين فقط.  
- **هل أحتاج إلى ترخيص لتجربته؟** نسخة تجريبية مجانية لمدة 30 يومًا متاحة؛ الترخيص مطلوب للإنتاج.  
- **ما إصدارات Java المدعومة؟** Java 8 إلى 17 مدعومة بالكامل.  
- **هل يمكنني ربط أكثر من مهمتين؟** نعم – كرّر نمط الربط لأي عدد من أزواج السلف‑الخلف.

## ما هي تبعيات مهام إدارة المشروع؟
تحدد تبعيات مهام إدارة المشروع كيف يرتبط بدء أو انتهاء مهمة بأخرى، مما يفرض ترتيب تنفيذ الأعمال. تمثل Aspose.Tasks هذه العلاقات عبر كائنات `TaskLink`، التي يمكنك إنشاؤها أو تعديلها أو حذفها برمجيًا.

## لماذا تستخدم Aspose.Tasks لربط المهام؟
تدعم Aspose.Tasks **50+ input and output formats** (بما في ذلك MPP وXML وCSV) ويمكنها معالجة مشاريع تحتوي على **10,000+ tasks** مع استهلاك أقل من 200 ميغابايت من الذاكرة على خادم عادي. يمنحك API تحكمًا دقيقًا في أنواع الروابط، وفترات التأخير، ومعالجة القيود دون الحاجة إلى تثبيت Microsoft Project.

## المتطلبات المسبقة
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:
- بيئة تطوير Java: قم بإعداد بيئة تطوير Java وظيفية على جهازك.  
- مكتبة Aspose.Tasks: قم بتنزيل وتكامل مكتبة Aspose.Tasks للغة Java، المتاحة [هنا](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
لبدء العمل، استورد الحزم الضرورية إلى مشروع Java الخاص بك. هذا أمر حاسم للوصول إلى وظائف Aspose.Tasks.

فئة `Project` هي نقطة الدخول في Aspose.Tasks التي تمثل ملف مشروع كامل في الذاكرة.  
```text
```java
import com.aspose.tasks.*;
```
```

## كيفية إنشاء روابط المهام باستخدام Aspose.Tasks للغة Java؟
حمّل أو أنشئ مثيل `Project`، أضف المهام المطلوبة، ثم استدعِ `getTaskLinks().add()` لإنشاء تبعية. هذه الطريقة تنشئ كائن `TaskLink` يربط المهمة السلفية بالمهمة الخلفية، مع إمكانية تحديد نوع الرابط والفترة الزمنية الاختيارية. الخطوات التالية توضح الشيفرة الدقيقة التي تحتاجها—بدون أي كود إضافي غير ضروري.

### الخطوة 1: تعيين دليل المستندات
حدد الدليل الذي تُخزن فيه مستنداتك لضمان أن Aspose.Tasks يجد الملفات ويعالجها بشكل صحيح.

تساعد أداة `java.nio.file.Paths` في بناء مسارات ملفات مستقلة عن النظام.  
```text
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
```

### الخطوة 2: تهيئة المشروع والمهام
أنشئ مشروعًا جديدًا وتهيئ المهام داخله. في هذا المثال، يتم إضافة "Task 1" و"Task 2" إلى المهمة الجذرية.

فئة `Task` تمثل عنصر عمل فردي؛ كل مهمة يمكن أن يكون لها معرفها، اسمها، وجدولها الزمني.  
```text
```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```
```

### الخطوة 3: إنشاء رابط المهمة
استخدم طريقة `getTaskLinks()` لإضافة رابط بين مهمتين. يوضح هذا المثال ربط "Task 1" كمهمة سلفية لـ "Task 2".

كائن `TaskLink` يحدد نوع التبعية (Finish‑to‑Start، Start‑to‑Start، إلخ) وفترة التأخير الاختيارية.  
```text
```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```
```

### الخطوة 4: عرض النتيجة
اطبع رسالة تشير إلى إكمال عملية إنشاء رابط المهمة بنجاح. هذه الخطوة حاسمة للتصحيح والتحقق.

استدعاء `System.out.println` بسيط يؤكد أن الرابط أُضيف دون أخطاء.  
```text
```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```
```

كرر هذه الخطوات لسيناريوهات ربط مهام أكثر تعقيدًا، خصّص أسماء المهام، وأنشئ التبعيات وفقًا لمتطلبات مشروعك.

ارجع إلى [توثيق Aspose.Tasks](https://reference.aspose.com/tasks/java/) للحصول على معلومات مفصلة عن API.  
لدعم المجتمع، زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## المشكلات الشائعة والحلول
طريقة `save` تكتب المشروع إلى مسار الملف المحدد، مع حفظ جميع التغييرات بما في ذلك الروابط المضافة.  
تُعرّف تعداد `TaskLinkType` نوع العلاقة، مثل `FinishToStart` لتبعية الانتهاء‑لبداية.

- **الرابط غير ظاهر في الملف المحفوظ** – تأكد من استدعاء `project.save(outputPath)` بعد إضافة الروابط.  
- **نوع الرابط غير صحيح** – استخدم `TaskLinkType.FinishToStart`، `StartToStart`، إلخ، لتطابق منطق الجدولة الخاص بك.  
- **المشاريع الكبيرة تسبب ارتفاعًا في استهلاك الذاكرة** – فعّل `project.setReadOnly(true)` قبل التحميل للعمل في وضع البث.

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.Tasks للغة Java مع أطر عمل Java أخرى؟**  
ج: نعم، تتكامل Aspose.Tasks بسلاسة مع Spring وJakarta EE وAndroid وأي بيئة Java قياسية.

**س: هل هناك نسخة تجريبية مجانية متاحة قبل شراء المكتبة؟**  
ج: نعم، استكشف الوظائف من خلال [الإصدار التجريبي المجاني](https://releases.aspose.com/) قبل اتخاذ القرار.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks للغة Java؟**  
ج: احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.

**س: هل هناك مشاريع نموذجية متاحة للرجوع إليها؟**  
ج: نعم، راجع الوثائق للحصول على مشاريع نموذجية شاملة ومقاطع شيفرة.

**س: ما هي الطريقة الموصى بها لشراء Aspose.Tasks للغة Java؟**  
ج: احصل على نسختك بزيارة [صفحة الشراء](https://purchase.aspose.com/buy) واستكشف خيارات الترخيص.

**آخر تحديث:** 2026-07-05  
**تم الاختبار باستخدام:** Aspose.Tasks 24.12 للغة Java  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [إنشاء مهام Aspose Java – خصائص المهمة](/tasks/java/task-properties/)
- [الخط الأساسي لإدارة المشروع – جدولة المهام باستخدام Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)
- [كيفية إنشاء الموارد – إدارة الموارد مع Aspose.Tasks للغة Java](/tasks/java/resource-management/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}