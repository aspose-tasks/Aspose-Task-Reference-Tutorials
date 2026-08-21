---
date: 2026-03-19
description: تعلم كيفية قراءة الخطوط الأساسية وإدارة خطوط أساس إدارة المشاريع بكفاءة
  باستخدام Aspose.Tasks لـ .NET.
linktitle: Project Management Baselines using Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: خطوط أساس إدارة المشاريع باستخدام Aspose.Tasks
url: /ar/net/advanced-features/assignment-baseline-collection/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# خطوط أساس إدارة المشاريع باستخدام Aspose.Tasks

## المقدمة

في إدارة المشاريع، تُعد خطوط الأساس نقاط مرجعية تتيح لك مقارنة الأداء المخطط به مقابل الأداء الفعلي. يساعد إدارة **خطوط أساس إدارة المشاريع**—وخاصة خطوط أساس التعيين—في الحفاظ على الجداول الزمنية ضمن المسار الصحيح وضمان المساءلة. توفر Aspose.Tasks for .NET واجهة برمجة تطبيقات قوية لإنشاء وقراءة وتحديث وحذف هذه الخطوط برمجيًا. في هذا الدرس، سنستعرض كيفية العمل مع مجموعات خطوط أساس التعيين باستخدام Aspose.Tasks for .NET.

## إجابات سريعة
- **ما هو الغرض الأساسي من خطوط أساس التعيين؟** لتسجيل تواريخ البدء/الانتهاء المخطط لها لكل تعيين مورد.  
- **أي طريقة في API تقرأ خطوط الأساس؟** مجموعة `Assignment.Baselines`.  
- **هل يمكن حذف خطوط الأساس برمجيًا؟** نعم، عن طريق إزالة العناصر من مجموعة `Assignment.Baselines`.  
- **هل أحتاج إلى ترخيص لاستخدام هذه الميزات؟** يتطلب استخدام هذه الميزات ترخيص صالح لـ Aspose.Tasks في بيئة الإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.

## ما هي خطوط أساس إدارة المشاريع؟
خطوط أساس إدارة المشاريع هي لقطات من بيانات الجدول الزمني والتكلفة والنطاق تُؤخذ في نقطة زمنية محددة. تُستخدم كمعيار لقياس أداء المشروع وتحديد الفروقات طوال دورة حياة المشروع.

## لماذا استخدام Aspose.Tasks لخطوط أساس إدارة المشاريع؟
- **تحكم كامل:** الوصول إلى بيانات الخط الأساسي ومعالجتها دون فتح المشروع في Microsoft Project.  
- **جاهزة للأتمتة:** دمج معالجة الخطوط الأساسية في خطوط CI/CD أو أدوات التقارير.  
- **دعم صيغ متعددة:** يعمل مع ملفات MPP وXML وMPX، مما يضمن مرونة عبر صيغ ملفات المشروع المختلفة.  

## المتطلبات المسبقة

قبل المتابعة مع هذا الدرس، تأكد من توفر المتطلبات التالية:

1. معرفة أساسية بلغة البرمجة C#.  
2. تثبيت Visual Studio على نظامك.  
3. مكتبة Aspose.Tasks for .NET مثبتة. يمكنك تنزيلها من [هنا](https://releases.aspose.com/tasks/net/).

## استيراد المساحات الاسمية

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;
```

## الخطوة 1: تحميل ملف المشروع

أولاً، نحتاج إلى تحميل ملف المشروع الذي يحتوي على خطوط أساس التعيين.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## كيف تقرأ خطوط الأساس؟

بعد ذلك، نقوم بالتكرار عبر كل تعيين مورد في المشروع للوصول إلى خطوط الأساس الخاصة به.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## الخطوة 3: حذف خطوط أساس التعيين

في هذه الخطوة، نوضح كيفية حذف جميع خطوط أساس التعيين من المشروع.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **خطوط الأساس تظهر فارغة** | تأكد من أن ملف المشروع يحتوي فعليًا على خطوط أساس محفوظة؛ لا يتم إنشاؤها تلقائيًا. |
| **`NullReferenceException` عند الوصول إلى `baselines.ParentAssignment`** | تحقق من أن كائن التعيين ليس فارغًا وأن خطوط الأساس قد تم تهيئتها. |
| **تباطؤ الأداء في المشاريع الكبيرة** | عالج التعيينات على دفعات أو قم بالتصفيه باستخدام `Assignment.Id` لتقليل النطاق. |

## الخلاصة

إدارة خطوط أساس التعيين بفعالية أمر حيوي في إدارة المشاريع، حيث يضمن الالتزام بالجداول الزمنية وتتبع تقدم المشروع بدقة. مع Aspose.Tasks for .NET، يصبح التعامل مع خطوط أساس التعيين سلسًا، مما يزوّد المطورين بالأدوات اللازمة لتبسيط عمليات إدارة المشاريع.

## الأسئلة المتكررة

### س1: هل يمكن لـ Aspose.Tasks التعامل مع خطوط أساس التعيين لصيغ ملفات مشروع مختلفة؟

**ج1:** نعم، تدعم Aspose.Tasks صيغ ملفات مشروع متعددة، بما في ذلك MPP وXML وMPX، مما يتيح لك إدارة خطوط أساس التعيين عبر أنواع ملفات مختلفة بسهولة.

### س2: هل Aspose.Tasks متوافق مع جميع إصدارات .NET Framework؟

**ج2:** Aspose.Tasks for .NET متوافق مع إصدارات متعددة من .NET Framework، مما يضمن التوافق والمرونة للمطورين عبر بيئات مختلفة.

### س3: هل يمكنني تعديل خطوط أساس التعيين برمجيًا باستخدام Aspose.Tasks؟

**ج3:** بالتأكيد، توفر Aspose.Tasks واجهة برمجة تطبيقات شاملة تمكّن المطورين من إنشاء وقراءة وتحديث وحذف خطوط أساس التعيين برمجيًا وفقًا لمتطلبات المشروع.

### س4: هل تقدم Aspose.Tasks دعمًا فنيًا للمطورين؟

**ج4:** نعم، توفر Aspose.Tasks دعمًا فنيًا قويًا عبر منتدى المجتمع الخاص بها، حيث يمكن للمطورين طلب المساعدة ومشاركة المعرفة والتعاون مع الزملاء.

### س5: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟

**ج5:** نعم، تقدم Aspose.Tasks نسخة تجريبية مجانية، مما يتيح للمطورين استكشاف الميزات والوظائف قبل اتخاذ قرار الشراء.

## الأسئلة المتداولة

**س: كيف أقرأ خطوط الأساس لتعيين محدد؟**  
**ج:** قم بالوصول إلى مجموعة `Assignment.Baselines` لهذا التعيين وتكرارها كما هو موضح في قسم “كيف تقرأ خطوط الأساس؟”.

**س: هل يمكن إضافة خط أساس جديد إلى تعيين موجود؟**  
**ج:** نعم، يمكنك إنشاء كائن `AssignmentBaseline`، تعيين قيمتي `Start` و`Finish`، ثم إضافته إلى مجموعة `Assignment.Baselines`.

**س: هل سيؤثر حذف خطوط الأساس على الجدول الزمني الأصلي؟**  
**ج:** حذف خطوط الأساس يزيل اللقطات المحفوظة فقط؛ الجدول الزمني الحالي (التواريخ الفعلية) يظل دون تغيير.

**س: هل يمكنني تصدير بيانات الخط الأساسي إلى CSV؟**  
**ج:** رغم أن Aspose.Tasks لا توفر تصديرًا مباشرًا إلى CSV للخطوط الأساسية، يمكنك التكرار عبر المجموعة وكتابة القيم إلى ملف CSV باستخدام فئات I/O القياسية في .NET.

**س: هل تدعم Aspose.Tasks تقارير مقارنة الخطوط الأساسية؟**  
**ج:** نعم، يمكنك مقارنة تواريخ الخط الأساسي مع التواريخ الفعلية برمجيًا وإنشاء تقارير مخصصة باستخدام أي مكتبة تقارير تفضلها.

---

**آخر تحديث:** 2026-03-19  
**تم الاختبار مع:** Aspose.Tasks for .NET (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}