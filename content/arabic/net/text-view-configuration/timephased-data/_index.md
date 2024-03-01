---
title: إتقان التعامل مع البيانات الموزعة على الوقت باستخدام Aspose.Tasks لـ .NET
linktitle: التعامل مع البيانات الموزعة على الوقت في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: استكشف Aspose.Tasks لـ .NET للتعامل بسهولة مع البيانات الموزعة على الوقت، وتحسين تخطيط المشروع، وتحسين إدارة الموارد. #تخصيص #المهام #مشروع MS
type: docs
weight: 14
url: /ar/net/text-view-configuration/timephased-data/
---
## مقدمة
في عالم إدارة المشاريع، يعد التعامل الفعال مع البيانات الموزعة على الوقت أمرًا بالغ الأهمية لتخصيص الموارد وتقدير التكلفة والتخطيط الشامل للمشروع. يوفر Aspose.Tasks for .NET حلاً قويًا للعمل مع البيانات المخصصة الموزعة على الوقت بسلاسة. سيرشدك هذا البرنامج التعليمي خلال عملية التعامل مع البيانات الموزعة على الوقت باستخدام Aspose.Tasks، مما يسمح لك بتحسين إدارة الموارد في مشاريعك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي لمفاهيم إدارة المشاريع.
-  تم تثبيت Aspose.Tasks لـ .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
- محرر التعليمات البرمجية، مثل Visual Studio، لتنفيذ الأمثلة المقدمة.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.Tasks. أضف الأسطر التالية في بداية ملف التعليمات البرمجية الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    
```
الآن، دعنا نقسم المثال المقدم إلى خطوات متعددة لإرشادك خلال التعامل مع البيانات الموزعة على الوقت باستخدام Aspose.Tasks:
## الخطوة 1: إعداد المشروع
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
هنا، نقوم بتهيئة مشروع جديد وضبط وضع الحساب الخاص به.
## الخطوة 2: تحديد الموارد والمهام
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
قم بإنشاء موارد العمل والتكلفة، بالإضافة إلى مهمة، لمحاكاة هيكل المشروع.
## الخطوة 3: تعيين الموارد للمهمة
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
تعيين موارد العمل والتكلفة للمهمة.
## الخطوة 4: إضافة بيانات مخصصة موزعة على الوقت
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// خطوات مماثلة لcostAssignment
costAssignment.TimephasedData.Clear();
```
أضف بيانات مخصصة موزعة على الوقت لتعيينات العمل والتكلفة.
## الخطوة 5: عرض البيانات الموزعة على الوقت
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // عرض المعلومات ذات الصلة حول كل إدخال بيانات موزعة على الوقت
    }
}
```
وأخيرًا، قم بعرض البيانات الموزعة على الوقت لكل مهمة.
#
## خاتمة
يفتح التعامل الفعال مع البيانات الموزعة على الوقت في Aspose.Tasks إمكانيات جديدة للتخطيط التفصيلي للمشروع وإدارة الموارد. باتباع هذا الدليل التفصيلي، تعلمت كيفية التعامل مع البيانات الموزعة على الوقت لتلبية الاحتياجات المحددة لمشاريعك.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Tasks لـ .NET مع أدوات إدارة المشاريع الأخرى؟
تم تصميم Aspose.Tasks بشكل أساسي لتطوير .NET. ومع ذلك، يمكن أن تكون وظائفه مكملة لمختلف أدوات إدارة المشاريع.
### هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟
 نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟
 قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع.
### ما هو الترخيص المؤقت وكيف يمكنني الحصول عليه؟
 تعرف على التراخيص المؤقتة[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Tasks لـ .NET؟
 الرجوع إلى الشامل[توثيق](https://reference.aspose.com/tasks/net/) للحصول على معلومات مفصلة.