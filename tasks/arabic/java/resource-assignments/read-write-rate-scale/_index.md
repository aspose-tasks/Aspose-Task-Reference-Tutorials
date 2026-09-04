---
date: 2026-06-10
description: تعلم كيفية قراءة rate وكيفية كتابة rate scale لتعيينات الموارد باستخدام
  Aspose.Tasks for Java. يدعم material resources، multiple formats، و large projects.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: قراءة وكتابة Rate Scale لتعيينات الموارد في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية قراءة Rate Scale وكتابة Rate Scale لتعيينات الموارد في Aspose.Tasks
url: /ar/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة مقياس المعدل وكتابة مقياس المعدل لتعيينات الموارد في Aspose.Tasks

في هذا البرنامج التعليمي ستكتشف **كيفية قراءة المعدل** وضبطه لتعيينات الموارد باستخدام Aspose.Tasks للـ Java. سواء كنت تبني أداة جدولة، أو أداة تقارير، أو تحتاج ببساطة إلى أتمتة تحديثات المشروع، فإن إتقان تعديل مقياس المعدل يمنحك تحكمًا دقيقًا في الموارد المادية والعملية.

## إجابات سريعة
`ResourceAssignment` يربط مهمة بموارد ويحفظ بيانات خاصة بالتعيين.  
`Asn` يحتوي على ثوابت لحقول التعيين، بما في ذلك `RATE_SCALE`.  
`RateScaleType` تعداد يسرد الوحدات الزمنية الممكنة لتدرج المعدل.  

- **ما هو الصنف الأساسي لمعالجة المعدل؟** `ResourceAssignment` مع الخاصية `Asn.RATE_SCALE`.  
- **أي تعداد يحدد خيارات المقياس؟** `RateScaleType` (Day, Week, Month, إلخ).  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** ترخيص تجريبي مجاني يعمل للاختبار؛ ترخيص تجاري مطلوب للإنتاج.  
- **هل يمكنني تغيير المقياس بعد الحفظ؟** نعم – أعد تحميل المشروع وعدل `Asn.RATE_SCALE` كما هو موضح.  
- **بيئات التطوير المتكاملة المدعومة؟** أي IDE للـ Java (IntelliJ IDEA، Eclipse، NetBeans) يمكنه تجميع الكود.

## كيفية قراءة مقياس المعدل لتعيينات الموارد؟

حمّل المشروع، حدد `ResourceAssignment` المطلوب، واستدعِ `getRateScale()` – هذا يُعيد قيمة من نوع `RateScaleType` تُخبرك ما إذا كان المعدل يُطبق يوميًا، أسبوعيًا، شهريًا، أو بوحدة أخرى. الإجابة فورية وتتطلب فقط استدعاءين لـ API، مما يجعلها مثالية لسكربتات التدقيق أو عروض واجهة المستخدم.

## كيفية كتابة مقياس المعدل لتعيينات الموارد؟

أنشئ أو استرجع كائن `ResourceAssignment`، عيّن خاصية `Asn.RATE_SCALE` إلى `RateScaleType` المطلوب (مثال: `RateScaleType.Week`)، ثم احفظ المشروع. هذا التغيير في الخاصية الواحدة يُحدّث حسابات التكلفة تلقائيًا ويستمر عبر جميع صيغ الملفات المدعومة. بعد ضبط المقياس، قد تحتاج أيضًا إلى تعديل معدل المورد القياسي أو معدل العمل الإضافي ليتماشى مع وحدة الوقت الجديدة، لضمان دقة حسابات التكلفة.

## ما هو مقياس المعدل؟

مقياس المعدل يحدد وحدة الوقت (يوم، أسبوع، شهر، إلخ) التي يُطبق عليها معدل تكلفة المورد. تعديل المقياس يتيح لك نمذجة استهلاك المواد أو جهد العمل بدقة. على سبيل المثال، ضبط المقياس على أسبوع يعني أن معدل التكلفة يُفسّر كتكلفة لكل أسبوع، ويتم حساب التكلفة الإجمالية للمهمة بناءً على عدد الأسابيع التي يُعين فيها المورد.

## لماذا قراءة وكتابة مقياس المعدل؟

قراءة المقياس الحالي تساعدك على تدقيق الجداول الزمنية القائمة، بينما كتابة مقياس جديد يتيح لك مواءمة الموارد مع سياسات الفوترة أو الاستهلاك في المشروع. هذا مفيد بشكل خاص عند **تحديد تكاليف الموارد المادية** أو عندما تحتاج إلى **ضبط المقياس** لتقويمات العمل غير القياسية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك المتطلبات التالية:
1. **بيئة تطوير Java** – JDK 8 أو أعلى مثبتة.  
2. **مكتبة Aspose.Tasks للـ Java** – قم بتنزيل وتثبيت المكتبة من [هنا](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
الصنف `ResourceAssignment` يمثل رابطًا بين مهمة وموارد، بينما `RateScaleType` تعداد يحدد الوحدات الزمنية الممكنة للمعدل. استورد الفئات اللازمة من Aspose.Tasks قبل بدء الترميز.  

`Project` هو الكائن الرئيسي الذي يحمل ويحفظ ملفات Microsoft Project.  
`Resource` يعرّف مورد المشروع مثل العمل أو المادة.  
`ResourceType` تعداد يحدد ما إذا كان المورد عملًا أم مادة.  
`Task` يمثل عنصر عمل في جدول المشروع.  
`SaveFileFormat` تعداد يحدد صيغة الإخراج لحفظ المشروع.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## الخطوة 1: إعداد مشروع Java الخاص بك
أنشئ مشروع Maven أو Gradle وأضف ملف Aspose.Tasks JAR إلى مسار الفئات الخاص بك. هذه الخطوة تضمن أن المترجم يستطيع العثور على الفئات المستوردة.

## الخطوة 2: تحميل ملف المشروع
حمّل ملف Microsoft Project الموجود الذي تريد العمل معه.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## الخطوة 3: إضافة مهمة
أنشئ مهمة جديدة ستستقبل لاحقًا تعيينات الموارد.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## الخطوة 4: تعريف الموارد
هنا نـ**نعرّف موردًا ماديًا** ومورد عمل عادي. لاحظ استخدام `ResourceType.Material` للمورد من النوع المادي.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## الخطوة 5: تعيين الموارد للمهمة
الآن نـ**نُعيّن الموارد للمهمة** ونحدد **كيفية ضبط المقياس** باستخدام `RateScaleType.Week`. هذا يوضح كلًا من قراءة وكتابة مقياس المعدل.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## الخطوة 6: حفظ المشروع
احفظ التغييرات في ملف جديد حتى نتمكن لاحقًا من التحقق من مقياس المعدل المخزن.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## الخطوة 7: استرجاع تعيينات الموارد
أعد تحميل المشروع المحفوظ و**اقرأ مقياس المعدل** للتأكد من أنه تم كتابته بشكل صحيح.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## الأخطاء الشائعة والنصائح
- **عدم تطابق UID** – عند استرجاع التعيينات بواسطة UID، تأكد من أن قيم UID تتطابق مع تلك التي تم تعيينها أثناء الإنشاء.  
- **نوع المورد غير الصحيح** – استخدام `ResourceType.Material` لمورد عمل سيتسبب في سلوك غير متوقع لحسابات المعدل.  
- **صيغة الحفظ** – احفظ دائمًا باستخدام `SaveFileFormat.Mpp` (أو صيغة مدعومة أخرى) للحفاظ على الحقول المخصصة مثل مقياس المعدل.  
- **المشاريع الكبيرة** – يمكن لـ Aspose.Tasks معالجة ملفات تحتوي على **500+ صفحة** دون تحميل المستند بالكامل في الذاكرة، بفضل بنية البث.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks للـ Java مع أي بيئة تطوير Java؟**  
نعم، Aspose.Tasks للـ Java متوافق مع جميع بيئات التطوير الرئيسية للـ Java، بما في ذلك IntelliJ IDEA، Eclipse، و NetBeans.

**س: هل يدعم Aspose.Tasks صيغ ملفات أخرى غير MPP؟**  
نعم، Aspose.Tasks يدعم صيغ ملفات متعددة، بما في ذلك MPP، XML، و HTML.

**س: هل Aspose.Tasks مناسب لإدارة المشاريع على مستوى المؤسسات؟**  
بالطبع، Aspose.Tasks يقدم ميزات شاملة لإدارة المشاريع من أي حجم، مما يجعله مناسبًا لإدارة المشاريع على مستوى المؤسسات.

**س: هل يمكنني تخصيص تعيينات الموارد أكثر من مجرد مقياس المعدل؟**  
نعم، Aspose.Tasks يوفر إمكانيات واسعة لتخصيص تعيينات الموارد، بما في ذلك تعديل التكلفة، العمل، والمدة.

**س: هل هناك منتدى مجتمع لدعم Aspose.Tasks؟**  
نعم، يمكنك العثور على الدعم والتفاعل مع المستخدمين الآخرين في منتدى Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2026-06-10  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [كيفية تعديل التعيينات – قراءة الموارد المشتركة مع Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [كيفية إضافة ملاحظات إلى تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}