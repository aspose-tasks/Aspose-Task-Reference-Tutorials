---
date: 2025-12-21
description: تعلم كيفية تخصيص عروض مخطط جانت، وإدارة تصور المشروع، وحفظ المشروع كملف
  PDF باستخدام Aspose.Tasks للغة Java. اضبط عدد مقياس الوقت بسهولة.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تخصيص مخطط جانت – إتقان حساب مقياس الوقت في MS Project باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تخصيص مخطط جانت – إتقان عدد مقياس الوقت في MS Project باستخدام Aspose.Tasks

## المقدمة
إذا كنت بحاجة إلى **customize Gantt chart** في Microsoft Project، فإن التحكم في عدد مقياس الوقت يُعد تقنية أساسية. باستخدام Aspose.Tasks for Java يمكنك برمجيًا تعيين مستويات مقياس الوقت السفلية والوسطى، وضبط ظهور العلامات، ثم **save project as PDF** لمشاركة المشروع مع أصحاب المصلحة. يشرح هذا الدرس العملية بالكامل—من إعداد البيئة إلى إنشاء ملف PDF مصقول يعكس عرض المخطط المخصص.

## إجابات سريعة
- **What does “customize Gantt chart” mean?** تعديل مستويات مقياس الوقت، الألوان، وتخطيط لتتناسب مع احتياجات التقارير الخاصة بك.  
- **Which API method sets the bottom tier count?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Can I generate a PDF directly from the project?** نعم—استخدم `project.save(..., SaveFileFormat.Pdf)`.  
- **Do I need a license for production use?** يلزم الحصول على ترخيص تجاري؛ يتوفر إصدار تجريبي مجاني.  
- **Which Java version is supported?** Java 8 أو أعلى يعمل مع أحدث مكتبة Aspose.Tasks.

## ما هو “customize Gantt chart” في Aspose.Tasks؟
يعني تخصيص مخطط جانت تعديل مكوّناته البصرية برمجيًا—مثل فواصل مقياس الوقت، العلامات، وأشرطة المهام—بحيث يتماشى المخطط مع الطريقة التي تريد **manage project visualization** بها. من خلال تغيير عدد مقياس الوقت، تتحكم في عدد الأيام أو الأسابيع أو الشهور التي يمثلها كل جزء، مما يجعل المخطط أوضح لمختلف الجماهير.

## المتطلبات المسبقة
1. **Java Development Environment** – يجب تثبيت JDK 8 أو أحدث.  
2. **Aspose.Tasks for Java Library** – قم بتنزيله من [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – الإلمام بصياغة Java ومفاهيم البرمجة الكائنية.

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
حدد مكان قراءة وكتابة ملفات المشروع:

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق على جهازك.

### الخطوة 2: إنشاء مثيل مشروع جديد
أنشئ كائن `Project` جديد سيحتوي على جميع المهام وإعدادات العرض:

```java
Project project = new Project();
```

### الخطوة 3: تكوين عرض مخطط جانت
أنشئ كائن `GanttChartView`—هذا هو المكان الذي ستقوم فيه بـ **generate Gantt view Java** للتحكم في مظهر المخطط:

```java
GanttChartView view = new GanttChartView();
```

### الخطوة 4: تعيين عدد مقياس الوقت للطبقة السفلية
اضبط الطبقة السفلية لعرض فاصلين وإخفاء العلامات:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### الخطوة 5: تعيين عدد مقياس الوقت للطبقة الوسطى
طبق نفس الإعدادات على الطبقة الوسطى:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### الخطوة 6: إضافة العرض المخصص إلى المشروع
اربط العرض الذي قمت بتكوينه مؤخرًا بكائن `Project`:

```java
project.getViews().add(view);
```

### الخطوة 7: إضافة مهام نموذجية (بيانات اختبارية)
أنشئ عددًا من المهام بمدة محددة لتوضيح مخطط جانت المخصص:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### الخطوة 8: حفظ المشروع كملف PDF
أخيرًا، صدّر المشروع—بما في ذلك **customized Gantt chart**—إلى ملف PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

يوضح ملف PDF الناتج كيف تم **customized** الطبقتين السفلية والوسطى لمقياس الوقت، مما يمنح أصحاب المصلحة عرضًا واضحًا وقابلًا للطباعة للجدول الزمني.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها
- **PDF is blank** – تأكد من أن مسار `dataDir` ينتهي بفاصل ملفات (`/` أو `\`) وأن الدليل موجود.  
- **Ticks still appear** – تحقق من استدعاء `setShowTicks(false)` على كلتا الطبقتين.  
- **Duration not applied** – تأكد من استخدام `TimeUnitType.Hour` (أو الوحدة المناسبة) عند إنشاء الفترات الزمنية.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks for Java معالجة ملفات مشاريع ذات نطاق واسع؟**  
ج: نعم، تم تحسين المكتبة لمعالجة بيانات المشاريع الضخمة بأداء عالي.

**س: هل Aspose.Tasks for Java متوافق مع بيئات تطوير Java المختلفة؟**  
ج: بالتأكيد—يعمل بسلاسة مع Eclipse، IntelliJ IDEA، NetBeans، وغيرها من بيئات التطوير الشائعة.

**س: هل يمكنني تخصيص مظهر مخططات جانت بخلاف إعدادات مقياس الوقت؟**  
ج: نعم، توفر Aspose.Tasks خيارات تنسيق واسعة مثل ألوان الأشرطة، الخطوط، وخطوط الشبكة.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من [here](https://releases.aspose.com/).

**س: أين يمكنني الحصول على دعم لـ Aspose.Tasks for Java؟**  
ج: يمكنك العثور على الدعم والمساعدة في منتدى Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**س: كيف يمكنني برمجيًا تغيير لون خلفية مخطط جانت؟**  
ج: استخدم الطريقة `view.getGanttChartProperties().setBackgroundColor(Color)` بعد استيراد `java.awt.Color`.

## الخلاصة
باتباعك لهذه الخطوات، تعلمت كيفية **customize Gantt chart** لمستويات مقياس الوقت، تحسين **project visualization**، و**save project as PDF** باستخدام Aspose.Tasks for Java. يمنحك هذا النهج سيطرة كاملة على المخرجات البصرية، مما يسهل مشاركة جداول زمنية واضحة ومهنية مع فريقك أو عملائك.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}