---
title: إتقان تعريفات السمات الموسعة لمشروع MS في Aspose.Tasks
linktitle: مجموعة تعريفات السمات الموسعة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة تعريفات السمات الموسعة في Microsoft Project باستخدام Aspose.Tasks لـ .NET. قم بتخصيص وتحسين بيانات مشروعك دون عناء.
type: docs
weight: 14
url: /ar/net/tasks-project-management/extended-attribute-definition-collection/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية العمل مع تعريفات السمات الموسعة في Microsoft Project باستخدام Aspose.Tasks لـ .NET. توفر السمات الموسعة طريقة مرنة لتخصيص بيانات المشروع وتحسينها، مما يسمح للمستخدمين بإضافة حقول إضافية تتجاوز الحقول القياسية المتوفرة افتراضيًا. باستخدام Aspose.Tasks، يمكنك إدارة هذه السمات الموسعة بسهولة لتناسب احتياجات إدارة مشروعك.
## المتطلبات الأساسية
قبل المتابعة، تأكد من تثبيت المتطلبات الأساسية التالية:
- [.الإطار الصافي](https://dotnet.microsoft.com/download)
-  Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية للوصول إلى فئات Aspose.Tasks وطرقها في مشروع .NET الخاص بك. اتبع الخطوات التالية:
## الخطوة 1: افتح مشروع .NET الخاص بك
افتح مشروع .NET الخاص بك في بيئة التطوير المتكاملة (IDE) المفضلة لديك، مثل Visual Studio.
## الخطوة 2: إضافة مساحة الاسم Aspose.Tasks
أضف السطر التالي في بداية ملف التعليمات البرمجية الخاص بك لاستيراد مساحة الاسم Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

الآن، دعونا نقسم أمثلة التعليمات البرمجية المقدمة إلى خطوات متعددة لفهم شامل:
## الخطوة 1: تحميل ملف المشروع
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## الخطوة 2: مسح تعريفات السمات الموسعة الموجودة (اختياري)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## الخطوة 3: إنشاء وإضافة تعريف موسع للسمة لمهمة ما
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## الخطوة 4: التكرار على سمات المهمة الموسعة
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## الخطوة 5: إنشاء وإضافة تعريف موسع للسمة لمورد ما
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## الخطوة 6: أدخل تعريف سمة المورد الموسعة
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## الخطوة 7: إزالة سمة موسعة حسب الفهرس
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية أساسيات العمل مع تعريفات السمات الموسعة في Microsoft Project باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك إدارة السمات الموسعة وتخصيصها بكفاءة لتناسب متطلبات إدارة مشروعك.
## الأسئلة الشائعة
### س: هل يمكنني تعديل تعريفات السمات الموسعة الموجودة؟
ج: نعم، يمكنك تعديل تعريفات السمات الموسعة الحالية أو إنشاء تعريفات جديدة وفقًا لاحتياجاتك.
### س: هل السمات الموسعة مدعومة في كافة إصدارات Microsoft Project؟
ج: نعم، يتم دعم السمات الموسعة في معظم إصدارات Microsoft Project، بما في ذلك الإصدارات الحديثة.
### س: هل يمكنني استخدام السمات الموسعة لحساب الحقول المخصصة؟
ج: بالتأكيد، يمكن استخدام السمات الموسعة لحساب الحقول المخصصة بناءً على معايير محددة تحددها.
### س: هل Aspose.Tasks متوافق مع أطر عمل .NET الأخرى؟
ج: يتوافق Aspose.Tasks مع أطر عمل .NET المختلفة، مما يضمن المرونة وسهولة التكامل.
### س: أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Tasks؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للحصول على الدعم واستكشاف الوثائق[هنا](https://reference.aspose.com/tasks/net/).