---
title: تخصيص أعمدة مخطط جانت باستخدام Aspose.Tasks
linktitle: أعمدة مخطط جانت في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تخصيص أعمدة مخطط جانت في Aspose.Tasks لـ .NET لعرض معلومات مهمة محددة بكفاءة.
type: docs
weight: 21
url: /ar/net/tasks-project-management/gantt-chart-columns/
---
## مقدمة
تعد مخططات جانت أداة أساسية في إدارة المشاريع، حيث توفر تمثيلاً مرئيًا للمهام والجداول الزمنية والموارد. يوفر Aspose.Tasks for .NET إمكانات قوية للتعامل مع مخططات جانت، بما في ذلك تخصيص الأعمدة لعرض معلومات مهمة محددة. في هذا البرنامج التعليمي، سوف نستكشف كيفية العمل مع أعمدة مخطط جانت باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  التثبيت: تم تثبيت Aspose.Tasks for .NET على نظامك. إذا لم يكن الأمر كذلك، قم بتنزيله وتثبيته من[هنا](https://releases.aspose.com/tasks/net/).
2. بيئة تطوير .NET: معرفة عملية بـ C# وإطار عمل .NET.
3. نموذج ملف مشروع: احصل على نموذج ملف Microsoft Project (`.mpp`) مفيد للتجربة. إذا لم يكن لديك واحد، يمكنك إنشاء مشروع بسيط في MS Project وحفظه.

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية للعمل مع Aspose.Tasks لـ .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## الخطوة 1: تحميل ملف المشروع
 قم بتحميل ملف المشروع باستخدام ملف`Project` الفئة المقدمة من Aspose.Tasks:
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## الخطوة 2: تحديد أعمدة مخطط جانت
حدد الأعمدة التي تريد عرضها في مخطط جانت. يمكنك تحديد الحقول المضمنة أو إنشاء حقول مخصصة:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## الخطوة 3: التكرار على الأعمدة
قم بالتكرار على الأعمدة المحددة للوصول إلى خصائصها وعرض المعلومات:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## الخطوة 4: حفظ مخطط جانت إلى ملف CSV
احفظ مخطط جانت مع الأعمدة المحددة في ملف CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
باتباع هذه الخطوات، يمكنك العمل بشكل فعال مع أعمدة مخطط جانت في Aspose.Tasks لـ .NET، مما يسمح لك بتخصيص معلومات المهمة وعرضها حسب الحاجة.

## خاتمة
إن إتقان التعامل مع أعمدة مخطط جانت في Aspose.Tasks لـ .NET يفتح إمكانيات لا حصر لها لتخصيص مرئيات إدارة المشروع وفقًا لاحتياجاتك المحددة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التعامل مع معلومات المهمة بكفاءة وتحسين وضوح المشروع وتنظيمه.
## الأسئلة الشائعة
### س: هل يمكنني إنشاء أعمدة مخصصة في Aspose.Tasks لـ .NET؟
ج: نعم، يمكنك تحديد أعمدة مخصصة لعرض سمات مهمة محددة وفقًا لمتطلبات مشروعك.
### س: هل يتوافق Aspose.Tasks for .NET مع كافة إصدارات ملفات Microsoft Project؟
ج: يدعم Aspose.Tasks for .NET إصدارات مختلفة من ملفات Microsoft Project، مما يضمن التوافق عبر بيئات المشروع المختلفة.
### س: كيف يمكنني التعامل مع بنيات المشروع المعقدة باستخدام Aspose.Tasks لـ .NET؟
ج: يوفر Aspose.Tasks for .NET واجهات برمجة تطبيقات وميزات شاملة لإدارة هياكل المشاريع المعقدة، مما يوفر المرونة وقابلية التوسع.
### س: هل هناك أي قيود على عدد الأعمدة التي يمكنني إضافتها إلى مخطط جانت؟
ج: يوفر Aspose.Tasks for .NET خيارات تخصيص واسعة النطاق، مما يسمح لك بإضافة عدد كبير من الأعمدة إلى مخططات جانت دون قيود.
### س: أين يمكنني العثور على دعم وموارد إضافية لـ Aspose.Tasks لـ .NET؟
ج: يمكنك استكشاف الوثائق ومنتديات المجتمع وقنوات الدعم التي يوفرها Aspose.Tasks لـ .NET للوصول إلى الموارد والمساعدة الشاملة.