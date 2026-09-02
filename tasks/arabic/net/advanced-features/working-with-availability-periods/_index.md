---
date: 2026-04-06
description: تعلم كيفية إضافة مورد إلى المشروع وتحديد فترات توافر المورد باستخدام
  Aspose.Tasks لـ .NET. دليل خطوة بخطوة لإدارة تقاويم الموارد.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: العمل مع فترات التوفر في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: إضافة مورد إلى المشروع وتعيين التوافر في Aspose.Tasks
url: /ar/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مورد إلى المشروع وتحديد التوفر في Aspose.Tasks

## مقدمة

في هذا البرنامج التعليمي ستتعلم **كيفية إضافة مورد إلى المشروع** ثم تعريف فترات توافره باستخدام مكتبة Aspose.Tasks .NET. إدارة تقاويم الموارد أمر أساسي لإنشاء جداول زمنية واقعية للمشروعات، وتوضح الخطوات أدناه العملية بالكامل — من إنشاء كائن المشروع إلى طباعة تفاصيل كل فترة.

## إجابات سريعة
- **ما هو الهدف الرئيسي؟** إضافة مورد إلى مشروع وتكوين فترات توافره.  
- **أي مكتبة مطلوبة؟** Aspose.Tasks for .NET.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم الحصول على ترخيص تجاري.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **مدة التنفيذ؟** عادةً أقل من 15 دقيقة للسيناريوهات الأساسية.

## ما هو “إضافة مورد إلى المشروع”؟

إضافة مورد إلى مشروع تُنشئ عنصرًا نائبًا لشخص أو جهاز أو مادة يمكن تعيينها للمهام. بمجرد وجود المورد، يمكنك **تحديد توافر المورد**، تعريف تقويم عمله، والسماح للجدولة باحترام تلك القيود.

## لماذا يتم تكوين جدول العمل وفترات التوفر؟

- **تخطيط دقيق:** تُجدول المهام فقط عندما يكون المورد فعليًا متاحًا.  
- **التحكم في التكلفة:** تعكس وحدات التوافر الجهد الجزئي، مما يساعدك على حساب تكاليف العمالة بدقة.  
- **تسوية الموارد:** يمكن للمحرك تسوية الزيادات تلقائيًا عندما يعرف تقويم كل مورد.

## المتطلبات المسبقة

1. Visual Studio (أو أي بيئة تطوير متوافقة مع .NET).  
2. Aspose.Tasks for .NET – تحميل من [هنا](https://releases.aspose.com/tasks/net/).  
3. معرفة أساسية بلغة C#.

## استيراد المساحات الاسمية

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## كيفية إضافة مورد إلى المشروع؟

### الخطوة 1: إنشاء كائن `Project` جديد

```csharp
var project = new Project();
```

هذا الكائن يمثل ملف المشروع بالكامل في الذاكرة.

### الخطوة 2: إضافة مورد إلى المشروع

```csharp
var resource = project.Resources.Add("Work Resource");
```

النداء يُنشئ **موردًا** باسم *Work Resource* يمكنك لاحقًا ربطه بالمهام.

### الخطوة 3: تعريف فترات التوفر

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` هي طريقة مساعدة (التنفيذ غير معروض) تُعيد مجموعة من كائنات `AvailabilityPeriod`. كل فترة تحدد تاريخ البدء، تاريخ الانتهاء، والوحدات (نسبة الجهد من الوقت الكامل) التي يكون فيها المورد متاحًا.

### الخطوة 4: إضافة الفترات إلى المورد

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

هنا نقوم **بتحديد توافر المورد** عبر حلقة تمر على المجموعة وتضيف كل فترة إلى تقويم المورد.

### الخطوة 5: عرض تفاصيل التوفر

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

مخرجات وحدة التحكم تسمح لك بالتحقق من أن الفترات تم تخزينها بشكل صحيح.

## الأخطاء الشائعة والنصائح

- **دقة التاريخ:** `AvailableFrom` و `AvailableTo` هما قيمتا `DateTime`؛ تأكد من ضبطهما على منتصف الليل إذا كنت تريد فترات يوم كامل.  
- **نطاق الوحدات:** القيم الصالحة هي 0‑100 ٪؛ القيم خارج هذا النطاق ستؤدي إلى استثناء.  
- **فترات متداخلة:** يتم دمج الفترات المتداخلة تلقائيًا، لكن من الأفضل إبقاؤها منفصلة للوضوح.

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.Tasks for .NET في المشاريع التجارية؟
نعم، يمكن استخدام Aspose.Tasks for .NET في المشاريع التجارية. يمكنك شراء ترخيص [هنا](https://purchase.aspose.com/buy).

### س2: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for .NET؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks for .NET [هنا](https://releases.aspose.com/).

### س3: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Tasks for .NET؟
يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/tasks/net/).

### س4: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks for .NET؟
يمكنك الحصول على الدعم من منتدى المجتمع [هنا](https://forum.aspose.com/c/tasks/15).

### س5: هل تقدمون تراخيص مؤقتة لـ Aspose.Tasks for .NET؟
نعم، التراخيص المؤقتة متاحة [هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-04-06  
**تم الاختبار مع:** Aspose.Tasks for .NET (أحدث إصدار ثابت)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}