---
date: 2026-01-15
description: تعلم كيفية حفظ المشروع كملف PDF وعرض مشاهد استخدام الموارد والورقة في
  MS Project باستخدام Aspose.Tasks للغة Java. اتبع دليلنا خطوة بخطوة لتصدير المشروع
  إلى PDF بسهولة.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: حفظ المشروع كملف PDF – عرض استخدام الموارد وعرض الورقة في Aspose.Tasks
url: /ar/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ المشروع كملف PDF – عرض استهلاك الموارد وعرض الورقة في Aspose.Tasks

## المقدمة
في هذا الدرس ستكتشف كيفية **حفظ المشروع كملف PDF** مع عرض استهلاك الموارد وعرض الورقة لملف Microsoft Project. سواء كنت بحاجة إلى إنشاء تقرير قابل للطباعة لأصحاب المصلحة أو تحويل ملفات MPP إلى تنسيق يمكن للجميع مشاهدته، فإن Aspose.Tasks for Java يجعل العملية بسيطة—دون الحاجة لتثبيت Microsoft Project.

## إجابات سريعة
- **ما الذي يفعله “حفظ المشروع كملف pdf”؟** يقوم بتحويل ملف مشروع (MPP) إلى مستند PDF مع الحفاظ على العرض المحدد.  
- **أي عرض يمكن تصديره؟** استهلاك الموارد، الورقة، المخطط الزمني (Gantt)، استهلاك المهام، وأكثر.  
- **هل يمكنني تغيير مقياس الزمن في PDF؟** نعم—الخيارات تشمل الأيام (Days)، أجزاء من الشهور (ThirdsOfMonths)، والشهور (Months).  
- **هل أحتاج إلى تثبيت Microsoft Project؟** لا، Aspose.Tasks يعمل بشكل مستقل.  
- **هل يلزم وجود ترخيص للاستخدام في الإنتاج؟** نعم، يلزم الحصول على ترخيص تجاري للاستخدام غير التجريبي.

## ما هو “حفظ المشروع كملف PDF”؟
حفظ المشروع كملف PDF يُنشئ تمثيلًا ثابتًا وعالي الدقة لعرض مشروع مختار. هذا مثالي للمشاركة مع العملاء، الأرشفة، أو الطباعة دون كشف ملف المشروع الأصلي.

## لماذا نستخدم Aspose.Tasks لتصدير المشروع إلى PDF؟
- **لا توجد تبعيات خارجية** – يعمل على أي منصة تدعم Java.  
- **تحكم دقيق** – يمكنك اختيار العرض، مقياس الزمن، والتخطيط.  
- **دقة عالية** – يعكس PDF مظهر عرض المشروع الأصلي.  
- **جاهز للأتمتة** – يمكن دمجه في خطوط CI، خدمات التقارير، أو محولات الدفعات.

## المتطلبات المسبقة
قبل المتابعة، تأكد من وجود:

1. **Java Development Kit (JDK)** – يوصى بأحدث نسخة.  
2. **Aspose.Tasks for Java** – قم بالتحميل من [صفحة التحميل](https://releases.aspose.com/tasks/java/).  

## استيراد الحزم
أولاً، استورد الفئات الضرورية إلى مشروع Java الخاص بك:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## دليل خطوة بخطوة

### الخطوة 1: قراءة مشروع المصدر
حمّل ملف MPP الذي تريد تحويله.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### الخطوة 2: تعريف SaveOptions مع المقياس الزمني المطلوب (تصدير المشروع إلى PDF)
قم بتكوين خيارات تصدير PDF وحدد مقياس الزمن المطلوب.  
*هنا نستخدم **Days** كمثال.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### الخطوة 3: تعيين تنسيق العرض إلى ResourceUsage
اختر العرض الذي تريد تصييره. في هذه الحالة، عرض **Resource Usage**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### الخطوة 4: حفظ المشروع (تحويل MPP إلى PDF)
نفّذ التحويل وأنشئ ملف PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### الخطوة 5: عرض المشاهد لإعدادات مقياس زمني أخرى (تغيير مقياس الزمن في PDF)
كرر الخطوات السابقة لإنتاج ملفات PDF بمقاييس زمنية مختلفة مثل **ThirdsOfMonths** و **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## المشكلات الشائعة والحلول
- **أخطاء عدم العثور على الملف** – تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن اسم ملف MPP مطابق تمامًا.  
- **إخراج PDF فارغ** – تأكد من أن `PresentationFormat` يطابق عرضًا يحتوي على بيانات (مثل ResourceUsage).  
- **مقياس زمن غير صحيح** – تأكد من استدعاء `options.setTimescale()` قبل كل `project.save()`.

## الأسئلة المتكررة

### هل يمكن لـ Aspose.Tasks عرض مشاهد أخرى غير استهلاك الموارد والورقة؟
يدعم Aspose.Tasks عرض مشاهد متعددة مثل مخطط Gantt، استهلاك المهام، وعروض التقويم، وغيرها.

### هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟
نعم، يدعم Aspose.Tasks مجموعة واسعة من صيغ ملفات Microsoft Project، بما في ذلك صيغ MPP، MPT، وXML.

### هل يمكنني تخصيص مظهر المشاهد المعروضة باستخدام Aspose.Tasks؟
بالطبع! يوفر Aspose.Tasks خيارات واسعة لتخصيص المظهر والتخطيط للمشاهد المعروضة لتلبية متطلباتك الخاصة.

### هل يتطلب Aspose.Tasks تثبيت Microsoft Project على النظام؟
لا، Aspose.Tasks مكتبة مستقلة ولا تحتاج إلى تثبيت Microsoft Project لتعمل.

### هل يتوفر دعم فني لمستخدمي Aspose.Tasks؟
نعم، يمكن لمستخدمي Aspose.Tasks الحصول على الدعم الفني عبر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-01-15  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

---