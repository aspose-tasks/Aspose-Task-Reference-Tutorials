---
title: قم بتكوين MS Project Legends في Aspose.Tasks
linktitle: تكوين وسيلة إيضاح الصفحة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تكوين أساطير صفحة MS Project في .NET باستخدام Aspose.Tasks لإدارة المشروعات بكفاءة. دليل خطوة بخطوة المقدمة.
type: docs
weight: 18
url: /ar/net/outline-code-page-settings/page-legend/
---
## مقدمة
في مجال تطوير .NET، تعد إدارة المهام بكفاءة أمرًا بالغ الأهمية، خاصة عند التعامل مع إدارة المشاريع. يظهر Aspose.Tasks for .NET كأداة قوية تقدم عددًا كبيرًا من الوظائف لتبسيط عمليات إدارة المهام. إحدى هذه الميزات هي القدرة على تكوين وسائل إيضاح صفحة MS Project، مما يوفر للمستخدمين رؤى قيمة حول عرض بيانات المشروع.
## المتطلبات الأساسية
قبل الخوض في تكوين وسائل إيضاح صفحات MS Project باستخدام Aspose.Tasks لـ .NET، تأكد من استيفاء المتطلبات الأساسية التالية:
1.  التثبيت: قم بتثبيت Aspose.Tasks for .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
2. المعرفة الأساسية بـ .NET: تعرف على أساسيات تطوير .NET، بما في ذلك إعداد المشاريع والعمل مع مساحات الأسماء.
3. بيئة التطوير: استخدم بيئة تطوير متكاملة (IDE) مثل Visual Studio للحصول على تجربة برمجة سلسة.
4. ملف المشروع: احصل على ملف Microsoft Project (MPP) جاهزًا للتجربة.

## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى الوظائف التي يوفرها Aspose.Tasks لـ .NET.
1. افتح مشروعك: قم بتشغيل مشروع .NET الخاص بك في بيئة التطوير المتكاملة (IDE) المفضلة لديك.
2. استيراد مساحات الأسماء: في بداية ملف التعليمات البرمجية الخاص بك، قم باستيراد مساحات الأسماء المطلوبة:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
دعنا نقسم المثال المقدم إلى تنسيق دليل خطوة بخطوة لفهم تكوين وسائل إيضاح صفحات MS Project باستخدام Aspose.Tasks لـ .NET بشكل شامل.

## الخطوة 1: حدد دليل المستندات
قم بتعيين المسار إلى دليل المستند الخاص بك حيث يوجد ملف Microsoft Project الخاص بك.

```csharp
String DataDir = "Your Document Directory";
```
## الخطوة 2: تحميل المشروع
 تهيئة مثيل جديد لـ`Project` فئة عن طريق تحميل ملف Microsoft Project الخاص بك.

```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
## الخطوة 3: قراءة معلومات وسيلة إيضاح الصفحة
قم بالوصول إلى معلومات وسيلة إيضاح الصفحة من العرض الافتراضي للمشروع.

```csharp
var legend = project.DefaultView.PageInfo.Legend;
```
## الخطوة 4: عرض معلومات وسيلة الإيضاح
قم بإخراج تفاصيل وسيلة الإيضاح مثل النص الأيسر والصورة اليسرى والنص المركزي والصورة المركزية والنص الأيمن والصورة اليمنى وحالة وسيلة الإيضاح والعرض.

```csharp
Console.WriteLine("Legend left text: {0} ", legend.LeftText);
Console.WriteLine("Legend left image: {0} ", legend.LeftImage);
Console.WriteLine("Legend center text: {0} ", legend.CenteredText);
Console.WriteLine("Legend center image: {0} ", legend.CenteredImage);
Console.WriteLine("Legend right text: {0} ", legend.RightText);
Console.WriteLine("Legend right image: {0} ", legend.RightImage);
Console.WriteLine("Legend On: {0} ", legend.LegendOn);
Console.WriteLine("Legend Width: {0} ", legend.Width);
```
## الخطوة 5: تعديل وسيلة الإيضاح
اختياريًا، قم بتعديل وسيلة الإيضاح حسب الحاجة. في هذا المثال، نقوم بتغيير النص الأيسر.

```csharp
legend.LeftText = "New Left Text";
```
## الخطوة 6: حفظ التغييرات
احفظ التغييرات التي تم إجراؤها على ملف المشروع.

```csharp
project.Save(DataDir + "WorkWithPageLegend_out.mpp", SaveFileFormat.Mpp);
```

## خاتمة
في الختام، فإن إتقان تكوين وسائل إيضاح صفحات MS Project باستخدام Aspose.Tasks لـ .NET يمكن أن يعزز بشكل كبير قدرات إدارة المشروع داخل النظام البيئي .NET. ومن خلال اتباع الخطوات والمتطلبات الأساسية الموضحة، يمكن للمطورين دمج هذه الوظيفة بسلاسة في مشاريعهم، مما يضمن تصورًا وتفسيرًا أفضل لبيانات المشروع.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ .NET مع أطر عمل .NET الأخرى؟
ج: نعم، Aspose.Tasks for .NET متوافق مع أطر عمل .NET المختلفة، مما يضمن المرونة والقدرة على التكيف عبر متطلبات المشروع المختلفة.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/)مما يسمح لك باستكشاف ميزاته قبل إجراء عملية الشراء.
### س: هل هناك أي قيود عند استخدام التراخيص المؤقتة لـ Aspose.Tasks لـ .NET؟
ج: توفر التراخيص المؤقتة إمكانية الوصول الكامل إلى Aspose.Tasks لوظائف .NET ولكنها محدودة بمرور الوقت. وهي مناسبة للمشاريع قصيرة الأجل أو لأغراض التقييم.
### س: هل يمكنني تخصيص وسائل إيضاح الصفحة بما يتجاوز المثال المقدم؟
ج: بالتأكيد، يوفر Aspose.Tasks for .NET خيارات تخصيص واسعة النطاق، مما يسمح لك بتخصيص وسائل إيضاح الصفحة وفقًا لمتطلبات مشروعك المحددة.
### س: أين يمكنني العثور على منتديات الدعم أو منتديات المجتمع الخاصة بـ Aspose.Tasks لـ .NET؟
 ج: يمكنك طلب الدعم والتفاعل مع المجتمع على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)حيث يمكنك العثور على إجابات للاستفسارات والتفاعل مع زملائك من المطورين.