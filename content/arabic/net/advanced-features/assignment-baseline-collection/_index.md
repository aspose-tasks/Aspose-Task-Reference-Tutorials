---
title: مجموعة من الخطوط الأساسية للمهمة في Aspose.Tasks
linktitle: مجموعة من الخطوط الأساسية للمهمة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة الخطوط الأساسية للمهمة بكفاءة في إدارة المشاريع باستخدام Aspose.Tasks لـ .NET. تعزيز الإنتاجية والدقة.
type: docs
weight: 15
url: /ar/net/advanced-features/assignment-baseline-collection/
---
## مقدمة

في مجال إدارة المشاريع، يعد تتبع وإدارة الخطوط الأساسية للمهمة أمرًا بالغ الأهمية لضمان نجاح المشروع والالتزام بالجداول الزمنية. يقدم Aspose.Tasks for .NET مجموعة قوية من الميزات لتسهيل المعالجة الفعالة للخطوط الأساسية للمهمة داخل المشاريع. في هذا البرنامج التعليمي، سوف نتعمق في تعقيدات العمل مع مجموعات Assignment Baseline Collections باستخدام Aspose.Tasks لـ .NET.

## المتطلبات الأساسية

قبل متابعة هذا البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

1. المعرفة الأساسية بلغة البرمجة C#.
2. تم تثبيت Visual Studio على نظامك.
3.  تم تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).

## استيراد مساحات الأسماء

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;


```

## الخطوة 1: تحميل ملف المشروع

أولاً، نحتاج إلى تحميل ملف المشروع الذي يحتوي على الخطوط الأساسية للمهمة.

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## الخطوة 2: قراءة الخطوط الأساسية للمهمة

بعد ذلك، نقوم بالتكرار خلال كل تعيين موارد في المشروع للوصول إلى خطوط الأساس الخاصة بكل منها.

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

## الخطوة 3: حذف الخطوط الأساسية للمهمة

في هذه الخطوة، نوضح كيفية حذف جميع الخطوط الأساسية للمهمة من المشروع.

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

## خاتمة

تعد الإدارة الفعالة للخطوط الأساسية للمهمة أمرًا بالغ الأهمية في إدارة المشروع، مما يضمن الالتزام بالجداول الزمنية وتتبع تقدم المشروع بدقة. باستخدام Aspose.Tasks for .NET، يصبح التعامل مع الخطوط الأساسية للمهمة سلسًا، مما يوفر للمطورين الأدوات اللازمة لتبسيط عمليات إدارة المشروع.

## الأسئلة الشائعة

### س1: هل يمكن لـ Aspose.Tasks التعامل مع الخطوط الأساسية للمهمة لتنسيقات ملفات المشروع المختلفة؟

ج1: نعم، يدعم Aspose.Tasks تنسيقات ملفات المشروع المختلفة، بما في ذلك MPP وXML وMPX، مما يسمح لك بإدارة الخطوط الأساسية للمهمة عبر أنواع الملفات المختلفة دون عناء.

### س2: هل Aspose.Tasks متوافق مع كافة إصدارات .NET Framework؟

ج2: يتوافق Aspose.Tasks for .NET مع إصدارات متعددة من .NET Framework، مما يضمن التوافق والمرونة للمطورين عبر بيئات مختلفة.

### س3: هل يمكنني معالجة الخطوط الأساسية للمهمة برمجيًا باستخدام Aspose.Tasks؟

ج3: بالتأكيد، يوفر Aspose.Tasks واجهة برمجة تطبيقات شاملة تمكن المطورين من إنشاء الخطوط الأساسية للمهمة وقراءتها وتحديثها وحذفها برمجيًا وفقًا لمتطلبات المشروع.

### س4: هل يقدم Aspose.Tasks الدعم الفني للمطورين؟

ج4: نعم، توفر Aspose.Tasks دعمًا فنيًا قويًا من خلال منتدى المجتمع الخاص بها، حيث يمكن للمطورين طلب المساعدة ومشاركة المعرفة والتعاون مع أقرانهم.

### س5: هل يمكنني تجربة Aspose.Tasks قبل إجراء عملية الشراء؟

ج5: نعم، يقدم Aspose.Tasks إصدارًا تجريبيًا مجانيًا، مما يسمح للمطورين باستكشاف ميزاته ووظائفه قبل اتخاذ قرار الشراء.