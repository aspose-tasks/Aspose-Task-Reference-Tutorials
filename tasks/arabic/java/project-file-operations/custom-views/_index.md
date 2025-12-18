---
date: 2025-12-18
description: تعلم كيفية إنشاء عرض في Aspose.Tasks للغة Java، بما في ذلك كيفية حفظ
  عرض المشروع وتعيين خصائص العرض. عزّز كفاءة إدارة المشاريع من خلال عروض مخصصة مخصصة
  لبرنامج MS Project.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'كيفية إنشاء عرض: عروض مخصصة في MS Project باستخدام Aspose.Tasks'
url: /ar/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء عرض: عروض مخصصة في MS Project باستخدام Aspose.Tasks

## المقدمة
إذا كنت تبحث عن **كيفية إنشاء عرض** يتماشى مع احتياجات تقارير مشروعك الفريدة، فقد وصلت إلى المكان الصحيح. في إدارة المشاريع، يمكن لتخصيص العروض أن يحسن بشكل كبير الوضوح والكفاءة عند التعامل مع المهام والموارد. **Aspose.Tasks for Java** يزودك بواجهة برمجة تطبيقات غنية لت **إضافة عرض مخصص بنمط Java**، مما يتيح لك تعديل عروض MS Project بالضبط كما تحتاجها. في هذا البرنامج التعليمي سنستعرض العملية خطوة بخطوة، بدءًا من إعداد المشروع وحتى حفظ عرض المشروع.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إنشاء وحفظ عرض مخصص في MS Project باستخدام Aspose.Tasks for Java.  
- **أي فئة تنشئ العرض؟** `GanttChartView` (أو أنواع عروض أخرى).  
- **كيف أجعل العرض يظهر في القائمة؟** اضبط `view.setShowInMenu(true)`.  
- **كيف يمكنني حفظ العرض مع المشروع؟** استخدم `MPPSaveOptions` مع `setWriteViewData(true)`.  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في بيئة الإنتاج.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:

### بيئة تطوير جافا
تأكد من تثبيت Java على نظامك.

### Aspose.Tasks for Java
قم بتحميل وتثبيت Aspose.Tasks for Java من [هنا](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أولاً، استورد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## الخطوة 1: إعداد المشروع
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## الخطوة 2: إنشاء العرض
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## الخطوة 3: تخصيص خصائص العرض *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### كيفية إظهار العرض في القائمة
يضمن الاستدعاء `view.setShowInMenu(true)` ظهور العرض الذي تم إنشاؤه حديثًا في **قائمة العرض** في MS Project، مما يوفر وصولًا سريعًا للمستخدمين النهائيين.

## الخطوة 4: ضبط إعدادات العرض
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## الخطوة 5: إضافة العرض إلى المشروع *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## الخطوة 6: حفظ المشروع *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### لماذا يعتبر حفظ عرض المشروع مهمًا
إعداد `options.setWriteViewData(true)` يخبر Aspose.Tasks بـ **حفظ معلومات عرض المشروع** داخل ملف MPP، بحيث يبقى العرض المخصص محفوظًا عبر الجلسات.

## الخطوة 7: فحص خصائص العرض
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## حالات الاستخدام الشائعة
- **تقارير أصحاب المصلحة:** إنشاء عرض يُظهر فقط المعالم العليا والمهام الحرجة.  
- **تخصيص الموارد:** بناء عرض يسرد الموارد جنبًا إلى جنب مع المهام المخصصة لها لتسهيل فحص السعة.  
- **مستندات جاهزة للطباعة:** ضبط إعدادات الصفحة (كما في الخطوة 4) لإنشاء لقطات مشروع قابلة للطباعة.

## نصائح استكشاف الأخطاء وإصلاحها
- **العرض لا يظهر في القائمة:** تأكد من استدعاء `view.setShowInMenu(true)` قبل عملية الحفظ.  
- **الأعمدة مفقودة في الطباعة:** تأكد من أن `setFirstColumnsCount` يطابق عدد الأعمدة المطلوبة وأن `setPrintFirstColumnsCountOnAllPages(true)` مفعَّل.  
- **استثناءات الترخيص:** إذا واجهت أخطاء ترخيص، تحقق من تحميل ملف ترخيص Aspose.Tasks صالح قبل إنشاء كائن `Project`.

## الأسئلة المتكررة
### س1: هل يمكنني تخصيص العروض بما يتجاوز مخططات جانت؟
ج: نعم، يوفر Aspose.Tasks for Java مرونة لتخصيص أنواع مختلفة من العروض بخلاف مخططات جانت، بما في ذلك الجداول والرسوم البيانية.

### س2: هل Aspose.Tasks for Java مناسب للمشاريع الكبيرة؟
ج: بالتأكيد. تم تصميم المكتبة للتعامل مع مشاريع بأي حجم، مع تقديم أداء قوي وإدارة فعّالة للذاكرة.

### س3: هل يدعم Aspose.Tasks for Java تصدير العروض إلى صيغ مختلفة؟
ج: نعم، يمكنك تصدير العروض إلى PDF، XLSX، HTML، وصيغ أخرى، مما يضمن مشاركة سلسة عبر المنصات.

### س4: هل يمكنني أتمتة إنشاء العروض المخصصة باستخدام Aspose.Tasks for Java؟
ج: بالطبع. تتيح واجهة البرمجة أتمتة كاملة، مما يسمح لك بإنشاء وإدارة العروض المخصصة برمجيًا.

### س5: هل هناك منتدى مجتمع لدعم Aspose.Tasks for Java؟
ج: نعم، يمكنك الحصول على المساعدة والتفاعل مع المستخدمين الآخرين في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) الخاص باستفسارات ومناقشات Java.

---

**آخر تحديث:** 2025-12-18  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}