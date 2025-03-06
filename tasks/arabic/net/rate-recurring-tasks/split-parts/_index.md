---
title: التعامل مع أجزاء مشروع MS المقسمة في Aspose.Tasks
linktitle: التعامل مع الأجزاء المنقسمة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع أجزاء MS Project المقسمة بكفاءة باستخدام Aspose.Tasks لـ .NET. تعزيز سير عمل إدارة المشروع الخاص بك.
type: docs
weight: 18
url: /ar/net/rate-recurring-tasks/split-parts/
---

## مقدمة
يمكن أن تكون إدارة أجزاء MS Project المقسمة جانبًا مهمًا لإدارة المشروع عند استخدام Aspose.Tasks لـ .NET. في هذا البرنامج التعليمي، سوف نستكشف كيفية التعامل مع الأجزاء المنقسمة بشكل فعال باستخدام إرشادات خطوة بخطوة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1.  تثبيت Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[موقع إلكتروني](https://releases.aspose.com/tasks/net/).
   
2. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء
في كود C# الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## الخطوة 1: إنشاء مثيل المشروع
```csharp
var project = new Project();
```
 إنشاء مثيل جديد لـ`Project` فصل.
## الخطوة الثانية: تحديد تاريخ بدء المشروع وانتهائه
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
تحديد تاريخ البدء والانتهاء للمشروع.
## الخطوة 3: إضافة مهمة
```csharp
var task = project.RootTask.Children.Add("Task1");
```
إضافة مهمة جديدة إلى المشروع.
## الخطوة 4: تحديد خصائص المهمة
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
قم بتعيين خصائص مثل الحالة اليدوية وتاريخ البدء والمدة للمهمة.
## الخطوة 5: إضافة تعيينات الموارد
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
إضافة تعيينات الموارد إلى المهمة.
## الخطوة 6: تحديد خصائص المهمة
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
قم بتعيين خصائص مثل تاريخ البدء والعمل وتاريخ الانتهاء للمهمة.
## الخطوة 7: إنشاء البيانات الموزعة على الوقت
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
قم بإنشاء بيانات موزعة على الوقت للمهمة بناءً على تقويم المشروع.
## الخطوة 8: تقسيم المهمة
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
تقسيم المهمة إلى أجزاء متعددة ضمن الإطار الزمني المحدد.
## الخطوة 9: التكرار على الأجزاء المقسمة
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
قم بالتكرار على الأجزاء المقسمة من المهمة واطبع تاريخي البدء والانتهاء الخاصين بها.

## خاتمة
يعد التعامل بفعالية مع أجزاء MS Project المقسمة في Aspose.Tasks لـ .NET أمرًا بالغ الأهمية لكفاءة إدارة المشروع. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك إدارة المهام المقسمة بسلاسة وتحسين سير عمل إدارة المشروع.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ .NET مع أطر عمل .NET الأخرى؟
ج: نعم، Aspose.Tasks for .NET متوافق مع أطر عمل .NET المختلفة بما في ذلك .NET Core و.NET Standard.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: هل يدعم Aspose.Tasks لـ .NET إدارة الموارد؟
ج: نعم، Aspose.Tasks for .NET يسمح لك بإدارة موارد المشروع بكفاءة.
### س: هل يمكنني تخصيص تقويمات المشروع باستخدام Aspose.Tasks لـ .NET؟
ج: بالتأكيد، يمكنك تخصيص تقويمات المشروع وفقًا لمتطلبات مشروعك.
### س: أين يمكنني العثور على الدعم لـ Aspose.Tasks لـ .NET؟
 ج: يمكنك العثور على الدعم والمساعدة على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).