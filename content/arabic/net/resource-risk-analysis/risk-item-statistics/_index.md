---
title: إحصائيات لعناصر المخاطرة في Aspose.Tasks
linktitle: إحصائيات لعناصر المخاطرة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: أطلق العنان لقوة تحليل المخاطر في ملفات MS Project باستخدام Aspose.Tasks لـ .NET. احصل على رؤى وخفف من حالات عدم اليقين وحقق نجاح المشروع دون عناء.
type: docs
weight: 21
url: /ar/net/resource-risk-analysis/risk-item-statistics/
---
## مقدمة
هل تتطلع إلى تعزيز براعتك في إدارة المشاريع باستخدام Aspose.Tasks لـ .NET؟ انغمس في عالم تحليل المخاطر من خلال برنامجنا التعليمي خطوة بخطوة حول الحصول على إحصائيات لعناصر المخاطر في ملفات MS Project. من خلال الاستفادة من القدرات القوية لـ Aspose.Tasks، يمكنك الحصول على رؤى لا تقدر بثمن حول أوجه عدم اليقين في المشروع واتخاذ قرارات مستنيرة للتخفيف من المخاطر بشكل فعال.
## المتطلبات الأساسية
قبل أن نبدأ هذه الرحلة، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لـ .NET Library: قم بتنزيل المكتبة وتثبيتها من[Aspose.Tasks لوثائق .NET](https://reference.aspose.com/tasks/net/), تزودك هذه المكتبة بأدوات قوية لمعالجة ملفات MS Project برمجياً.
2. بيئة تطوير .NET: قم بإعداد بيئة تطوير .NET الخاصة بك، بما في ذلك Visual Studio أو أي بيئة تطوير متكاملة أخرى من اختيارك، لتسهيل التكامل السلس لـ Aspose.Tasks في مشاريعك.

## استيراد مساحات الأسماء
قم بدمج مساحات الأسماء الضرورية في مشروعك لتسخير وظائف Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## الخطوة 1: تحديد دليل البيانات
```csharp
String DataDir = "Your Document Directory";
```
 تأكد من الاستبدال`"Your Document Directory"`مع المسار إلى دليل المستند الخاص بك حيث توجد ملفات MS Project الخاصة بك.
## الخطوة 2: تكوين إعدادات تحليل المخاطر
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 أضبط ال`IterationsCount` المعلمة بناءً على متطلبات مشروعك للتحكم في دقة تحليل المخاطر.
## الخطوة 3: تحميل ملف مشروع MS
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 قم بتحميل ملف MS Project المطلوب في ملف`project` كائن لمزيد من التحليل.
## الخطوة 4: تحديد المهمة وتهيئة نمط المخاطر
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
حدد مهمة تحليل المخاطر وقم بتكوين نمط المخاطر باستخدام المعلمات المناسبة مثل نوع التوزيع والمدد المتفائلة والمتشائمة ومستوى الثقة.
## الخطوة 5: تحليل مخاطر المشروع
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
ابدأ عملية تحليل المخاطر باستخدام الإعدادات المحددة وبيانات المشروع.
## الخطوة 6: استرجاع وعرض الإحصائيات
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
قم باسترجاع وعرض المقاييس الإحصائية المختلفة المتعلقة بعناصر المخاطر في ملف MS Project، بما في ذلك القيمة المتوقعة والانحراف المعياري والنسب المئوية والحد الأدنى والحد الأقصى للقيم.

## خاتمة
في الختام، فإن إتقان تحليل المخاطر في ملفات MS Project باستخدام Aspose.Tasks لـ .NET يفتح مجالًا من الإمكانيات لمديري المشاريع وأصحاب المصلحة. من خلال اتباع برنامجنا التعليمي الشامل، يمكنك التنقل عبر حالات عدم اليقين بثقة، مما يضمن نتائج ناجحة للمشروع.
## الأسئلة الشائعة
### هل يمكنني دمج Aspose.Tasks مع مكتبات .NET الأخرى للحصول على وظائف موسعة؟
قطعاً! يتكامل Aspose.Tasks بسلاسة مع مكتبات .NET المختلفة، مما يسمح لك بتضخيم قدراتها وفقًا لمتطلبات مشروعك.
### هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟
 نعم، يمكنك استكشاف ميزات Aspose.Tasks عن طريق الوصول إلى[تجربة مجانية](https://releases.aspose.com/) متاح على موقعنا.
### ما مدى تكرار إصدار التحديثات والتحسينات لـ Aspose.Tasks؟
نحن نسعى جاهدين لتحسين Aspose.Tasks بشكل مستمر من خلال إصدار التحديثات والتحسينات بشكل دوري، مما يضمن حصولك دائمًا على أحدث الميزات والتحسينات.
### هل يمكنني الحصول على الدعم الفني لـ Aspose.Tasks؟
بالتأكيد! فريق الدعم المخصص لدينا متاح بسهولة على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لمساعدتك في أي استفسارات أو تحديات قد تواجهها أثناء رحلة التنفيذ.
### هل تقدمون تراخيص مؤقتة للمشاريع قصيرة المدى؟
 نعم، إذا كنت بحاجة إلى Aspose.Tasks لمشروع قصير المدى، فيمكنك الاستفادة من خدماتنا المريحة[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) خيار لتلبية احتياجات الترخيص الخاصة بك دون أي التزامات طويلة الأجل.