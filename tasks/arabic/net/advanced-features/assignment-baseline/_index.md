---
date: 2026-03-19
description: تعلم كيفية تعيين خط الأساس للمشروع وإدارة خطوط أساس المهام بفعالية باستخدام
  Aspose.Tasks لـ .NET، لضمان تتبع دقيق لتقدم المشروع.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: تعيين خط أساس المشروع – إدارة خط أساس التعيين في Aspose.Tasks
url: /ar/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين خط الأساس للمشروع – إدارة خط الأساس للتعيين في Aspose.Tasks

## المقدمة

عند العمل على مهام إدارة المشاريع، **تعيين خط الأساس للمشروع** أمر أساسي لقياس التقدم الفعلي مقارنةً بالخطة الأصلية. Aspose.Tasks لـ .NET لا يتيح لك فقط **تعيين خط الأساس للمشروع** بل يمنحك أيضًا تحكمًا كاملاً في خطوط أساس التعيينات، مما يتيح تتبعًا دقيقًا للأداء. في هذا الدرس سنستعرض العملية بالكامل — تحميل المشروع، تعيين خط الأساس، قراءة بيانات خط الأساس للتعيينات، ومقارنة الخطوط — لتتمكن من مراقبة مشاريعك بثقة.

## إجابات سريعة
- **ماذا يعني “تعيين خط الأساس للمشروع”؟** يسجل جدول الزمن الأصلي وبيانات التكلفة للمقارنة لاحقًا مع الأداء الفعلي.  
- **أي طريقة API تُعيّن خط الأساس؟** `Project.SetBaseline(BaselineType.Baseline)`.  
- **هل تتطلب خطوط أساس التعيينات استدعاءً منفصلًا؟** لا، يتم تخزينها تلقائيًا عند تعيين خط أساس للمشروع.  
- **ما الصيغ المدعومة؟** MPP، XML، MPX وغيرها عبر Aspose.Tasks.  
- **هل يلزم وجود ترخيص للإنتاج؟** نعم، يلزم ترخيص تجاري للاستخدام غير التجريبي.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- معرفة أساسية ببرمجة C#.  
- Visual Studio (أي نسخة حديثة).  
- مكتبة Aspose.Tasks لـ .NET مضافة إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/tasks/net/).  
- إمكانية الوصول إلى ملف مشروع بصيغة MPP (مثال: `AssignmentBaseline2007.mpp`).

## استيراد المساحات الاسمية

أضف المساحات الاسمية المطلوبة في أعلى ملف C# الخاص بك حتى يعرف المترجم أين يجد فئات Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## الخطوة 1: تحميل المشروع وتعيين خط الأساس للمشروع

أولاً، قم بتحميل ملف MPP الموجود ثم استدعِ `SetBaseline` لت **تعيين خط الأساس للمشروع** لكامل المشروع.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## الخطوة 2: قراءة معلومات خط الأساس للتعيين

بعد تعيين الخط الأساسي، يحتوي كل تعيين مورد على سجلات خط أساس خاصة به. الحلقة أدناه تستخرج وتطبع تلك التفاصيل، بما في ذلك تواريخ البدء/الانتهاء، التكلفة، العمل، وأي بيانات زمنية مُفصَّلة.

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

## الخطوة 3: مقارنة خطوط أساس التعيينات

يمكنك مقارنة خطوط الأساس لتعيينات مختلفة باستخدام عوامل المساواة والمقارنة المدمجة. هذا مفيد عندما تحتاج إلى اكتشاف تغييرات الجدول الزمني أو تجاوزات التكلفة بين المهام.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## المشكلات الشائعة والحلول

| المشكلة | لماذا يحدث | الحل |
|-------|----------------|-----|
| **بيانات خط الأساس تظهر فارغة** | تم فتح ملف المشروع في وضع القراءة فقط أو لم يتم تعيين خط الأساس أبداً. | استدعِ `project.SetBaseline(BaselineType.Baseline)` قبل قراءة خطوط أساس التعيينات. |
| **`NullReferenceException` على `TimephasedData`** | ليست كل خطوط الأساس تحتوي على إدخالات زمنية مفصَّلة. | تحقق دائمًا من `baseline.TimephasedData != null` (كما هو موضح في الشيفرة). |
| **استخراج UID غير صحيح** | قيم UID تختلف بين إصدارات الملفات. | استخدم `ResourceAssignments.GetByUid` مع الـ UID الصحيح أو قم بالتكرار للعثور على التعيين المطلوب. |

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks التعامل مع خطوط أساس متعددة لتعيين واحد؟**  
ج: نعم، يدعم Aspose.Tasks خطوط أساس متعددة لكل تعيين، مما يسمح بتتبع شامل لتقدم المشروع عبر الزمن.

**س: هل Aspose.Tasks متوافق مع صيغ ملفات مشروع مختلفة غير MPP؟**  
ج: نعم، يدعم Aspose.Tasks مجموعة واسعة من صيغ ملفات المشروع، بما في ذلك XML، MPX، وMPP، مما يضمن التوافق مع أدوات إدارة المشاريع المتنوعة.

**س: هل يمكنني تعديل معلومات خط الأساس برمجيًا باستخدام Aspose.Tasks؟**  
ج: بالتأكيد، يوفر Aspose.Tasks واجهات برمجة تطبيقات واسعة لتعديل معلومات الخط الأساسي ديناميكيًا وفقًا لمتطلبات المشروع، مما يمنح مرونة وتحكمًا في عمليات إدارة المشروع.

**س: هل يقدم Aspose.Tasks وثائق وموارد دعم للمطورين؟**  
ج: نعم، يمكن للمطورين الوصول إلى وثائق شاملة، دروس، ومنتديات على موقع Aspose.Tasks، مما يسهل عملية التكامل وحل المشكلات.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks لـ .NET؟**  
ج: نعم، يمكن للمطورين الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من [هنا](https://releases.aspose.com/)، مما يتيح لهم تقييم الميزات والقدرات قبل اتخاذ قرار الشراء.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-19  
**تم الاختبار مع:** Aspose.Tasks 24.12 لـ .NET  
**المؤلف:** Aspose