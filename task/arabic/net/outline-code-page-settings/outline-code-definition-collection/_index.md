---
title: مجموعة من تعريفات التعليمات البرمجية التفصيلية في Aspose.Tasks .NET
linktitle: مجموعة من تعريفات التعليمات البرمجية التفصيلية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع تعريفات التعليمات البرمجية التفصيلية في مستندات Microsoft Project باستخدام Aspose.Tasks لـ .NET. تصنيف بيانات المشروع الخاص بك دون عناء.
type: docs
weight: 13
url: /ar/net/outline-code-page-settings/outline-code-definition-collection/
---
## مقدمة
Aspose.Tasks هي مكتبة .NET قوية مصممة للتعامل مع مستندات Microsoft Project بسهولة وكفاءة. إحدى ميزاته الرئيسية هي القدرة على العمل مع تعريفات التعليمات البرمجية التفصيلية، مما يسمح للمستخدمين بتنظيم وتصنيف بيانات المشروع بشكل فعال. في هذا البرنامج التعليمي، سوف نستكشف كيفية العمل مع تعريفات التعليمات البرمجية التفصيلية باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.
2. Visual Studio: قم بتثبيت Visual Studio أو أي بيئة تطوير مفضلة أخرى لـ C#.
3.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).

## استيراد مساحات الأسماء
للبدء، تأكد من استيراد مساحات الأسماء الضرورية:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## الخطوة 1: قم بتحميل مستند Microsoft Project
أولاً، قم بتحميل مستند Microsoft Project لبدء العمل باستخدام تعريفات التعليمات البرمجية التفصيلية:
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## الخطوة 2: الوصول إلى تعريفات التعليمات البرمجية التفصيلية
الآن، دعنا نصل إلى تعريفات الكود التفصيلي داخل المشروع:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## الخطوة 3: إضافة تعريفات رمز المخطط التفصيلي المخصصة
يمكنك إضافة تعريفات تعليمات برمجية مخصصة للمخطط التفصيلي كما يلي:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## الخطوة 4: تعديل تعريفات التعليمات البرمجية للمخطط التفصيلي
قم بتعديل تعريفات كود المخطط التفصيلي الموجودة بسهولة:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## الخطوة 5: إزالة تعريفات التعليمات البرمجية التفصيلية
قم بإزالة تعريفات التعليمات البرمجية التفصيلية عندما لم تعد هناك حاجة إليها:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## الخطوة 6: حفظ التغييرات
وأخيرًا، احفظ التغييرات التي أجريتها على مستند المشروع:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## خاتمة
في الختام، يوفر Aspose.Tasks for .NET وظائف شاملة لإدارة تعريفات التعليمات البرمجية التفصيلية في مستندات Microsoft Project. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التعامل بكفاءة مع تعريفات التعليمات البرمجية التفصيلية لتنظيم وتصنيف بيانات مشروعك بشكل فعال.
## الأسئلة الشائعة
### س: هل يمكنني إضافة تعريفات أكواد تفصيلية متعددة لمشروع واحد؟
 ج: نعم، يمكنك إضافة تعريفات متعددة لرمز المخطط التفصيلي إلى مشروع بناءً على متطلباتك. ببساطة استخدم`Add` طريقة لكل تعريف تريد تضمينه.
### س: هل من الممكن إزالة كافة تعريفات التعليمات البرمجية التفصيلية من المشروع مرة واحدة؟
 ج: نعم، يمكنك مسح كافة تعريفات التعليمات البرمجية التفصيلية من المشروع باستخدام ملف`Clear` طريقة.
### س: ماذا يحدث إذا حاولت تعديل تعريف التعليمات البرمجية للمخطط التفصيلي للقراءة فقط؟
ج: إذا كان تعريف التعليمات البرمجية التفصيلية للقراءة فقط، فلن تتمكن من تعديله مباشرة. ستحتاج إلى التحقق من حالة القراءة فقط قبل محاولة إجراء أي تعديلات.
### س: هل هناك أي قيود على عدد تعريفات التعليمات البرمجية التفصيلية التي يمكنني إضافتها إلى المشروع؟
ج: لا يفرض Aspose.Tasks for .NET أي قيود محددة على عدد تعريفات التعليمات البرمجية التفصيلية التي يمكنك إضافتها إلى المشروع. ومع ذلك، خذ بعين الاعتبار الآثار المترتبة على الأداء عند العمل مع عدد كبير من التعريفات.
### س: هل يمكنني استخدام تعريفات التعليمات البرمجية التفصيلية لتجميع المهام بناءً على معايير مخصصة؟
ج: نعم، تسمح لك تعريفات التعليمات البرمجية التفصيلية بتصنيف المهام بناءً على معايير مخصصة، مما يوفر المرونة في تنظيم بيانات المشروع. ## كود المصدر الكامل