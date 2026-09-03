---
date: 2026-05-26
description: تعلم كيفية إضافة عرض إلى المشروع باستخدام Aspose.Tasks for Java، حفظ
  custom view، وتعيين view properties لتقارير MS Project المتقدمة.
keywords:
- add view to project
- save custom view
- persist custom view
- create gantt chart view
- set view properties
linktitle: العروض المخصصة في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to add view to project using Aspose.Tasks for Java, save
    custom view, and set view properties for robust MS Project reporting.
  headline: How to Add View to Project with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes – Aspose.Tasks lets you create custom task sheets, resource sheets,
      and even custom tables, giving you full control over every visual aspect.
    question: Can I customize views beyond Gantt charts?
  - answer: Absolutely. The library processes projects with **500,000+ tasks** using
      a streaming API that keeps memory usage under 200 MB.
    question: Is Aspose.Tasks for Java suitable for large‑scale projects?
  - answer: Yes – you can export a view to PDF, XLSX, HTML, and several image formats
      directly from the API.
    question: Does Aspose.Tasks for Java support exporting views to different formats?
  - answer: Certainly. The API is fully scriptable, allowing you to generate, modify,
      and persist views in batch jobs or CI pipelines.
    question: Can I automate the creation of custom views using Aspose.Tasks for Java?
  - answer: Yes, you can get help from other developers and Aspose staff in the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks for Java support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية إضافة عرض إلى المشروع باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة عرض إلى المشروع باستخدام Aspose.Tasks

## مقدمة
إذا كنت تبحث عن **كيفية إضافة عرض إلى المشروع** بحيث تتطابق تقاريرك تمامًا مع ما يحتاجه أصحاب المصلحة، فقد وصلت إلى المكان الصحيح. يتيح تخصيص عروض MS Project لك إبراز البيانات الأكثر صلة، وتصفية الفوضى، وتسريع اتخاذ القرار. **Aspose.Tasks for Java** توفر واجهة برمجة تطبيقات قوية وآمنة من حيث النوع تتيح لك إنشاء وتكوين وحفظ العروض المخصصة مباشرة داخل ملف MPP. في هذا الدليل سنستعرض كل خطوة — من إعداد البيئة إلى حفظ العرض — حتى تتمكن من تقديم حل مصقول وقابل للتكرار.

## إجابات سريعة
- **ما هو الغرض الأساسي؟** إضافة عرض إلى المشروع وحفظه داخل ملف MPP باستخدام Aspose.Tasks for Java.  
- **أي فئة تنشئ عرضًا؟** `GanttChartView` (أو أنواع عروض أخرى مثل `TaskSheetView`).  
- **كيف أجعل العرض يظهر في القائمة؟** استدعِ `view.setShowInMenu(true)` قبل الحفظ.  
- **كيف يمكنني حفظ العرض مع المشروع؟** استخدم `MPPSaveOptions` مع `setWriteViewData(true)`.  
- **هل أحتاج إلى ترخيص؟** نعم – يلزم وجود ترخيص Aspose.Tasks صالح للنشر في بيئة الإنتاج.

## ما هو “إضافة عرض إلى المشروع”؟
يعني *إضافة عرض إلى مشروع* إنشاء تمثيل بصري جديد (مثل مخطط جانت أو ورقة المهام) وتضمين تعريفه داخل ملف MPP بحيث يمكن لـ Microsoft Project عرضه لاحقًا. هذه العملية تتم برمجة كاملة باستخدام Aspose.Tasks، مما يلغي الحاجة إلى خطوات يدوية في واجهة المستخدم.

## لماذا نستخدم العروض المخصصة؟
يدعم Aspose.Tasks **أكثر من 50 خاصية متعلقة بالعرض** ويمكنه التعامل مع مشاريع تحتوي على **مئات الآلاف من المهام** دون تحميل الملف بالكامل إلى الذاكرة. من خلال تعريف العرض مرة واحدة وحفظه، تضمن تقارير متسقة لجميع أعضاء الفريق وتقلل من خطر الأخطاء الناتجة عن التكوين اليدوي.

## المتطلبات المسبقة
- **Java Development Kit** (JDK 8 أو أحدث) مثبت ومُعد على جهازك.  
- **Aspose.Tasks for Java** مكتبة – حمّلها من [here](https://releases.aspose.com/tasks/java/).  
- ملف ترخيص **Aspose.Tasks** صالح للاستخدام في الإنتاج (الإصدار التجريبي المجاني يعمل للتقييم).

## استيراد الحزم
توجد الفئات `GanttChartView` و `MPPSaveOptions` والفئات ذات الصلة في مساحة الاسم `com.aspose.tasks`. استوردها في أعلى ملف المصدر الخاص بك:

`GanttChartView` تمثل تعريف عرض مخطط جانت.  
`MPPSaveOptions` تتحكم في طريقة حفظ المشروع، بما في ذلك بيانات العرض.  
`Project` هي الفئة الرئيسية التي تمثل ملف MS Project.  
`View` هي الفئة الأساسية لجميع أنواع العروض.  

```text
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
```

## الخطوة 1: إعداد المشروع
أنشئ كائن `Project` جديد أو حمّل ملفًا موجودًا. هذا الكائن يحتوي على جميع بيانات المشروع، بما في ذلك المهام والموارد والعروض. توفر `Prj` مفاتيح ثابتة لخصائص المشروع مثل اسم المشروع.

```text
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
```

## الخطوة 2: إنشاء عرض
`GanttChartView` هو تمثيل Aspose.Tasks لمخطط جانت الكلاسيكي. يتيح لك التحكم في الأعمدة، وأنماط الأشرطة، ومقاييس الوقت، وأكثر.

```text
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```
```

## الخطوة 3: تخصيص خصائص العرض *(set view properties)*
هنا يمكنك ضبط مظهر العرض بدقة: تعيين العمود الأول المرئي، تعريف ألوان الأشرطة، وضبط دقة مقياس الوقت. `setShowInMenu(boolean)` يحدد ما إذا كان العرض سيظهر في قائمة MS Project. `setHighlightFilter(boolean)` يشير إلى ما إذا كان الفلتر مميزًا للعرض.

```text
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```
```

### كيفية إظهار قائمة العرض
استدعاء `view.setShowInMenu(true)` يضمن ظهور العرض الذي تم إنشاؤه حديثًا في قائمة **View** في MS Project، مما يمنح المستخدمين النهائيين وصولًا فوريًا دون إعداد إضافي.

## الخطوة 4: ضبط إعدادات العرض
يتم تكوين الإعدادات المتقدمة مثل تخطيط الصفحة، خيارات الطباعة، وعرض الأعمدة في هذه الخطوة. يضمن الضبط السليم أن تتطابق التقارير المطبوعة مع العرض على الشاشة.

```text
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```
```

## الخطوة 5: إضافة عرض إلى المشروع *(add custom view java)*
بعد تكوين العرض، أضفه إلى مجموعة `Views` في المشروع. `getViews()` تُعيد مجموعة العروض في المشروع. هذه الخطوة فعليًا **تضيف عرضًا إلى المشروع** بحيث يصبح جزءًا من البنية الداخلية للملف.

```text
```java
// Add the view to our project
project.getViews().add(view);
```
```

## الخطوة 6: حفظ المشروع *(save project view)*
عند حفظ المشروع، يجب إبلاغ Aspose.Tasks بكتابة بيانات العرض. تتحكم فئة `MPPSaveOptions` في هذا السلوك. `setWriteViewData(boolean)` تخبر أداة الحفظ بتضمين تعريفات العرض.

```text
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```
```

### لماذا حفظ عرض المشروع مهم
تعيين `options.setWriteViewData(true)` يوجه Aspose.Tasks لتضمين تعريف العرض المخصص داخل ملف MPP. بدون هذا الإعداد، سيبقى العرض في الذاكرة فقط ويختفي بعد إغلاق الملف.

## الخطوة 7: فحص خصائص العرض
بعد الحفظ، يمكنك إعادة تحميل المشروع والتحقق من أن العرض يظهر بشكل صحيح في واجهة المستخدم وأن جميع الخصائص (الأعمدة، أنماط الأشرطة، إلخ) محفوظة.

```text
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```
```

## حالات الاستخدام الشائعة
- **تقارير أصحاب المصلحة:** عرض فقط المعالم ومهام المسار الحرج للإدارة العليا.  
- **تخصيص الموارد:** عرض الموارد جنبًا إلى جنب مع المهام المخصصة لها لتخطيط السعة.  
- **لقطات جاهزة للطباعة:** تكوين حجم الصفحة، الاتجاه، ورؤية الأعمدة لإنشاء ملفات PDF نظيفة للمراجعة دون اتصال.

## نصائح استكشاف الأخطاء وإصلاحها
- **العرض لا يظهر في القائمة:** تأكد من استدعاء `view.setShowInMenu(true)` *قبل* الحفظ وأن `MPPSaveOptions.setWriteViewData(true)` مفعّل.  
- **الأعمدة مفقودة في الطباعة:** تحقق من أن `setFirstColumnsCount` يطابق عدد الأعمدة التي حددتها وفعل `setPrintFirstColumnsCountOnAllPages(true)`.  
- **استثناءات الترخيص:** حمّل ملف الترخيص باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.lic");` قبل إنشاء أي كائنات `Project`.

## الأسئلة المتكررة

**Q:** هل يمكنني تخصيص العروض بما يتجاوز مخططات جانت؟  
**A:** نعم – يتيح لك Aspose.Tasks إنشاء أوراق مهام مخصصة، أوراق موارد، وحتى جداول مخصصة، مما يمنحك التحكم الكامل في كل جانب بصري.

**Q:** هل Aspose.Tasks for Java مناسب للمشاريع الكبيرة النطاق؟  
**A:** بالطبع. المكتبة تعالج مشاريع تحتوي على **أكثر من 500,000 مهمة** باستخدام واجهة برمجة تطبيقات تدفقية تحافظ على استهلاك الذاكرة تحت 200 ميغابايت.

**Q:** هل يدعم Aspose.Tasks for Java تصدير العروض إلى صيغ مختلفة؟  
**A:** نعم – يمكنك تصدير عرض إلى PDF أو XLSX أو HTML وعدة صيغ صور مباشرة من الواجهة البرمجية.

**Q:** هل يمكنني أتمتة إنشاء العروض المخصصة باستخدام Aspose.Tasks for Java؟  
**A:** بالتأكيد. الواجهة البرمجية قابلة للبرمجة بالكامل، مما يتيح لك إنشاء وتعديل وحفظ العروض في وظائف دفعة أو خطوط أنابيب CI.

**Q:** هل هناك منتدى مجتمع لدعم Aspose.Tasks for Java؟  
**A:** نعم، يمكنك الحصول على المساعدة من مطورين آخرين وموظفي Aspose في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2026-05-26  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بتنسيق MPP باستخدام Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [تعيين دليل البيانات لعرض مخطط جانت في Aspose.Tasks](/tasks/java/project-configuration/configure-gantt-chart/)
- [تحميل ملف MPP Java - إدارة خصائص المشروع باستخدام Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}