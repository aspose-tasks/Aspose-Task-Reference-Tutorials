---
title: إتقان معايير تصفية مشروع MS باستخدام Aspose.Tasks
linktitle: معايير التصفية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تنفيذ معايير التصفية في MS Project باستخدام Aspose.Tasks لـ .NET. تعزيز كفاءة إدارة المشروع من خلال تحليل البيانات المستهدفة.
type: docs
weight: 18
url: /ar/net/tasks-project-management/filter-criteria/
---
## مقدمة
في مجال إدارة المشاريع، يعد Microsoft Project بمثابة أداة قوية، حيث يقدم عددًا كبيرًا من الميزات لمساعدة مخططي ومديري المشاريع. ومن بين وظائفه العديدة تكمن القدرة على تصفية بيانات المشروع، مما يسمح للمستخدمين بالتركيز على جوانب محددة من مهام مشروعهم. ومع ذلك، فإن إتقان قدرات التصفية هذه يمكن أن يكون مهمة شاقة بدون التوجيه الصحيح. يهدف هذا البرنامج التعليمي إلى إزالة الغموض عن العملية من خلال توفير دليل خطوة بخطوة حول تطبيق معايير التصفية في MS Project باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# ضروري لفهم المفاهيم التي يغطيها هذا البرنامج التعليمي.
2.  تثبيت Aspose.Tasks لـ .NET: تأكد من تثبيت Aspose.Tasks لـ .NET في بيئة التطوير لديك. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
3. ملف Microsoft Project: قم بإعداد ملف Microsoft Project (على سبيل المثال، Project2003.mpp)، والذي ستستخدمه لتنفيذ معايير التصفية.

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية للعمل مع Aspose.Tasks لـ .NET. اتبع الخطوات التالية:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## الخطوة 1: تحميل ملف المشروع
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Explanation: هذا السطر من التعليمات البرمجية يقوم بتهيئة نسخة جديدة من`Project` class ويقوم بتحميل ملف Microsoft Project المحدد بواسطة مساره.
## الخطوة 2: استرداد عامل تصفية المهام
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Explanation: هنا، نقوم باسترجاع مرشح المهام من المشروع. ضبط الفهرس (`[1]`) وفقًا لمتطلباتك لتحديد الفلتر المطلوب.
## الخطوة 3: عرض صفوف المعايير
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Explanation: يتكرر هذا القسم خلال كل صف معايير لمرشح التصفية ويعرض المجال والعملية والاختبار والقيم الخاصة به (إن وجدت).
## الخطوة 4: طباعة معايير التصفية
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Explanation: طباعة عملية معايير التصفية.
## الخطوة 5: عرض تفاصيل المعايير
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Explanation: يقوم هذا الجزء باسترجاع وعرض معلومات تفصيلية حول كل صف معايير، مما يوفر معلومات حول توصيف عامل التصفية.

## خاتمة
يعد إتقان معايير التصفية في MS Project باستخدام Aspose.Tasks لـ .NET مهارة قيمة يمكنها تحسين كفاءة إدارة المشروع بشكل كبير. باتباع هذا البرنامج التعليمي، تعلمت كيفية التعامل مع معايير التصفية برمجيًا، مما يمكّنك من تخصيص طرق عرض المشروع وفقًا لاحتياجاتك المحددة.
## الأسئلة الشائعة
### س: هل يمكنني تطبيق مرشحات متعددة في وقت واحد في MS Project؟
ج: نعم، يمكنك الجمع بين عوامل تصفية متعددة لتحسين بيانات مشروعك بشكل أكبر.
### س: هل يدعم Aspose.Tasks الإصدارات الأقدم من ملفات Microsoft Project؟
ج: نعم، يوفر Aspose.Tasks التوافق مع الإصدارات السابقة، مما يسمح لك بالعمل مع إصدارات مختلفة من ملفات Microsoft Project.
### س: هل Aspose.Tasks متوافق مع أطر عمل .NET الأخرى؟
ج: يدعم Aspose.Tasks .NET Framework و.NET Core و.NET Standard، مما يضمن المرونة عبر بيئات التطوير المختلفة.
### س: هل يمكنني تخصيص معايير التصفية بناءً على الشروط الديناميكية؟
ج: بالتأكيد، يمكنك ضبط معايير التصفية برمجيًا استنادًا إلى المعلمات الديناميكية، مما يتيح تحليل بيانات المشروع التكيفي.
### س: أين يمكنني طلب المساعدة إذا واجهت مشاكل مع Aspose.Tasks؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لطلب الدعم من المجتمع أو التواصل مباشرة مع دعم Aspose.Tasks للحصول على مساعدة شخصية.