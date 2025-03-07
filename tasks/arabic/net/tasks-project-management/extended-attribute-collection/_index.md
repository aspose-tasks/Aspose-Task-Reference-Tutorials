---
title: إدارة مجموعة سمات مشروع MS في Aspose.Tasks
linktitle: إدارة مجموعة السمات الموسعة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة السمات الموسعة لـ MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET. يمكنك التعامل مع سمات المهمة بسلاسة من خلال إرشادات خطوة بخطوة.
weight: 12
url: /ar/net/tasks-project-management/extended-attribute-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة مجموعة سمات مشروع MS في Aspose.Tasks

## مقدمة
هل تتطلع إلى إدارة السمات الموسعة لـ MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET؟ في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة. دعونا الغوص في!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Visual Studio: قم بتثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[هنا](https://releases.aspose.com/tasks/net/).
3. المعرفة الأساسية بـ C#: تعرف على أساسيات لغة البرمجة C#.

## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروعك:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## الخطوة 1: تحميل ملف المشروع
أولاً، قم بتحميل ملف MS Project باستخدام مقتطف التعليمات البرمجية التالي:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## الخطوة 2: الوصول إلى المهمة والسمات الموسعة
الوصول إلى مهمة محددة وسماتها الموسعة:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## الخطوة 3: مسح السمات الموسعة
امسح السمات الموسعة الموجودة إذا لزم الأمر:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## الخطوة 4: إنشاء تعريفات السمات الموسعة
إنشاء تعريفات للسمات الموسعة الجديدة:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## الخطوة 5: التكرار على السمات الموسعة للمهمة
التكرار على سمات المهمة الموسعة:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## الخطوة 6: إضافة السمات الموسعة
أضف سمات موسعة جديدة إلى المهمة:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## الخطوة 7: العمل مع السمات الموسعة
تنفيذ العمليات على السمات الموسعة كما هو مطلوب.
## الخطوة 8: إزالة السمات الموسعة
إزالة السمات الموسعة حسب الفهرس أو بشكل مشروط:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## الخطوة 9: نسخ السمات إلى مهمة أخرى
انسخ السمات إلى مهمة أخرى داخل نفس المشروع أو مشروع مختلف:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## خاتمة
أصبحت إدارة مجموعات السمات الموسعة لـ MS Project أمرًا سلسًا مع Aspose.Tasks لـ .NET. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التعامل بكفاءة مع السمات الموسعة، مما يعزز قدرات إدارة المشروع لديك.
## الأسئلة الشائعة
### س: هل يمكنني التعامل مع السمات الموسعة عبر مشاريع متعددة؟
ج: نعم، يمكنك نسخ السمات الموسعة بين المهام في مشاريع مختلفة باستخدام Aspose.Tasks لـ .NET.
### س: هل هناك قيود على عدد السمات الموسعة لكل مهمة؟
ج: لا يفرض Aspose.Tasks لـ .NET أي قيود متأصلة على عدد السمات الموسعة لكل مهمة.
### س: هل يمكنني إنشاء حقول سمات موسعة مخصصة؟
ج: بالتأكيد! يتيح لك Aspose.Tasks for .NET تحديد حقول السمات الموسعة المخصصة خصيصًا وفقًا لمتطلبات مشروعك.
### س: هل يدعم Aspose.Tasks for .NET القراءة والكتابة إلى ملفات MS Project ذات الإصدارات المختلفة؟
ج: نعم، يدعم Aspose.Tasks for .NET تنسيقات ملفات MS Project عبر إصدارات مختلفة.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
