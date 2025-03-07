---
title: إدارة مجموعة خصائص المشروع المخصصة في Aspose.Tasks
linktitle: إدارة مجموعة خصائص المشروع المخصصة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة خصائص المشروع المخصصة بشكل فعال في Aspose.Tasks لـ .NET، مما يعزز تجربة إدارة المشروع لديك.
weight: 24
url: /ar/net/calendar-scheduling/custom-project-property-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة مجموعة خصائص المشروع المخصصة في Aspose.Tasks

## مقدمة

هل أنت مستعد لتحسين تجربتك في إدارة المشاريع باستخدام Aspose.Tasks لـ .NET؟ تعد إدارة خصائص المشروع المخصصة جانبًا مهمًا لإدارة المشروع، مما يسمح لك بإضافة بيانات تعريف محددة مصممة خصيصًا لمتطلبات مشروعك. في هذا البرنامج التعليمي، سوف نتعمق في كيفية العمل بفعالية مع مجموعات خصائص المشروع المخصصة باستخدام Aspose.Tasks لـ .NET.

## المتطلبات الأساسية

قبل المتابعة، تأكد من إعداد المتطلبات الأساسية التالية:

1. بيئة Visual Studio: قم بتثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[رابط التحميل](https://releases.aspose.com/tasks/net/).
3. المعرفة الأساسية بـ C#: تعرف على أساسيات لغة البرمجة C#.

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء الضرورية للعمل مع Aspose.Tasks لـ .NET:

```csharp
using Aspose.Tasks;
using System;


```

دعونا نقسم رمز المثال إلى خطوات متعددة لفهم شامل:

## الخطوة 1: تهيئة المشروع

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

تعمل هذه الخطوة على تهيئة مشروع جديد باستخدام Aspose.Tasks.

## الخطوة 2: التحقق من جاهزية مجموعة الخصائص المخصصة

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

يتحقق هذا الرمز مما إذا كانت مجموعة الخصائص المخصصة للقراءة فقط.

## الخطوة 3: إضافة خصائص مخصصة

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

هنا، نضيف خصائص مخصصة إلى المشروع، وندعم الأنواع المنطقية، وDateTime، وDouble، وString.

## الخطوة 4: الوصول إلى الخصائص المخصصة

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

تتيح لنا هذه الحلقة تكرار الخصائص المخصصة وعرض نوعها واسمها وقيمتها.

## الخطوة 5: استرداد قيمة خاصية مخصصة

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

يسترد هذا الرمز قيمة خاصية مخصصة محددة تسمى "الاسم المخصص".

## الخطوة 6: التكرار على أسماء الخصائص المخصصة

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

هنا، نكرر أسماء الخصائص المخصصة ونعرضها.

## الخطوة 7: إزالة أو مسح الخصائص المخصصة

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

يمكنك إزالة خاصية مخصصة معينة حسب اسمها أو مسح المجموعة بأكملها.

## خاتمة

إن إتقان مجموعات خصائص المشروع المخصصة في Aspose.Tasks لـ .NET يمكّنك من إدارة بيانات تعريف المشروع بكفاءة. باتباع هذا الدليل المفصّل خطوة بخطوة، يمكنك دمج الخصائص المخصصة بسلاسة في سير عمل إدارة المشروع لديك، مما يعزز التنظيم والكفاءة.

## الأسئلة الشائعة

### س1: هل يمكنني إضافة خصائص مخصصة لأي نوع بيانات إلى مشروعي باستخدام Aspose.Tasks لـ .NET؟

A1: نعم، يمكنك إضافة خصائص مخصصة تدعم الأنواع المنطقية، وDateTime، وDouble، وString.

### س2: هل من الممكن التكرار على أسماء الخصائص المخصصة في Aspose.Tasks لـ .NET؟

 ج2: بالتأكيد، يمكنك التكرار على أسماء الخصائص المخصصة باستخدام ملف`Names` ملكية.

### س3: كيف يمكنني إزالة خاصية مخصصة معينة من مشروعي؟

 A3: يمكنك إزالة خاصية مخصصة حسب اسمها باستخدام الملف`Remove` طريقة.

### س٤: هل يوفر Aspose.Tasks لـ .NET الدعم للتراخيص المؤقتة؟

ج4: نعم، يمكنك الحصول على ترخيص مؤقت من موقع Aspose لأغراض التقييم.

### س5: أين يمكنني العثور على الدعم أو المساعدة الإضافية فيما يتعلق بـ Aspose.Tasks لـ .NET؟

 ج5: يمكنك زيارة منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15) لأية استفسارات أو مساعدة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
