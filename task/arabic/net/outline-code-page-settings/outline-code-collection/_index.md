---
title: مجموعة مشروع MS للأكواد التفصيلية في Aspose.Tasks
linktitle: مجموعة من الرموز التفصيلية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية جمع رموز المخطط التفصيلي لـ Microsoft Project باستخدام Aspose.Tasks لـ .NET. يوفر هذا البرنامج التعليمي الشامل تعليمات خطوة بخطوة.
type: docs
weight: 11
url: /ar/net/outline-code-page-settings/outline-code-collection/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية جمع رموز المخطط التفصيلي لـ Microsoft Project باستخدام Aspose.Tasks لـ .NET. سنقوم بتقسيم العملية إلى تعليمات خطوة بخطوة لضمان الوضوح والفهم.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Visual Studio: قم بتثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[هنا](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لبرمجة C#: الإلمام بـ C# سيكون مفيدًا.

## استيراد مساحات الأسماء
أولاً، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظيفة Aspose.Tasks في مشروع C# الخاص بك.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## الخطوة 1: تحميل ملف المشروع
 ابدأ بتحميل ملف Microsoft Project باستخدام ملف`Project` فصل.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## الخطوة 2: جمع رموز المخطط التفصيلي
قم بإنشاء أداة تجميع لتجميع رموز المخطط التفصيلي من مهام المشروع.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## الخطوة 3: التكرار من خلال المهام وأكواد المخطط التفصيلي
قم بالتكرار من خلال المهام المجمعة ورموز المخطط التفصيلي، وطباعة تفاصيلها.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## الخطوة 4: إضافة تعريف رمز المخطط التفصيلي المخصص
إضافة تعريف رمز مخطط تفصيلي مخصص للمشروع.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## الخطوة 5: إنشاء وإدراج رمز المخطط التفصيلي
قم بإنشاء رمز مخطط تفصيلي وأدخله في مهمة.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## الخطوة 6: التعامل مع رموز المخطط التفصيلي
قم بمعالجة رموز المخطط التفصيلي حسب الحاجة، مثل الإدراج أو الإزالة أو المسح.
```csharp
// مثال على التلاعب
// ...
// أدخل الرمز مع 2 في الموضع الصحيح
task.OutlineCodes.Insert(2, code2);
// تحقق مما إذا تم إدخال الرمز
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية جمع رموز المخطط التفصيلي لـ Microsoft Project باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك إدارة رموز المخطط التفصيلي بشكل فعال داخل مشاريعك، مما يعزز التنظيم والوضوح.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ .NET مع لغات البرمجة الأخرى؟
ج: نعم، يستهدف Aspose.Tasks for .NET بشكل أساسي النظام الأساسي .NET، ولكنه يوفر أيضًا الدعم للغات البرمجة الأخرى من خلال Aspose.Tasks for Cloud.
### س: هل هناك أي قيود على حجم ملفات المشروع التي يمكن لـ Aspose.Tasks لـ .NET التعامل معها؟
ج: يمكن لـ Aspose.Tasks لـ .NET التعامل مع ملفات المشاريع الكبيرة بكفاءة، ولكن قد يختلف الأداء وفقًا لتعقيد الملف وحجمه.
### س: هل Aspose.Tasks for .NET متوافق مع أحدث إصدارات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks for .NET إصدارات مختلفة من Microsoft Project، بما في ذلك الإصدارات الأحدث.
### س: هل يمكنني تخصيص تنسيق الإخراج عند العمل مع Aspose.Tasks لـ .NET؟
ج: بالتأكيد، يوفر Aspose.Tasks for .NET خيارات شاملة لتخصيص تنسيق الإخراج وفقًا لمتطلباتك.
### س: أين يمكنني العثور على دعم أو موارد إضافية لـ Aspose.Tasks لـ .NET؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للحصول على أي مساعدة أو استفسارات بخصوص Aspose.Tasks لـ .NET.