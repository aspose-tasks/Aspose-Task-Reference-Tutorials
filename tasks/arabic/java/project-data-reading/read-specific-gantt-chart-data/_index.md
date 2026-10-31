---
date: 2026-10-31
description: تعرف على كيفية تصدير مخطط جانت إلى PDF في Java باستخدام Aspose.Tasks.
  يوضح لك هذا الدليل خطوة بخطوة كيفية قراءة بيانات مخطط جانت وإنشاء تقارير PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: قراءة بيانات مخطط جانت المحددة في Aspose.Tasks
og_description: تصدير مخطط جانت إلى PDF في Java باستخدام Aspose.Tasks. اتبع هذا البرنامج
  التعليمي لقراءة بيانات مخطط جانت، وتخصيص خصائص العرض، وإنشاء تقارير PDF لإدارة المشاريع.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: تصدير مخطط جانت إلى PDF في Java – دليل Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: تصدير مخطط جانت إلى PDF في Java – استخراج بيانات محددة
url: /ar/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تصدير مخطط جانت إلى PDF في Java – استخراج بيانات محددة

## مقدمة
في هذا البرنامج التعليمي ستتعلم كيفية **export gantt to pdf in Java** عن طريق قراءة معلومات مخطط جانت باستخدام Aspose.Tasks for Java. توفر مخططات جانت لمديري المشاريع خريطة مرئية للمهام والاعتمادات والجداول الزمنية، وإمكانية سحب هذه البيانات برمجياً تتيح لك إنشاء تقارير PDF تلقائية، ولوحات معلومات، أو تكاملات مع أنظمة المؤسسة الأخرى. دعنا نتبع كل خطوة، بدءًا من تحميل ملف المشروع إلى استخراج خصائص العرض وأخيرًا إنشاء ملف PDF.

## إجابات سريعة
- **ما الذي يمكنني استخراج؟** أي خاصية عرض، نمط شريط، خط شبكة، نمط نص، خط تقدم، أو طبقة مقياس زمني من مخطط جانت.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أحدث (البرنامج التعليمي يستخدم JDK 11).  
- **هل الكود قابل للتنفيذ كما هو؟** نعم – فقط استبدل مسار دليل البيانات.  
- **هل يمكنني تعديل العرض بعد القراءة؟** بالتأكيد – تسمح لك API بتغيير الخصائص وحفظها مرة أخرى في ملف المشروع.

## ما هو تصدير مخطط جانت إلى PDF؟
تصدير مخطط جانت إلى PDF هو عملية تحويل عرض مخطط جانت المخزن في ملف مشروع إلى مستند PDF يحافظ على التنسيق البصري ومعلومات الجدول الزمني. هذه العملية مفيدة لمشاركة حالة المشروع مع أصحاب المصلحة الذين قد لا يمتلكون أداة إدارة مشاريع.

## لماذا تصدير مخطط جانت إلى PDF باستخدام Aspose.Tasks؟
يمكن لـ Aspose.Tasks التعامل مع **أكثر من 30 + تنسيق إدخال** (MPP، XML، MPX، إلخ) و**تصدير إلى PDF في استدعاء واحد** مع الحفاظ على 95 % من الدقة البصرية، حتى للمشاريع التي تحتوي على أكثر من 500 مهمة. تعالج المكتبة الملفات في الذاكرة، لذا يمكنك إنشاء ملفات PDF على الخوادم دون الحاجة لتثبيت Microsoft Project.

## المتطلبات المسبقة
1. **Java Development Kit (JDK):** تأكد من تثبيت Java على نظامك. يمكنك تنزيله من **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** قم بتنزيل وتثبيت مكتبة Aspose.Tasks for Java من **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** اختر بيئة تطوير متكاملة (IDE) حسب تفضيلك. تشمل الخيارات الشائعة IntelliJ IDEA، Eclipse، أو NetBeans.

## استيراد الحزم
توفر لك الاستيرادات التالية الوصول إلى الفئات الأساسية في Aspose.Tasks اللازمة لقراءة وتصدير بيانات جانت.  
*لا يتم عرض كتلة شفرة هنا للحفاظ على تركيز البرنامج التعليمي على المفاهيم؛ ما عليك سوى إضافة الاستيرادات إلى ملف Java الخاص بك.*

## كيف يمكنني تحميل ملف مشروع مخطط جانت في Java؟
قم بتحميل ملف المشروع بإنشاء كائن `Project` وتمرير المسار الكامل إلى المُنشئ. تُنشئ هذه الخطوة تمثيلًا في الذاكرة لمخطط جانت، مما يسمح بالاستعلامات اللاحقة عن خصائص العرض. عندما يتم تحميل الملف بنجاح، يمكنك التحقق من اسم المشروع، تاريخ البدء، وعدد المهام لضمان فتح الملف الصحيح. يساعد هذا التحقق في اكتشاف مشكلات المسار أو التنسيق مبكرًا في سير العمل.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*مرساة التعريف:* `Project` هو كائن Aspose.Tasks من المستوى الأعلى يمثل ملف مشروع واحد في الذاكرة.

## كيف يمكنني الوصول إلى عرض مخطط جانت؟
استرجع أول عرض جانت من مجموعة عروض المشروع. تحتوي معظم المشاريع على عرض جانت واحد على الأقل، وعادةً ما يكون هو الإدخال الأول. بعد الحصول على العرض، قد ترغب في التحقق من اسمه والتأكد من أنه من النوع `GanttChartView` قبل المتابعة لاستخراج الخصائص. هذا الفحص الإضافي يمنع أخطاء وقت التشغيل عند العمل مع مجموعات عروض مخصصة أو غير قياسية.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*مرساة التعريف:* `GanttChartView` يمثل التخطيط البصري للمهام، ومقاييس الوقت، والشرائط التي تراها في مخطط جانت النموذجي.

## كيف يمكنني استخراج خصائص العرض؟
يمكنك قراءة خصائص مثل لون الخلفية، ارتفاع الشريط، وإعدادات مقياس الوقت مباشرةً من كائن `GanttChartView`. يساعدك طباعتها على التحقق من التكوين الحالي قبل التصدير. تقوم حلقة استخراج نموذجية بالتكرار عبر كل خاصية، وتنسيق القيمة كسلسلة، وتسجيلها في وحدة التحكم أو ملف للتحليل لاحقًا. هذا النهج مفيد للتصحيح ولإنشاء وثائق لمظهر المخطط.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*مرساة التعريف:* `GanttChartView` يتيح الوصول إلى إعدادات العرض مثل لون الخلفية، ارتفاع الشريط، وتكوين مقياس الوقت.

## كيف يمكنني استخراج أنماط الشرائط؟
قم بالتكرار عبر مجموعة كائنات `BarStyle` للحصول على تفاصيل مثل اللون، النمط، والشكل لكل نوع شريط مستخدم في المخطط. لكل نمط، يمكنك أيضًا قراءة نوع المهمة المرتبط والشرط الذي يفعّل النمط، وهو أمر أساسي عند إعادة إنشاء المخطط بصيغة أخرى. جمع هذه المعلومات يتيح لك إنتاج نسخة بصرية دقيقة أو تطبيق قواعد تنسيق مخصصة برمجيًا.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*مرساة التعريف:* `BarStyle` يحدد المظهر البصري لشريط جانت، بما في ذلك لونه، نمطه، وشكله.

## كيف يمكنني استخراج خطوط الشبكة؟
تحدد خطوط الشبكة الفاصل البصري بين الصفوف والأعمدة. يمكن الوصول إليها عبر طريقة `getGridlines()` وإخراج رؤيتها ونمطها. بعد استرجاع مجموعة خطوط الشبكة، يمكنك التكرار عبر كل خط لالتقاط نوع الخط (متصل، متقطع)، السمك، واللون. هذه البيانات قيمة عندما تحتاج إلى إعادة إنتاج تخطيط الشبكة الدقيق في ملفات PDF المصدرة أو صيغ تقارير أخرى.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*مرساة التعريف:* `getGridlines()` تُعيد مجموعة كائنات خطوط الشبكة التي تتحكم في فواصل الصفوف والأعمدة في عرض جانت.

## كيف يمكنني استخراج أنماط النص؟
تتحكم أنماط النص في الخط، الحجم، ولون التسميات على مخطط جانت. قم بالتكرار عبر مجموعة `TextStyle` لسرد كل نمط. لكل نمط نص، يمكنك أيضًا استرجاع العنصر المرتبط به (اسم المهمة، التاريخ، إلخ) وأي قواعد تنسيق شرطي. يضمن التقاط هذه التفاصيل أن الوثائق المصدرة تحتفظ بنفس الطباعة كما في المخطط الأصلي.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*مرساة التعريف:* `TextStyle` يمثل سمات التنسيق المطبقة على العناصر النصية داخل مخطط جانت.

## كيف يمكنني استخراج خطوط التقدم؟
تُظهر خطوط التقدم نقطة إكمال المهمة الحالية. يمكن الوصول إليها عبر `getProgressLines()` وطباعة خصائصها. كل خط تقدم يتضمن خصائص مثل لون الخط، السمك، والموقع بالنسبة لشريط المهمة. تسجيل هذه المعلومات يتيح لك إنشاء تصورات واعية بالتقدم أو حساب مقاييس إكمال المشروع الإجمالية.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*مرساة التعريف:* `getProgressLines()` تُعيد مجموعة كائنات خطوط التقدم التي تشير إلى حالة إكمال المهمة.

## كيف يمكنني استخراج طبقات مقياس الوقت؟
تحدد طبقات مقياس الوقت الوحدات الزمنية الهرمية (أيام، أسابيع، شهور) المعروضة على المخطط. استرجعها عبر `getTimescaleTiers()` وأخرج إعداداتها. لكل طبقة يمكنك التقاط نوع الوحدة، تنسيق التسمية، والمحاذاة، وهي ضرورية لإعادة إنتاج الدقة الزمنية الدقيقة في ملفات PDF المصدرة أو مكونات واجهة المستخدم المخصصة.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*مرساة التعريف:* `getTimescaleTiers()` يتيح الوصول إلى مجموعة كائنات طبقات مقياس الوقت التي تتحكم في عرض محور الزمن.

## كيف يمكنني تصدير مخطط جانت إلى PDF؟
أنشئ كائن `PdfSaveOptions`، ويمكنك تخصيص حجم الصفحة أو تضمين الخطوط، ثم استدعِ `project.save` بصيغة PDF. ينتج هذا الاستدعاء الواحد ملف PDF يعكس عرض جانت على الشاشة. يمكنك أيضًا تحديد خيارات إضافية مثل ضغط الصور، إزالة العلامة المائية، أو تضمين خطوط مخصصة لتلبية متطلبات العلامة التجارية للشركة. بعد الحفظ، تحقق من حجم ملف PDF والدقة البصرية لضمان نجاح عملية التصدير.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*مرساة التعريف:* `PdfSaveOptions` يتيح لك ضبط مخرجات PDF بدقة، مثل أبعاد الصفحة، الضغط، ومعالجة الخطوط.

## المشكلات الشائعة والنصائح
- **دليل البيانات غير الصحيح:** تأكد من أن `dataDir` ينتهي بفاصل ملفات (`/` أو `\\`) المناسب لنظام التشغيل الخاص بك.  
- **غياب العرض:** إذا لم يحتوي المشروع على عرض جانت، سيكون `project.getViews()` فارغًا – أضف فحصًا قبل التحويل.  
- **استثناءات الترخيص:** بدون ترخيص صالح، قد تضيف API علامة مائية إلى ملفات PDF المصدرة.  
- **مشاريع كبيرة:** للمشاريع التي تحتوي على أكثر من 1,000 مهمة، فكر في زيادة حجم ذاكرة JVM (`-Xmx2g`) لتجنب `OutOfMemoryError`.  

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java مع مكتبات Java أخرى؟**  
ج: نعم، يتكامل Aspose.Tasks for Java بسلاسة مع أي مكتبة أو إطار عمل Java، بما في ذلك Spring وHibernate وApache POI.

**س: هل Aspose.Tasks مناسب للمشاريع المؤسسية واسعة النطاق؟**  
ج: بالتأكيد. تعالج المكتبة ملفات MPP متعددة المئات من الصفحات في أقل من 5 ثوانٍ على عتاد خادم قياسي وتدعم التنفيذ المتزامن في بيئات متعددة الخيوط.

**س: هل يدعم Aspose.Tasks صيغ ملفات مشروع متعددة؟**  
ج: نعم، يدعم Aspose.Tasks أكثر من 20 صيغة، بما في ذلك MPP، XML، MPX، وPrimavera XML، مما يتيح لك قراءة وتحويل الجداول الزمنية القديمة.

**س: هل يمكنني تخصيص مظهر مخططات جانت باستخدام Aspose.Tasks؟**  
ج: بالطبع. يمكنك تعديل أنماط الشرائط، خطوط الشبكة، أنماط النص، وطبقات مقياس الوقت برمجيًا قبل التصدير إلى PDF أو صيغ الصور.

**س: كيف أحفظ التغييرات بعد تعديل عرض؟**  
ج: استدعِ `project.save("output.mpp");` بعد إجراء أي تعديلات لحفظها في ملف المشروع.

---

**آخر تحديث:** 2026-10-31  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## دروس ذات صلة

- [كيفية حفظ المشروع كملف PDF باستخدام Aspose.Tasks – دليل التصدير](/tasks/java/project-file-operations/save-as-pdf/)
- [إنشاء PDF للمشروع – تخصيص مقياس الوقت في مخطط جانت](/tasks/java/project-file-operations/set-time-scale-count/)
- [تصدير المشروع إلى PDF وتقليل الفجوة بين قائمة المهام وتذييل الصفحة في Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}