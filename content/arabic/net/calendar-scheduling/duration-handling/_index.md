---
title: التعامل مع المدة في Aspose.Tasks
linktitle: التعامل مع المدة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع الفترات بشكل فعال في Aspose.Tasks لـ .NET من خلال البرامج التعليمية خطوة بخطوة.
type: docs
weight: 30
url: /ar/net/calendar-scheduling/duration-handling/
---
## مقدمة

يعد التعامل مع الفترات بشكل فعال أمرًا بالغ الأهمية في تطبيقات إدارة المشاريع. يوفر Aspose.Tasks for .NET وظائف قوية لإدارة الفترات بكفاءة. في هذا البرنامج التعليمي، سوف نستكشف الجوانب المختلفة للتعامل مع المدة باستخدام Aspose.Tasks لـ .NET.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

1. المعرفة الأساسية بـ C#: يعد الإلمام بلغة البرمجة C# أمرًا ضروريًا لفهم الأمثلة وتنفيذها.
2. Visual Studio: قم بتثبيت Visual Studio IDE لإنشاء تطبيقات .NET وتشغيلها.
3.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية لاستخدام وظائف Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

دعنا نقسم كل مثال إلى خطوات متعددة بتنسيق دليل خطوة بخطوة:

## تحديث مدة المهام

### الخطوة 1: تحميل ملف المشروع

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### الخطوة 2: احصل على المهمة والمدة

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### الخطوة 3: مدة التحديث

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### الخطوة 4: عرض المدة المحدثة

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## طرح فترات المهام

### الخطوة 1: تحميل ملف المشروع

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### الخطوة 2: احصل على المهمة والمدة

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### الخطوة 3: طرح المدة

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### الخطوة 4: عرض المدة المحدثة

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## تحويل المدة إلى TimeSpan

### الخطوة 1: تحميل ملف المشروع

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### الخطوة 2: احصل على المهمة والمدة

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### الخطوة 3: تحويل المدة إلى TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## تحويل المدة إلى سلسلة

### الخطوة 1: تحميل ملف المشروع

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### الخطوة 2: احصل على المهمة والمدة

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### الخطوة 3: تحويل المدة إلى سلسلة

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية الجوانب المختلفة للتعامل مع المدة في Aspose.Tasks لـ .NET. يعد فهم الفترات وإدارتها بشكل فعال أمرًا حيويًا لإدارة المشاريع الناجحة. يوفر Aspose.Tasks وظائف شاملة لتبسيط مهام إدارة المدة في تطبيقات .NET الخاصة بك.

## الأسئلة الشائعة

### س1: ما هو Aspose.Tasks لـ .NET؟

A1: Aspose.Tasks for .NET هي مكتبة قوية للعمل مع ملفات Microsoft Project في تطبيقات .NET.

### س2: هل يمكن لـ Aspose.Tasks التعامل مع هياكل المشروع المعقدة؟

ج2: نعم، يمكن لـ Aspose.Tasks التعامل مع بنيات المشروع المعقدة بسهولة، مما يوفر واجهات برمجة تطبيقات واسعة النطاق للمعالجة.

### س3: هل Aspose.Tasks لـ .NET متوافق مع .NET Core؟

ج3: نعم، Aspose.Tasks for .NET متوافق مع .NET Core، مما يسمح لك باستخدامه في التطبيقات عبر الأنظمة الأساسية.

### س 4: هل يدعم Aspose.Tasks قراءة وكتابة ملفات Microsoft Project؟

ج4: نعم، يدعم Aspose.Tasks قراءة وكتابة ملفات Microsoft Project بتنسيقات مختلفة، بما في ذلك MPP وXML وMPX.

### س5: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟

 ج5: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[هنا](https://releases.aspose.com/).