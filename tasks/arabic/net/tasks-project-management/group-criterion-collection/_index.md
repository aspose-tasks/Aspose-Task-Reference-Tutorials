---
title: إدارة معايير مجموعة مشروع MS باستخدام Aspose.Tasks
linktitle: إدارة مجموعة معايير المجموعة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة مجموعة Group Criterion MS Project باستخدام Aspose.Tasks لـ .NET. دليل خطوة بخطوة للمطورين.
weight: 28
url: /ar/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة معايير مجموعة مشروع MS باستخدام Aspose.Tasks

## مقدمة
Aspose.Tasks for .NET عبارة عن واجهة برمجة تطبيقات قوية تتيح للمطورين العمل مع ملفات Microsoft Project برمجيًا. في هذا البرنامج التعليمي، سوف نستكشف كيفية إدارة مجموعة معايير المجموعة داخل MS Project باستخدام Aspose.Tasks.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1.  Aspose.Tasks لـ .NET: تأكد من تثبيت مكتبة Aspose.Tasks في مشروع .NET الخاص بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).

2. ملف Microsoft Project: احصل على ملف Microsoft Project (MPP) جاهز للعمل معه.

## استيراد مساحات الأسماء

أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى كود C# الخاص بك. هذه الخطوة ضرورية للوصول إلى الوظائف التي يوفرها Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## الخطوة 1: تحميل ملف المشروع

 تهيئة أ`Project` كائن عن طريق تحميل ملف MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## الخطوة 2: الوصول إلى معايير المجموعة

استرداد المجموعة من المشروع والوصول إلى معاييرها.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## الخطوة 3: التكرار على معايير المجموعة

قم بمراجعة كل معيار في المجموعة واعرض خصائصه.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## الخطوة 4: مسح معايير المجموعة

امسح معايير المجموعة الموجودة إذا لم تكن للقراءة فقط.

```csharp
group.GroupCriteria.Clear();
```

## الخطوة 5: إضافة معيار جديد

أنشئ معيارًا جديدًا للمجموعة وأضفه إلى المجموعة.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## الخطوة 6: انسخ المعايير إلى مجموعة أخرى

انسخ المعايير من مجموعة إلى أخرى.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إدارة مجموعة Group Criterion MS Project باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك التعامل بشكل فعال مع معايير المجموعة ضمن ملفات Microsoft Project الخاصة بك برمجياً.

## الأسئلة الشائعة

### س1: هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟

ج: نعم، يدعم Aspose.Tasks ملفات Microsoft Project بمختلف الإصدارات، بما في ذلك 2003 و2007 و2010 و2013 و2016.

### س2: هل يمكنني تطبيق معايير متعددة على مجموعة واحدة؟

ج: بالتأكيد، يمكنك إضافة معايير متعددة إلى مجموعة من خلال تكرار كل منها وإضافتها وفقًا لذلك.

### س3: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟

 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).

### س4: أين يمكنني العثور على وثائق Aspose.Tasks؟

 ج: يمكنك الرجوع إلى الوثائق[هنا](https://reference.aspose.com/tasks/net/).

### س5: كيف يمكنني الحصول على الدعم إذا واجهت أية مشكلات؟

 ج: إذا كانت لديك أية أسئلة أو واجهت أي مشكلات، يمكنك طلب الدعم من منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
