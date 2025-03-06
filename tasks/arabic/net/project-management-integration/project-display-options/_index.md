---
title: تكوين خيارات عرض MS Project في Aspose.Tasks
linktitle: تكوين خيارات عرض المشروع في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تكوين خيارات عرض MS Project برمجياً باستخدام Aspose.Tasks لـ .NET. قم بتخصيص مظهر مشروعك دون عناء.
weight: 17
url: /ar/net/project-management-integration/project-display-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكوين خيارات عرض MS Project في Aspose.Tasks

## مقدمة
يقدم Microsoft Project عددًا كبيرًا من خيارات العرض لتخصيص مظهر مشروعك. يوفر Aspose.Tasks for .NET إطارًا قويًا لمعالجة هذه الخيارات برمجيًا. في هذا البرنامج التعليمي، سنستكشف كيفية تكوين خيارات عرض MS Project باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1.  Aspose.Tasks لـ .NET: قم بتنزيل المكتبة وتثبيتها من[هنا](https://releases.aspose.com/tasks/net/).
2. ملف Microsoft Project: احصل على ملف MS Project صالح (.mpp) جاهز لتطبيق خيارات العرض.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# مطلوب.

## استيراد مساحات الأسماء
أولاً، تأكد من استيراد مساحات الأسماء الضرورية إلى كود C# الخاص بك:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## الخطوة 1: تحميل ملف المشروع
 قم بتحميل ملف MS Project باستخدام ملف`Project` الفئة المقدمة من Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## الخطوة 2: تكوين خيارات العرض
الآن، لنقم بتكوين خيارات العرض المتنوعة المتوفرة في MS Project:
### تعطيل تحذيرات جدول المهام
لتعطيل التحذيرات الخاصة بتعارضات الجدولة مع المهام المجدولة يدويًا (متوفرة لـ Project 2010 والإصدارات الأحدث):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### أضف مسافة قبل التسمية
اضبط لإضافة مسافة قبل قيمة الرقم واختصار الوقت:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### تكوين عرض التسمية لوحدات الوقت
تخصيص كيفية عرض الوحدات الزمنية المختلفة:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### إظهار مهمة ملخص المشروع
عرض معلومات موجزة حول المشروع بأكمله في صف واحد:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### تمكين اقتراحات جدول المهام
السماح بعرض اقتراحات لتعارضات الجدولة مع المهام المجدولة يدويًا:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### تسطير الارتباطات التشعبية
تعيين لتسطير الارتباطات التشعبية داخل المشروع:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## الخطوة 3: احفظ المشروع
وأخيرًا، احفظ المشروع بخيارات العرض المطبقة:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تكوين خيارات عرض MS Project باستخدام Aspose.Tasks لـ .NET. باستخدام هذه الإمكانات، يمكنك تخصيص مظهر ملفات مشروعك برمجيًا بكفاءة.
## الأسئلة الشائعة
### س: هل يمكنني تطبيق خيارات العرض هذه على مهام محددة فقط؟
ج: نعم، يمكنك تطبيق خيارات العرض بشكل انتقائي على المهام الفردية باستخدام Aspose.Tasks API.
### س: هل تؤثر خيارات العرض هذه على بيانات المشروع الأساسية؟
ج: لا، هذه الخيارات تقوم فقط بتعديل التمثيل المرئي للمشروع ولا تغير البيانات الأساسية.
### س: هل خيارات العرض هذه متوافقة مع كافة إصدارات Microsoft Project؟
ج: لا، قد تكون بعض الخيارات خاصة بإصدارات معينة من MS Project. راجع الوثائق للحصول على تفاصيل التوافق.
### س: هل يمكنني إعادة خيارات العرض إلى الإعدادات الافتراضية؟
ج: نعم، يمكنك إعادة تعيين خيارات العرض إلى قيمها الافتراضية باستخدام Aspose.Tasks API.
### س: هل هناك أي قيود على تخصيص خيارات العرض برمجياً؟
ج: على الرغم من أن Aspose.Tasks يوفر إمكانات تخصيص واسعة النطاق، فقد لا يمكن الوصول إلى بعض خيارات العرض برمجيًا بسبب القيود الموجودة في تنسيق ملف MS Project.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
