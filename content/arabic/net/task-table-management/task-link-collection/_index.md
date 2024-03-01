---
title: التعامل مع ارتباطات المهام في Aspose.Tasks
linktitle: التعامل مع ارتباطات المهام في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: اكتشف قوة Aspose.Tasks لـ .NET في إدارة روابط مهام المشروع بكفاءة. اتبع دليلنا خطوة بخطوة لتعزيز تجربة إدارة المشروع الخاص بك.
type: docs
weight: 19
url: /ar/net/task-table-management/task-link-collection/
---
## مقدمة
مرحبًا بك في الدليل التفصيلي حول التعامل مع ارتباطات المهام في Aspose.Tasks لـ .NET! تلعب روابط المهام دورًا حاسمًا في إدارة المشاريع، مما يسمح لك بإقامة علاقات بين المهام وإنشاء التبعيات. في هذا البرنامج التعليمي، سنرشدك خلال عملية العمل مع مجموعات روابط المهام باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لمكتبة .NET: قم بتنزيل وتثبيت مكتبة Aspose.Tasks. يمكنك العثور على المكتبة[هنا](https://releases.aspose.com/tasks/net/).
2. نموذج ملف مشروع: قم بإعداد ملف مشروع نموذجي (على سبيل المثال، "SampleProject.mpp") للمتابعة مع الأمثلة.
الآن، دعونا نبدأ!
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، تأكد من استيراد مساحات الأسماء اللازمة للعمل مع Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## الخطوة 1: قم بتحميل مهام المشروع والوصول
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
// تحميل المشروع
var project = new Project(DataDir + "SampleProject.mpp");
// الوصول إلى المهام عن طريق معرف
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## الخطوة 2: إنشاء روابط المهام
ربط المهام معًا لإنشاء التبعيات:
```csharp
// ربط المهام باستخدام تبعية FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## الخطوة 3: طباعة روابط المهام
اطبع روابط المهام الخاصة بالمشروع:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//التكرار من خلال روابط المهام
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## الخطوة 4: تحرير رابط المهمة
تحرير رابط مهمة عن طريق الوصول إلى الفهرس:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## الخطوة 5: إزالة روابط المهام
قم بإزالة جميع روابط المهام من المشروع:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية التعامل مع روابط المهام في Aspose.Tasks لـ .NET. يغطي هذا الدليل الشامل تحميل المشروع وإنشاء روابط المهام وطباعة الروابط وتحرير الروابط وإزالة روابط المهام.
لا تتردد في استكشاف المزيد من الميزات والوظائف التي تقدمها Aspose.Tasks لتعزيز تجربة إدارة المشروع الخاص بك.
## الأسئلة الشائعة
### هل Aspose.Tasks متوافق مع كافة إصدارات .NET؟
نعم، تم تصميم Aspose.Tasks للعمل بسلاسة مع كافة إصدارات .NET.
### هل يمكنني إنشاء أنواع ارتباطات مهام مخصصة باستخدام Aspose.Tasks؟
حاليًا، يدعم Aspose.Tasks أنواع ارتباطات المهام القياسية، ولا تتوفر أنواع الارتباطات المخصصة.
### كيف يمكنني تطبيق القيود على المهام في Aspose.Tasks؟
 يمكنك تطبيق القيود باستخدام`ConstraintType` ملكية`Task` فئة في Aspose.Tasks.
### هل هناك أي قيود على حجم ملفات المشروع التي يمكن لـ Aspose.Tasks التعامل معها؟
يمكن لـ Aspose.Tasks التعامل مع ملفات المشاريع الكبيرة بكفاءة مع الحد الأدنى من التأثير على الأداء.
### هل يوجد منتدى مجتمعي لدعم Aspose.Tasks؟
 نعم، يمكنك العثور على الدعم والتفاعل مع المجتمع على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).