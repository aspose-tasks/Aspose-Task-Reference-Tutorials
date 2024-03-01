---
title: خيارات التحميل في Aspose.Tasks
linktitle: خيارات التحميل في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية الاستفادة من قوة Aspose.Tasks لـ .NET لإدارة مستندات Microsoft Project بكفاءة من خلال إرشادات خطوة بخطوة.
type: docs
weight: 16
url: /ar/net/advanced-concepts/loading-options/
---
## مقدمة

Aspose.Tasks for .NET هي مكتبة قوية تسمح للمطورين بمعالجة مستندات Microsoft Project برمجياً. سواء كنت بحاجة إلى إنشاء ملفات المشروع أو قراءتها أو كتابتها أو تحويلها، فإن Aspose.Tasks يوفر نطاقًا واسعًا من الوظائف لتبسيط مهامك. في هذا البرنامج التعليمي، سنتعمق في أساسيات استخدام Aspose.Tasks لـ .NET، وتقسيم العمليات الأساسية إلى خطوات بسيطة وقابلة للتنفيذ.

## المتطلبات الأساسية

قبل الغوص في Aspose.Tasks لـ .NET، تأكد من إعداد المتطلبات الأساسية التالية:

1. Visual Studio: قم بتثبيت Visual Studio أو أي بيئة تطوير متكاملة أخرى من اختيارك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[موقع إلكتروني](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لـ C#: تعرف على أساسيات لغة البرمجة C#.

الآن بعد أن قمنا بتغطية متطلباتنا الأساسية، دعنا نستكشف مساحات الأسماء الأساسية ونتعمق في الدليل خطوة بخطوة.

## استيراد مساحات الأسماء

في مشروع C# الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Tasks:

1. Aspose.Tasks: توفر مساحة الاسم هذه الفئات الأساسية والواجهات للعمل مع مستندات المشروع.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

الآن، دعونا نقسم المهام المختلفة إلى أدلة خطوة بخطوة.

## الخطوة 1: تحميل المشاريع المحمية بكلمة مرور

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // قم بتهيئة FileStream لتحميل ملف المشروع
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // إنشاء مثيل LoadOptions
        var options = new LoadOptions
        {
            Password = "password" // قم بتعيين كلمة المرور
        };

        // قم بتحميل المشروع بالخيارات المحددة
        var project = new Project(stream, options);

        // عرض اسم المشروع
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## الخطوة 2: تحميل مشاريع بريمافيرا بخيارات مخصصة

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // إنشاء مثيل LoadOptions
    var loadOptions = new LoadOptions();

    // تكوين خيارات القراءة بريمافيرا
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // قم بتعيين معرف المشروع
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // ضبط خيارات القراءة لبرنامج بريمافيرا
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // قم بتحميل مشروع بريمافيرا بالخيارات المحددة
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // عرض اسم المشروع
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // إجراء المزيد من العمليات مع المشروع المحمل
}
```

## الخطوة 3: تحديد ترميز الملف

```csharp
public void SpecifyFileEncoding()
{
    // إنشاء مثيل LoadOptions
    LoadOptions lo = new LoadOptions();

    // حدد التشفير عند فتح مشروع من ملف Primavera XER
    lo.Encoding = Encoding.GetEncoding(1251);

    // قم بتحميل المشروع بالترميز المحدد
    var project = new Project("encoding1251.xer", lo);

    // إجراء المزيد من العمليات مع المشروع المحمل
}
```

## الخطوة 4: تحميل مشاريع بريمافيرا مع معالجة الأخطاء

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // إنشاء مثيل LoadOptions
    var loadOptions = new LoadOptions();

    // تكوين خيارات القراءة بريمافيرا
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // قم بتعيين معرف المشروع
    };

    // ضبط خيارات القراءة لبرنامج بريمافيرا
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //قم بتعيين معالجة الأخطاء المخصصة
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // قم بتحميل مشروع Primavera بالخيارات المحددة ومعالجة الأخطاء
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // إجراء المزيد من العمليات مع المشروع المحمل
}

// طريقة معالجة الأخطاء المخصصة
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // تنفيذ منطق معالجة الأخطاء المخصص
}
```

باتباع هذه الخطوات، يمكنك الاستفادة بشكل فعال من خيارات التحميل في Aspose.Tasks لـ .NET لمعالجة مستندات المشروع وفقًا لمتطلباتك.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا أساسيات العمل مع خيارات التحميل في Aspose.Tasks لـ .NET. بدءًا من تحميل المشروعات المحمية بكلمة مرور وحتى تحديد معالجة مخصصة للأخطاء، فإن إتقان هذه التقنيات سيمكنك من إدارة ملفات المشروع بكفاءة داخل تطبيقات .NET الخاصة بك.

## الأسئلة الشائعة

### س 1: هل Aspose.Tasks لـ .NET متوافق مع كافة إصدارات Microsoft Project؟

ج1: نعم، يدعم Aspose.Tasks for .NET إصدارات مختلفة من Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.

### س2: هل يمكنني دمج Aspose.Tasks لـ .NET مع مكتبات الجهات الخارجية الأخرى؟

ج2: بالتأكيد، Aspose.Tasks for .NET يتكامل بسلاسة مع مكتبات .NET الأخرى، مما يوفر وظائف ومرونة محسنة.

### س3: هل يوفر Aspose.Tasks لـ .NET الوثائق وموارد الدعم؟

 ج3: نعم، يمكنك الرجوع إلى الشامل[توثيق](https://reference.aspose.com/tasks/net/) والوصول إلى الدعم من خلال[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).

### س4: هل توجد أية خيارات ترخيص متاحة لـ Aspose.Tasks لـ .NET؟

 ج4: نعم، يمكنك استكشاف خيارات الترخيص المختلفة، بما في ذلك التجارب المجانية والتراخيص المؤقتة، على[موقع Aspose.Tasks](https://purchase.aspose.com/buy).

### س5: ما مدى تكرار التحديثات والميزات الجديدة التي يتم إصدارها لـ Aspose.Tasks لـ .NET؟

ج5: يتلقى Aspose.Tasks لـ .NET تحديثات منتظمة وتحسينات في الميزات لضمان الأداء الأمثل والتوافق مع التقنيات المتطورة.