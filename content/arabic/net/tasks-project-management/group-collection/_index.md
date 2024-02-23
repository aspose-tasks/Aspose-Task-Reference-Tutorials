---
title: إدارة مجموعات المشروع في Aspose.Tasks
linktitle: إدارة مجموعة المجموعة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة مجموعات MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET. اتبع دليلنا خطوة بخطوة.
type: docs
weight: 26
url: /ar/net/tasks-project-management/group-collection/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إدارة مجموعات MS Project الجماعية باستخدام Aspose.Tasks لـ .NET. تعد إدارة مجموعات المجموعة أمرًا ضروريًا لتنظيم المهام والموارد ومعالجتها بكفاءة داخل مشروعك.
## المتطلبات الأساسية
قبل متابعة هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1.  Aspose.Tasks لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[رابط التحميل](https://releases.aspose.com/tasks/net/).
2. المعرفة الأساسية بـ C#: تعرف على أساسيات لغة البرمجة C# حيث يتضمن هذا البرنامج التعليمي البرمجة في C#.
3. بيئة التطوير: قم بإعداد بيئة تطوير مثل Visual Studio أو أي بيئة تطوير متكاملة أخرى تدعم تطوير .NET.

## استيراد مساحات الأسماء
أولاً، لنستورد مساحات الأسماء الضرورية للعمل مع وظائف Aspose.Tasks في كود C# الخاص بنا.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## الخطوة 1: تحميل المشروع
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
تتضمن هذه الخطوة تحميل ملف MS Project إلى كائن مشروع Aspose.Tasks، مما يسمح لنا بتنفيذ العمليات عليه.
## الخطوة 2: التكرار على مجموعات المهام
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
هنا، نقوم بالتكرار على مجموعات المهام داخل المشروع، وطباعة التفاصيل مثل الفهرس والاسم والرؤية في القائمة لكل مجموعة.
## الخطوة 3: التكرار على مجموعات الموارد
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
وبالمثل، تتكرر هذه الخطوة على مجموعات الموارد، مع عرض فهرسها وأسمائها وإمكانية رؤيتها في القائمة.
## الخطوة 4: مسح المجموعات ونسخها إلى مشروع آخر
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// مسح مجموعات المشروع الأخرى
otherProject.TaskGroups.Clear();
// نسخ المجموعات إلى مشروع آخر
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
هنا نقوم بمسح مجموعات مشروع آخر ثم نقوم بنسخ المجموعات من المشروع الأصلي إليه.
## الخطوة 5: إضافة مجموعة مهام مخصصة
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
في هذه الخطوة، نقوم بإنشاء مجموعة مهام مخصصة وإضافتها إلى المشروع الآخر إذا لم تكن موجودة بالفعل.
## الخطوة 6: إزالة كافة المجموعات
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
وأخيرا، نقوم بإزالة جميع المجموعات من المشروع الآخر.

## خاتمة
تعد إدارة مجموعات MS Project الجماعية في Aspose.Tasks لـ .NET أمرًا ضروريًا لتنظيم بيانات المشروع ومعالجتها بكفاءة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التعامل بفعالية مع مجموعات المهام والموارد ضمن مشاريعك، مما يؤدي إلى تحسين الإدارة العامة للمشروع.
## الأسئلة الشائعة
### هل يتوافق Aspose.Tasks for .NET مع كافة إصدارات MS Project؟
يدعم Aspose.Tasks for .NET إصدارات مختلفة من Microsoft Project، بما في ذلك 2003 و2007 و2010 و2013 و2016 و2019.
### هل يمكنني تخصيص خصائص المجموعة باستخدام Aspose.Tasks لـ .NET؟
نعم، يمكنك تخصيص خصائص المجموعة مثل الاسم وإمكانية الرؤية باستخدام Aspose.Tasks لـ .NET.
### هل يوفر Aspose.Tasks لـ .NET التوافق بين الأنظمة الأساسية؟
يستهدف Aspose.Tasks for .NET بشكل أساسي إطار عمل .NET، ولكن يمكن استخدامه في سيناريوهات الأنظمة الأساسية المشتركة مع .NET Core و.NET Standard.
### كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟
 يمكنك الحصول على دعم لـ Aspose.Tasks لـ .NET من خلال[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
### هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[موقع إلكتروني](https://releases.aspose.com/).