---
date: 2026-01-10
description: تعلم كيفية تغيير الكونتور وإنشاء بيانات زمنية لتعيينات الموارد باستخدام
  Aspose.Tasks للغة Java، مما يحسن كفاءة إدارة المشروع.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تغيير المنحنى في Aspose.Tasks للبيانات الزمنية
url: /ar/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تغيير الشكل (Contour) في Aspose.Tasks للبيانات الزمنية (Timephased Data)

## المقدمة
في هذا الدرس، ستكتشف **كيفية تغيير الشكل** لتخصيص مورد وتوليد بيانات زمنية باستخدام Aspose.Tasks for Java. تُظهر البيانات الزمنية توزيع العمل على طول جدول المشروع، مما يتيح لك ضبط الجداول، موازنة أعباء العمل، واتخاذ قرارات مستندة إلى البيانات.

## الإجابات السريعة
- **ما هو الشكل (contour)؟** يُعرّف شكل العمل كيفية توزيع الجهد عبر مدة المهمة (مثل Flat، Turtle، Bell).  
- **لماذا تغيير الشكل؟** لتعكس أنماط عمل واقعية مثل تحميل الجهد في البداية أو النهاية.  
- **أي مكتبة مطلوبة؟** Aspose.Tasks for Java (أي نسخة حديثة).  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في الإنتاج.  
- **هل يمكنني رؤية النتائج في وحدة التحكم؟** يعرض العينة تواريخ البدء والقيم لكل مقطع زمني.

## ما هو “كيفية تغيير الشكل”؟
تغيير الشكل يعني تحديث خاصية `WORK_CONTOUR` لكائن `ResourceAssignment`. تدعم Aspose.Tasks عدة أشكال مسبقة التعريف (Flat، Turtle، Bell، إلخ) تؤثر على كيفية تخصيص العمل عبر الزمن.

## لماذا نستخدم Aspose.Tasks لتوليد البيانات الزمنية؟
- **تقارير دقيقة:** تصدير توزيع العمل بدقة لأدوات التقارير.  
- **تخطيط السيناريوهات:** اختبار أشكال مختلفة دون تعديل الجدول الأصلي.  
- **الأتمتة:** دمجها في خطوط أنابيب CI للتحقق من صحة صحة المشروع تلقائيًا.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله وتثبيته من [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. مكتبة Aspose.Tasks for Java: تحتاج إلى مكتبة Aspose.Tasks for Java. يمكنك تنزيلها من [الموقع الإلكتروني](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أولاً، لنستورد الحزم الضرورية للعمل مع Aspose.Tasks:
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
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## الخطوة 2: الحصول على المهمة وتخصيص المورد
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## كيفية تغيير الشكل – Flat (الافتراضي)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الشكل – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الشكل – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الشكل – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الشكل – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الشكل – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الشكل – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## كيفية تغيير الشكل – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## المشكلات الشائعة والنصائح
- **الشكل لا يتغير؟** تأكد من استدعاء `firstRA.set(Asn.WORK_CONTOUR, …)` *قبل* استرجاع البيانات الزمنية.  
- **قيم غير متوقعة؟** تحقق من أن تواريخ بدء وانتهاء المهمة مضبوطة بشكل صحيح في ملف MPP المصدر.  
- **نصيحة الأداء:** أعد استخدام نفس كائن `Project` عند التكرار عبر أشكال متعددة لتجنب عمليات إدخال/إخراج الملفات غير الضرورية.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Tasks مع مكتبات جافا أخرى؟
نعم، يمكن دمج Aspose.Tasks مع مكتبات جافا أخرى لتعزيز قدرات إدارة المشاريع.

### هل Aspose.Tasks مناسب للمشاريع المؤسسية الكبيرة؟
بالطبع، تم تصميم Aspose.Tasks للتعامل مع مشاريع بجميع الأحجام، بما في ذلك المبادرات المؤسسية واسعة النطاق.

### هل يوفر Aspose.Tasks دعمًا لصيغ ملفات مشروع مختلفة؟
نعم، يدعم Aspose.Tasks مجموعة متنوعة من الصيغ مثل MPP، XML، وMPX.

### هل يمكنني تخصيص أشكال العمل وفقًا لمتطلبات مشروعي؟
نعم، يمكنك تعريف أشكال عمل مخصصة لتتناسب مع احتياجات الجدولة المحددة.

### هل هناك منتدى مجتمع يمكنني الحصول فيه على مساعدة بخصوص Aspose.Tasks؟
نعم، يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على الدعم والنقاشات.

---

**آخر تحديث:** 2026-01-10  
**تم الاختبار مع:** Aspose.Tasks for Java (أحدث إصدار)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}