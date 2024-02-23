---
title: تكوين كود WBS خطوة بخطوة في Aspose.Tasks .NET
linktitle: قم بتكوين أقنعة كود WBS في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: استكشف تكوين أقنعة رمز WBS خطوة بخطوة في مشاريع .NET باستخدام Aspose.Tasks. تعزيز قدرات إدارة المشاريع دون عناء.
type: docs
weight: 14
url: /ar/net/view-wbs-code-configuration/wbs-code-masks/
---
## مقدمة
Aspose.Tasks for .NET هي مكتبة قوية تمكّن المطورين من معالجة بيانات إدارة المشروع بكفاءة في تطبيقات .NET. في هذا البرنامج التعليمي، سنستكشف عملية تكوين أقنعة التعليمات البرمجية لهيكل تنظيم العمل (WBS) باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Tasks لـ .NET Library: قم بتنزيل المكتبة وتثبيتها من[Aspose.Tasks لتوثيق .NET](https://reference.aspose.com/tasks/net/).
- بيئة التطوير: تأكد من إعداد بيئة تطوير .NET صالحة للعمل.
- دليل المستندات: اختر دليلاً على نظامك لتخزين ملفات المشروع.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم بتضمين مساحات الأسماء اللازمة للعمل مع Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## الخطوة 1: إنشاء مثيل المشروع
ابدأ بإنشاء مثيل مشروع جديد:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## الخطوة 2: تحديد تعريف رمز WBS
قم بإعداد تعريف كود WBS لمشروعك:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## الخطوة 3: إضافة أقنعة رمز WBS
حدد أقنعة كود WBS وأضفها إلى المشروع:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## الخطوة 4: إنشاء المهام
إضافة مهام إلى المشروع:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## الخطوة 5: إعادة الحساب
أعد حساب المشروع لضمان تطبيق رموز WBS بشكل صحيح:
```csharp
project.Recalculate();
```
## الخطوة 6: عرض معلومات قناع WBS
معلومات الإخراج حول أقنعة WBS إلى وحدة التحكم:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## الخطوة 7: احفظ المشروع
احفظ المشروع باستخدام رموز WBS المضافة:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
تهانينا! لقد قمت بتكوين أقنعة رمز WBS بنجاح في مشروع Aspose.Tasks الخاص بك.
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا العملية خطوة بخطوة لتكوين أقنعة كود WBS باستخدام Aspose.Tasks لـ .NET. توفر هذه المكتبة القوية للمطورين طريقة سلسة لتعزيز قدرات إدارة المشروعات ضمن تطبيقات .NET الخاصة بهم.

## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks مجانًا؟
 يقدم Aspose.Tasks نسخة تجريبية مجانية يمكنك تنزيلها[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على دعم إضافي؟
 قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)لدعم المجتمع.
### كيف يمكنني الحصول على ترخيص مؤقت؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل هناك وثائق مفصلة متاحة؟
 نعم، الوثائق الشاملة متوفرة[هنا](https://reference.aspose.com/tasks/net/).
### أين يمكنني شراء Aspose.Tasks؟
 شراء Aspose.Tasks[هنا](https://purchase.aspose.com/buy).