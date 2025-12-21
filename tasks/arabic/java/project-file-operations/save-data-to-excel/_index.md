---
date: 2025-12-21
description: تعلم كيفية تصدير MPP إلى Excel وتحويل ملف المشروع إلى Excel باستخدام
  Aspose.Tasks للغة Java. خطوات بسيطة لمطوري Java.
linktitle: Save Data to Excel in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تصدير MPP إلى Excel باستخدام Aspose.Tasks للـ Java
url: /ar/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تصدير MPP إلى Excel باستخدام Aspose.Tasks for Java

## مقدمة
Aspose.Tasks for Java هي مكتبة قوية تتيح لك **تصدير MPP إلى Excel** بسرعة وبشكل موثوق. في هذا الدليل سنرشدك عبر الخطوات الدقيقة المطلوبة لتحويل ملف Microsoft Project (.mpp) إلى مصنف Excel (.xlsx). في النهاية ستفهم كيفية **تحويل ملف المشروع إلى Excel**، ولماذا هذه العملية مفيدة، وكيفية دمجها في أي تطبيق Java.

## إجابات سريعة
- **ماذا تفعل الـ API؟** تقوم بقراءة ملفات Project وحفظها مباشرةً كدفاتر عمل XLSX.  
- **ما هو التنسيق الناتج؟** ملف Excel باستخدام خيار `SaveFileFormat.Xlsx`.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **ما هي المتطلبات المسبقة؟** تثبيت JDK وإضافة مكتبة Aspose.Tasks for Java إلى مشروعك.  
- **كم من الوقت تستغرق عملية التنفيذ؟** عادةً أقل من 10 دقائق للتصدير الأساسي.

## ما هو “كيفية تصدير MPP إلى Excel”؟
يعني تصدير MPP إلى Excel أخذ الجدول الزمني والموارد وبيانات المهام المخزنة في ملف Microsoft Project وكتابتها في جدول بيانات Excel منظم. هذا يجعل مشاركة بيانات المشروع مع أصحاب المصلحة الذين قد لا يكون لديهم برنامج Project سهلًا.

## لماذا تحويل ملف MPP إلى XLSX؟
- **إمكانية وصول أوسع:** Excel شائع في بيئات الأعمال.  
- **تقارير مبسطة:** استخدم جداول Pivot، الرسوم البيانية، والصيغ في Excel لتحليل مؤشرات المشروع.  
- **ملائم للأتمتة:** يمكن للأنظمة أو السكريبتات الأخرى معالجة ملفات Excel دون الحاجة إلى Project.  

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – مثبت ومضاف إلى PATH في نظامك.  
2. **مكتبة Aspose.Tasks for Java** – قم بتنزيلها من [رابط التحميل](https://releases.aspose.com/tasks/java/) وأضف ملف JAR إلى classpath الخاص بمشروعك.

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. احتفظ بهذا المقطع كما هو بالضبط – فهو مطلوب لعمل الـ API.

```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## دليل خطوة بخطوة

### الخطوة 1: تحديد مسار دليل البيانات
حدد المجلد الذي يوجد فيه ملف `.mpp` الخاص بك. استبدل العنصر النائب بالمسار الفعلي.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بتحميل ملف `.mpp` الذي تريد تحويله. هذا يقرأ جميع المهام والموارد ومعلومات الجدولة.

```java
Project project = new Project(dataDir + "project5.mpp");
```

### الخطوة 3: حفظ المشروع كملف XLSX
أخيرًا، صدّر المشروع المحمّل إلى مصنف Excel. علم `SaveFileFormat.Xlsx` يخبر Aspose.Tasks بإنشاء ملف `.xlsx` حديث، وبالتالي **تحويل ملف MPP إلى XLSX**.

```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```

## حالات الاستخدام الشائعة
- **تقارير تنفيذية:** تقديم لمحات عامة عن المشروع في Excel للإدارة العليا.  
- **تحليل البيانات:** إدخال بيانات المهام والموارد إلى Power Query في Excel للحصول على رؤى أعمق.  
- **التكامل:** تمرير ملف Excel المُصدّر إلى الأنظمة اللاحقة التي تقبل فقط مدخلات CSV/Excel.  

## الخلاصة
في هذا الدليل، عرضنا **كيفية تصدير MPP إلى Excel** باستخدام Aspose.Tasks for Java. باتباع الخطوات الثلاث البسيطة — تحديد دليل البيانات، تحميل ملف المشروع، وحفظه كملف XLSX — يمكنك بسهولة **تصدير بيانات المشروع إلى Excel** وتمكين فريقك من تقارير مرنة وقابلة للمشاركة.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Tasks for Java للتعامل مع بيانات المشروع برمجياً؟
نعم، توفر Aspose.Tasks for Java ميزات واسعة للتعامل مع بيانات المشروع، بما في ذلك القراءة والكتابة وتعديل ملفات المشروع.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks for Java من [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Tasks for Java؟
يمكنك العثور على وثائق Aspose.Tasks for Java [هنا](https://reference.aspose.com/tasks/java/).

### كيف يمكنني الحصول على الدعم لأي مشكلات أو استفسارات تتعلق بـ Aspose.Tasks for Java؟
يمكنك الحصول على الدعم بزيارة منتدى Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks for Java؟
نعم، يمكنك شراء ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose