---
title: عمود عرض المهام المخصصة في Aspose.Tasks
linktitle: عمود عرض المهام المخصصة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إضافة أعمدة عرض المهام المخصصة في Aspose.Tasks لـ .NET لتعزيز قدرات إدارة المشروع.
type: docs
weight: 16
url: /ar/net/advanced-features/assignment-view-column/
---
## مقدمة

في هذا البرنامج التعليمي، سنستكشف كيفية إضافة أعمدة مخصصة لطرق عرض المهام باستخدام Aspose.Tasks لـ .NET. توفر الأعمدة المخصصة المرونة وتسمح لك بعرض معلومات إضافية ذات صلة باحتياجات إدارة مشروعك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. المعرفة الأساسية بلغة البرمجة C#.
2.  تم تثبيت Aspose.Tasks لمكتبة .NET. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
3. بيئة تطوير متكاملة (IDE) مثل Visual Studio.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية للوصول إلى الفئات والأساليب المطلوبة لإنشاء أعمدة عرض المهام المخصصة:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## الخطوة 1: تحميل المشروع

 للبدء، قم بتحميل ملف المشروع الخاص بك باستخدام ملف`Project` فصل:

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## الخطوة 2: إنشاء خيارات حفظ جدول البيانات

 بعد ذلك، قم بإنشاء مثيل لـ`Spreadsheet2003SaveOptions` والذي يسمح لنا بتخصيص أعمدة عرض المهمة:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## الخطوة 3: تحديد العمود المخصص

 الآن، قم بتعريف العمود المخصص الخاص بك عن طريق إنشاء مثيل لـ`AssignmentViewColumn`. تتطلب هذه الفئة اسم العمود وعرضه ووظيفة المفوض لتحويل بيانات المهمة إلى نص العمود:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## الخطوة 4: إضافة عمود مخصص إلى الخيارات

أضف العمود المخصص إلى مجموعة أعمدة عرض المهمة لخيارات الحفظ:

```csharp
options.AssignmentView.Columns.Add(column);
```

## الخطوة 5: التكرار من خلال المهام

قم بالتكرار خلال كل تعيين مورد في المشروع وعرض نص العمود المخصص:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## الخطوة 6: احفظ المشروع باستخدام الأعمدة المخصصة

أخيرًا، احفظ المشروع باستخدام أعمدة عرض المهمة المخصصة:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة أعمدة عرض المهام المخصصة باستخدام Aspose.Tasks لـ .NET. توفر الأعمدة المخصصة المرونة في عرض معلومات إضافية مصممة خصيصًا لمتطلبات مشروعك، مما يعزز إمكانات إدارة المشروع.

## الأسئلة الشائعة

### س1: هل يمكنني إضافة أعمدة مخصصة متعددة إلى طريقة عرض الواجب؟

 ج1: نعم، يمكنك إضافة أعمدة مخصصة متعددة عن طريق إنشاء مثيلات إضافية`AssignmentViewColumn` وإضافتهم إلى`Columns` مجموعة.

### س2: هل تتوفر محولات محددة مسبقًا لحقول التعيين الشائعة؟

ج2: نعم، يوفر Aspose.Tasks محولات محددة مسبقًا لحقول التعيين الشائعة، مما يسهل استخراج البيانات للأعمدة المخصصة.

### س3: هل يمكنني تخصيص مظهر الأعمدة المخصصة، مثل تنسيق النص أو تطبيق الأنماط؟

ج3: نعم، يمكنك تخصيص مظهر الأعمدة المخصصة عن طريق تعديل خصائص مثل العرض والخط والمحاذاة.

### س4: هل من الممكن إزالة الأعمدة الافتراضية من طريقة عرض المهام؟

 ج4: نعم، يمكنك إزالة الأعمدة الافتراضية عن طريق استبعادها من`Columns` جمع أو ضبط عرضها إلى الصفر.

### س 5: هل يدعم Aspose.Tasks تصدير المشاريع إلى تنسيقات أخرى إلى جانب جداول البيانات ذات الأعمدة المخصصة؟

ج5: نعم، يدعم Aspose.Tasks تصدير المشاريع إلى تنسيقات مختلفة مثل PDF وHTML وXML، مما يسمح بخيارات متعددة لإعداد التقارير عن المشروع.