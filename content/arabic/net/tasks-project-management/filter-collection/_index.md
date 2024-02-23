---
title: إدارة مرشحات مشروع MS بكفاءة باستخدام Aspose.Tasks
linktitle: إدارة مجموعة عوامل التصفية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة مجموعات تصفية MS Project بشكل فعال باستخدام Aspose.Tasks لـ .NET.
type: docs
weight: 17
url: /ar/net/tasks-project-management/filter-collection/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية إدارة مجموعات تصفية MS Project بشكل فعال باستخدام Aspose.Tasks لـ .NET. تعد إدارة عوامل التصفية أمرًا ضروريًا لتنظيم بيانات المشروع وتحليلها بكفاءة. يوفر Aspose.Tasks وظائف قوية للتعامل مع مرشحات المهام والموارد بسلاسة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  تثبيت Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[رابط التحميل](https://releases.aspose.com/tasks/net/).
2. الوصول إلى بيئة تطوير .NET: تأكد من إعداد بيئة تطوير .NET للعمل مع Aspose.Tasks.

## استيراد مساحات الأسماء
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## الخطوة 1: تحميل ملف المشروع
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## الخطوة 2: التكرار على مرشحات المهام
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## الخطوة 3: التكرار عبر مرشحات الموارد
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## الخطوة 4: مسح ونسخ المرشحات
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// مسح مرشحات المشروع الآخر
otherProject.TaskFilters.Clear();
// نسخ المرشحات إلى مشروع آخر
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## الخطوة 5: إضافة عامل تصفية المهام المخصصة
```csharp
// إضافة عامل تصفية المهام المخصصة
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## الخطوة 6: إزالة جميع عوامل التصفية
```csharp
// قم بإزالة جميع المرشحات
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
باتباع هذه الخطوات، يمكنك إدارة مجموعات تصفية MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET.

## خاتمة
تعد إدارة عوامل التصفية بشكل فعال في مجموعات MS Project أمرًا ضروريًا لتنظيم بيانات المشروع وتحليلها. يوفر Aspose.Tasks for .NET وظائف شاملة للتعامل مع مرشحات المهام والموارد بسلاسة، مما يمكّن المطورين من تبسيط مهام إدارة المشروعات بكفاءة.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks التعامل مع هياكل المشروع المعقدة؟
ج: يوفر Aspose.Tasks ميزات قوية للتعامل مع هياكل المشروع المختلفة، بما في ذلك الهياكل المعقدة، مما يضمن إمكانات إدارة المشروع الشاملة.
### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات MS Project؟
ج: نعم، يدعم Aspose.Tasks نطاقًا واسعًا من تنسيقات ملفات MS Project، مما يضمن التوافق عبر الإصدارات المختلفة.
### س: هل يمكنني تخصيص المرشحات وفقًا لمتطلبات المشروع المحددة؟
ج: بالتأكيد! يسمح Aspose.Tasks للمطورين بإنشاء مرشحات مخصصة مصممة خصيصًا لتلبية احتياجات المشروع الفريدة، مما يعزز المرونة والكفاءة.
### س: هل يوفر Aspose.Tasks الوثائق وموارد الدعم؟
ج: نعم، يقدم Aspose.Tasks وثائق شاملة وبرامج تعليمية ومنتدى دعم مخصص لمساعدة المطورين في كل خطوة من خطوات تنفيذ مشروعهم.
### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟
ج: نعم، يمكن للمطورين الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks لاستكشاف ميزاته قبل اتخاذ قرار الشراء.