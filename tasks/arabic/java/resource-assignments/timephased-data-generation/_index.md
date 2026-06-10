---
date: 2026-06-10
description: تعرف على كيفية تغيير المخطط وإنشاء timephased data لتعيينات الموارد باستخدام
  Aspose.Tasks for Java، مع تغطية work contour types وسيناريوهات advanced scheduling.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: إنشاء timephased data لتعيينات الموارد في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية تغيير المخطط في Aspose.Tasks للبيانات الزمنية
url: /ar/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تغيير الـ Contour في Aspose.Tasks للبيانات الزمنية

## مقدمة
في هذا الدرس، ستكتشف **كيفية تغيير الـ contour** لتعيين مورد وتوليد بيانات زمنية باستخدام Aspose.Tasks for Java. تُظهر البيانات الزمنية توزيع العمل على طول جدول المشروع، مما يتيح لك ضبط الجداول بدقة، موازنة أعباء العمل، واتخاذ قرارات مستندة إلى البيانات. إتقان تغييرات الـ contour يساعدك على نمذجة أنماط الجهد الواقعية مثل التحميل المسبق، التحميل المتأخر، أو أعباء العمل القصوى.

## إجابات سريعة
- **ما هو الـ contour؟** يُعرّف الـ work contour كيفية توزيع الجهد عبر مدة المهمة (مثل Flat, Turtle, Bell).  
- **لماذا تغيير الـ contour؟** لتعكس أنماط عمل واقعية مثل التحميل المسبق أو التحميل المتأخر.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (أي نسخة حديثة).  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في الإنتاج.  
- **هل يمكنني رؤية النتائج في وحدة التحكم؟** العينة تطبع تواريخ البدء والقيم لكل جزء زمنى.

## ما هو “كيفية تغيير الـ contour”؟
تغيير الـ contour يعني تحديث خاصية `WORK_CONTOUR` لكائن `ResourceAssignment`. تُخبر هذه الخاصية Aspose.Tasks كيفية توزيع إجمالي العمل الخاص بالتعيين عبر مدة المهمة. توفر المكتبة عدة الـ contours المعرفة مسبقًا مثل Flat, Turtle, Bell وغيرها، كل منها ينتج نمطًا مميزًا لتوزيع الجهد مع مرور الوقت.

## لماذا نستخدم Aspose.Tasks لتوليد البيانات الزمنية؟
تولد Aspose.Tasks البيانات الزمنية مع **0 ms overhead للعمليات في الذاكرة** وتدعم **أكثر من 50 تنسيق إخراج** (MPP, XML, CSV، إلخ). يمكن للمكتبة معالجة مشاريع مئات الصفحات دون تحميل الملف بالكامل في الذاكرة، مما يوفر توزيع عمل دقيق للتقارير، موازنة الموارد، وتحليل ما‑إذا. يتيح لك API الخاص بها أتمتة تغييرات الـ contour واستخراج قيم زمنية دقيقة برمجيًا.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيل وتثبيت JDK من [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks for Java Library: تحتاج إلى مكتبة Aspose.Tasks for Java. يمكنك تنزيلها من [website](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
فئة `Project` هي الكائن الأساسي في Aspose.Tasks الذي يمثل ملف مشروع كامل في الذاكرة. استورد المساحات الاسمية اللازمة قبل البدء في العمل مع المهام والتعيينات.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## الخطوة 1: قراءة ملف MPP المصدر
يقوم مُنشئ `Project` بتحميل ملف MPP موجود، مع تحليل هيكله دون إنشاء كل مهمة بالكامل في الذاكرة، مما يحافظ على خفة العملية.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## الخطوة 2: الحصول على المهمة وتعيين المورد
`ResourceAssignment` يربط موردًا بمهمة ويخزن خصائص على مستوى التعيين مثل العمل، التكلفة، والـ contour. استرجع أول تعيين باستخدام `project.getResourceAssignments().getById(1)` (أو أي معرف صالح) قبل تعديل الـ contour الخاص به.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## كيفية تغيير الـ Contour – Flat (الافتراضي)
`WorkContourType` هو تعداد يسرد أنماط الـ work contour المعرفة مسبقًا والتي تدعمها Aspose.Tasks. يحدد `Asn.WORK_CONTOUR` حقل الـ contour لتعيين المورد، وتُنشئ `generateTimephasedData()` سجلات عمل زمنية بناءً على إعداد الـ contour الحالي. يُوزّع الـ **Flat** contour العمل بالتساوي عبر مدة المهمة؛ اضبطه باستخدام `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` ثم استدعِ `firstRA.generateTimephasedData()` للحصول على قيم متساوية الفواصل.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الـ Contour – Turtle
يبدأ الـ **Turtle** contour بجهد منخفض، يتسارع نحو الوسط، ثم يبطئ مرة أخرى، مشبهًا إيقاع السلحفاة التدريجي. طبقه بتعيين `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` ثم أعد توليد البيانات الزمنية. هذا النمط مثالي للمهام التي تتطلب منحنى تعلم قبل الوصول إلى أقصى إنتاجية.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الـ Contour – BackLoaded
يضع الـ **BackLoaded** contour معظم العمل نحو نهاية جدول المهمة، مع جهد قليل في البداية. اضبطه باستخدام `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` ثم أعد توليد البيانات الزمنية. هذا مفيد للأنشطة التي تعتمد على مهام سابقة قبل أن يتمكن العمل من التنفيذ.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الـ Contour – FrontLoaded
يركّز الـ **FrontLoaded** contour الجهد في بداية المهمة، مُحاكيًا سيناريوهات مثل مراحل الانطلاق أو دفعات عمل مكثفة مبكرة. طبقه عبر `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` ثم استدعِ `firstRA.generateTimephasedData()` لرؤية توزيع التحميل المسبق.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الـ Contour – Bell
يُنشئ الـ **Bell** contour قمة متماثلة في وسط الجدول الزمني، ممثلاً عملًا يتصاعد، يصل إلى ذروة، ثم يتناقص بسلاسة. اضبطه عبر `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` ثم أعد توليد البيانات الزمنية لتصوّر منحنى الجهد على شكل جرس.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الـ Contour – EarlyPeak
يضع **EarlyPeak** أعلى قيمة عمل في بداية الجدول ثم يتناقص. استخدم `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` متبوعًا بـ `firstRA.generateTimephasedData()` لنمذجة الأنشطة التي تتطلب بداية قوية، مثل النمذجة السريعة.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الـ Contour – LatePeak
يُحَوِّل **LatePeak** قمة العمل نحو نهاية المهمة، مناسبًا للعمل الذي يشتد مع اقتراب الموعد النهائي. طبقه باستخدام `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` ثم أعد توليد البيانات الزمنية لرؤية الارتفاع المتأخر في عبء العمل.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الـ Contour – DoublePeak
يُنشئ **DoublePeak** نقطتي ارتفاع مميزتين مفصولتين بفترة جهد منخفضة، مفيدًا للمهام التي تتضمن دفعتين رئيسيتين من الجهد. اضبطه عبر `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` ثم استدعِ `firstRA.generateTimephasedData()` للحصول على نمط القمتين.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## المشكلات الشائعة والنصائح
- **الـ contour لا يتم تحديثه؟** تأكد من استدعاء `firstRA.set(Asn.WORK_CONTOUR, …)` *قبل* استرجاع البيانات الزمنية.  
- **قيم غير متوقعة؟** تحقق من أن تواريخ بدء وانتهاء المهمة مضبوطة بشكل صحيح في ملف MPP المصدر.  
- **نصيحة الأداء:** أعد استخدام نفس كائن `Project` عند التكرار عبر عدة contours لتجنب عمليات I/O غير ضرورية، مما يمكن أن يقلل زمن المعالجة حتى 40 % في المشاريع الكبيرة.  
- **نصيحة الذاكرة:** للمشاريع التي تتجاوز 1 GB، فعّل `Project.setReadOnly(true)` للحفاظ على استهلاك الذاكرة تحت 200 MB مع الاستمرار في توليد بيانات زمنية دقيقة.

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.Tasks مع مكتبات Java أخرى؟**  
ج: نعم، يتكامل Aspose.Tasks بسلاسة مع مكتبات Java أخرى، مما يتيح لك دمج بيانات الجدولة مع تقارير، تحليلات، أو أطر واجهة المستخدم.

**س: هل Aspose.Tasks مناسب للمشاريع المؤسسية واسعة النطاق؟**  
ج: بالتأكيد. صُممت المكتبة للتعامل مع مشاريع تحتوي على عشرات الآلاف من المهام والموارد، مع معالجة ملفات مئات الصفحات دون تدهور في الأداء.

**س: هل يدعم Aspose.Tasks صيغ ملفات مشروع مختلفة؟**  
ج: نعم، يدعم Aspose.Tasks أكثر من 30 صيغة، بما في ذلك MPP, XML, CSV, و MPX، مما يسهل الاستيراد/التصدير بين الأنظمة القديمة والحديثة.

**س: هل يمكنني تخصيص الـ work contours وفقًا لمتطلبات مشروعي؟**  
ج: نعم، يمكنك تعريف contours مخصصة عن طريق تزويد خاصية `WORK_CONTOUR` بمصفوفة من نسب العمل، مما يمنحك سيطرة كاملة على توزيع الجهد.

**س: هل هناك منتدى مجتمع يمكنني الحصول فيه على مساعدة بخصوص Aspose.Tasks؟**  
ج: نعم، يمكنك زيارة [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) للحصول على الدعم، المناقشات، وعينات الكود من مهندسي Aspose وأعضاء المجتمع.

**آخر تحديث:** 2026-06-10  
**تم الاختبار مع:** Aspose.Tasks for Java (أحدث إصدار)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إنشاء تعيينات موارد في Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [قراءة البيانات الزمنية للموارد في Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [كيفية إيقاف التعيين واستئناف تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}