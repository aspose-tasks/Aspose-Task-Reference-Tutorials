---
title: العمل مع كائنات OLE في Aspose.Tasks
linktitle: العمل مع كائنات OLE في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية العمل بكفاءة مع كائنات OLE في تطبيقات .NET باستخدام Aspose.Tasks، مما يعزز قدرات إدارة المشروع.
type: docs
weight: 22
url: /ar/net/advanced-concepts/ole-objects/
---
## مقدمة

يوفر Aspose.Tasks for .NET وظائف شاملة للعمل مع كائنات OLE (ربط الكائنات وتضمينها) داخل ملفات المشروع. سيرشدك هذا البرنامج التعليمي خلال عملية إدارة كائنات OLE بكفاءة باستخدام Aspose.Tasks في تطبيقات .NET الخاصة بك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. التثبيت: تأكد من تثبيت Aspose.Tasks for .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).

2. المعرفة الأساسية: تعرف على لغة البرمجة C# ومفاهيم إطار عمل .NET.

3. بيئة التطوير: قم بإعداد بيئة تطوير مناسبة مثل Visual Studio.

## استيراد مساحات الأسماء

أولاً، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظيفة Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;


```

الآن، دعونا نقسم كل مثال إلى خطوات متعددة بتنسيق دليل خطوة بخطوة:

## العمل مع كائنات OLE

### الخطوة 1: تحميل ملف المشروع
```csharp
var project = new Project("TaskImage2010.mpp");
```

### الخطوة 2: الوصول إلى كائنات OLE
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

### الخطوة 3: التكرار عبر كائنات OLE
```csharp
foreach (var oleObject in oleObjects)
{
    // الوصول إلى خصائص كائن OLE وطباعتها
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // تواصل للعقارات الأخرى
}
```

### الخطوة 4: استرداد بايتات المحتوى
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

## مسح كائنات OLE

### الخطوة 1: تحميل ملف المشروع
```csharp
var project = new Project("TaskImage2010.mpp");
```

### الخطوة 2: مسح كائنات OLE
```csharp
project.OleObjects.Clear();
```

### الخطوة 3: حفظ المشروع
```csharp
project.Save("ClearedProject.mpp");
```

## الحصول على خصائص وضع الكائنات المرئية

### الخطوة 1: تحميل ملف المشروع
```csharp
var project = new Project("TaskImage2010.mpp");
```

### الخطوة 2: الوصول إلى كائن OLE وموضع الكائنات المرئية
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

### الخطوة 3: استرداد الخصائص
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية العمل بفعالية مع كائنات OLE في Aspose.Tasks لـ .NET. باتباع هذه الأمثلة خطوة بخطوة، يمكنك دمج إمكانات إدارة كائنات OLE بسلاسة في تطبيقات .NET الخاصة بك، مما يعزز وظائفها وسهولة استخدامها.

## الأسئلة الشائعة

### س١: هل يمكن لـ Aspose.Tasks التعامل مع تنسيقات كائنات OLE المتنوعة؟

ج1: نعم، يدعم Aspose.Tasks نطاقًا واسعًا من تنسيقات كائنات OLE بما في ذلك الصور والمستندات وملفات الوسائط المتعددة.

### س2: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟

ج2: نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، مما يضمن التوافق والتكامل السلس.

### Q3: هل يمكنني معالجة موضع كائن OLE ضمن طرق عرض المشروع؟

ج3: بالتأكيد، يوفر Aspose.Tasks واجهات برمجة التطبيقات (APIs) لإدارة خصائص موضع ومظهر كائنات OLE ضمن طرق عرض المشروع.

### س 4: هل Aspose.Tasks مناسب للمشاريع على مستوى المؤسسة؟

ج4: نعم، يعتبر Aspose.Tasks مناسبًا تمامًا لكل من المشروعات الصغيرة الحجم وعلى مستوى المؤسسات، ويوفر ميزات قوية وأداءً موثوقًا.

### س5: هل يقدم Aspose.Tasks دعم العملاء وموارد التوثيق؟

ج5: نعم، يوفر Aspose.Tasks وثائق ومنتديات ودعمًا مكثفًا للعملاء لمساعدة المطورين في استخدام ميزاته بفعالية.