---
title: تجميع مهام مشروع MS بكفاءة باستخدام Aspose.Tasks
linktitle: تجميع المهام في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تجميع مهام Microsoft Project بشكل فعال باستخدام Aspose.Tasks لـ .NET.
type: docs
weight: 25
url: /ar/net/tasks-project-management/grouping-tasks/
---
## مقدمة
قد تكون إدارة المهام في Microsoft Project صعبة في بعض الأحيان، خاصة عندما يتعلق الأمر بتنظيمها بكفاءة. يقدم Aspose.Tasks for .NET حلاً شاملاً لذلك من خلال توفير وظائف لتجميع المهام بشكل فعال. في هذا البرنامج التعليمي، سوف نستكشف كيفية تجميع مهام MS Project باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: تأكد من إعداد بيئة تطوير .NET.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك لاستخدام وظائف Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## الخطوة 1: تحميل ملف مشروع MS
ابدأ بتحميل ملف MS Project الخاص بك باستخدام الكود التالي:
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## الخطوة 2: الوصول إلى مجموعات المهام
بعد ذلك، دعنا نصل إلى مجموعات المهام داخل المشروع:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## الخطوة 3: استرداد معلومات المجموعة
الآن، قم باسترداد المعلومات حول مجموعة المهام:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## الخطوة 4: الوصول إلى معايير المجموعة
الوصول إلى المعايير المحددة لمجموعة المهام:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## الخطوة 5: استرداد معلومات المعيار
استرجاع معلومات مفصلة حول كل معيار:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
باتباع هذه الخطوات، يمكنك تجميع مهام MS Project بشكل فعال باستخدام Aspose.Tasks لـ .NET، مما يعزز تنظيم وإدارة بيانات مشروعك.

## خاتمة
في الختام، يوفر Aspose.Tasks for .NET إمكانات قوية لتجميع مهام MS Project، مما يسمح بتنظيم وإدارة بيانات المشروع بشكل أفضل. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك استخدام هذه الميزات بكفاءة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني تجميع المهام بناءً على معايير مخصصة؟
نعم، يمكنك تحديد معايير مخصصة لتجميع المهام وفقًا لمتطلباتك المحددة باستخدام Aspose.Tasks لـ .NET.
### هل يدعم Aspose.Tasks إصدارات مختلفة من ملفات MS Project؟
نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات MS Project، مما يضمن التوافق والتكامل السلس.
### هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[هنا](https://releases.aspose.com/).
### هل يمكنني تخصيص مظهر المهام المجمعة؟
بالتأكيد، يوفر Aspose.Tasks خيارات لتخصيص مظهر المهام المجمعة، بما في ذلك ألوان الخلايا والخطوط والأنماط.
### أين يمكنني العثور على دعم لـ Aspose.Tasks لـ .NET؟
 يمكنك العثور على الدعم والمساعدة لـ Aspose.Tasks لـ .NET في[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).