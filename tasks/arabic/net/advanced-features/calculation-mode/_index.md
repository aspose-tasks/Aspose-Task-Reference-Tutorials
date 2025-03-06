---
title: وضع الحساب في Aspose.Tasks
linktitle: وضع الحساب في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة أوضاع الحساب بشكل فعال في Aspose.Tasks لـ .NET لتبسيط جدولة المشروع وتبعيات المهام.
type: docs
weight: 29
url: /ar/net/advanced-features/calculation-mode/
---
## مقدمة

Aspose.Tasks for .NET عبارة عن واجهة برمجة تطبيقات قوية تتيح للمطورين العمل مع ملفات Microsoft Project برمجيًا في تطبيقات .NET الخاصة بهم. أحد الجوانب الحاسمة للعمل مع ملفات المشروع هو إدارة أوضاع الحساب، التي تحدد كيفية حساب المهام وجداول المشروع وتحديثها. في هذا البرنامج التعليمي، سوف نتعمق في أوضاع الحساب المختلفة التي يدعمها Aspose.Tasks لـ .NET ونوضح كيفية استخدامها بفعالية.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. Visual Studio: تأكد من تثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لبرمجة C#: تعرف على مفاهيم برمجة C#.

## استيراد مساحات الأسماء

قبل أن نبدأ العمل مع Aspose.Tasks لـ .NET، فلنستورد مساحات الأسماء الضرورية:

```csharp
using Aspose.Tasks;
using System;


```

## تطبيق وضع الحساب التلقائي

### الخطوة 1: إنشاء مثيل مشروع جديد

 تهيئة جديدة`Project` الكائن وتعيينه`CalculationMode` الملكية ل`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### الخطوة 2: تحديد تاريخ بدء المشروع وإضافة المهام

تحديد تاريخ بدء المشروع وإضافة المهام إليه.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### الخطوة 3: ربط المهام

إنشاء التبعيات بين المهام.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### الخطوة 4: التحقق من التواريخ المعاد حسابها

تحقق مما إذا كان قد تم إعادة حساب التواريخ تلقائيًا.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// أضف المزيد من عمليات التحقق حسب الحاجة
```

## تطبيق وضع الحساب اليدوي

### الخطوة 1: إنشاء مثيل مشروع جديد

 تهيئة جديدة`Project` الكائن وتعيينه`CalculationMode` الملكية ل`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### الخطوة 2: تحديد تاريخ بدء المشروع وإضافة المهام

تحديد تاريخ بدء المشروع وإضافة المهام إليه.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### الخطوة 3: التحقق من خصائص المهمة

تحقق مما إذا تم تعيين خصائص المهمة بشكل صحيح في الوضع اليدوي.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// أضف المزيد من عمليات التحقق حسب الحاجة
```

### الخطوة 4: ربط المهام والتحقق من التواريخ

قم بربط المهام معًا وتحقق من عدم إعادة حساب تواريخها.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## تطبيق لا شيء وضع الحساب

### الخطوة 1: إنشاء مثيل مشروع جديد

 تهيئة جديدة`Project` الكائن وتعيينه`CalculationMode` الملكية ل`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### الخطوة 2: إضافة مهمة جديدة

إضافة مهمة جديدة إلى المشروع.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### الخطوة 3: التحقق من خصائص المهمة

تحقق مما إذا لم يتم حساب خصائص المهمة تلقائيًا.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// أضف المزيد من عمليات التحقق حسب الحاجة
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا أوضاع الحساب المتوفرة في Aspose.Tasks لـ .NET وتعلمنا كيفية تطبيقها في سيناريوهات عملية. سواء كنت بحاجة إلى وضع حساب تلقائي أو يدوي أو بدون وضع حساب، فإن Aspose.Tasks يوفر المرونة التي تناسب متطلبات مشروعك.

## الأسئلة الشائعة

### س1: هل يمكنني تغيير وضع الحساب ديناميكيًا أثناء وقت التشغيل؟

ج1: نعم، يمكنك تغيير وضع الحساب للمشروع في أي وقت أثناء وقت التشغيل عن طريق تعديل`CalculationMode` ملكية.

### س2: هل يدعم Aspose.Tasks تنسيقات ملفات إدارة المشاريع الأخرى إلى جانب Microsoft Project؟

ج2: يركز Aspose.Tasks بشكل أساسي على تنسيقات ملفات Microsoft Project، ولكنه يدعم أيضًا تنسيقات أخرى مثل Primavera P6 XML، وPrimavera DB، وAsta Powerproject XML.

### س3: هل Aspose.Tasks مناسب لكل من المشاريع الصغيرة والمشاريع على مستوى المؤسسات؟

ج3: بالتأكيد! تم تصميم Aspose.Tasks لتلبية احتياجات كل من المشاريع الصغيرة الحجم وعلى مستوى المؤسسات من خلال ميزاته الشاملة وواجهات برمجة التطبيقات القوية.

### س 4: هل يمكنني دمج Aspose.Tasks مع مكتبات وإطارات عمل .NET الأخرى؟

ج4: نعم، يمكنك دمج Aspose.Tasks بسلاسة مع مكتبات وأطر عمل .NET الأخرى لتحسين وظائف تطبيقاتك.

### س5: هل يوجد منتدى مجتمعي أو قناة دعم متاحة لمستخدمي Aspose.Tasks؟

 ج5: نعم، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع والمناقشات.