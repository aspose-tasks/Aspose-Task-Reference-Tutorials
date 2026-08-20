---
date: 2026-03-08
description: تعلم كيفية تعيين عرض الملصق وتخصيص ملصق اليوم في إدارة المشاريع باستخدام
  Aspose.Tasks لـ .NET، مما يحسن القابلية للقراءة والوضوح.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية تعيين عرض التسمية في Aspose.Tasks لـ .NET
url: /ar/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين عرض التسمية في Aspose.Tasks لـ .NET

## المقدمة

عند بناء حل لإدارة المشاريع باستخدام **Aspose.Tasks for .NET**، فإن القدرة على **كيفية تعيين التسمية** أمر أساسي لجعل الجداول الزمنية سهلة القراءة. سواء كنت تحتاج إلى دقة دقيقة دقيقة أو عرض سنوي عالي المستوى، فإن تخصيص عرض التسمية يتيح لك تقديم الخط الزمني بالضبط كما يتوقع أصحاب المصلحة. في هذا الدرس سنستعرض العملية خطوة بخطوة لتعيين عروض التسمية للدقائق والساعات والأيام والأسابيع والشهور والسنوات، وسنظهر لك أيضًا كيفية **تخصيص تسمية اليوم** للحصول على أقصى وضوح.

## إجابات سريعة
- **ماذا يعني “كيفية تعيين التسمية”؟** يشير إلى تكوين خصائص `DisplayOptions` التي تتحكم في كيفية ظهور وحدات الوقت في ملف المشروع.  
- **أي تسمية يمكنني تغييرها؟** الدقائق والساعات والأيام والأسابيع والشهور والسنوات كلها قابلة للتكوين.  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام في الإنتاج؛ النسخة التجريبية المجانية تعمل للاختبار.  
- **هل هذا مدعوم على .NET Core؟** نعم، الـ API يعمل مع .NET Core، .NET 5/6، وإطار .NET الكامل.  
- **هل يمكنني تغيير التسمية أثناء التشغيل؟** بالتأكيد – يمكنك تعديل خيارات العرض في أي وقت قبل حفظ المشروع.

## ما هو عرض التسمية في Aspose.Tasks؟

يحدد عرض التسمية التمثيل النصي لوحدات الوقت (دقيقة، ساعة، يوم، إلخ) على مخطط جانت ومقياس الوقت. من خلال ضبط خاصية `DisplayOptions` المناسبة، توجه Aspose.Tasks كيفية عرض تلك الوحدات، مما يمكن أن يحسن بشكل كبير من قابلية قراءة المشروع.

## لماذا تخصيص عروض التسمية؟

- **تحسين قابلية القراءة:** يمكن لأصحاب المصلحة فهم تفاصيل الجدول الزمني فورًا.  
- **تقارير متسقة:** يطابق المخرجات البصرية مع المعايير المؤسسية (مثلاً، استخدام “Mo” للشهور).  
- **المرونة:** التبديل بين العروض التفصيلية والعامة دون تعديل بيانات الجدول الأساسية.

## المتطلبات المسبقة

1. **معرفة C#** – إلمام أساسي بصياغة C# وبنية مشروع .NET.  
2. **Aspose.Tasks for .NET** – قم بتنزيل وتثبيت المكتبة من [here](https://releases.aspose.com/tasks/net/).  
3. **بيئة التطوير** – Visual Studio أو VS Code أو أي بيئة تطوير تدعم .NET.

## استيراد مساحات الأسماء

قبل البدء، استورد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## كيفية تعيين عرض التسمية للدقائق

### 1. عرض تسميات الدقائق

لتعيين تسمية الدقيقة، استخدم خاصية `MinuteLabel`:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## كيفية تعيين عرض التسمية للساعات

### 2. عرض تسميات الساعات

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## تخصيص عرض تسمية اليوم

### 3. عرض تسميات اليوم

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## كيفية تعيين عرض التسمية للأسابيع

### 4. عرض تسميات الأسابيع

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## كيفية تعيين عرض التسمية للشهور

### 5. عرض تسميات الشهور

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## كيفية تعيين عرض التسمية للسنوات

### 6. عرض تسميات السنوات

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## الأخطاء الشائعة والنصائح

- **نصيحة:** احرص دائمًا على تعيين عرض التسمية *قبل* حفظ المشروع؛ التغييرات التي تُجرى بعد الحفظ لن تظهر في الملف.  
- **مشكلة:** استخدام قيمة enum غير مدعومة سيتسبب في رمي `ArgumentException`. التزم بالقيم `*LabelDisplay` المتوفرة.  
- **نصيحة:** إذا كنت بحاجة إلى أنماط تسمية مختلفة لعرضات منفصلة، أنشئ مثيلات `Project` منفصلة أو استنسخ كائن `DisplayOptions`.

## الخلاصة

من خلال إتقان **كيفية تعيين التسمية** في Aspose.Tasks، تحصل على تحكم دقيق في العرض البصري لجداول مواعيد مشاريعك. سواء كنت تخصص تسمية اليوم للوحة Scrum اليومية أو تعدل تسمية السنة لخريطة طريق متعددة السنوات، تساعدك هذه الإعدادات على تقديم وثائق مشروع أوضح وأكثر احترافية.

## الأسئلة الشائعة

### س1: هل يمكنني تخصيص عروض التسمية لأقسام محددة من المشروع؟

ج1: نعم، يتيح Aspose.Tasks for .NET تحكمًا دقيقًا في عروض التسمية، مما يمكن من تخصيصها لأقسام معينة من المشروع حسب الحاجة.

### س2: هل Aspose.Tasks متوافق مع أطر .NET الشائعة؟

ج2: نعم، Aspose.Tasks for .NET متوافق مع أطر .NET المختلفة، بما في ذلك .NET Core و .NET Framework.

### س3: هل يمكنني تغيير عروض التسمية ديناميكيًا بناءً على متطلبات المشروع؟

ج3: بالتأكيد، تسمح مرونة Aspose.Tasks for .NET بإجراء تعديلات ديناميكية على عروض التسمية بناءً على متطلبات المشروع المتغيرة.

### س4: هل هناك أي قيود على تخصيص عروض التسمية؟

ج4: يوفر Aspose.Tasks for .NET خيارات تخصيص واسعة لعروض التسمية، مع قيود قليلة جدًا، مما يمنح المستخدمين مرونة كبيرة.

### س5: هل يدعم Aspose.Tasks التكامل مع أدوات إدارة المشاريع الأخرى؟

ج5: نعم، يقدم Aspose.Tasks إمكانات تكامل سلسة، مما يسهل التفاعل مع أدوات ومنصات إدارة المشاريع الأخرى.

---

**آخر تحديث:** 2026-03-08  
**تم الاختبار مع:** Aspose.Tasks 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}