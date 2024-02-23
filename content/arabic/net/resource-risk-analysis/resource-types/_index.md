---
title: أنواع الموارد في Aspose.Tasks
linktitle: أنواع الموارد في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية العمل مع أنواع مختلفة من الموارد في Aspose.Tasks لـ .NET، بما في ذلك موارد العمل والمواد والتكلفة، من خلال برنامج تعليمي خطوة بخطوة.
type: docs
weight: 14
url: /ar/net/resource-risk-analysis/resource-types/
---
## مقدمة
Aspose.Tasks for .NET هي مكتبة قوية تتيح للمطورين العمل مع ملفات Microsoft Project برمجياً. سواء كنت تدير المهام أو الموارد أو الجداول الزمنية، فإن Aspose.Tasks يبسط العملية من خلال توفير مجموعة شاملة من واجهات برمجة التطبيقات. في هذا البرنامج التعليمي، سوف نتعمق في الأنواع المختلفة من الموارد التي يمكنك استخدامها في مشاريعك باستخدام Aspose.Tasks for .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Visual Studio: قم بتثبيت Visual Studio، وهو بيئة تطوير متكاملة قوية (IDE) لتطوير .NET.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
3. المعرفة الأساسية بـ C#: تعرف على C#، لغة البرمجة المستخدمة لتطوير .NET.

## استيراد مساحات الأسماء
أولاً، لنستورد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Tasks لـ .NET:
```csharp
    
```

## الخطوة 1: إنشاء مثيل مشروع جديد
```csharp
var project = new Project();
```
يقوم هذا السطر بتهيئة كائن مشروع جديد، والذي يعمل كحاوية لجميع البيانات والعمليات المتعلقة بالمشروع.
## الخطوة 2: إضافة مورد العمل
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
هنا، نقوم بإنشاء مورد عمل جديد يسمى "مورد العمل" ونحدد نوعه كـ ResourceType.Work.
## الخطوة 3: إضافة مورد مادي
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
تضيف هذه الخطوة موردًا ماديًا يسمى "مورد المواد" مع تعيين نوعه على ResourceType.Material. بالإضافة إلى ذلك، نحدد علامة المادة بـ "kg" للإشارة إلى وحدة القياس.
## الخطوة 4: إضافة مورد التكلفة
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
وأخيرًا، نقوم بإضافة مورد تكلفة يسمى "مورد التكلفة" ونقوم بتعيين نوعه على أنه ResourceType.Cost. بالإضافة إلى ذلك، قمنا بتعيين قيمة التكلفة إلى 59.99، مما يمثل القيمة النقدية المرتبطة بهذا المورد.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية العمل مع أنواع مختلفة من الموارد في Aspose.Tasks لـ .NET، بما في ذلك موارد العمل والمواد والتكلفة. باتباع الدليل الموضح خطوة بخطوة، يمكنك إدارة الموارد بشكل فعال داخل مشاريعك برمجيًا.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ .NET مع تنسيقات برامج إدارة المشاريع الأخرى؟
ج: نعم، يدعم Aspose.Tasks العديد من التنسيقات، بما في ذلك Microsoft Project (MPP)، وPrimavera P6، والمزيد.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم الفني لـ Aspose.Tasks لـ .NET؟
 ج: يمكنك زيارة منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15) للحصول على المساعدة الفنية.
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك شراء ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س: هل يوفر Aspose.Tasks لـ .NET وثائق كمرجع؟
 ج: نعم، يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/tasks/net/).