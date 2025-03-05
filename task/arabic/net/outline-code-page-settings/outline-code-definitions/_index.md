---
title: تعريفات معالجة التعليمات البرمجية لمشروع MS في Aspose.Tasks
linktitle: التعامل مع تعريفات التعليمات البرمجية التفصيلية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع تعريفات التعليمات البرمجية التفصيلية لـ MS Project باستخدام Aspose.Tasks لـ .NET، مما يعمل على تمكين تطبيقات إدارة المشروعات لديك.
type: docs
weight: 12
url: /ar/net/outline-code-page-settings/outline-code-definitions/
---
## مقدمة
يعد Microsoft Project أداة قوية لإدارة المشاريع، ويوفر Aspose.Tasks for .NET دعمًا شاملاً لمعالجة ملفات المشروع برمجيًا. أحد الجوانب الأساسية لإدارة المشروع هو تنظيم المهام باستخدام رموز المخطط التفصيلي. في هذا البرنامج التعليمي، سنستكشف كيفية التعامل مع تعريفات التعليمات البرمجية للمخطط التفصيلي لـ MS Project باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نتعمق في التنفيذ، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. تثبيت Aspose.Tasks لـ .NET
 تأكد من تثبيت Aspose.Tasks لـ .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
### 2. الفهم الأساسي لـ C# و.NET Framework
تعرف على لغة البرمجة C# وإطار عمل .NET حيث يتطلب هذا البرنامج التعليمي معرفة متوسطة المستوى بـ C#.
### 3. بيئة التطوير المتكاملة (IDE)
قم بتثبيت IDE مثل Visual Studio على نظامك للتشفير وتصحيح الأخطاء.
## استيراد مساحات الأسماء
قبل أن نبدأ البرمجة، فلنستورد مساحات الأسماء الضرورية للعمل مع Aspose.Tasks لـ .NET.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة لفهم واضح.
## الخطوة 1: تحميل ملف المشروع
أولاً، نحتاج إلى تحميل ملف MS Project في تطبيقنا.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## الخطوة 2: إنشاء تعريف رمز المخطط التفصيلي
الآن، لنقم بإنشاء تعريف جديد لرمز المخطط التفصيلي.
```csharp
var outline = new OutlineCodeDefinition();
```
## الخطوة 3: تعيين رقم الحقل واسمه
قم بتعيين رقم الحقل واسم رمز المخطط التفصيلي.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## الخطوة 4: تعيين GUID والخصائص الأخرى
قم بتعيين المعرف الفريد العمومي (GUID) والخصائص الأخرى لرمز المخطط التفصيلي.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## الخطوة 5: إضافة قناع المخطط التفصيلي
إضافة قناع مخطط تفصيلي إلى رمز المخطط التفصيلي.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## الخطوة 6: تعيين خصائص أخرى
قم بتعيين خصائص إضافية لرمز المخطط التفصيلي.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## الخطوة 7: إضافة قيمة المخطط التفصيلي
وأخيرا، دعونا نضيف قيمة المخطط التفصيلي إلى رمز المخطط التفصيلي.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع تعريفات التعليمات البرمجية للمخطط التفصيلي لـ MS Project باستخدام Aspose.Tasks لـ .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك التعامل بكفاءة مع رموز المخطط التفصيلي في ملفات مشروعك برمجيًا.
## الأسئلة الشائعة
### س1: هل يمكنني استخدام Aspose.Tasks لـ .NET مع إصدارات مختلفة من ملفات MS Project؟
ج: نعم، يدعم Aspose.Tasks for .NET إصدارات مختلفة من ملفات MS Project، بما في ذلك تنسيقات MPP وXML.
### س2: هل Aspose.Tasks لـ .NET متوافق مع .NET Core؟
ج: نعم، Aspose.Tasks for .NET متوافق مع .NET Core، مما يسمح لك بتطوير التطبيقات عبر الأنظمة الأساسية.
### س3: هل يمكنني التعامل مع تعيينات الموارد باستخدام Aspose.Tasks لـ .NET؟
ج: نعم، يوفر Aspose.Tasks for .NET ميزات شاملة لمعالجة تعيينات الموارد، بما في ذلك إضافة المهام وتحديثها وإزالتها.
### س 4: هل يدعم Aspose.Tasks لـ .NET قراءة الحقول المخصصة من ملفات MS Project؟
ج: بالتأكيد، يدعم Aspose.Tasks for .NET قراءة وكتابة الحقول المخصصة، بما في ذلك رموز المخطط التفصيلي، من ملفات MS Project.
### س5: هل يوجد منتدى مجتمعي لـ Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك الانضمام إلى منتدى المجتمع الخاص بـ Aspose.Tasks لـ .NET[هنا](https://forum.aspose.com/c/tasks/15) لطرح الأسئلة ومشاركة المعرفة والتعاون مع المطورين الآخرين.