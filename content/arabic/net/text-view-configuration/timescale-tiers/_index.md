---
title: تكوين طبقات النطاق الزمني لمخطط جانت في Aspose.Tasks
linktitle: تكوين طبقات الجدول الزمني في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: استكشف Aspose.Tasks لـ .NET لتكوين طبقات الجدول الزمني في طريقة عرض Gantt Chart للحصول على تصور دقيق للمخطط الزمني للمشروع. #Aspose.Tasks #MS Project
type: docs
weight: 16
url: /ar/net/text-view-configuration/timescale-tiers/
---
## مقدمة
في المشهد الديناميكي لإدارة المشاريع، يعد التصور الفعال أمرًا بالغ الأهمية لفهم الجداول الزمنية والمواعيد النهائية. يوفر Aspose.Tasks for .NET مجموعة أدوات قوية، وفي هذا البرنامج التعليمي، سنستكشف كيفية تكوين طبقات الجدول الزمني للحصول على التمثيل الأمثل في طريقة عرض مخطط جانت. اتبع هذه التعليمات خطوة بخطوة لتحسين تصور مشروعك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بـ C# و.NET.
-  تم تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
- بيئة تطوير تم إعدادها لتطوير تطبيقات .NET.
## استيراد مساحات الأسماء
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
الآن، دعونا نحلل كل خطوة من المثال المقدم.
## الخطوة 1: تهيئة المشروع وإضافة روابط المهام
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
هنا، نقوم بإنشاء مشروع وإنشاء روابط المهام بين "المهمة 1" و"المهمة 2".
## الخطوة 2: تكوين عرض مخطط جانت
```csharp
var view = (GanttChartView)project.DefaultView;
```
قم بالوصول إلى عرض مخطط جانت للتخصيص.
## الخطوة 3: ضبط مستوى النطاق الزمني الأوسط
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
قم بتخصيص طبقة النطاق الزمني الأوسط لعرض الأسابيع باستخدام تسميات ومحاذاة محددة.
## الخطوة 4: إضافة أعلى مستوى للجدول الزمني
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
أضف طبقة مقياس زمني عليا لتمثيل الأشهر.
## الخطوة 5: تخصيص تواريخ الطبقة المتوسطة
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
قم بتخصيص تسميات الشهر للحصول على تصور أفضل.
## الخطوة 6: تحديد الجدول الزمني للمشروع
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
تحديد الجدول الزمني للمشروع للتحكم في الجدول الزمني العام.
## الخطوة 7: احفظ المشروع بمقياس زمني مخصص
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
احفظ المشروع بإعدادات الجدول الزمني المحددة.
## خاتمة
في الختام، يتيح تكوين طبقات النطاق الزمني في Aspose.Tasks لـ .NET تمثيلًا أكثر تفصيلًا وجاذبية للجداول الزمنية للمشروع. تمكنك هذه الخطوات من إنشاء طريقة عرض مخطط جانت التي تلبي احتياجات إدارة مشروعك بدقة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks مع مكتبات .NET الأخرى؟
نعم، يتكامل Aspose.Tasks بسلاسة مع مكتبات .NET الأخرى، مما يوفر المرونة في حزمة التطوير الخاصة بك.
### هل الترخيص المؤقت متاح لأغراض الاختبار؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) للتقييم.
### هل توجد خيارات تخصيص إضافية لعرض مخطط جانت؟
بالتأكيد، يوفر Aspose.Tasks خيارات تخصيص واسعة النطاق لعرض Gantt Chart ليناسب متطلبات المشروع المتنوعة.
### هل يمكنني تقديم الجداول الزمنية بتنسيقات مختلفة؟
بالتأكيد، يمكنك استكشاف التنسيقات والأنماط المختلفة لتمثيل الجدول الزمني بما يتناسب بشكل أفضل مع سياق مشروعك.
### هل يوجد منتدى مجتمعي لدعم Aspose.Tasks؟
 نعم قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع والمناقشات.