---
title: إدارة خط الأساس للمهمة في Aspose.Tasks
linktitle: إدارة خط الأساس للمهمة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة الخطوط الأساسية للمهمة بكفاءة باستخدام Aspose.Tasks لـ .NET، مما يضمن التتبع الدقيق لتقدم المشروع وأدائه.
weight: 14
url: /ar/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة خط الأساس للمهمة في Aspose.Tasks

## مقدمة

عند العمل على مهام إدارة المشروع، تعد إدارة الخطوط الأساسية للمهمة أمرًا بالغ الأهمية لتتبع التقدم بدقة. يوفر Aspose.Tasks for .NET مجموعة شاملة من الأدوات للتعامل مع الخطوط الأساسية للمهمة بكفاءة. في هذا البرنامج التعليمي، سوف نتعمق في عملية إدارة الخطوط الأساسية للمهمة خطوة بخطوة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على نظامك.
- تمت إضافة Aspose.Tasks لمكتبة .NET إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
- الوصول إلى ملف المشروع بتنسيق MPP.

## استيراد مساحات الأسماء

لبدء العمل مع Aspose.Tasks، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. أضف مساحات الأسماء التالية في بداية ملف C# الخاص بك:

```csharp
using Aspose.Tasks;
using System;


```

## الخطوة 1: تحميل المشروع وتعيين خط الأساس

 أولاً، قم بتحميل ملف المشروع باستخدام ملف`Project` فئة من Aspose.Tasks. ثم قم بتعيين نوع الأساس للمشروع باستخدام`SetBaseline` طريقة.

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## الخطوة 2: قراءة المعلومات الأساسية للمهمة

قم بالتكرار خلال كل تعيين مورد في المشروع واسترجاع المعلومات الأساسية لكل تعيين.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## الخطوة 3: التحقق من المساواة الأساسية

قارن المعلومات الأساسية للمهام المختلفة باستخدام طرق المقارنة المتنوعة التي توفرها Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// التحقق من المساواة الأساسية
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// التحقق من مقارنة خط الأساس
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// عرض رموز التجزئة الأساسية
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## خاتمة

تعد إدارة الخطوط الأساسية للمهمة جزءًا لا يتجزأ من إدارة المشروع، مما يسمح بالتتبع الدقيق للتقدم والأداء. باستخدام Aspose.Tasks for .NET، يصبح التعامل مع الخطوط الأساسية للمهمة مبسطًا وفعالاً، مما يوفر للمطورين أدوات قوية لتحسين سير عمل إدارة المشروع.

## الأسئلة الشائعة

### س1: هل يمكن لـ Aspose.Tasks التعامل مع خطوط أساسية متعددة لمهمة واحدة؟

ج1: نعم، يدعم Aspose.Tasks خطوط أساس متعددة لكل مهمة، مما يسمح بالتتبع الشامل لتقدم المشروع بمرور الوقت.

### س2: هل Aspose.Tasks متوافق مع تنسيقات ملفات المشروع المختلفة بخلاف MPP؟

ج2: نعم، يدعم Aspose.Tasks نطاقًا واسعًا من تنسيقات ملفات المشروع، بما في ذلك XML وMPX وMPP، مما يضمن التوافق مع أدوات إدارة المشروعات المتنوعة.

### س3: هل يمكنني تعديل المعلومات الأساسية برمجياً باستخدام Aspose.Tasks؟

ج3: بالتأكيد، يوفر Aspose.Tasks واجهات برمجة تطبيقات واسعة النطاق لتعديل معلومات خط الأساس ديناميكيًا وفقًا لمتطلبات المشروع، مما يوفر المرونة والتحكم في عمليات إدارة المشروع.

### س4: هل يقدم Aspose.Tasks الوثائق وموارد الدعم للمطورين؟

ج4: نعم، يمكن للمطورين الوصول إلى الوثائق الشاملة والبرامج التعليمية والمنتديات على موقع Aspose.Tasks، مما يسهل التكامل السلس واستكشاف الأخطاء وإصلاحها.

### س5: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟

 ج5: نعم، يمكن للمطورين الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[هنا](https://releases.aspose.com/)مما يسمح لهم بتقييم ميزاته وإمكانياته قبل اتخاذ قرار الشراء.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
