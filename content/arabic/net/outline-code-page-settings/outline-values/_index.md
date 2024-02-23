---
title: إتقان القيم التفصيلية لمشروع MS باستخدام Aspose.Tasks
linktitle: إدارة القيم التفصيلية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة القيم التفصيلية لـ MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET. تخصيص الخطوط العريضة للمشروع بكل سهولة.
type: docs
weight: 16
url: /ar/net/outline-code-page-settings/outline-values/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إدارة القيم التفصيلية لـ Microsoft Project باستخدام مكتبة Aspose.Tasks لـ .NET. باستخدام Aspose.Tasks، يمكنك بسهولة التعامل مع رموز المخطط التفصيلي وإنشاء قيم مخطط تفصيلي جديدة وتخصيص مخططات المشروع وفقًا لمتطلباتك.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1.  تثبيت Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: تأكد من إعداد بيئة تطوير، مثل Visual Studio، مع التوافق مع إطار عمل .NET.
3. الفهم الأساسي لبرمجة C#: تعرف على أساسيات لغة البرمجة C#، حيث سنستخدم لغة C# للعمل مع مكتبة Aspose.Tasks.

## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى كود C# الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## الخطوة 1: تحميل ملف المشروع
```csharp
// المسار إلى دليل المستندات.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
تقوم هذه الخطوة بتهيئة كائن مشروع جديد وتحميل ملف Microsoft Project من الدليل المحدد.
## الخطوة 2: تحديد تعريفات التعليمات البرمجية التفصيلية
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
هنا، نحدد كائنين OutlineCodeDefinition ونضيفهما إلى مجموعة OutlineCodes الخاصة بالمشروع.
## الخطوة 3: تحديد قناع المخطط التفصيلي
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
تقوم هذه الخطوة بإعداد OutlineMask لتعريف رمز المخطط التفصيلي.
## الخطوة 4: إنشاء قيم المخطط التفصيلي
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
في هذه الخطوة، نقوم بإنشاء كائنين OutlineValue وتعيين خصائصهما مثل القيمة ومعرف القيمة والنوع والوصف وحالة الانهيار.

## خاتمة
تعد إدارة القيم التفصيلية لـ MS Project باستخدام Aspose.Tasks لـ .NET أمرًا مباشرًا مع الوظائف المتوفرة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التعامل بكفاءة مع رموز المخطط التفصيلي وقيمه لتخصيص مخططات المشروع وفقًا لاحتياجاتك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks مع أطر عمل .NET أخرى؟
ج: نعم، Aspose.Tasks متوافق مع أطر عمل .NET المختلفة، مما يضمن المرونة في بيئة التطوير الخاصة بك.
### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟
 ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 ج: للحصول على الدعم والمساعدة، يمكنك زيارة منتدى Aspose.Tasks.[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks؟
 ج: نعم، يمكنك شراء ترخيص مؤقت لـ Aspose.Tasks من[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني العثور على الوثائق التفصيلية الخاصة بـ Aspose.Tasks؟
 ج: يمكنك الرجوع إلى الوثائق الشاملة المتاحة[هنا](https://reference.aspose.com/tasks/net/).