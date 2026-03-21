---
date: 2026-03-21
description: تعلم كيفية إدارة فترات التوفر للموارد وتحقيق توفر فعال للموارد في المشروع
  باستخدام Aspose.Tasks لـ .NET. يوضح هذا الدليل خطوة بخطوة كيفية إضافة فترات التوفر
  وتحديثها وإزالتها.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: توفر موارد المشروع – إدارة فترات التوفر في Aspose.Tasks
url: /ar/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# توفر موارد المشروع: مجموعة فترات التوفر في Aspose.Tasks

إدارة **توفر موارد المشروع** هي جزء أساسي من التخطيط الناجح للمشروعات. في هذا الدرس ستتعلم **كيفية إدارة التوفر** للموارد باستخدام Aspose.Tasks for .NET API، خطوة بخطوة، بدءًا من تحميل المشروع وحتى نسخ الفترات بين الموارد.

## إجابات سريعة
- **ما هي الفئة الرئيسية لفترات التوفر؟** `AvailabilityPeriod` في مساحة الأسماء `Aspose.Tasks`.  
- **هل يمكنني مسح الفترات الحالية؟** نعم، استدعِ `resource.AvailabilityPeriods.Clear()`.  
- **كيف أضيف فترة جديدة؟** أنشئ كائن `AvailabilityPeriod` واستخدم `Add` أو `Insert`.  
- **هل يمكن نسخ الفترات إلى مورد آخر؟** بالطبع – استخدم `CopyTo` ثم أضف كل عنصر إلى المورد الهدف.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** نعم، يلزم وجود ترخيص تجاري لـ Aspose.Tasks للعمليات غير التجريبية.

## ما هو توفر موارد المشروع؟
يحدد توفر موارد المشروع التواريخ والوحدات (نسبة السعة) التي يمكن فيها تعيين المورد للمهام. من خلال التحكم في هذه الفترات، تمنع الإفراط في التخصيص وتحسن دقة الجدول الزمني.

## لماذا نستخدم Aspose.Tasks لإدارة فترات التوفر؟
- **تكامل كامل مع .NET** – لا تحتاج إلى COM interop، كل شيء Managed.  
- **تحكم دقيق** – ضبط تواريخ البدء/الانتهاء والوحدات الكسرية بدقة.  
- **نسخ سهل** – نقل بيانات التوفر بين الموارد دون الحاجة إلى تحليل يدوي.  
- **أداء محسّن** – يعمل بكفاءة مع ملفات MPP الكبيرة.

## المتطلبات المسبقة
1. **Visual Studio** – أي نسخة حديثة (2019، 2022 أو أحدث).  
2. **Aspose.Tasks for .NET** – حمّلها من [هنا](https://releases.aspose.com/tasks/net/).  
3. **معرفة أساسية بـ C#** – يجب أن تكون مرتاحًا مع الفئات، المجموعات، و LINQ.

## استيراد المساحات الاسم

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

نستورد مساحة الاسم الأساسية `Aspose.Tasks` مع مجموعات .NET القياسية التي سنحتاجها لاحقًا.

## الخطوة 1: تهيئة المشروع والموارد

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

هنا نقوم بتحميل ملف MPP موجود ونستخرج المورد الذي نريد تعديل توفره (المعرف = 1).

## الخطوة 2: مسح فترات التوفر الحالية

```csharp
resource.AvailabilityPeriods.Clear();
```

المسح يزيل أي فترات معرفة مسبقًا، مما يمنحنا لوحة نظيفة للبدء.

## الخطوة 3: إضافة فترات التوفر

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

نسترجع مجموعة من كائنات `AvailabilityPeriod` (يفترض أن الدالة المساعدة `GetPeriods` معرفة في مكان آخر) ونضيف كل واحدة، مع التأكد من أن المجموعة قابلة للكتابة.

## الخطوة 4: إدراج فترة توفر جديدة

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

ينشئ هذا فترة مخصصة للعام 2013 ويُدخلها في الموضع 1 (الخانة الثانية) إذا لم تكن موجودة بالفعل.

## الخطوة 5: عرض فترات التوفر

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

طباعة سريعة على وحدة التحكم تُظهر العدد الإجمالي وتفاصيل كل فترة – مفيدة للتصحيح أو التحقق.

## الخطوة 6: نسخ فترات التوفر إلى مورد آخر

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

ننسخ المجموعة بالكامل إلى مصفوفة، نمسح فترات المورد الهدف، ثم نعيد تعبئتها. يوضح هذا كيفية تكرار بيانات التوفر عبر الموارد.

## الخطوة 7: تحديث وإزالة فترات التوفر

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

هنا نقوم بتعديل `AvailableUnits` للفترة قبل الأخيرة ثم نزيل فترة 2013 التي أضفناها مسبقًا.

## المشكلات الشائعة والحلول
- **خطأ مجموعة للقراءة فقط** – تأكد من أن المشروع ليس مفتوحًا في وضع القراءة فقط أو أنك استدعيت `resource.AvailabilityPeriods.Clear()` قبل إضافة عناصر جديدة.  
- **فترات متداخلة** – لا يقوم Aspose.Tasks بدمج التداخلات تلقائيًا؛ قد تحتاج إلى كتابة منطق مخصص لاكتشافها وحلها.  
- **تنسيق تاريخ غير صحيح** – استخدم دائمًا كائنات `DateTime`؛ قد يتسبب تحليل السلاسل النصية في أخطاء متعلقة باللغات.

## الأسئلة المتكررة

**س: هل يمكنني إضافة حقول مخصصة إلى فترات التوفر؟**  
ج: لا، فترات التوفر في Aspose.Tasks for .NET لا تدعم الحقول المخصصة.

**س: هل ترتبط فترات التوفر بمهام محددة؟**  
ج: لا، فهي مرتبطة بالمورد وتحدد متى يكون المورد متاحًا عمومًا للمهام.

**س: هل يمكنني استيراد فترات التوفر من مصادر خارجية؟**  
ج: نعم، يمكنك استيراد الفترات من CSV أو XML أو قاعدة بيانات بإنشاء كائنات `AvailabilityPeriod` وإضافتها إلى المجموعة.

**س: كيف أتعامل مع فترات التوفر المتداخلة؟**  
ج: لا يتم حل التداخلات تلقائيًا؛ عليك تنفيذ تحقق مخصص لدمج أو رفض الفترات المتضاربة.

**س: هل هناك حد لعدد فترات التوفر التي يمكن أن يمتلكها المورد؟**  
ج: لا يوجد حد ثابت، لكن المجموعات الكبيرة جدًا قد تؤثر على الأداء؛ من الأفضل تجميع الفترات حيثما أمكن.

## الخلاصة

في هذا الدليل غطينا كل ما تحتاجه لإدارة **توفر موارد المشروع** باستخدام Aspose.Tasks for .NET—من تهيئة المشروع ومسح البيانات القديمة، إلى إضافة، إدراج، نسخ، تحديث وإزالة فترات التوفر. إتقان هذه الخطوات يساعدك على الحفاظ على تقاويم الموارد دقيقة وجداول المشروع واقعية.

---

**آخر تحديث:** 2026-03-21  
**تم الاختبار مع:** Aspose.Tasks for .NET (أحدث إصدار)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}