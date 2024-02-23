---
title: إتقان أقنعة كود WBS باستخدام Aspose.Tasks لـ .NET
linktitle: مجموعة أقنعة كود WBS في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تحسين إدارة المشروعات باستخدام Aspose.Tasks لـ .NET. تعلم كيفية إنشاء أقنعة WBS Code وإدارتها ونقلها بسهولة في هذا البرنامج التعليمي الشامل.
type: docs
weight: 15
url: /ar/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## مقدمة
في عالم إدارة المشاريع الديناميكي، يعد تنظيم المهام بكفاءة أمرًا بالغ الأهمية. يوفر Aspose.Tasks for .NET حلاً قويًا لإدارة رموز هيكلية عمل المشروع (WBS) دون عناء. في هذا البرنامج التعليمي، سوف نتعمق في مجموعة أقنعة كود WBS، ونستكشف كيفية تنفيذها ومعالجتها باستخدام Aspose.Tasks for .NET.
## المتطلبات الأساسية
قبل أن نبدأ رحلة البرمجة هذه، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية بلغة البرمجة C#.
-  تم تثبيت Aspose.Tasks لـ .NET في بيئة التطوير الخاصة بك. إذا لم يكن الأمر كذلك، قم بتنزيله[هنا](https://releases.aspose.com/tasks/net/).
- محرر أكواد برمجية مثل Visual Studio لتجربة برمجة سلسة.
## استيراد مساحات الأسماء
للبدء، فلنستورد مساحات الأسماء الضرورية:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. تهيئة المشروع وتعريف كود WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. تحديد أقنعة رمز WBS
امسح أي أقنعة تعليمات برمجية موجودة وأضف أقنعة جديدة:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. عرض معلومات أقنعة الكود
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. أضف المهام إلى المشروع
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. استرجاع معلومات المهمة
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. التعامل مع أقنعة التعليمات البرمجية
قم بإزالة قناع الكود وتأكد من إزالته:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. انسخ أقنعة التعليمات البرمجية إلى مشروع آخر
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. عرض أقنعة التعليمات البرمجية في مشروع آخر
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. أضف المهام إلى المشروع الآخر
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. عرض رموز WBS في المشروع الآخر
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## خاتمة
مع Aspose.Tasks for .NET، تصبح إدارة رموز WBS مهمة سهلة. يغطي هذا البرنامج التعليمي إنشاء أقنعة WBS Code ومعالجتها ونقلها، مما يوفر لك دليلًا شاملاً لتحسين تجربة إدارة المشروع لديك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ .NET مع لغات البرمجة الأخرى؟
ج: يدعم Aspose.Tasks بشكل أساسي لغات .NET، ولكن يمكنك استكشاف خيارات التشغيل التفاعلي مع اللغات الأخرى.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك تنزيل النسخة التجريبية.[هنا](https://releases.aspose.com/).
### س: كيف يمكنني طلب المساعدة أو الإبلاغ عن المشكلات المتعلقة بـ Aspose.Tasks لـ .NET؟
 ج: قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للدعم والمناقشات.
### س: ما هو الغرض من رموز WBS في إدارة المشاريع؟
ج: تساعد رموز WBS على تنظيم مهام المشروع وهيكلتها بشكل هرمي، مما يوفر أسلوبًا منظمًا لتخطيط المشروع.
### س: هل يمكنني تخصيص تنسيق رموز WBS في Aspose.Tasks لـ .NET؟
ج: بالتأكيد، لديك التحكم الكامل في تنسيق وبنية رموز WBS باستخدام Aspose.Tasks لـ .NET.