---
title: استخدام خوارزمية الشجرة في Aspose.Tasks
linktitle: استخدام خوارزمية الشجرة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل بشكل فعال مع التسلسلات الهرمية للمهام في مشاريع .NET الخاصة بك باستخدام خوارزمية شجرة Aspose.Tasks.
type: docs
weight: 13
url: /ar/net/advanced-concepts/tree-algorithm/
---
## مقدمة

يوفر Aspose.Tasks for .NET وظائف قوية للعمل مع مهام إدارة المشروع والموارد والجداول الزمنية. إحدى هذه الميزات هي خوارزمية الشجرة، والتي تتيح للمستخدمين التعامل مع التسلسل الهرمي للمهام بكفاءة. في هذا البرنامج التعليمي، سنستكشف كيفية استخدام خوارزمية الشجرة في Aspose.Tasks لـ .NET لجمع العمل المشترك وتحديث قيم العمل داخل المشروع.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: تأكد من تثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[هنا](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# مطلوب للمتابعة مع الأمثلة.

## استيراد مساحات الأسماء

في مشروع C# الخاص بك، قم باستيراد مساحات الأسماء الضرورية للعمل مع وظائف Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

الآن، دعونا نقسم كل مثال إلى خطوات متعددة:

## الخطوة 1: تحميل ملف المشروع

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 قم بتحميل ملف المشروع إلى الذاكرة باستخدام ملف`Project` فصل.

## الخطوة 2: تحديد التسلسل الهرمي للمهام

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

حدد التسلسل الهرمي للمهام عن طريق إضافة المهام الأصلية والفرعية.

## الخطوة 3: تعيين خصائص المهمة

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

قم بتعيين خصائص مثل تاريخ البدء والمدة وتاريخ الانتهاء للمهام.

## الخطوة 4: إضافة الموارد

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

أضف الموارد إلى المشروع وقم بتعيينها للمهام حسب الحاجة.

## الخطوة 5: تطبيق خوارزمية الشجرة

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 تهيئة`WorkAccumulator` الفصل وتطبيق خوارزمية الشجرة لجمع العمل المشترك.

## الخطوة 6: تحديث عمل المهمة

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

تحديث قيم العمل للمهام بناءً على المعلومات المجمعة.

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام خوارزمية الشجرة في Aspose.Tasks لـ .NET لمعالجة التسلسلات الهرمية للمهام بشكل فعال. باتباع الدليل الموضح خطوة بخطوة، يمكنك إدارة المهام والموارد داخل مشاريعك بكفاءة.

## الأسئلة الشائعة

### س1: ما هو Aspose.Tasks لـ .NET؟

ج1: يعد Aspose.Tasks for .NET واجهة برمجة تطبيقات قوية تسمح للمطورين بمعالجة ملفات Microsoft Project برمجيًا باستخدام لغة C#.

### س2: هل يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟

 ج2: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[هنا](https://releases.aspose.com/).

### س3: أين يمكنني العثور على وثائق Aspose.Tasks لـ .NET؟

 ج3: يمكنك العثور على وثائق Aspose.Tasks لـ .NET[هنا](https://reference.aspose.com/tasks/net/).

### س٤: كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟

 ج4: للحصول على الدعم المتعلق بـ Aspose.Tasks لـ .NET، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).

### س5: هل هناك ترخيص مؤقت متاح لأغراض الاختبار؟

 ج5: نعم، يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من[هنا](https://purchase.aspose.com/temporary-license/).