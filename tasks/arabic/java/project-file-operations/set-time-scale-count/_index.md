---
date: 2026-03-29
description: تعلم كيفية إنشاء ملفات PDF للمشروعات مع تخصيص عدد مقاييس الوقت في مخطط
  جانت باستخدام Aspose.Tasks للغة Java. يوضح لك هذا الدليل خطوة بخطوة كيفية تصدير
  مخطط جانت إلى PDF مع تحكم كامل.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إنشاء ملف PDF للمشروع – تخصيص مقياس الوقت لمخطط جانت
url: /ar/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء ملف PDF للمشروع – تخصيص مقياس الوقت لمخطط جانت

## مقدمة
إذا كنت بحاجة إلى **create project PDF** التي تعكس مخطط جانت مضبوطًا تمامًا، فإن التحكم في عدد مقياس الوقت هو المفتاح. باستخدام Aspose.Tasks for Java يمكنك برمجيًا ضبط مستويات مقياس الوقت السفلية والمتوسطة، إخفاء علامات التحديد، ثم **save project as PDF** لتسهيل التوزيع. في هذا البرنامج التعليمي سنستعرض كل ما تحتاجه — من إعداد بيئة التطوير إلى إنشاء ملف PDF مصقول يعرض عرض جانت المخصص الخاص بك.

## إجابات سريعة
- **What does “customize Gantt chart” mean?** تعديل مستويات مقياس الوقت، الألوان، وتخطيط العرض لتتناسب مع احتياجات التقارير الخاصة بك.  
- **Which API method sets the bottom tier count?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Can I generate a PDF directly from the project?** نعم—استخدم `project.save(..., SaveFileFormat.Pdf)`.  
- **Do I need a license for production use?** يلزم الحصول على ترخيص تجاري؛ يتوفر إصدار تجريبي مجاني.  
- **Which Java version is supported?** Java 8 أو أعلى يعمل مع أحدث مكتبة Aspose.Tasks.

## ما هو “customize Gantt chart” في Aspose.Tasks؟
تخصيص مخطط جانت يعني تعديل مكوناته البصرية برمجيًا — مثل فواصل مقياس الوقت، علامات التحديد، وأشرطة المهام — بحيث يتوافق المخطط مع الطريقة التي تريد بها **manage project visualization**. من خلال تغيير عدد مقياس الوقت، تتحكم في عدد الأيام أو الأسابيع أو الشهور التي يمثلها كل جزء، مما يجعل المخطط أوضح لجماهير مختلفة.

## لماذا إنشاء ملف PDF للمشروع مع مخطط جانت مخصص؟
- **Stakeholder‑ready output:** PDF يمكن عرضه عالميًا، مما يضمن أن يرى الجميع نفس تخطيط الجدول.  
- **Print‑friendly:** التحكم الدقيق في مستويات مقياس الوقت يمنع الطباعة المزدحمة أو غير الواضحة.  
- **Automation:** دمج إنشاء PDF في خطوط أنابيب CI أو خدمات التقارير لتقليل الجهد اليدوي إلى الصفر.  

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك:

1. **Java Development Environment** – JDK 8 أو أحدث مثبت.  
2. **Aspose.Tasks for Java Library** – قم بتنزيله من [هنا](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – الإلمام بتركيب Java ومفاهيم البرمجة الكائنية.

## استيراد الحزم
استورد الفئات الضرورية إلى مشروع Java الخاص بك:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## دليل خطوة بخطوة

### الخطوة 1: تعيين دليل البيانات
حدد المكان الذي سيتم قراءة ملفات مشروعك منه وكتابتها إليه:

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق على جهازك.

### الخطوة 2: إنشاء نسخة مشروع جديدة
أنشئ كائن `Project` جديد سيحتوي على جميع المهام وإعدادات العرض:

```java
Project project = new Project();
```

### الخطوة 3: تكوين عرض مخطط جانت
أنشئ كائن `GanttChartView` — هذا هو المكان الذي ستقوم فيه **generate Gantt view Java** لتوليد كود التحكم في مظهر المخطط:

```java
GanttChartView view = new GanttChartView();
```

### الخطوة 4: ضبط عدد مقياس الوقت للمستوى السفلي
اضبط المستوى السفلي لعرض فاصلين وإخفاء علامات التحديد:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### الخطوة 5: ضبط عدد مقياس الوقت للمستوى المتوسط
طبق نفس الإعدادات على المستوى المتوسط:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### الخطوة 6: إضافة العرض المخصص إلى المشروع
أرفق العرض الذي قمت بتكوينه للتو إلى نسخة `Project`:

```java
project.getViews().add(view);
```

### الخطوة 7: إضافة مهام نموذجية (بيانات اختبارية)
أنشئ عددًا من المهام ذات مدد محددة لتوضيح مخطط جانت المخصص:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### الخطوة 8: حفظ المشروع كملف PDF
أخيرًا، صدّر المشروع — بما في ذلك **customized Gantt chart** — إلى ملف PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

يوضح ملف PDF الناتج كيف تم **customized** مستويات مقياس الوقت السفلية والمتوسطة، مما يمنح أصحاب المصلحة عرضًا واضحًا وقابلًا للطباعة للجدول الزمني.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها
- **PDF is blank** – تأكد من أن مسار `dataDir` ينتهي بفاصل ملف (`/` أو `\`) وأن الدليل موجود.  
- **Ticks still appear** – تحقق من استدعاء `setShowTicks(false)` على كلا المستويين.  
- **Duration not applied** – تأكد من أنك تستخدم `TimeUnitType.Hour` (أو الوحدة المناسبة) عند إنشاء الفترات.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks for Java التعامل مع ملفات مشاريع واسعة النطاق؟**  
ج: نعم، المكتبة مُحسّنة لمعالجة عالية الأداء لبيانات المشاريع الضخمة.

**س: هل Aspose.Tasks for Java متوافق مع بيئات تطوير Java المختلفة؟**  
ج: بالتأكيد – يعمل بسلاسة مع Eclipse و IntelliJ IDEA و NetBeans وغيرها من بيئات التطوير الشائعة.

**س: هل يمكنني تخصيص مظهر مخططات جانت بخلاف إعدادات مقياس الوقت؟**  
ج: نعم، توفر Aspose.Tasks خيارات تنسيق واسعة مثل ألوان الأشرطة، الخطوط، وخطوط الشبكة.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks for Java؟**  
ج: يمكنك العثور على الدعم والمساعدة في منتدى Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

**س: كيف يمكنني برمجيًا تغيير لون خلفية مخطط جانت؟**  
ج: استخدم الطريقة `view.getGanttChartProperties().setBackgroundColor(Color)` بعد استيراد `java.awt.Color`.

## الخلاصة
باتباعك هذه الخطوات، تعلمت كيفية **create project PDF** ملفات مع مقياس وقت مخطط جانت مخصص بالكامل، تحسين **project visualization**، و **save project as PDF** باستخدام Aspose.Tasks for Java. يمنحك هذا النهج تحكمًا كاملاً في المخرجات البصرية، مما يسهل مشاركة جداول زمنية واضحة ومهنية مع فريقك أو عملائك.

---

**آخر تحديث:** 2026-03-29  
**تم الاختبار مع:** Aspose.Tasks for Java (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}