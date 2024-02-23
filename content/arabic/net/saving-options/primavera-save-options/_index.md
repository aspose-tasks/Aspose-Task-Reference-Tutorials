---
title: احفظ خيارات MS Project Primavera باستخدام Aspose.Tasks
linktitle: خيارات حفظ بريمافيرا لـ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: اكتشف كيفية حفظ خيارات MS Project لبرنامج Primavera بسلاسة باستخدام Aspose.Tasks لـ .NET. اتبع البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 14
url: /ar/net/saving-options/primavera-save-options/
---
## مقدمة
Aspose.Tasks for .NET هي مكتبة قوية تمكن المطورين من العمل مع ملفات Microsoft Project في تطبيقات .NET الخاصة بهم بسلاسة. إحدى الوظائف الرئيسية التي يقدمها هي القدرة على حفظ خيارات MS Project لبرنامج Primavera، وهو برنامج مشهور لإدارة المشاريع. في هذا البرنامج التعليمي، سوف نتعمق في كيفية تحقيق ذلك باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- الفهم الأساسي لـ C# و.NET Framework.
-  تم تثبيت Aspose.Tasks لـ .NET في بيئة التطوير الخاصة بك. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
- نموذج لملف MS Project للتجريب.

## استيراد مساحات الأسماء
أولاً، لنستورد مساحات الأسماء الضرورية إلى كود C# الخاص بنا:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## الخطوة 1: تحميل ملف مشروع MS
ابدأ بتحميل ملف MS Project الذي تنوي العمل به في تطبيق C# الخاص بك. يمكنك القيام بذلك باستخدام`Project` الفئة المقدمة من Aspose.Tasks.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## الخطوة 2: تحديد خيارات حفظ برنامج بريمافيرا
بعد ذلك، قم بإنشاء خيارات حفظ Primavera وقم بتخصيصها وفقًا لمتطلباتك. تتضمن هذه الخطوة تحديد معلمات مثل بادئة معرف النشاط، واللاحقة، والزيادة، وما إذا كان سيتم إعادة ترقيم معرفات النشاط.
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## الخطوة 3: حفظ خيارات MS Project لبرنامج Primavera
 الآن بعد أن قمت بتحميل ملف المشروع وتحديد خيارات حفظ برنامج Primavera، فقد حان الوقت لحفظ خيارات برنامج Primavera. استخدم ال`Save` الطريقة المقدمة من`Project` فئة، وتمرير مسار ملف الإخراج المطلوب وخيارات حفظ بريمافيرا.
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## خاتمة
في الختام، فإن الاستفادة من Aspose.Tasks لـ .NET تسمح للمطورين بمعالجة ملفات MS Project بسلاسة، بما في ذلك خيارات الحفظ لبرنامج Primavera. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج هذه الوظيفة بكفاءة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص معلمات أخرى بخلاف معرفات الأنشطة عند حفظ خيارات MS Project لبرنامج Primavera؟
ج: نعم، يوفر Aspose.Tasks نطاقًا واسعًا من خيارات التخصيص، بما في ذلك تخصيص الموارد وجدولة المهام.
### س: هل يدعم Aspose.Tasks برامج إدارة المشاريع الأخرى بخلاف Primavera؟
ج: نعم، يدعم Aspose.Tasks العديد من التنسيقات المتوافقة مع أدوات إدارة المشاريع الشائعة مثل Oracle Primavera وMicrosoft Project Server والمزيد.
### س: هل Aspose.Tasks مناسب لكل من المشاريع الصغيرة وعلى مستوى المؤسسات؟
ج: بالتأكيد، تم تصميم Aspose.Tasks لتلبية احتياجات المطورين الذين يعملون في مشاريع من جميع الأحجام، مما يوفر قابلية التوسع والأداء القوي.
### س: هل يمكنني تجربة Aspose.Tasks مجانًا قبل إجراء عملية الشراء؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/) للتعرف على مميزاته وإمكانياته.
### س: أين يمكنني الحصول على الدعم إذا واجهت مشكلات أو كانت لدي أسئلة أثناء استخدام Aspose.Tasks؟
ج: يمكنك طلب المساعدة من مجتمع Aspose.Tasks وفريق الدعم على الموقع[المنتدى](https://forum.aspose.com/c/tasks/15).