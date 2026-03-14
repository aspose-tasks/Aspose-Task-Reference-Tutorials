---
date: 2026-03-14
description: تعلم كيفية استخدام القيم البوليانية القابلة للـ null في Aspose.Tasks
  لـ .NET، بما في ذلك تحويل القيم البوليانية القابلة للـ null وتعيين خصائص البوليان
  القابلة للـ null.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية استخدام القيم البوليانية القابلة للـ null في Aspose.Tasks
url: /ar/net/advanced-concepts/nullable-booleans/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام القيم المنطقية القابلة للعدم في Aspose.Tasks

في هذا البرنامج التعليمي سنوضح **كيفية استخدام القيم القابلة للعدم** عند العمل مع Aspose.Tasks .NET API. القيم المنطقية القابلة للعدم توفر لك ثلاث حالات ممكنة — `true`، `false`، أو *غير معرف* — وهو مفيد بشكل خاص لإعدادات مستوى المشروع التي قد لا يتم تحديدها صراحةً. سترى كيفية إنشاء، تحويل، و**تعيين القيم المنطقية القابلة للعدم**، ولماذا يمكن أن يمنع التعامل الصحيح مع هذه القيم سلوكًا غير متوقع في تطبيقات الجدولة الخاصة بك.

## إجابات سريعة
- **ما هي القيمة المنطقية القابلة للعدم؟** نوع يمكنه احتواء `true`، `false`، أو أن يكون غير معرف.  
- **لماذا نستخدم القيم المنطقية القابلة للعدم في Aspose.Tasks؟** تسمح لك بتمثيل خصائص المشروع الاختيارية دون تخمين قيمة افتراضية.  
- **كيف يمكن تحويل قيمة منطقية قابلة للعدم إلى bool عادي؟** استخدم التحويل الضمني أو تحقق من `IsDefined` أولاً.  
- **ما هو الصنف الأساسي؟** `NullableBool` في مساحة الأسماء `Aspose.Tasks`.  
- **هل أحتاج إلى رخصة؟** نعم، يلزم وجود رخصة صالحة لـ Aspose.Tasks للاستخدام في بيئة الإنتاج.

## ما هي القيمة المنطقية القابلة للعدم؟

القيمة المنطقية القابلة للعدم (`NullableBool`) توسع النوع العادي `bool` بإضافة علم *IsDefined*. عندما يكون `IsDefined` مساويًا لـ `false`، تُعتبر القيمة غير معرفة، مما يتيح لك التمييز بين “false” و“غير محدد”.

## لماذا التعامل مع القيم المنطقية القابلة للعدم في إعدادات المشروع؟

العديد من خيارات المشروع — مثل **ActualsInSync** أو **HonorConstraints** — هي اختيارية. استخدام `bool` عادي يجبرك على اختيار `true` أو `false`، مما قد يتجاوز نية المستخدم عن غير قصد. من خلال **معالجة القيم المنطقية القابلة للعدم**، تحتفظ بالحالة الأصلية وتتفادى تغييرات التكوين غير المقصودة.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

1. **Visual Studio** (أو أي بيئة تطوير متوافقة مع .NET).  
2. **Aspose.Tasks for .NET** – قم بتنزيله من [here](https://releases.aspose.com/tasks/net/).

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

الآن دعنا نستعرض كل مثال خطوة بخطوة.

## العمل مع `NullableBool`

### الخطوة 1: إنشاء كائن `Project` جديد.

```csharp
var project = new Project();
```

### الخطوة 2: إنشاء كائن `NullableBool` بالقيم المحددة.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### الخطوة 3: فحص القيمة وحالة التعريف لكائن `NullableBool`.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### الخطوة 4: **تعيين القيمة المنطقية القابلة للعدم** على المشروع.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### الخطوة 5: إنشاء كائن `NullableBool` آخر بقيمة واحدة.

```csharp
var honorConstraints = new NullableBool(true);
```

### الخطوة 6: عرض تمثيل السلسلة لكائن `NullableBool`.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### الخطوة 7: استخدام مثيل `NullableBool` عن طريق تعيينه في المشروع.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## مقارنة مثيلات `NullableBool`

### الخطوة 1: إنشاء كائنين `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### الخطوة 2: فحص تمثيل السلسلة لكل كائن `NullableBool`.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### الخطوة 3: تحويل ضمني إلى `bool` وطباعة النتيجة.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### الخطوة 4: مقارنة كائنين `NullableBool` للتساوي.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## الحصول على رمز التجزئة لـ `NullableBool`

### الخطوة 1: إنشاء كائنين `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### الخطوة 2: طباعة رمز التجزئة لكل كائن `NullableBool`.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## الأخطاء الشائعة والنصائح

- **لا تفترض أبدًا أن القيمة المنطقية القابلة للعدم معرفة.** تحقق دائمًا من `IsDefined` قبل استخدام `Value`.  
- **التحويل إلى bool عادي** دون فحص قد يسبب استثناءً إذا كانت القيمة غير معرفة. استخدم التحويل الضمني فقط عندما تكون متأكدًا من تعريفها.  
- **عند تعيين خصائص المشروع**، استخدم طريقة `Set` مع `NullableBool` للحفاظ على الحالة غير المعرفة إذا لزم الأمر.

## الأسئلة المتكررة

**س: ما هي القيمة المنطقية القابلة للعدم؟**  
ج: يمكن للقيمة المنطقية القابلة للعدم تمثيل `true`، `false`، أو حالة غير معرفة، مما يتيح ثلاث نتائج متميزة.

**س: كيف يمكنني تحويل قيمة منطقية قابلة للعدم إلى bool عادي بأمان؟**  
ج: تحقق أولاً من `IsDefined`، ثم استخدم الخاصية `Value` أو اعتمد على التحويل الضمني عندما تكون متأكدًا من تعريفها.

**س: لماذا يجب أن أستخدم القيم المنطقية القابلة للعدم بدلاً من bool العادي في Aspose.Tasks؟**  
ج: لأنها تتيح لك الحفاظ على إعدادات المشروع الاختيارية دون تعديلها، مما يمنع التجاوزات غير المقصودة.

**س: هل يمكنني تعيين قيمة منطقية قابلة للعدم لتكون غير معرفة؟**  
ج: نعم — استخدم المُنشئ الذي يقبل علم التعريف فقط، مثل `new NullableBool(false, false)`.

**س: أين يمكنني العثور على مزيد من الوثائق حول Aspose.Tasks لـ .NET؟**  
ج: يمكنك العثور على وثائق مفصلة [here](https://reference.aspose.com/tasks/net/).

**آخر تحديث:** 2026-03-14  
**تم الاختبار مع:** Aspose.Tasks for .NET (أحدث إصدار)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}