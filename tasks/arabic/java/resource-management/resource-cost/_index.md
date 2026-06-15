---
date: 2026-06-15
description: تعلم كيفية إدارة التكاليف في ملفات MS Project باستخدام Aspose.Tasks for
  Java، بما في ذلك كيفية تحميل ملف MPP وقراءة تكلفة العمل الفعلية وجدول تكلفة الميزانية.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: معالجة تكلفة الموارد في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية إدارة التكاليف في MS Project باستخدام Aspose.Tasks for Java
url: /ar/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إدارة التكاليف في MS Project باستخدام Aspose.Tasks للغة Java

## مقدمة

إدارة ميزانيات المشاريع هي مسؤولية أساسية لأي مدير مشروع، و **كيفية إدارة التكاليف** بفعالية يمكن أن تكون الفارق بين نجاح المشروع أو فشله. توفر لك Aspose.Tasks للغة Java تحكمًا برمجيًا في ملفات Microsoft Project، مما يتيح لك قراءة وتحديث بيانات تكلفة الموارد دون الحاجة إلى فتح ملف .mpp يدويًا. في هذا البرنامج التعليمي ستتعرف خطوة بخطوة على كيفية تحميل ملف MPP، فحص تكلفة العمل الفعلية، واستخراج جدول تكلفة الميزانية لكل مورد.

## إجابات سريعة
- **ما الذي تفعله Aspose.Tasks للغة Java؟** تقرأ وتكتب ملفات Microsoft Project (.mpp) دون الحاجة إلى تثبيت Microsoft Project.  
- **كيف يمكنني تحميل ملف MPP؟** استخدم `new Project("path/to/file.mpp")` – تقوم الواجهة البرمجية بتحليل الملف في الذاكرة.  
- **ما هي حقول التكلفة المتاحة؟** Actual Cost Work (ACWP)، Budgeted Cost of Work Scheduled (BCWS)، و Budgeted Cost of Work Performed (BCWP).  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت مجاني يعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما إصدارات Java المدعومة؟** Java 8 وما بعده، بما في ذلك Java 17 LTS.

## كيفية إدارة التكاليف في MS Project؟

حمّل مشروعك باستخدام `new Project("yourFile.mpp")`، ثم تكرّر عبر كل كائن `Resource` لقراءة الخصائص المتعلقة بالتكلفة مثل ACWP و BCWS و BCWP. تقوم Aspose.Tasks تلقائيًا بتحويل القيم الداخلية للتكلفة إلى عملة المشروع، بحيث يمكنك عرضها أو تخزينها مباشرة. يزيل هذا النهج الحاجة إلى حسابات الجداول اليدوية ويضمن اتساق البيانات عبر جميع تقارير المشروع.

## المتطلبات المسبقة

1. فهم أساسي لبرمجة Java.  
2. إضافة مكتبة Aspose.Tasks للغة Java إلى مشروعك (Maven/Gradle أو JAR يدوي).  
3. الوصول إلى ملف Microsoft Project (`.mpp`) الذي تريد تحليله.  

## استيراد الحزم

فئات `Project` و `Resource` هي نقاط الدخول للعمل مع بيانات المشروع.

فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project واحد في الذاكرة.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## الخطوة 1: تحديد دليل البيانات

أولاً، حدد المجلد الذي يحتوي على ملف `.mpp` الخاص بك. يمكن أن يكون هذا المسار مطلقًا أو نسبيًا إلى دليل العمل لتطبيقك.

```text
```java
String dataDir = "Your Data Directory";
```
```

## الخطوة 2: تحميل ملف MS Project

`Project` يقوم بتحميل الملف ويبني نموذج كائن يمكنك الاستعلام عنه. تقوم الواجهة البرمجية بتحليل الملف دون الحاجة إلى تثبيت Microsoft Project، وتدعم أكثر من 30 تنسيق إدخال.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## الخطوة 3: التكرار عبر الموارد

كائنات `Resource` تمثل الأشخاص أو المعدات أو المواد التي تستهلك الميزانية. يمكنك التكرار عبر مجموعة `project.getResources()` للوصول إلى كل منها.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## الخطوة 4: التحقق من اسم المورد والتكاليف

لكل مورد، تحقق من أن الاسم معرف، ثم اقرأ حقول التكلفة. تُعيد طريقة `getActualCost()` **تكلفة العمل الفعلية** (ACWP)، بينما تُعطيك `getBudgetedCost()` **جدول تكلفة الميزانية** (BCWS/BCWP).

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## لماذا تستخدم Aspose.Tasks للغة Java لتحميل ملف MPP؟

تدعم Aspose.Tasks **أكثر من 30 تنسيق ملف** (بما في ذلك `.mpp` و `.xml` و `.xlsx`) ويمكنها معالجة مشاريع تحتوي على **حتى 10,000 مهمة** مع استهلاك أقل من 200 ميغابايت من الذاكرة RAM. تقوم المكتبة بإجراء جميع الحسابات على جانب الخادم، مما يلغي الحاجة إلى نسخة مرخصة من Microsoft Project.

## المشكلات الشائعة والحلول

- **أسماء موارد فارغة:** بعض الملفات القديمة تحتوي على موارد placeholder. تحقق دائمًا من `resource.getName() != null` قبل الوصول إلى خصائص التكلفة.  
- **ملفات كبيرة تسبب ضغطًا على الذاكرة:** LoadOptions هي فئة تكوين تسمح لك بتحديد بيانات المشروع التي تريد تحميلها. استخدم `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` لتحميل البيانات التي تحتاجها فقط، ثم فعّلها لاحقًا إذا لزم الأمر.  
- **اختلافات العملة:** تحترم الواجهة البرمجية إعدادات عملة المشروع؛ يمكنك تجاوزها باستخدام `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` إذا لزم الأمر. يعدد CostRateTableType جداول أسعار التكلفة المختلفة التي يمكن تطبيقها على مهمة.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks للغة Java التعامل مع هياكل مشاريع معقدة؟**  
نعم، تدعم بالكامل المهام الملخصة المتداخلة، جداول موارد متعددة، والحقول المخصصة عبر جميع إصدارات Project المدعومة.

**س: هل المكتبة متوافقة مع إصدارات مختلفة من ملفات Microsoft Project؟**  
بالتأكيد. تقوم Aspose.Tasks بقراءة وكتابة الملفات من Microsoft Project 2000 حتى أحدث تنسيق لعام 2023.

**س: هل يمكنني دمج Aspose.Tasks للغة Java مع مكتبات Java أخرى؟**  
نعم، تُعيد الواجهة البرمجية كائنات Java قياسية، مما يتيح دمجًا سلسًا مع أطر التسجيل، أدوات ORM، أو مكتبات التقارير.

**س: هل تقدم Aspose.Tasks للغة Java دعمًا للعملاء؟**  
توفر Aspose دعمًا مخصصًا عبر المنتديات، وثائق مفصلة، ومساعدة عبر البريد الإلكتروني للمستخدمين المرخصين.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks للغة Java؟**  
يمكنك تنزيل ترخيص تقييم لمدة 30 يومًا من موقع Aspose لاستكشاف جميع الميزات دون تكلفة.

---

**آخر تحديث:** 2026-06-15  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية حساب فرق التكلفة وإدارة تكاليف التعيين باستخدام Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [إدارة الميزانية والعمل والتكلفة للمهام في Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [إضافة مورد إلى المشروع باستخدام Aspose.Tasks للغة Java](/tasks/java/resource-management/create-resources/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}