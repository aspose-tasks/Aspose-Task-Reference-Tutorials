---
title: إتقان أسعار مشروع MS باستخدام Aspose.Tasks
linktitle: جمع الأسعار في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة الأسعار في ملفات MS Project باستخدام Aspose.Tasks لـ .NET. برنامج تعليمي خطوة بخطوة لإدارة الموارد بشكل فعال.
weight: 11
url: /ar/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان أسعار مشروع MS باستخدام Aspose.Tasks

## مقدمة
مرحبًا بك في برنامجنا التعليمي حول إدارة الأسعار في MS Project باستخدام Aspose.Tasks لـ .NET! في هذا الدليل، سنرشدك خلال عملية التعامل مع المعدلات في ملفات MS Project الخاصة بك باستخدام Aspose.Tasks. سواء كنت مطورًا متمرسًا أو بدأت للتو في تطوير .NET، فإن هذا البرنامج التعليمي سيزودك بتعليمات خطوة بخطوة للتعامل بفعالية مع المعدلات داخل مشروعاتك.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. تم تثبيت Visual Studio
تأكد من تثبيت Visual Studio على نظامك. يمكنك تنزيله من الموقع إذا لم تقم بذلك بالفعل.
### 2. Aspose.Tasks لـ .NET
 قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[موقع إلكتروني](https://releases.aspose.com/tasks/net/).
### 3. المعرفة الأساسية بـ C# و.NET
تعرف على لغة برمجة C# وأساسيات إطار عمل .NET لفهم أمثلة التعليمات البرمجية المتوفرة في هذا البرنامج التعليمي بشكل أفضل.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم باستيراد مساحات الأسماء اللازمة لاستخدام وظائف Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
الآن، دعونا نقسم كل مثال إلى خطوات متعددة:
## الخطوة 1: قم بتحميل ملف MS Project
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 هنا نقوم بإنشاء جديد`Project` كائن عن طريق تحميل ملف MS Project موجود.
## الخطوة 2: إضافة مورد وتعيين العمل والأسعار
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
نقوم بإضافة مورد جديد إلى المشروع، ونقوم بتعيين نوعه كعمل ومبلغ العمل والمعدل القياسي.
## الخطوة 3: إضافة الأسعار إلى المورد
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
نضيف الأسعار إلى المورد الذي يحدد تاريخي البدء والانتهاء، والسعر القياسي، وتنسيق السعر.
## الخطوة 4: طباعة معلومات الأسعار
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
تقوم هذه الخطوة بطباعة معلومات حول الأسعار المرتبطة بالمورد.
## الخطوة 5: تحديث السعر
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
نقوم بتحديث تاريخ انتهاء سعر محدد.
## الخطوة 6: إزالة الأسعار
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
تقوم هذه الخطوة بإزالة كافة المعدلات من نوع معين.
## الخطوة 7: التكرار على المعدلات المتبقية
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
وأخيرًا، نكرر المعدلات المتبقية بعد الإزالة.
## خاتمة
في الختام، قدم لك هذا البرنامج التعليمي دليلاً شاملاً حول إدارة المعدلات في ملفات MS Project باستخدام Aspose.Tasks لـ .NET. باتباع الإرشادات خطوة بخطوة الموضحة في هذا البرنامج التعليمي، يمكنك التعامل بكفاءة مع المعدلات داخل مشروعاتك، مما يضمن إدارة دقيقة للموارد.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ .NET مع برامج إدارة المشاريع الأخرى؟
ج: نعم، يدعم Aspose.Tasks for .NET التكامل مع العديد من برامج إدارة المشاريع، بما في ذلك MS Project وPrimavera والمزيد.
### س: هل يتوافق Aspose.Tasks for .NET مع الإصدارات المختلفة من ملفات MS Project؟
ج: بالتأكيد، يدعم Aspose.Tasks for .NET العمل مع ملفات MS Project ذات الإصدارات المختلفة، مما يضمن المرونة والتوافق.
### س: هل يقدم Aspose.Tasks لـ .NET الوثائق والدعم؟
 ج: نعم، يمكنك العثور على وثائق شاملة والوصول إلى منتديات الدعم على Aspose.Tasks[موقع إلكتروني](https://reference.aspose.com/tasks/net/).
### س: هل يمكنني تجربة Aspose.Tasks لـ .NET قبل الشراء؟
ج: نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Tasks لـ .NET لتقييم ميزاته ومدى توافقه مع متطلباتك.
### س: كيف يمكنني شراء ترخيص Aspose.Tasks لـ .NET؟
 ج: يمكنك شراء ترخيص Aspose.Tasks لـ .NET من[موقع إلكتروني](https://purchase.aspose.com/temporary-license/)، والذي يوفر خيارات ترخيص مرنة لتناسب احتياجاتك.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
