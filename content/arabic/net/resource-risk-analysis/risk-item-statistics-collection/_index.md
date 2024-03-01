---
title: قم بتجميع إحصائيات عناصر مخاطر مشروع MS في Aspose.Tasks
linktitle: مجموعة من إحصائيات عناصر الخطر في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية جمع إحصائيات عناصر المخاطرة من ملفات MS Project باستخدام Aspose.Tasks لـ .NET. تعزيز قدرات إدارة المشروع الخاص بك.
type: docs
weight: 22
url: /ar/net/resource-risk-analysis/risk-item-statistics-collection/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية جمع إحصائيات عناصر المخاطر من ملفات MS Project باستخدام Aspose.Tasks لـ .NET. توفر هذه المكتبة وظائف قوية لتحليل بيانات المشروع، بما في ذلك تقييم المخاطر والتحليل الإحصائي.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت مكتبة Aspose.Tasks. يمكنك الحصول عليه من[صفحة التحميل](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير لبرمجة .NET.

## استيراد مساحات الأسماء
قبل البدء في البرمجة، تأكد من استيراد مساحات الأسماء الضرورية في مشروعك:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## الخطوة 1: تحميل ملف المشروع
أولاً، تحتاج إلى تحميل ملف MS Project في التطبيق الخاص بك. وإليك كيف يمكنك تحقيق ذلك:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## الخطوة 2: تحديد إعدادات تحليل المخاطر
قم بتهيئة إعدادات تحليل المخاطر، بما في ذلك عدد التكرارات، كما هو موضح أدناه:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## الخطوة 3: تهيئة نمط المخاطر
قم بإعداد نمط المخاطر للتحليل، مع تحديد نوع التوزيع والنسب المئوية المتفائلة والمتشائمة ومستوى الثقة:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## الخطوة 4: إجراء تحليل المخاطر
 إنشاء مثيل`RiskAnalyzer` فئة وتحليل المشروع:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## الخطوة 5: استرجاع الإحصائيات
قم باسترجاع إحصائيات عناصر المخاطر، مثل الانتهاء المبكر، من نتيجة التحليل:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## الخطوة 6: طباعة الإحصائيات
كرر الإحصائيات واطبع التفاصيل:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //طباعة الإحصائيات الأخرى ذات الصلة...
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.Tasks لـ .NET لجمع إحصائيات عناصر المخاطر من ملفات MS Project. باتباع هذه الخطوات، يمكنك تحليل بيانات المشروع بشكل فعال وتقييم المخاطر المحتملة، مما يساعد في اتخاذ القرار وإدارة المشروع بشكل أفضل.

## الأسئلة الشائعة
### س: هل يستطيع Aspose.Tasks التعامل مع ملفات MS Project الكبيرة؟
ج: نعم، Aspose.Tasks قادر على التعامل مع ملفات MS Project الكبيرة بكفاءة، مما يوفر أداءً موثوقًا وقابلية للتوسع.
### س: هل يدعم Aspose.Tasks تنسيقات ملفات المشروع الأخرى إلى جانب .mpp؟
ج: نعم، يدعم Aspose.Tasks تنسيقات ملفات المشروع المختلفة، بما في ذلك XML وMPT.
### س: هل Aspose.Tasks مناسب لتطبيقات إدارة المشاريع على مستوى المؤسسة؟
ج: بالتأكيد، تم تصميم Aspose.Tasks لتلبية متطلبات تطبيقات إدارة المشاريع على مستوى المؤسسة، وتوفير ميزات قوية ووثائق شاملة.
### س: هل يمكنني تخصيص إعدادات تحليل المخاطر في Aspose.Tasks؟
ج: نعم، يوفر Aspose.Tasks المرونة في تكوين إعدادات تحليل المخاطر لتناسب متطلبات وسيناريوهات مشروعك المحددة.
### س: هل يتوفر الدعم الفني لمستخدمي Aspose.Tasks؟
 ج: نعم، يمكن لمستخدمي Aspose.Tasks الوصول إلى الدعم الفني من خلال Aspose[المنتديات](https://forum.aspose.com/c/tasks/15)حيث يمكنهم طرح الأسئلة والإبلاغ عن المشكلات والتفاعل مع المجتمع.