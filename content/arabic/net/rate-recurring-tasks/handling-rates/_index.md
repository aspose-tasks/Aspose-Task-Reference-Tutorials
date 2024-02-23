---
title: التعامل مع معدلات مشروع MS باستخدام Aspose.Tasks لـ .NET
linktitle: التعامل مع الأسعار في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: إتقان إدارة معدلات MS Project بسهولة باستخدام Aspose.Tasks لـ .NET. أتمتة المهام بكفاءة لسير عمل المشروع بشكل أكثر سلاسة.
type: docs
weight: 10
url: /ar/net/rate-recurring-tasks/handling-rates/
---
## مقدمة
مرحبًا بك في برنامجنا التعليمي حول التعامل مع معدلات MS Project باستخدام Aspose.Tasks لـ .NET! في هذا الدليل، سنرشدك خلال العملية خطوة بخطوة، مما يضمن قدرتك على إدارة الأسعار بكفاءة ضمن مستندات MS Project الخاصة بك. يوفر Aspose.Tasks for .NET ميزات قوية لمعالجة ملفات MS Project برمجيًا، مما يسمح لك بتبسيط مهام إدارة مشروعك دون عناء.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1. تثبيت Visual Studio: تأكد من تثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لـ C#: تعرف على أساسيات لغة البرمجة C#.
## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. ستوفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب المطلوبة للتعامل مع أسعار MS Project.
## الخطوة 1: استيراد مساحة الاسم Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة ونفهم كل خطوة بدقة.
## الخطوة 1: تحميل ملف المشروع
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 في هذه الخطوة، نقوم بتحميل ملف MS Project موجود باسم "Project1.mpp" باستخدام ملحق`Project` الفئة المقدمة من Aspose.Tasks.
## الخطوة 2: إضافة الموارد وتعيين العمل
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
هنا، نضيف موردًا جديدًا يسمى "المورد 1" إلى المشروع ونحدد نوعه على أنه "عمل". نحدد أيضًا مدة العمل لهذا المورد.
## الخطوة 3: تحديد السعر القياسي
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
في هذه الخطوة، قمنا بتعيين السعر القياسي للمورد إلى 20 ر.س. في الساعة.
## الخطوة 4: تحديد فترات الأسعار
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
هنا، نحدد فترات المعدل للمورد. تم تحديد السعر 1 من 1 يناير 2019 إلى 11 نوفمبر 2019، مع تحديد معدلات العمل القياسية والعمل الإضافي.
## الخطوة 5: إضافة فترة سعر أخرى
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
في هذه الخطوة النهائية، نضيف فترة أسعار أخرى تبدأ من 12 نوفمبر 2019 إلى 31 ديسمبر 2019، مع تحديد سعر قياسي مختلف وتكلفة لكل استخدام.
تهانينا! لقد نجحت في التعامل مع أسعار MS Project باستخدام Aspose.Tasks لـ .NET.
## خاتمة
يمكن أن تؤدي إدارة أسعار مشروع MS برمجيًا إلى تحسين سير عمل إدارة المشروع بشكل كبير. باستخدام Aspose.Tasks for .NET، لديك القدرة على أتمتة مهام معالجة المعدلات بكفاءة، مما يوفر الوقت والموارد.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks التعامل مع هياكل المشروع المعقدة؟
ج: نعم، يوفر Aspose.Tasks ميزات قوية للتعامل مع هياكل المشروع المعقدة بسهولة.
### س: هل Aspose.Tasks متوافق مع كافة إصدارات ملفات MS Project؟
ج: يدعم Aspose.Tasks إصدارات مختلفة من ملفات MS Project، مما يضمن التوافق عبر الأنظمة الأساسية المختلفة.
### س: هل يمكنني تعديل المعدلات الموجودة في ملف MS Project باستخدام Aspose.Tasks؟
ج: بالتأكيد! يتيح لك Aspose.Tasks تعديل الأسعار الحالية وإضافة أسعار جديدة وإدارتها ديناميكيًا.
### س: هل يقدم Aspose.Tasks الدعم لحسابات الأسعار المخصصة؟
ج: نعم، يمكنك تنفيذ حسابات الأسعار المخصصة باستخدام Aspose.Tasks لتلبية متطلبات المشروع المحددة.
### س: هل هناك منتدى مجتمعي أو دعم متاح لمستخدمي Aspose.Tasks؟
 ج: نعم، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)لطلب المساعدة والتفاعل مع المستخدمين الآخرين.