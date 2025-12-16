---
date: 2025-12-16
description: تعلم كيفية قراءة بيانات جانت باستخدام Aspose.Tasks للغة Java. دليل خطوة
  بخطوة للتكامل السلس في تطبيقات Java الخاصة بك.
linktitle: Read Specific Gantt Chart Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: قراءة بيانات جانت aspose.tasks – قراءة بيانات مخطط جانت المحددة
url: /ar/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة بيانات gantt aspose.tasks – قراءة بيانات مخطط جانت المحددة

## المقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية **قراءة بيانات gantt aspose.tasks** واستخراج تفاصيل مخطط جانت محددة باستخدام Aspose.Tasks for Java. تُعد مخططات جانت أدوات لا غنى عنها لإدارة المشاريع، حيث تسمح للمستخدمين برؤية المهام والجداول الزمنية والاعتمادات. مع Aspose.Tasks for Java، يمكن للمطورين سحب المعلومات الدقيقة التي يحتاجونها بفعالية ودمجها في تطبيقاتهم. دعنا نتبع العملية خطوة بخطوة.

## إجابات سريعة
- **ماذا يمكنني استخراج؟** أي خاصية عرض، نمط شريط، خط شبكة، نمط نص، خط تقدم، أو مستوى مقياس زمني من مخطط جانت.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أحدث (يستخدم البرنامج التعليمي JDK 11).  
- **هل الكود قابل للتنفيذ كما هو؟** نعم – فقط استبدل مسار دليل البيانات.  
- **هل يمكن تعديل العرض بعد القراءة؟** بالطبع – تتيح API تعديل الخصائص وحفظها مرة أخرى في ملف المشروع.

## لماذا قراءة بيانات gantt aspose.tasks؟
يسمح استخراج بيانات مخطط جانت برمجياً لك بـ:
- بناء لوحات تحكم أو أدوات تقارير مخصصة.
- مزامنة جداول المشروع مع أنظمة المؤسسة الأخرى.
- إجراء تدقيقات آلية لاعتمادات المهام والجداول الزمنية.
- إنشاء ملفات PDF أو جداول Excel أو تصورات ويب دون الحاجة لتصدير يدوي.

## المتطلبات المسبقة
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيله [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. مكتبة Aspose.Tasks for Java: قم بتنزيل وتثبيت مكتبة Aspose.Tasks for Java من [هنا](https://releases.aspose.com/tasks/java/).
3. بيئة تطوير متكاملة (IDE): اختر IDE تفضله. الخيارات الشائعة تشمل IntelliJ IDEA، Eclipse، أو NetBeans.

## استيراد الحزم
أولاً، استورد الحزم اللازمة في مشروع Java للوصول إلى وظائف Aspose.Tasks:
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

## كيفية قراءة بيانات gantt aspose.tasks – تحميل ملف المشروع
ابدأ بتحميل ملف المشروع الذي يحتوي على بيانات مخطط جانت. قدم مسار دليل البيانات وحدد اسم الملف.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

## الخطوة 1: الوصول إلى عرض مخطط جانت
استرجع عرض مخطط جانت من المشروع. سنفترض أنه العرض الأول في القائمة.
```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

## الخطوة 2: استخراج خصائص العرض
الآن، لنستخرج مختلف خصائص عرض مخطط جانت ونطبعها للفحص.
```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

## الخطوة 3: استخراج أنماط الأشرطة
قم بالتكرار عبر أنماط الأشرطة في عرض مخطط جانت واطبع تفاصيلها.
```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

## الخطوة 4: استخراج خطوط الشبكة
استرجع واطبع معلومات حول خطوط الشبكة في عرض مخطط جانت.
```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

## الخطوة 5: استخراج أنماط النص
استرجع واطبع أنماط النص المستخدمة في عرض مخطط جانت.
```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

## الخطوة 6: استخراج خطوط التقدم
الوصول إلى وطباعة خصائص خطوط التقدم في عرض مخطط جانت.
```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

## الخطوة 7: استخراج مستويات مقياس الزمن
استرجع واطبع معلومات حول مستويات مقياس الزمن في عرض مخطط جانت.
```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## الأخطاء الشائعة والنصائح
- **دليل البيانات غير الصحيح:** تأكد من أن `dataDir` ينتهي بفاصل ملفات (`/` أو `\\`) المناسب لنظام التشغيل الخاص بك.  
- **غياب العرض:** إذا لم يحتوي المشروع على عرض جانت، فستكون `project.getViews()` فارغة – أضف فحصًا قبل التحويل.  
- **استثناءات الترخيص:** بدون ترخيص صالح، قد تضيف API علامة مائية إلى البيانات المصدرة.  

## الأسئلة المتكررة (موسعة)

**س: هل يمكنني استخدام Aspose.Tasks for Java مع مكتبات Java أخرى؟**  
ج: نعم، تم تصميم Aspose.Tasks for Java لتتكامل بسلاسة مع مكتبات وإطارات عمل Java الأخرى.

**س: هل Aspose.Tasks مناسب للمشاريع المؤسسية الضخمة؟**  
ج: بالتأكيد. يقدم Aspose.Tasks ميزات قوية وأداءً ممتازًا، مما يجعله ملائمًا لأي حجم من المشاريع.

**س: هل يدعم Aspose.Tasks صيغ ملفات مشروع متعددة؟**  
ج: نعم، يدعم Aspose.Tasks صيغ ملفات مشروع متنوعة، بما في ذلك MPP، XML، وMPX.

**س: هل يمكنني تخصيص مظهر مخططات جانت باستخدام Aspose.Tasks؟**  
ج: بالطبع. يوفر Aspose.Tasks واجهات برمجة تطبيقات واسعة لتخصيص مظهر مخطط جانت وفقًا لمتطلباتك.

**س: هل يتوفر دعم فني لمستخدمي Aspose.Tasks؟**  
ج: نعم، يقدم Aspose.Tasks دعمًا فنيًا شاملاً عبر منتدياته وقنوات الدعم المخصصة.

**س: كيف أحفظ التغييرات بعد تعديل العرض؟**  
ج: استدعِ `project.save("output.mpp");` بعد إجراء أي تعديل لتثبيت التغييرات.

## الخاتمة
تهانينا! لقد تعلمت بنجاح كيفية **قراءة بيانات gantt aspose.tasks** واستخراج معلومات مخطط جانت المحددة باستخدام Aspose.Tasks for Java. باتباعك لهذه الخطوات، يمكنك سحب وتحليل وتعديل بيانات مخطط جانت بفعالية داخل تطبيقات Java الخاصة بك، مما يفتح الباب أمام تقارير قوية، وتكامل، وسيناريوهات أتمتة متقدمة.

---

**آخر تحديث:** 2025-12-16  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
