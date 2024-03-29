---
title: التكرار حسب سنة، أسبوع، يوم في Aspose.Tasks
linktitle: التكرار حسب سنة، أسبوع، يوم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: اكتشف قوة Aspose.Tasks لـ .NET في إدارة المهام المتكررة بكفاءة. دليل خطوة بخطوة لتنفيذ ميزة التكرار حسب أيام الأسبوع والسنة.
type: docs
weight: 28
url: /ar/net/advanced-features/repetition-by-year-week-day/
---
## مقدمة

في مجال إدارة المشاريع، تعتبر الكفاءة والدقة أمرًا بالغ الأهمية. يظهر Aspose.Tasks for .NET كأداة قوية تقدم مجموعة كبيرة من الميزات لتبسيط التعامل مع المشروع. ومن بين ترسانتها القدرة على إدارة المهام المتكررة بمرونة ملحوظة. إحدى هذه الميزات هي وظيفة "التكرار حسب يوم الأسبوع والسنة"، مما يسمح للمستخدمين بإعداد المهام التي تتكرر في أيام محددة من الأسبوع، خلال أشهر محددة، وعلى مدار عدة سنوات.

## المتطلبات الأساسية

قبل التعمق في تعقيدات استخدام ميزة "التكرار حسب يوم الأسبوع والسنة" في Aspose.Tasks لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:

### 1. المعرفة ببرنامج .NET Framework

تعرف على أساسيات .NET Framework، بما في ذلك مفاهيم البرمجة الموجهة للكائنات وبناء جملة C#.

### 2. تثبيت Aspose.Tasks لـ .NET

 قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[رابط التحميل](https://releases.aspose.com/tasks/net/). اتبع تعليمات التثبيت المقدمة لدمج المكتبة في بيئة التطوير الخاصة بك.

### 3. الوصول إلى التوثيق

 الرجوع إلى[توثيق](https://reference.aspose.com/tasks/net/) للحصول على إرشادات شاملة حول Aspose.Tasks for .NET، بما في ذلك التوضيحات التفصيلية للفئات والأساليب وأمثلة الاستخدام.

## 4. إعداد بيئة التطوير

تأكد من تكوين بيئة تطوير مناسبة، مثل Visual Studio أو أي بيئة تطوير متكاملة (IDE) متوافقة لتطوير .NET.

الآن بعد أن أصبحت لديك المتطلبات الأساسية، دعنا نتعمق في الدليل خطوة بخطوة حول تنفيذ "التكرار حسب يوم الأسبوع والسنة" في Aspose.Tasks لـ .NET.


## استيراد مساحات الأسماء الضرورية

للبدء، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى فئات Aspose.Tasks ووظائفها داخل تطبيق .NET الخاص بك.

في ملف التعليمات البرمجية C# الخاص بك، قم بتضمين إعلانات مساحة الاسم التالية:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

توفر مساحات الأسماء هذه إمكانية الوصول إلى مكتبة Aspose.Tasks والفئات اللازمة للعمل مع المهام وملفات المشروع.

الآن، دعنا نقسم عملية إعداد مهمة متكررة باستخدام ميزة "التكرار حسب أيام الأسبوع والسنة" في Aspose.Tasks لـ .NET إلى خطوات يمكن التحكم فيها.

## الخطوة 1: تهيئة معلمات المشروع والمهمة

أولاً، قم بتهيئة المشروع وتحديد المعلمات للمهمة المتكررة.

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

يقوم مقطع التعليمات البرمجية هذا بتهيئة مشروع جديد وتحديد المعلمات لمهمة متكررة. يقوم بتعيين اسم المهمة ومدتها وتحديد نمط التكرار.

## الخطوة 2: إضافة المعلمات إلى المشروع

بعد ذلك، أضف المعلمات المحددة إلى المشروع.

```csharp
project.RootTask.Children.Add(parameters);
```

يضيف هذا السطر معلمات المهمة إلى المهمة الجذرية للمشروع، بما في ذلك تكوين المهمة المتكررة.

## الخطوة 3: حفظ ملف المشروع

وأخيرًا، احفظ ملف المشروع بالمهمة المتكررة التي تم تكوينها.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

يحفظ هذا المقتطف ملف المشروع بتكوين المهمة المتكررة المحددة في دليل الإخراج المحدد.

## خاتمة

في الختام، فإن إتقان ميزة "التكرار حسب يوم الأسبوع والسنة" في Aspose.Tasks for .NET يمكّن مديري المشاريع والمطورين من التعامل بكفاءة مع المهام المتكررة بدقة ومرونة. باتباع الدليل التفصيلي الموضح في هذه المقالة، يمكنك دمج هذه الوظيفة بسلاسة في سير عمل إدارة المشروع لديك، مما يعزز الإنتاجية والتنظيم.

## الأسئلة الشائعة

### س1: هل يمكنني تخصيص نمط التكرار بما يتجاوز الأمثلة المتوفرة؟

ج: نعم، يوفر Aspose.Tasks for .NET خيارات تخصيص واسعة النطاق للمهام المتكررة، مما يسمح لك بتخصيص نمط التكرار وفقًا لمتطلباتك المحددة.

### س2: هل Aspose.Tasks for .NET متوافق مع برامج إدارة المشاريع الأخرى؟

ج: يدعم Aspose.Tasks for .NET إمكانية التشغيل التفاعلي مع العديد من تنسيقات إدارة المشاريع، مما يتيح التكامل السلس مع مجموعات البرامج الشائعة.

### س3: كيف يمكنني معالجة الاستثناءات أو التعديلات على المهام المتكررة؟

ج: يوفر Aspose.Tasks for .NET واجهات برمجة التطبيقات للتعامل مع الاستثناءات والتعديلات على المهام المتكررة، مما يضمن المرونة في إدارة متطلبات المشروع المتطورة.

### س 4: هل يوفر Aspose.Tasks for .NET الدعم لحلول إدارة المشاريع المستندة إلى السحابة؟

ج: نعم، يوفر Aspose.Tasks for .NET الدعم لحلول إدارة المشاريع المستندة إلى السحابة، مما يسهل التعاون وإمكانية الوصول عبر الأنظمة الأساسية المتنوعة.

### س5: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟

ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Tasks لـ .NET من[موقع إلكتروني](https://releases.aspose.com/)مما يسمح لك باستكشاف ميزاته قبل اتخاذ قرار الشراء.