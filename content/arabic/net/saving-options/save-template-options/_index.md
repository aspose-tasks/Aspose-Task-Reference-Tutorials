---
title: احفظ ملفات مشروع MS كقوالب باستخدام Aspose.Tasks
linktitle: حفظ خيارات القالب لـ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية حفظ ملفات Microsoft Project كقوالب باستخدام Aspose.Tasks لـ .NET. قم بتخصيص إعدادات القالب لإدارة مبسطة للمشروع.
type: docs
weight: 18
url: /ar/net/saving-options/save-template-options/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعرف على عملية حفظ القالب باستخدام Aspose.Tasks لـ .NET. تعتبر القوالب مفيدة لتوحيد هياكل المشروع وإعداداته للاستخدام المستقبلي. سنوضح كيفية حفظ المشروع كقالب، وضبط خصائصه على طول الطريق.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لمكتبة .NET: تأكد من تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
2. المعرفة ببرمجة C#: المعرفة الأساسية ببرمجة C# مطلوبة لفهم مقتطفات التعليمات البرمجية المقدمة وتنفيذها.
3. ملف Microsoft Project: قم بإعداد ملف Microsoft Project (تنسيق MPP) الذي تريد حفظه كقالب.

## استيراد مساحات الأسماء
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## الخطوة 1: تحميل المشروع
أولاً، نحتاج إلى تحميل ملف Microsoft Project (.mpp) الذي نريد حفظه كقالب.
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## الخطوة 2: الحصول على معلومات ملف المشروع
استرداد المعلومات حول ملف المشروع الذي تم تحميله، مثل تنسيقه.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## الخطوة 3: تكوين خيارات حفظ القالب
قم بإنشاء خيارات حفظ القالب وتكوين خصائصه وفقًا لمتطلباتك. تسمح لك هذه الخيارات بتخصيص البيانات التي يجب إزالتها من القالب.
```csharp
var options = new SaveTemplateOptions
{
	// إزالة كافة التكاليف الثابتة من قالب المشروع
	RemoveFixedCosts = true,
	// قم بإزالة كافة القيم الفعلية من قالب المشروع
	RemoveActualValues = true,
	// إزالة معدلات الموارد من قالب المشروع
	RemoveResourceRates = true,
	// إزالة كافة القيم الأساسية من قالب المشروع
	RemoveBaselineValues = true
};
```
## الخطوة 4: حفظ المشروع كقالب
احفظ المشروع كقالب بالخيارات المحددة.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## الخطوة 5: الحصول على معلومات ملف القالب
استرداد معلومات حول ملف القالب المحفوظ، مثل تنسيقه.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
تهانينا! لقد نجحت في حفظ قالب باستخدام Aspose.Tasks لـ .NET، وقمت بتخصيص خصائصه حسب الحاجة.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية حفظ ملف Microsoft Project كقالب باستخدام Aspose.Tasks لـ .NET. تعتبر القوالب ذات قيمة لتوحيد هياكل المشروع وإعداداته، وتبسيط عمليات إنشاء المشروعات المستقبلية.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص البيانات المراد إزالتها من القالب؟
ج: نعم، يمكنك تكوين خيارات حفظ القالب لإزالة بيانات محددة مثل التكاليف الثابتة والقيم الفعلية ومعدلات الموارد وقيم الأساس.
### س: هل Aspose.Tasks for .NET متوافق مع كافة إصدارات Microsoft Project؟
ج: يوفر Aspose.Tasks for .NET توافقًا شاملاً مع الإصدارات المختلفة من Microsoft Project، مما يضمن التكامل والأداء السلس.
### س: هل يمكنني تطبيق القوالب على المشاريع الحالية؟
ج: نعم، يمكنك تطبيق القوالب على المشاريع الموجودة عن طريق تحميل ملف القالب ودمجه مع مشروعك الحالي حسب الحاجة.
### س: هل يدعم Aspose.Tasks for .NET التطوير عبر الأنظمة الأساسية؟
ج: تم تصميم Aspose.Tasks for .NET بشكل أساسي لتطبيقات .NET Framework التي تعمل على أنظمة Windows الأساسية.
### س: هل يتوفر الدعم الفني لـ Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك طلب المساعدة الفنية والتوجيه من مجتمع Aspose.Tasks[المنتديات](https://forum.aspose.com/c/tasks/15)أو اتصل بفريق الدعم مباشرة.