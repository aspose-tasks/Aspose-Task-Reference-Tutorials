---
title: العمل مع الواجب في Aspose.Tasks
linktitle: العمل مع الواجب في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة مهام المشروع في .NET باستخدام Aspose.Tasks. اكتشف الخطوط المختلفة لجدولة الموارد.
type: docs
weight: 13
url: /ar/net/advanced-features/working-with-assignment/
---
## مقدمة

في هذا البرنامج التعليمي، سوف نستكشف كيفية التعامل مع المهام في Aspose.Tasks لـ .NET. تعد المهام أمرًا بالغ الأهمية في إدارة المشروع حيث تقوم بتخصيص الموارد للمهام، مما يساعد في جدولة وتتبع التقدم. سنركز على إنشاء بيانات موزعة على الوقت لتخصيص الموارد باستخدام خطوط مختلفة باستخدام Aspose.Tasks.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1.  تثبيت Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[رابط التحميل](https://releases.aspose.com/tasks/net/).
2. الفهم الأساسي لـ C# و.NET Framework: من الضروري متابعة الإلمام بلغة البرمجة C# ومفاهيم إطار عمل .NET.

## استيراد مساحات الأسماء

تأكد من استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## الخطوة 1: إنشاء مشروع ومهمة

لنبدأ بإنشاء مشروع جديد وإضافة مهمة إليه. قم بتعيين تاريخ البدء والمدة وتاريخ الانتهاء للمهمة:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## الخطوة 2: إضافة مورد وتعيينه إلى المهمة

بعد ذلك، أضف موردًا إلى المشروع وقم بتعيينه للمهمة التي تم إنشاؤها مسبقًا:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## الخطوة 3: إنشاء بيانات موزعة على الوقت بملامح مختلفة

الآن، لنقم بإنشاء بيانات موزعة على الوقت بخطوط مختلفة لتعيين المورد:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## الخطوة 4: تغيير الخطوط وإنشاء البيانات

يمكننا تغيير نوع الكفاف وإنشاء بيانات موزعة على الوقت وفقًا لذلك. وهنا بعض الأمثلة:

```csharp
// تغيير الكفاف
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// توليد البيانات الموزعة على الوقت والطباعة
// كرر هذه الخطوة لأنواع الكفاف الأخرى
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع المهام في Aspose.Tasks لـ .NET. لقد استكشفنا إنشاء بيانات موزعة على الوقت لتخصيص الموارد بخطوط مختلفة. يمكن أن تكون هذه المعرفة مفيدة للغاية في سيناريوهات إدارة المشاريع.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Tasks لجدولة المهام في تطبيق .NET الخاص بي؟

ج1: نعم، يوفر Aspose.Tasks واجهات برمجة تطبيقات شاملة لجدولة المهام وإدارتها في تطبيقات .NET.

### س2: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟

 ج2: نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من[هنا](https://releases.aspose.com/).

### س3: هل توجد أية قيود على عدد المهام أو الموارد في Aspose.Tasks؟

ج3: لا يفرض Aspose.Tasks أي قيود على عدد المهام أو الموارد التي يمكنك إدارتها في مشاريعك.

### س4: هل يمكنني تخصيص الخطوط العريضة لتعيينات الموارد في Aspose.Tasks؟

ج4: نعم، كما هو موضح في هذا البرنامج التعليمي، يمكنك تعيين معالم مختلفة مثل السلحفاة والجرس والذروة وما إلى ذلك، وفقًا لمتطلبات مشروعك.

### س5: أين يمكنني العثور على دعم للاستعلامات المتعلقة بـ Aspose.Tasks؟

 ج5: يمكنك العثور على الدعم على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) حيث يشارك الخبراء وأفراد المجتمع بنشاط في المناقشات.