---
title: إتقان طرق عرض استخدام المهام في Aspose.Tasks لـ .NET
linktitle: تكوين طرق عرض استخدام المهام في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: استكشف Aspose.Tasks لـ .NET وتعرف على كيفية تكوين طرق عرض استخدام المهام. قم بتخصيص إعدادات الجدول الزمني وتحسين صور إدارة مشروعك.
type: docs
weight: 24
url: /ar/net/task-table-management/task-usage-views/
---
## مقدمة
في مجال إدارة المشاريع، يعد تصور استخدام المهام أمرًا محوريًا للتخطيط والتنفيذ الفعال. يوفر Aspose.Tasks for .NET حلاً قويًا لعرض طرق عرض استخدام المهام، مما يسمح لك بتخصيص إعدادات النطاق الزمني وتنسيقات العرض التقديمي. في هذا البرنامج التعليمي، سنتعرف على خطوات تكوين طرق عرض استخدام المهام باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks for .NET: تأكد من أن مكتبة Aspose.Tasks مدمجة في مشروع .NET الخاص بك. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
2. بيئة .NET: قم بإعداد بيئة .NET عاملة على جهازك.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Tasks. أضف الأسطر التالية إلى الكود الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## الخطوة 1: قم بتعيين مسار دليل المستندات
 قبل العمل مع وظائف Aspose.Tasks، قم بتعيين المسار إلى دليل المستندات الخاص بك. يستبدل`"Your Document Directory"` مع المسار الفعلي
```csharp
String DataDir = "Your Document Directory";
```
## الخطوة 2: تحميل المشروع
 تهيئة Aspose.Tasks`Project` كائن عن طريق تحميل ملف المشروع الخاص بك (على سبيل المثال، TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## الخطوة 3: تحديد SaveOptions
 إنشاء`SaveOptions`كائن لتحديد خيارات العرض. اضبط الجدول الزمني على "أيام" وتنسيق العرض التقديمي على "TaskUsage".
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## الخطوة 4: احفظ باستخدام مقياس الأيام
احفظ المشروع باستخدام إعدادات الجدول الزمني المحددة مسبقًا لـ "الأيام".
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## الخطوة 5: احفظ باستخدام مقياس ThirdsOfMonths الزمني
قم بتغيير إعدادات الجدول الزمني إلى "ThirdsOfMonths" واحفظ المشروع.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## الخطوة 6: احفظ باستخدام الجدول الزمني للأشهر
اضبط الجدول الزمني على "أشهر" واحفظ المشروع بالإعدادات المحدثة.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## خاتمة
يعد تكوين طرق عرض استخدام المهام باستخدام Aspose.Tasks لـ .NET عملية مباشرة. من خلال تخصيص إعدادات الجدول الزمني، يمكنك تخصيص تصور مهام مشروعك وفقًا لاحتياجاتك المحددة.
 لا تتردد في استكشاف المزيد من الميزات والوظائف في[توثيق](https://reference.aspose.com/tasks/net/).
## أسئلة مكررة
### هل يمكنني تخصيص الجدول الزمني بما يتجاوز الإعدادات المحددة مسبقًا؟
نعم، يمكنك تعيين مقياس زمني مخصص عن طريق تحديد الفواصل الزمنية والوحدات.
### هل هناك تنسيقات عرض أخرى متاحة؟
يدعم Aspose.Tasks تنسيقات العروض التقديمية المتنوعة، بما في ذلك GanttChart وResourceUsage والمزيد.
### هل Aspose.Tasks متوافق مع تنسيقات ملفات المشروع المختلفة؟
نعم، يدعم Aspose.Tasks تنسيقات ملفات المشاريع الشائعة مثل MPP، وXML، وCSV.
### هل يمكنني تطبيق إعدادات مقياس زمني مختلفة على مهام محددة؟
بالتأكيد، يمكنك تخصيص إعدادات الجدول الزمني للمهام الفردية داخل مشروعك.
### كيف يمكنني الحصول على الدعم أو طلب المساعدة بخصوص Aspose.Tasks؟
 قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم وتوجيه المجتمع.