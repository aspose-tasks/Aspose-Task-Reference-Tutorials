---
title: إدارة مجموعة موارد المشروع في Aspose.Tasks
linktitle: إدارة مجموعة الموارد في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة مجموعات موارد Microsoft Project بكفاءة في .NET باستخدام Aspose.Tasks API. زيادة الإنتاجية والمرونة.
type: docs
weight: 13
url: /ar/net/resource-risk-analysis/managing-resource-collection/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية إدارة مجموعات موارد Microsoft Project بشكل فعال باستخدام Aspose.Tasks لـ .NET. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات قوية تمكن المطورين من العمل مع ملفات Microsoft Project برمجيًا، مما يسمح بالتكامل السلس ومعالجة بيانات المشروع.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. المعرفة بـ C# و.NET Framework: يفترض هذا البرنامج التعليمي الإلمام بلغة البرمجة C# و.NET Framework.
2. تثبيت Aspose.Tasks لـ .NET: تأكد من تثبيت Aspose.Tasks لـ .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
3. إعداد بيئة التطوير: قم بإعداد بيئة التطوير الخاصة بك باستخدام Visual Studio أو أي بيئة تطوير متكاملة مفضلة أخرى.

## استيراد مساحات الأسماء
قبل أن نبدأ، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## الخطوة 1: تحميل ملف المشروع
أولاً، قم بتحميل ملف Microsoft Project إلى كائن مشروع Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## الخطوة 2: إضافة مورد فارغ
بعد ذلك، دعونا نضيف موردًا فارغًا إلى المشروع:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## الخطوة 3: إضافة مورد بالاسم
الآن، أضف موردًا باسم محدد إلى المشروع:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## الخطوة 4: إضافة المورد قبل مورد آخر
أضف موردًا باسم محدد قبل مورد آخر بناءً على معرفه:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## الخطوة 5: الوصول إلى الموارد عن طريق المعرف أو UID
يمكنك الوصول إلى الموارد إما عن طريق معرفهم أو UID:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## الخطوة 6: طباعة معلومات الموارد
طباعة معلومات حول موارد المشروع:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## الخطوة 7: حذف الموارد
حذف الموارد من المشروع:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## خاتمة
توفر إدارة مجموعات موارد Microsoft Project باستخدام Aspose.Tasks لـ .NET للمطورين مجموعة قوية من الأدوات للتعامل بكفاءة مع موارد المشروع برمجيًا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التعامل بسهولة مع الموارد داخل مشاريعك، مما يعزز الإنتاجية والمرونة في مهام إدارة المشروع.
## الأسئلة الشائعة
### س: هل يستطيع Aspose.Tasks التعامل مع ملفات المشاريع واسعة النطاق؟

ج: نعم، تم تصميم Aspose.Tasks للتعامل مع ملفات المشاريع واسعة النطاق بكفاءة، مما يوفر أداءً عاليًا وموثوقية.

### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من Microsoft Project؟

ج: يدعم Aspose.Tasks إصدارات مختلفة من Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.

### س: هل يمكنني تخصيص خصائص الموارد باستخدام Aspose.Tasks؟

ج: بالتأكيد، يوفر Aspose.Tasks إمكانات واسعة النطاق لتخصيص خصائص الموارد وفقًا لمتطلبات المشروع المحددة.

### س: هل يدعم Aspose.Tasks مؤشرات الترابط المتعددة للعمليات المتزامنة؟

ج: نعم، يدعم Aspose.Tasks تعدد العمليات، مما يسمح بإجراء عمليات متزامنة على بيانات المشروع لتحسين الأداء.

### س: هل يتوفر الدعم الفني لمستخدمي Aspose.Tasks؟

 ج: نعم، يمكن لمستخدمي Aspose.Tasks الوصول إلى الدعم الفني من خلال المنتدى[هنا](https://forum.aspose.com/c/tasks/15).