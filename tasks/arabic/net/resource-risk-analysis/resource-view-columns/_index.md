---
title: تخصيص أعمدة عرض موارد مشروع MS في Aspose.Tasks
linktitle: تخصيص أعمدة عرض الموارد في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تخصيص أعمدة عرض موارد MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET. إنشاء طرق عرض مخصصة لإدارة أفضل للمشروع.
weight: 17
url: /ar/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تخصيص أعمدة عرض موارد مشروع MS في Aspose.Tasks

## مقدمة
Aspose.Tasks for .NET عبارة عن واجهة برمجة تطبيقات قوية تتيح للمطورين العمل مع ملفات Microsoft Project برمجيًا. إحدى المهام الشائعة في إدارة المشاريع هي تخصيص طرق العرض لعرض معلومات محددة. في هذا البرنامج التعليمي، سنستكشف كيفية تخصيص أعمدة عرض موارد MS Project باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Aspose.Tasks لمكتبة .NET: يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
2. ملف Microsoft Project: احصل على نموذج لملف MS Project سهل الاستخدام للاختبار.
3. بيئة التطوير: بيئة تطوير تم إعدادها باستخدام .NET Framework.
## استيراد مساحات الأسماء
أولاً، لنستورد مساحات الأسماء الضرورية لمشروعنا:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## الخطوة 1: تحميل ملف المشروع
قم بتحميل ملف MS Project باستخدام Aspose.Tasks API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## الخطوة 2: الحصول على الموارد وتحديد الخيارات
بعد ذلك، احصل على المورد الذي تريد تخصيص أعمدته وحدد خيارات حفظ PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## الخطوة 3: تحديد الأعمدة المخصصة
الآن، حدد الأعمدة المخصصة لعرض الموارد. يمكنك تحديد حقول مختلفة وحتى استخدام المفوضين للحسابات المخصصة:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## الخطوة 4: التكرار على الأعمدة
قم بالتكرار على الأعمدة المحددة وعرض خصائصها:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## الخطوة 5: احفظ العرض المخصص
أخيرًا، قم بتعيين العرض المخصص واحفظه كملف PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
باتباع هذه الخطوات، يمكنك تخصيص أعمدة عرض موارد MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET.
## خاتمة
يعد تخصيص أعمدة عرض موارد MS Project أمرًا ضروريًا لعرض المعلومات ذات الصلة المصممة وفقًا لاحتياجات مشروعك. مع Aspose.Tasks for .NET، تصبح هذه المهمة واضحة وفعالة، مما يسمح لك بإنشاء طرق عرض مخصصة دون عناء.
## الأسئلة الشائعة
### هل يمكنني تخصيص طرق العرض لعناصر أخرى إلى جانب الموارد؟
نعم، يسمح Aspose.Tasks بتخصيص المهام والواجبات وعناصر المشروع الأخرى أيضًا.
### هل يدعم Aspose.Tasks حفظ طرق العرض بتنسيقات أخرى غير PDF؟
نعم، يمكنك حفظ العروض بتنسيقات مختلفة مثل XLSX وHTML والصور.
### هل من الممكن تطبيق التنسيق على العرض المخصص؟
بالتأكيد، يوفر Aspose.Tasks خيارات تنسيق واسعة النطاق لتحسين مظهر طرق العرض المخصصة الخاصة بك.
### هل يمكنني تحديث العرض المخصص ديناميكيًا بناءً على تغيير بيانات المشروع؟
نعم، يمكنك تحديث العرض المخصص وإعادة إنشائه كلما تغيرت بيانات المشروع الأساسية.
### هل يدعم Aspose.Tasks التطوير عبر الأنظمة الأساسية؟
يستهدف Aspose.Tasks لـ .NET بشكل أساسي منصات .NET، ولكن هناك أيضًا إصدارات متاحة لـ Java والأنظمة الأساسية الأخرى.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
